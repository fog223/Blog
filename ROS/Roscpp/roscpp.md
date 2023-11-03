# Clinent Library之RosCpp

---

### roscpp主要包括

ros::init() 解析传入的ros参数，使用roscpp第一步需要用到的函数

ros::NodeHandle() 用于创建节点的句柄，和topic、service、parameter等进行交互的公共接口

ros::master 包含从master查询信息的函数

ros::this_node 包含查询这个进程（node）的函数

ros::service 包含查询服务的函数

ros::param 包含查询参数的函数,不需要用到NodeHandle

ros::names 包含处理ros图资源名称的函数

---

### 具体解析

1）ros::init() 解析ros参数，为本node命名

```
void ros::init(int &argc, char **argv, const std::string &name = std::string(), uint32_t options = 0);
```

2）ros::NodeHandle() Class

常用成员函数
```
// 创建话题的publisher
ros::Publisher advertise(const std::string &topic, uint32_t queue_size, bool latch = false);
// 创建话题的subscriber
ros::Subscriber subscribe(const std::string &topic, uint32_t queue_size, void(*)(M));
// 创建服务的server
ros::ServiceServer advertiseService(const std::string &service, bool(*)(SrvT &, RspT &));
// 创建服务的client
ros::ServiceClient serviceClient(const std::string &service, bool persistent = false);
// 查询某个参数的值
bool getParam(const std::string &key, T &val);
// 给参数赋值
bool setParam(const std::string &key, T val);
```

3）ros::master Namespace

常用函数
```
bool check(); //检查master是否启动
const string& getHost(); //返回master的hostname
bool getNodes(vector<string> &nodes); //返回当前运行的nodes
bool getTopics(vector<TopicInfo> &topics); //返回当前运行的topics
bool getURI(string &uri); //返回master的uri,如：http://localhost:11311
uint32_t getPort(); //返回master的端口号
```

4）ros::this_node Namespace

常用函数
```
void getAdvertisedTopics(vector<string> &topics); //返回当前node发布的topics
const string& getName(); //返回当前node的名称
cosnt string& getNamespace(); //返回当前node的namespace
void getSubscribedTopics(vector<string> &topics); //返回当前node订阅的topics
```

5）ros::service Namespace

常用函数
```
//调用一个RPC服务
bool call(const string &service, Service &service); 
//创建一个服务的client
ServiceClinet createClinet(const string &service, bool persistent = false); 
//检查一个服务是否存在
bool exists(const string &service); 
//等待一个服务,直到它可调用
bool waitForService(const string &service, uint32_t timeout = 0); 
```

6）ros::names Namespace

常用函数
```
string append(const string &ns, const string &name); //追加名称
string clean(const string &name); //清除名称
const M_string& getRemappings(); //返回当前的remappings
string remap(const string &name); //对名称重映射
string resolve(const string &name); //解析名称
bool validate(const string &name); //验证名称
``` 

