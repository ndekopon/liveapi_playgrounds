# inventoryDrop

アイテムを捨てる

## 定義

```.text
message InventoryDrop
{
	uint64 timestamp	= 1;
	string category		= 2;

	Player player		= 3;
	string item			= 4;
	int32  quantity		= 5;
	repeated string extraData = 6;
}
```

## 例


```.text
timestamp: 1679501003
category: "inventoryDrop"
player {
  name: "sampleuser"
  teamId: 19
  pos {
    x: -14096.0
    y: -7537.75
    z: -3840.0
  }
  angles {
    y: 12.48046875
  }
  currentHealth: 100
  maxHealth: 100
  shieldHealth: 50
  shieldMaxHealth: 50
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PC"
  teamName: "Team 18"
  squadIndex: 2
  character: "Seer"
  skin: "Heart Stopper"
}
item: "P2020"
quantity: 1
```

