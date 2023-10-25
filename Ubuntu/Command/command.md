# Ubuntu常用命令

### 1、文件操作
```
pwd   显示当前目录路径名称

cd    目录名称
cd .. 退出当前目录
cd /  退到根目录（经常用到）
cd ~  等价于  cd /home/fog  ：会进入当前用户的home目录

ls    列出当前目录文件（不包括隐含文件） 
ls -a 列出当前目录文件（包括隐含文件） 
ls -l 列出当前目录下文件的详细信息

gedit 写入文件

touch 创建任意格式的文件
  例如：touch a.txt b.cpp c.py

mkdir 创建目录
  a、既可以是一个绝对路径，也可以是一个相对路径。
  b、可以创建多个文件.如：mkdir f2 f3 f4

cp(copy) 复制文件
  格式：cp 源文件 目标文件
  例如：cp a.txt b.txt
  a、如果目标文件不存在，则创建一个新的文件，将源文件的内容复制到目标文件中。
  b、如果目标文件存在，则将源文件的内容覆盖到目标文件中。

  如果想把某目录下所有文件都复制，可以使用参数-r
  cp -r ~/test1/ ~/test2  //将test1目录下的所有文件都复制到test2目录中

rm    文件删除
  格式：rm -rf test/f2 test/f3
  a、-rf r将目录与其子目录一起删除，f是用来强制删除的。
  b、test/f2 test/f3 可以同时删除多个文件。

mv    移动文件到指定目录
  例如：
  mv a.txt b.txt    //同一路径，名称从a.txt变为b.txt，重命名
  mv ~/test/a.txt ~/test    //不同路径，没有指定新的名称，移动
  mv ~/test1/a.txt ~/test2/b.txt //不同路径不同名称，移动+重命名

注：当打开虚拟文件夹时，需要在前面加"."
  **例如：home属于虚拟文件夹，所以打开它的命令为**
  cd ./home

```

---

### 2、安装软件
```
1）apt
sudo apt-cache search package 搜索包 
sudo apt-get install package 安装包 
sudo apt-get remove package 删除包 
sudo apt-get remove package -- purge 删除包，包括删除配置文件等
sudo apt-get update 更新源
sudo apt-get upgrade 更新已安装的包

apt-cache show package 获取包的相关信息，如说明、大小、版本等 
sudo apt-get install package -- reinstall 重新安装包 
sudo apt-get -f install 修复安装”-f = –fix-missing” 
sudo apt-get dist-upgrade 升级系统 
sudo apt-get dselect-upgrade 使用 dselect 升级 
apt-cache depends package 了解使用依赖 
apt-cache rdepends package 查看该包被哪些包依赖 
sudo apt-get build-dep package 安装相关的编译环境 
apt-get source package 下载该包的源代码 
sudo apt-get clean && sudo apt-get autoclean 清理无用的包 
sudo apt-get check 检查是否有损坏的依赖 
sudo apt-get clean 清理所有软件缓存（即缓存在/var/cache/apt/archives目录里的deb包）

2）dpkg(Debian package) 包管理工具
sudo dpkg -i <.deb后缀的软件名>  //i 表示 install
sudo dpkg -r <包的名字>  //r 表示 remove, 此种方法会保留配置文件
sudo dpkg -P <包的名字>  //直接全删了，配置也不会保留
sudo dpkg -l            //查看安装列表
sudo dpkg -S <包的名字>  //搜索某个包
```

---

### 3、压缩解压缩
```
1）.tar
解包：tar xvf xxx.tar
打包：tar cvf xxx.tar DirName
（注：tar是打包，不是压缩！）

2）.tar.gz 和 .tgz
解压：tar zxvf FileName.tar.gz
压缩：tar zcvf FileName.tar.gz DirName

3）.tar.bz2
解压：tar jxvf FileName.tar.bz2
压缩：tar jcvf FileName.tar.bz2 DirName

4）.gz
解压1：gunzip FileName.gz
解压2：gzip -d FileName.gz
压缩：gzip FileName

5）.bz2
解压1：bzip2 -d FileName.bz2
解压2：bunzip2 FileName.bz2
压缩： bzip2 -z FileName

6）.zip
解压：unzip FileName.zip
压缩：zip FileName.zip DirName

7）.7z
解压：7z x FileName.7z
压缩：7z a FileName.7z DirName
```
 
---

### 4、其他
```
命令 --help 可得到帮助手册，显示命令的option

uname -a 查看内核版本

cat 查看文件的内容
cat /proc/cpuinfo 用于查看计算机的cpu信息。
cat /proc/meminfo 用于查看计算机的内在信息。
cat /etc/issue    查看ubuntu的版本信息。
```
