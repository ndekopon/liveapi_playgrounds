# blackMarketAction

## 定義

```.text
message BlackMarketAction
{
	uint64 timestamp	= 1;
	string category		= 2;

	Player player		= 3;
	string item			= 4;
}
```

## 例

```.text
timestamp: 1679501318
category: "blackMarketAction"
player {
  name: "sampleuser"
  teamId: 18
  pos {
    x: -8993.375
    y: 29712.5
    z: -3498.0
  }
  angles {
    y: 76.5966796875
  }
  currentHealth: 100
  maxHealth: 100
  shieldHealth: 100
  shieldMaxHealth: 100
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PC"
  teamName: "Team 17"
  character: "Loba"
  skin: "Rose Gold"
}
item: "1x HCOG \'CLASSIC\'"
```
