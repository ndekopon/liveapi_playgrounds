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
	   Enable Live API functionality

	cl_liveapi_allow_requests (default "1")
	   Allow processing and running any incoming requests.

	cl_liveapi_pretty_print_log (default "0")
	   Makes the JSON output more human-readable

	cl_liveapi_use_protobuf (default "1")
	   Use protobuf as the serialization format. Otherwise, use JSON.

	cl_liveapi_ws_keepalive (default "30")
	   Interval of time to send Pong to any connected server

	cl_liveapi_ws_retry_count (default "5")
	   Amount of times to retry connecting before marking the connection as unavailable

	cl_liveapi_ws_retry_time (default "30")
	   Time between retries 

	cl_liveapi_ws_servers (default "")
	   Comma separated list of addresses to connect to. Must be in the form 'ws://domain.com:portNum'

	cl_liveapi_ws_timeout (default "300")
	   Websocket connection timeout in seconds

# FAQ

- How do I pass command line parameters to the game?
On Steam, navigate to your library and right click on Apex Legends. In the "General" options, add the desired command line to the "Launch options" text box.

On the EA app, go to installed games, click on Apex Legends and select "Manage". Click on "View Properties" in the dropdown. Enter your desired command line in the "Advanced launch properties" text box.

- I've been reading gameplay events from a JSON File Stream, how do I migrate to this?
While previously it was possible to read gameplay events from a JSON file on disk, this method is deprecated and may no longer work in a future release. However, the shape of the JSON events is the same and your code will still be able to read these events. An already existing app can easily be migrated to the new Live API by first enabling WebSocket support (i.e. adding a WebSocket server in your app). As more functionality comes online, you should consider switching to protobuf later for faster processing and reduced bandwidth.

- Can I connect to multiple servers?
Yes! Theoretically, any amount of servers can be specified through the json config file. Please note, however, that connecting to more than one server may affect the game's performance.

- Will you be adding more events or API request methods?
Yes! Stay tuned!

We’re always looking for feedback from you! Got any suggestions, ideas or requests of your own? Share them with us! Tag us on Twitter and feel free to show us what you do with the Live API

