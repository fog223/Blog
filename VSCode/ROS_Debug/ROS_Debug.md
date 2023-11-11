# VSCode中进行ROS项目的 Debug 配置方法

### c_cpp_properties.json

```
{
    "configurations": [
        {
            "browse": {
                "databaseFilename": "${default}",
                "limitSymbolsToIncludedHeaders": true
            },
            "includePath": [
                "/home/fog/rviz_ws/devel/include/**",
                "/opt/ros/noetic/include/**",
                "/usr/include/**"
            ],
            "name": "ROS",
            "intelliSenseMode": "gcc-x64",
            "compilerPath": "/usr/bin/gcc",
            "cStandard": "gnu11",
            "cppStandard": "c++14",
        }
    ],
    "version": 4
}
```

---

### tasks.json(ctrl+shift+b)

```
{
	"version": "2.0.0",
	"tasks": [
		{
			"type": "catkin_make",
			"args": [
				"--directory",
				"/home/fog/rviz_ws",
				"-j8"
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

```
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "(gdb) Launch", // 配置名称，将会在调试配置下拉列表中显示
            "type": "cppdbg", // 调试器类型 该值自动生成
            "request": "launch", // 调试方式,还可以选择attach
            "program": "${workspaceFolder}/devel/lib/rviz/rviz", //要调试的程序（完整路径，支持相对路径）
            "args": [], // 传递给上面程序的参数，没有参数留空即可
            "stopAtEntry": false, // 是否停在程序入口点（停在main函数开始）
            "cwd": "${workspaceFolder}", // 调试程序时的工作目录
            "environment": [], //针对调试的程序，要添加到环境中的环境变量. 例如: [ { "name": "squid", "value": "clam" } ]
            "externalConsole": false, //如果设置为true，则为应用程序启动外部控制台。 如果为false，则不会启动控制台，并使用VS Code的内置调试控制台。
            "MIMode": "gdb", // VSCode要使用的调试工具
            "preLaunchTask": "catkin_make: build", // 这个很重要，需要与task.json中的label相同
            "setupCommands": [
                {
                    "description": "Enable pretty-printing for gdb",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                }
            ]
        }
    ]
}
```