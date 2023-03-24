# grenadeThrown

グレネード投擲

## 定義

```.text
message GrenadeThrown
{
	uint64 timestamp	= 1;
	string category		= 2;

	Player player		= 3;
	string linkedEntity = 4;
}
```

## 例

```.text
timestamp: 1679501049
category: "grenadeThrown"
player {
  name: "sampleuser"
  teamId: 7
  pos {
    x: 20616.103515625
    y: 25090.658203125
    z: -4800.67626953125
  }
  angles {
    y: -164.1524658203125
  }
  currentHealth: 100
  maxHealth: 100
  shieldHealth: 50
  shieldMaxHealth: 50
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PC"
  teamName: "Team 6"
  squadIndex: 2
  character: "Catalyst"
  skin: "Technowitch"
}
linkedEntity: "Tactical (#WPN_GRENADE_ELECTRIC_SMOKE_SHORT)"
```

