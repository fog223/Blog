# Ubuntu安装

### 1、Ubuntu系统镜像下载
```
https://cn.ubuntu.com/download/desktop
```

---

### 2、镜像安装工具win32diskimager下载
```
https://sourceforge.net/projects/win32diskimager/
```

---

### 3、磁盘管理

需要给ubuntu分配磁盘空间，遇到无法删除的磁盘

采用```Win+R,cmd```,```diskpart```命令进入磁盘管理

```list```查看磁盘列表

```select disk 0```选择磁盘0

```list partition```查看磁盘0的分区列表

```select partition 1```选择分区1

```delete partition override```删除分区1

---

### 4、磁盘格式

```MBR```格式，通常对应Legacy BIOS，引导区为```/boot```

```GPT```格式，通常对应UEFI, 引导区为```/efi```

```Windows磁盘管理```中可以查看磁盘格式，磁盘属性中```卷```

---

### 5、启动U盘

**U盘格式化问题**

```FAT32```无兼容性问题，```exFAT```和```NTFS```可能有很多老旧主板和电脑不识别，
但```FAT32```单个分区不能超过```32G```，单个文件不能超过```4G```

---

### 6、Ubuntu安装，分区方式

**efi, ubuntu引导区**

```1G```足够

---

**swap, ubuntu交换分区**

一般比物理内存大一点，如```16G```内存，```swap```设置为```20G```

---

**/, ubuntux系统分区,类似Window中的C盘**

---

**/home, 类似Window中的D盘，存储个人数据**

---

### 7、同步Windows和Ubuntu时间

```
sudo apt-get install ntpdate
sudo ntpdate time.windows.com
sudo hwclock --localtime --systohc
```