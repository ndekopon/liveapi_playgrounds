# playerAbilityUsed

アビリティの使用

## 定義

```.text
message PlayerAbilityUsed
{
	uint64 timestamp	= 1;
	string category		= 2;

	Player player		= 3;
	string linkedEntity = 4;
}
```


## 例

```.text
timestamp: 1679501027
category: "playerAbilityUsed"
player {
  name: "sampleuser"
  teamId: 5
  pos {
    x: 18593.01953125
    y: 26183.1796875
    z: -5071.875
  }
  angles {
    y: 3.003365993499756
  }
  currentHealth: 100
  maxHealth: 100
  shieldHealth: 50
  shieldMaxHealth: 50
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PS5"
  teamName: "Team 4"
  squadIndex: 1
  character: "Ash"
  skin: "Fallen Angel"
}
linkedEntity: "Tactical (Arc Snare)"
```


## linkedEntityの例

```.text
Arc Star
Frag Grenade
Tactical (#WPN_GRENADE_ELECTRIC_SMOKE_SHORT)
Tactical (Arc Snare)
Tactical (Focus of Attention)
Tactical (Into the Void)
Tactical (Knuckle Cluster)
Tactical (Missile Swarm)
Tactical (Nox Gas Trap)
Tactical (Perimeter Security)
Tactical (Surveillance Drone)
Thermite Grenade
Ultimate (Black Market Boutique)
Ultimate (Dark Veil)
Ultimate (Drone EMP)
Ultimate (Exhibit)
Ultimate (Interception Pylon)
Ultimate (Nox Grenade)
Ultimate (Rift Portals)
Ultimate (Rolling Thunder)
Ultimate (Skyward Dive)
Ultimate (Wrecking Ball)
zipline
```
