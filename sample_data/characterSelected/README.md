# characterSelected

キャラ選択

## 定義

```.text
message CharacterSelected
{
	uint64 timestamp	= 1;
	string category		= 2;

	Player player 		= 3;
}
```

## 例

```.text
timestamp: 1679500934
category: "characterSelected"
player {
  name: "sampleuser"
  teamId: 17
  pos {
    x: -11180.0
    y: 37319.0
    z: -705.125
  }
  angles {
  }
  nucleusHash: "0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
  hardwareName: "PC"
  teamName: "Team 16"
  squadIndex: 1
  character: "Valkyrie"
  skin: "Heat Sync"
}
```
