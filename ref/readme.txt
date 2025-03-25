This readme contains the basic information for getting started with Apex Legend's Live API

# Overview 

The Live API is a built-in mechanism for listening to gameplay events and programmatically interacting with the game. It provides a stable interface that allows application developers to integrate with Apex Legends and drive other services based on gameplay events. This API is particularly useful for online streaming, live tournaments or even offline analysis after a match.

In order for the Live API to provide gameplay events, it must be allowed by the server your game is connecting to and can only be activated by using the additional command line argument `+cl_liveapi_enabled 1`

# Quick Start

This API is built on top of WebSockets and Google's Protocol Buffer (protobuf) technology. All gameplay events and requests supported by the Live API are documented in the `events.proto` protobuf file that lives in this directory. If you're not familiar with protobuf, visit https://developers.google.com/protocol-buffers to learn more.

Protobuf bindings can be easily generated for your language of choice after you obtain the Protobuf Compiler `protoc`. For example, to generate bindings for Python, use:

`protoc.exe --proto_path=<current directory of this readme> --python_out=<your project output directory> events.proto`

The bindings can then be included into your app code. In order to consume the events, your app will have to open a WebSocket server that the running game can connect and send events to. The game must also be running with additional command line parameters to activate the LiveAPI and connect to the app. For example, if the app has a websocket server in port 7777 of the same machine the game is running on, the following command line can be passed to the game

`+cl_liveapi_enabled 1 +cl_liveapi_ws_servers "ws://127.0.0.1:7777"`

Upon launching with these parameters, the game will connect to the WebSocket server at 127.0.0.1 in port 7777. Once the game has connected to a server (and the server allows the use of Live API), gameplay events are sent to the WebSocket server app.

# Configuration

The Live API has several options that can be specified through command line or through a separate JSON configuration file (named config.json) in the Windows User "Saved Games" folder (default location %USERPROFILE%\Saved Games). 

A simple `config.json` is located in this folder for reference. To use the JSON configuration file, simply place it in the "Saved Games" folder under Respawn\Apex\assets\temp\live_api. For example, for a user named "Nessie" whose Saved Games folder is in `C:\Users\Nessie\Saved Games`, the `config.json` file should be moved to `C:\Users\Nessie\Saved Games\Respawn\Apex\assets\temp\live_api\config.json`.

As mentioned, command line parameters can also be used to configure the Live API. These will take precedence over any configuration values in the config.json file being read. Some of the following command line parameters can be passed into the game

	cl_liveapi_enabled (default "0")
	   Enable Live API functionality.

	cl_liveapi_allow_requests (default "1")
	   Allow processing and running any incoming requests.

	cl_liveapi_pretty_print_log (default "0")
	   Makes the JSON output more human-readable.

	cl_liveapi_use_protobuf (default "1")
	   Use protobuf as the serialization format. Otherwise, use JSON.

	cl_liveapi_ws_keepalive (default "30")
	   Interval of time to send Pong to any connected server.

	cl_liveapi_ws_retry_count (default "5")
	   Amount of times to retry connecting before marking the connection as unavailable.

	cl_liveapi_ws_retry_time (default "30")
	   Time between retries.

	cl_liveapi_ws_servers (default "")
	   Comma separated list of addresses to connect to. Must be in the form 'ws://domain.com:portNum'.

	cl_liveapi_ws_timeout (default "300")
	   Websocket connection timeout in seconds.
	   
	cl_liveapi_ws_lax_ssl (default "1")
	   Skip SSL certificate validation for all WSS connections. Allows the use of self-signed certificates.
	   
	cl_liveapi_ws_event_delay (default "")
	   Delay (in seconds) to be used when broadcasting an event to all connections.
	   
	cl_liveapi_requests_psk (default "")
	    A preshared key that will be used to validate requests. When set, if a request is received with a key that does not match, it is rejected.
		
	cl_liveapi_requests_psk_tries (default "10")
		Attempts allowed when making a request with the wrong key before the connection is dropped. It will always be minimum 10 tries.
		
	cl_liveapi_session_name (default "")
		Session name that can be used in WebSocket connections to identify this client

# Sending and Receiving messages over WebSocket

The `events.proto` file describes all the messages in use by LiveAPI with additional annotations regarding their behaviour as comments over each defined message. While LiveAPI can be used primarily to listen for in-game events, websockets allows for bidirectional communication between an app and the game. 

