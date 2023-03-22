# inventoryUse

アイテム使用

## 定義

```.text
message InventoryUse
{
	uint64 timestamp	= 1;
	string category		= 2;

	Player player		= 3;
	string item			= 4;
	int32  quantity		= 5;
}
```

## 例

```.text
timestamp: 1679501049
category: "inventoryUse"
player {
  name: "sampleuser"
  teamId: 3
  pos {
    x: 11535.798828125
    y: -10349.3544921875
    z: -3708.75
  }
  angles {
    y: 104.96110534667969
  }
  currentHealth: 87
  maxHealth: 100
  shieldMaxHealth: 50
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PS4"
  teamName: "Team 2"
  squadIndex: 2
  character: "Valkyrie"
  skin: "Military Grade"
}
item: "Shield Cell"
quantity: 1
```
