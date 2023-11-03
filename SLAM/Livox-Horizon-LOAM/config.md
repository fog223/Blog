# Ubuntu20.04中配置Livox-Horizon-LOAM

### 要求

默认安装PCL版本1.10，不适配，改为1.8，修改CMakeLists.txt中的PCL版本为1.8

ceres版本2.1.0

opencv版本4.2.0

---

*1、PCL安装*

详情见SLAM/env.md

*2、Ceres安装*

详情见SLAM/env.md

*3、opencv安装*

```
sudo apt-get install libopencv-dev
```

---

### 构建ROS工作空间
```
mkdir -p horizon_ws/src
cd horizon_ws/src
git clone https://github.com/Livox-SDK/livox_horizon_loam.git
git clone https://github.com/Livox-SDK/livox_ros_driver.git
cd ..
catkin_make
```

### 注意事项

*1、ceres版本2.1.0中，livox_ros_driver编译需要将C++14修改为C++17,
需要g++ 7.0以上的版本*

*2、livox_horizon_loam中的CMakeLists.txt*

修改如下：

set(CMAKE_CXX_FLAGS "-std=c++17 -fext-numeric-literals")

set(PCL_DIR "/usr/local/pcl-1.8/share/pcl-1.8")
find_package(PCL 1.8 REQUIRED)

### 编译错误

*1、fatal error: opencv/cv.h: No such file or directory*

把源码中的#include <opencv/cv.h>改成#include <opencv2/opencv.hpp>