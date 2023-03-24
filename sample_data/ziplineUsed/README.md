# ziplineUsed

ジップラインの使用

## 定義

```.text
message ZiplineUsed
{
	uint64 timestamp	= 1;
	string category		= 2;
	
	Player player		= 3;
	string linkedEntity = 4;
}
```

## 例

```.text
timestamp: 1679501015
category: "ziplineUsed"
player {
  name: "sampleuser"
  teamId: 10
  pos {
    x: -10928.4677734375
    y: 24829.232421875
    z: -3377.890625
  }
  angles {
    y: -28.388525009155273
  }
  currentHealth: 100
  maxHealth: 100
  shieldHealth: 50
  shieldMaxHealth: 50
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PC"
  teamName: "Team 9"
  squadIndex: 2
  character: "Bangalore"
  skin: "Original"
}
linkedEntity: "zipline"
```

