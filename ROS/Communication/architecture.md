# ROS通信架构

### Master

每个node启动时需要向master注册，管理node之间的通信

```roscore```启动ros master：节点管理器

顺带启动rosout：日志输出，paremeter server:参数服务器

---

### Node

ROS的进程，pkg里的可执行文件运行的实例

---

1）rosrun

启动一个node

```
rosrun [pkg_name][node_name]
```

2）rosnode

列出当前运行的node信息
```
rosnode list
```
显示某个node的详细信息
```
rosnode info [node_name]
```
结束某个node
```
rosnode kill [node_name]
```

3）roslaunch

启动master和多个node
```
roslaunch [pkg_name][file_name.launch]
```
