# inventoryPickUp

## 定義

```.text
message InventoryPickUp
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
timestamp: 1679500994
category: "inventoryPickUp"
player {
  name: "sampleuser"
  teamId: 11
  pos {
    x: -20122.177734375
    y: -20238.69140625
    z: -4312.125
  }
  angles {
    y: -87.02933502197266
  }
  currentHealth: 100
  maxHealth: 100
  shieldHealth: 50
  shieldMaxHealth: 50
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PC"
  teamName: "Team 10"
  squadIndex: 2
  character: "Crypto"
  skin: "Midnight"
}
item: "Light Rounds"
quantity: 20
```

## アイテム例

```.text
1x DIGITAL THREAT (Level 4)
1x HCOG \'CLASSIC\'
1x HOLO
1x-2x VARIABLE HOLO (Level 2)
2x HCOG \'BRUISER\' (Level 2)
2x-4x VARIABLE AOG (Level 3)
30-30 Repeater
3x HCOG \'RANGER\' (Level 3)
4x-8x VARIABLE SNIPER (Level 3)
6x SNIPER (Level 2)
Alternator SMG
Arc Star
Backpack (Level 2)
Backpack (Level 3)
Backpack (Level 4)
Backpack
Barrel Stabilizer (Level 2)
Barrel Stabilizer (Level 3)
Barrel Stabilizer
Body Shield (Level 4)
C.A.R. SMG
Charge Rifle
Devotion LMG
Double Tap Trigger (Level 4)
EVA-8 Auto
Energy Ammo
Evo Shield (Level 2)
Evo Shield (Level 3)
Evo Shield (Level 5)
Evo Shield
Extended Energy Mag (Level 2)
Extended Energy Mag (Level 3)
Extended Energy Mag (Level 4)
Extended Energy Mag
Extended Heavy Mag (Level 2)
Extended Heavy Mag (Level 3)
Extended Heavy Mag (Level 4)
Extended Heavy Mag
Extended Light Mag (Level 2)
Extended Light Mag (Level 3)
Extended Light Mag (Level 4)
Extended Light Mag
Extended Sniper Mag (Level 2)
Extended Sniper Mag (Level 3)
Extended Sniper Mag
Frag Grenade
G7 Scout
HAVOC Rifle
Hammerpoint Rounds (Level 4)
Heavy Rounds
Helmet (Level 2)
Helmet (Level 3)
Helmet (Level 4)
Helmet
Knockdown Shield (Level 2)
Knockdown Shield (Level 3)
Knockdown Shield (Level 4)
Kraber .50-Cal Sniper (Level 5)
L-STAR EMG
Laser Sight (Level 2)
Laser Sight (Level 3)
Laser Sight
Light Rounds
M600 Spitfire
Mastiff Shotgun
Med Kit (Level 2)
Mobile Respawn Beacon (Level 2)
Mozambique Shotgun
Nemesis Burst AR
P2020
Peacekeeper
Phoenix Kit (Level 3)
Prowler Burst PDW
R-301 Carbine
R-99 SMG
RE-45 Auto (Level 5)
Rampage LMG
Sentinel
Shield Battery (Level 2)
Shield Cell
Shotgun Bolt (Level 2)
Shotgun Bolt (Level 3)
Shotgun Bolt (Level 4)
Shotgun Bolt
Shotgun Shells
Skullpiercer Rifling (Level 4)
Sniper Ammo
Sniper Stock (Level 2)
Sniper Stock (Level 3)
Sniper Stock
Standard Stock (Level 2)
Standard Stock (Level 3)
Standard Stock
Syringe
Thermite Grenade
Triple Take
Turbocharger (Level 4)
Ultimate Accelerant (Level 2)
VK-47 Flatline
Vault Key (Level 5)
Wingman
```

