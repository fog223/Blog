# ROS通信方式之Parameter Server

存储各种参数的字典

可用命令行，launch文件和node(API)读写

---

### 常用命令

1）命令行中，rosparam

列出当前所有参数
```
rosparam list
```
显示某个参数的值
```
rosparam get <param_key>
```
设置某个参数的值
```
rosparam set <param_key> <param_value>
```
保存参数到文件
```
rosparam dump <file_name>
```
从文件读取参数，需要是yaml格式
```
rosparam load <file_name>
```
删除参数
```
rosparam delete <param_key>
```

2）luanch文件中定义
```
<param>与<rosparam>标签
```
