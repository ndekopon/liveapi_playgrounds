# ammoUsed

弾薬使用(弾薬捨てたときもイベント発生するかも)


## 定義

```.text
message AmmoUsed
{
	uint64 timestamp	= 1;
	string category		= 2;

	Player player		= 3;
	string ammoType		= 4;
	uint32 amountUsed	= 5;
	uint32 oldAmmoCount	= 6;
	uint32 newAmmoCount = 7;
}
```

## 例

```.text
timestamp: 1679501007
category: "ammoUsed"
player {
  name: "sampleuser"
  teamId: 13
  pos {
    x: -28841.125
    y: 500.875
    z: -3328.625
  }
  angles {
    y: 129.55078125
  }
  currentHealth: 100
  maxHealth: 100
  shieldHealth: 50
  shieldMaxHealth: 50
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PC"
  teamName: "Team 12"
  squadIndex: 1
  character: "Catalyst"
  skin: "Archon"
}
ammoType: "shotgun"
amountUsed: 16
oldAmmoCount: 32
newAmmoCount: 16
```

## ammoType例

```.text
bullet
highcal
shotgun
sniper
special
```

