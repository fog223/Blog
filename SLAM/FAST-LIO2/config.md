# FAST-LIO2配置

### 要求

Ubuntu >= 16.04

ROS >= Melodic

PCL >= 1.8

Eigen >= 3.3.4

Livox ROS Driver，依赖于Livox-SDK

---

*1、PCL安装*

```
sudo apt-get install libpcl-dev
```

*2、Eigen安装*

```
sudo apt-get install libeigen3-dev
```

*3、Livox-SDK安装*

```
git clone https://github.com/Livox-SDK/Livox-SDK.git
cd Livox-SDK/build
cmake ..
make -j4
sudo make install
```

---

*5、构建Fast-Lio2*
```
git clone https://github.com/hku-mars/FAST_LIO.git
cd FAST_LIO
git submodule update --init //获取子模组ikd-Tree
cd ..
git clone https://github.com/Livox-SDK/livox_ros_driver.git
```

### 注意事项

*1、ceres版本2.1.0中，livox_ros_driver编译需要将C++14修改为C++17,
需要g++ 7.0以上的版本*
