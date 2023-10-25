# Rosbag

ROS命令行工具，记录和回放数据流

---

### 常用命令

1）rosbag

记录某些topic到bag中
```
rosbag record <topic_names>
```
记录所有topic到bag中
```
rosbag record -a
```
回放bag
```
rosbag play <bag_files>
```

2）rosmsg

列出系统上所有msg
```
rosmsg list
```
显示某个msg的内容
```
rosmsg show /<msg_name>
```
