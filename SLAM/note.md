# 随想笔记，tips

#### 1、luanch文件中的remap

话题重映射，将一个话题重映射到另一个话题，如下：
```
<node pkg="loam_horizon" type="scanRegistration" name="scanRegistration" output="screen" >
    <remap from="/livox_undistort" to="/iv_points" />
```
含义：将scanRegistration中订阅的话题/livox_undistort映射为订阅/iv_points的意思，代码中的订阅话题为/livox_undistort，但是实际上订阅的是/iv_points。

#### 2、Failed to transform from frame [/camera_init] to frame [camera_init]

ros版本noetic中坐标系的写法问题，不能带"/"，‘/camera_init‘写成’camera_init‘即可。