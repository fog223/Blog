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
cd Livox-SDK
mkdir build && cd build
cmake ..
make -j4
sudo make install
```

*4、Livox ROS Driver安装*

```
git clone https://github.com/Livox-SDK/livox_ros_driver.git ws_livox/src
cd ws_livox
catkin_make
```
配置环境变量
```
source ./devel/setup.sh
```
