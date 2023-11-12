# VSCode中进行ROS项目的 Debug 配置方法

### 注意

在VSCode里加载ROS工作空间前，必须要catkin_make

即`mkdir -p ~/catkin_ws/src && cd ~/catkin_ws && catkin_make`

---

### c_cpp_properties.json(默认)

```
{
  "configurations": [
    {
      "browse": {
        "databaseFilename": "${default}",
        "limitSymbolsToIncludedHeaders": false
      },
      "includePath": [
        "/home/fog/rviz_ws/devel/include/**",
        "/opt/ros/noetic/include/**",
        "/opt/ros/noetic/share/innovusion_pointcloud/include/**",
        "/usr/include/**"
      ],
      "name": "ROS",
      "intelliSenseMode": "gcc-x64",
      "compilerPath": "/usr/bin/gcc",
      "cStandard": "gnu11",
      "cppStandard": "c++14"
    }
  ],
  "version": 4
}
```

---

### tasks.json(ctrl+shift+b->catkin_make: build)

```
{
	"version": "2.0.0",
	"tasks": [
		{
			"type": "catkin_make",
			"args": [
				"--directory",
				"/home/fog/rviz_ws",
				"-j14",
				"-DCMAKE_BUILD_TYPE=Debug"
			],
			"problemMatcher": [
				"$catkin-gcc"
			],
			"group": {
				"kind": "build",
				"isDefault": true
			},
			"label": "catkin_make: build"
		}
	]
}
```

---

### launch.json

## 单节点 ## 
(add configuration中选(gdb) Launch即可)
然后修改`program`以及增加`preLaunchTask`

```
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "(gdb) Launch",
            "type": "cppdbg",
            "request": "launch",
            "program": "${workspaceRoot}/devel/lib/loam_horizon/livox_repub",
            "args": [],
            "stopAtEntry": false,
            "cwd": "${fileDirname}",
            "environment": [],
            "externalConsole": false,
            "MIMode": "gdb",
            "setupCommands": [
                {
                    "description": "Enable pretty-printing for gdb",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                },
                {
                    "description": "Set Disassembly Flavor to Intel",
                    "text": "-gdb-set disassembly-flavor intel",
                    "ignoreFailures": true
                }
            ],
            "preLaunchTask": "catkin_make: build"
        }
    ]
}
```

---

## 多节点（采用ROS：Launch） ## 

(add configuration中选(ROS: Launch即可))
然后修改`target`为.launch文件路径

```
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "ROS: Launch",
            "type": "ros",
            "request": "launch",
            "target": "absolute path to launch file"
        }
    ]
}
```