To simplify how messages are read and received, LiveAPI exposes two types of envelope messages: `LiveAPIEvent` and `Request`. As the name implies, the `Request` message is what a websocket server application would send in order to have the game fulfill an action. The `LiveAPIEvent` is the envelope for all messages from the game to any websocket connections. 

Note that when using JSON as the primary data transfer method, a `LiveAPIEvent` message is human-readable and not wrapped in the LiveAPIEvent envelope. This is for backwards compatibility with older applications. LiveAPI requests made using JSON must still be sent over a `Request` message type. It is recommended to use Protobuf bindings to ensure serialization is done correctly, even when using JSON.

When using Protobuf and WebSockets, it is important to unpack/pack messages correctly. To read a `LiveAPIEvent` message in protobuf, it is necessary to obtain the type of the `gameMessage` and call the unpack function with an instance of that type. Before proceeding, familiarize yourself with the proto3 `Any` field type at https://protobuf.dev/programming-guides/proto3/#any and make sure to consult the documentation for the programming language in use.

To generate a protobuf `Request` message, a single action must be specified and any fields for that message should be appropriately populated. Consult the protobuf documentation on using the oneof fields https://protobuf.dev/programming-guides/proto3/#oneof. LiveAPI is able to acknowledge successful requests upon receipt. These are sent in `Response` messages and are only sent to the connection that initiated the request. Note that receiving a response does not mean the Request has completed. This is a great tool to use during development to ensure requests are well crafted.

Finally, certain requests may trigger game events upon successful completion. For example, a `Request` with a `changeCam` action will result in a `LiveAPIEvent` that has an `ObserverSwitched` gameMessage as the payload.

# Support for Secure WebSockets (wss)

Secure WebSockets support is available for Live API to avoid transferring sensitive data over plaintext. Applications intending to use WSS must be listening over port 443, as this is the only acceptable port for secure negotiation. By default, there is a lax SSL policy to allow a wide variety of certificates to be used, including those which are self-signed. This is for ease of integration but may not be suitable in production scenarios or where the network channel is not trusted (for example, over the internet or a local datacenter connection). When lax SSL policy is disabled, only certificates from the VeriSign and DigiCert CAs can be validated appropriately and secure connections will fail otherwise. It is recommended to leverage the preshared key feature (cl_liveapi_requests_psk) alongside WSS to guarantee requests are always made by trusted parties.

# FAQ

- How do I pass command line parameters to the game?
On Steam, navigate to your library and right click on Apex Legends. In the "General" options, add the desired command line to the "Launch options" text box.

On the EA app, go to installed games, click on Apex Legends and select "Manage". Click on "View Properties" in the dropdown. Enter your desired command line in the "Advanced launch properties" text box.

- I've been reading gameplay events from a JSON File Stream, how do I migrate to this?
While previously it was possible to read gameplay events from a JSON file on disk, this method is deprecated and may no longer work in a future release. However, the shape of the JSON events is the same and your code will still be able to read these events. An already existing app can easily be migrated to the new Live API by first enabling WebSocket support (i.e. adding a WebSocket server in your app). As more functionality comes online, you should consider switching to protobuf later for faster processing and reduced bandwidth.

- Can I connect to multiple servers?
Yes! Theoretically, any amount of servers can be specified through the json config file. Please note, however, that connecting to more than one server may affect the game's performance.

- Why do I sometimes get "Could not parse your request correctly!" when it is correctly formed?
If you are sending many requests within an extremely short amount of time (e.g. dozens of requests per second) the WebSocket library of either server or client may batch the requests in an attempt to efficiently process/transport them. This batching can cause issues when reconstructing the requests and has been observed when making requests in JSON format. Switch to protobuf or try reducing the frequency of requests to mitigate the problem.

- Where can I see what changes have been made in the LiveAPI
We've collected feedback that changes to the API were hard to keep track of. Starting with LiveAPI v2.3 releasing with Season 24.1, you'll be able to find an additional changelog.txt

- Will you be adding more events or API request methods?
Yes! Stay tuned!

We’re always looking for feedback from you! Got any suggestions, ideas or requests of your own? Share them with us! Tag us on social media and feel free to show us what you do with the Live API!

