# weaponSwitched

武器切り替え

## 定義

```.text
message WeaponSwitched
{
	uint64 timestamp	= 1;
	string category		= 2;

	Player player		= 3;
	string oldWeapon	= 4;
	string newWeapon	= 5;
}
```

## 例

```.text
timestamp: 1679377197
category: "weaponSwitched"
player {
  name: "sampleuser"
  teamId: 3
  pos {
    x: 12153.0712890625
    y: -14403.35546875
    z: -3717.5
  }
  angles {
    y: -85.5758056640625
  }
  currentHealth: 100
  maxHealth: 100
  shieldHealth: 75
  shieldMaxHealth: 75
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PS5"
  teamName: "Team 2"
  squadIndex: 1
  character: "Octane"
  skin: "Extreme Measures"
}
oldWeapon: "mp_weapon_melee_survival"
newWeapon: "mp_weapon_car"
```

## 武器データ例

```.text
melee_pilot_emptyhanded
melee_wraith_kunai
mp_ability_companion_launch
mp_ability_companion_launch_entry
mp_ability_consumable
mp_ability_emote_projector
mp_ability_heal
mp_ability_holopilot
mp_ability_horizon_black_hole
mp_ability_mirage_ultimate
mp_ability_phase_walk
mp_ability_sniper_ult
mp_ability_space_elevator_tac
mp_weapon_alternator_smg
mp_weapon_autopistol
mp_weapon_car
mp_weapon_cluster_bomb_launcher
mp_weapon_cover_wall
mp_weapon_dirty_bomb
mp_weapon_dmr
mp_weapon_doubletake
mp_weapon_dragon_lmg
mp_weapon_energy_ar
mp_weapon_energy_shotgun
mp_weapon_frag_grenade
mp_weapon_g2
mp_weapon_grenade_bangalore
mp_weapon_grenade_creeping_bombardment
mp_weapon_grenade_emp
mp_weapon_grenade_gas
mp_weapon_hemlok
mp_weapon_jump_pad
mp_weapon_lmg
mp_weapon_mastiff
mp_weapon_melee_survival
mp_weapon_mobile_hmg
mp_weapon_mortar_ring
mp_weapon_mounted_turret_placeable
mp_weapon_mounted_turret_weapon
mp_weapon_nemesis
mp_weapon_pdw
mp_weapon_phase_tunnel
mp_weapon_r97
mp_weapon_rspn101
mp_weapon_semipistol
mp_weapon_sentinel
mp_weapon_shotgun_pistol
mp_weapon_sniper
mp_weapon_thermite_grenade
mp_weapon_vinson
mp_weapon_volt_smg
mp_weapon_wingman
mp_weapon_wraith_kunai_primary
mp_weapon_zipline
```

