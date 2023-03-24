# wraithPortal

## 定義

```.text
message WraithPortal
{
	uint64 timestamp	= 1;
	string category		= 2;

	Player player		= 3;
}
```

## 例

```.text
timestamp: 1679501287
category: "wraithPortal"
player {
  name: "sampleuser"
  teamId: 18
  pos {
    x: -7666.35888671875
    y: 30869.369140625
    z: -4112.46630859375
  }
  angles {
    y: 9.370124816894531
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
```
