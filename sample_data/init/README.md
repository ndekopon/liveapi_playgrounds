# Initサンプルデータ

定義

```.protobuf
message Init
{
	uint64 timestamp	= 1;
	string category		= 2;

	string gameVersion 	= 3;
	Version apiVersion	= 4;
}
```

## データの例

### Version(2023_02_21_10_58)

```.text
timestamp: 1677626398
category: "init"
gameVersion: "Build ID: R5pc_r5-160_J29_CL4008794_2023_02_21_10_58"
apiVersion {
  major_num: 2
  minor_num: 1
  build_stamp: 887211
}
```

### Version(2023_02_14_10_52)

```.text
timestamp: 1677332980
category: "init"
gameVersion: "Build ID: R5pc_r5-160_J26_CL3925509_EX3959381_3973117_2023_02_14_10_52"
apiVersion {
  major_num: 2
  minor_num: 1
  build_stamp: 886511
}
```

