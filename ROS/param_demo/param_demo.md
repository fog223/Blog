# param_demo

---

### param_demo.cpp

```
#include <ros/ros.h>

int main(int argc,char** argv){
    ros::init(argc,argv,"param_demo"); //解析参数，为本node命名
    ros::NodeHandle nh; //创建句柄，实例化node
    int param1,param2,param3,param4,param5;
    // 获取参数
    ros::param::get("param1",param1);
    nh.getParam("param2",param2);
    nh.param("param3",param3,0);
    // 设置参数
    ros::param::set("param4",4);
    nh.setParam("param5",5);
    // 检查参数是否存在
    ros::param::has("param1");
    nh.hasParam("param2");
    // 删除参数
    ros::param::del("param1");
    nh.deleteParam("param2");

    return 0;
}
```

---

### param_demo_cpp.launch

```
<launch>
    <!--Param标签设置单个参数-->
    <param name="param1" value="1"/>
    <param name="param2" value="2"/>
    <param name="robot_descrption" command="$(find xacro)/xacro.py &(find demo)/urdf/robot.urdf"/>

    <!--Param标签设置多个参数-->
    <rosparm>
        param3: 3
        param4: 4
        param10:helloworld!
    </rosparm>
    <rosparam file="$(find param_demo)/config/myparam.yaml" command="load">

    <node pkg="param_demo" type="param_demo" name="param_demo" output="screen"/>

</launch>
