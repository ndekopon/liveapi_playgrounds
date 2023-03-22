# playerConnected

プレイヤー接続

## 定義

```.text
message PlayerConnected
{
	uint64 timestamp	= 1;
	string category		= 2;
	
	Player player 		= 3;
}
```

## 例

```.text
player {
  name: "sampleuser"
  teamId: 2
  pos {
    x: -11180.0
    y: 37319.0
    z: -705.125
  }
  angles {
  }
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PC"
  teamName: "Team 1"
  squadIndex: 1
  character: "Wattson"
  skin: "Wired for Speed"
}
```

