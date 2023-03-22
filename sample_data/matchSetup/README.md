# matchSetup

マッチ開始

## 定義

```.text
message MatchSetup
{
	uint64 timestamp		= 1;
	string category			= 2;

	string map 				= 3;
	string playlistName 	= 4;
	string playlistDesc 	= 5;
	Datacenter datacenter 	= 6;
	bool aimAssistOn		= 7;
	bool anonymousMode		= 8;
	string serverId			= 9;
}
```


## 例

```.text
timestamp: 1679500913
category: "matchSetup"
map: "mp_rr_desertlands_mu4"
playlistName: "World\'s Edge (Season 16)"
playlistDesc: "Fight to be the last squad standing."
datacenter {
  name: "japan west"
}
aimAssistOn: true
serverId: "889415:16019:45710738"
```

