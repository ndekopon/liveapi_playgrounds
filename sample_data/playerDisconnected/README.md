# PlayerDisconnected

プレイヤー切断

## 定義

```.text
message PlayerDisconnected
{
	uint64 timestamp	= 1;
	string category		= 2;

	Player player 		= 3;
	bool canReconnect	= 4;
}
```

## 例


```.text
timestamp: 1679501238
category: "playerDisconnected"
player {
  name: "sampleuser"
  teamId: 5
  pos {
    x: 8971.25
    y: 34533.875
    z: -4087.75
  }
  angles {
    y: -124.8046875
  }
  currentHealth: 100
  maxHealth: 100
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PC"
  teamName: "Team 4"
  squadIndex: 2
  character: "Seer"
  skin: "Original"
}
```

