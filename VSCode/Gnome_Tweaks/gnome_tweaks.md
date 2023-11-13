# Ubuntu 20.04 桌面美化之Mac Big Sur风格

### 前言

GNOME（GNU Network Object Model Environment）是一个开源的桌面环境，它是GNU计划的一部分。GNOME提供了一个直观、用户友好的桌面体验，旨在让用户能够轻松地使用和控制他们的计算机。GNOME的设计理念包括简单性、易用性和可访问性，使得用户可以方便地进行各种任务，从日常办公到娱乐和互联网浏览。

一些GNOME的特点包括：

1. **面向用户友好：** GNOME的设计注重用户体验，力求简单直观，使得使用计算机的过程更加愉快。

2. **可定制性：** 尽管GNOME注重简单性，但它也允许用户通过各种插件和主题进行定制，以满足不同用户的需求和喜好。

3. **多任务处理：** GNOME支持多任务处理，使用户能够轻松地切换和管理运行的应用程序。

4. **开源：** GNOME是开源软件，这意味着任何人都可以查看、修改和分发源代码。

GNOME的桌面环境包含许多基本应用程序，如文件管理器（Nautilus）、文本编辑器（gedit）、终端模拟器（GNOME Terminal）等，以及一套共享的库和工具，以确保一致性和集成性。

`gnome-tweaks`是一个GNOME桌面环境下的工具，允许用户进行更深入的系统和桌面设置调整。以下是一些 gnome-tweaks 的功能：

1. **外观设置：** 允许用户更改桌面主题、图标、字体和其他外观相关的设置。

2. **窗口管理：** 提供一些窗口管理相关的选项，如窗口焦点、工作区和窗口操作的行为。

3. **Shell扩展：** 允许用户管理和启用/禁用 GNOME Shell 的扩展，这些扩展可以增强桌面环境的功能。

4. **字体设置：** 允许用户调整系统字体的大小和样式。

5. **调整器设置：** 提供一些其他调整选项，例如电源、键盘、鼠标等设置。

总的来说，`gnome-tweaks` 提供了更多高级用户定制和调整 GNOME 桌面环境的选项，使用户能够更好地满足个人需求。

### 安装

1. `gnome-tweaks` 可以通过以下命令安装：

```
sudo apt install gnome-tweaks
```

2. 安装扩展管理器

```
sudo apt install gnome-shell-extensions
```

`gnome-shell-extensions` 是GNOME桌面环境的扩展。

具体来说，这个命令会安装 GNOME 桌面环境的一组扩展，这些扩展可以通过`gnome-tweaks` 工具进行管理。这些扩展提供了一些额外的功能和定制选项，以增强桌面环境的功能和外观。

一些常见的 GNOME Shell 扩展包括：

1. **Dash to Dock** 允许将应用程序启动器（Dash）转移到桌面底部，并提供了一些自定义选项，如图标大小和显示效果。

1. **TopIcons Plus** 将一些应用程序的托盘图标移到顶部栏，确保它们在 GNOME Shell 3.26及更高版本中可见。

2. **User Themes** 允许用户使用自定义的 GNOME Shell 主题。

3. **Applications Menu** 提供一个经典的应用程序菜单，类似于传统的“开始”菜单。

4. **Workspace Indicator** 在顶部栏显示当前工作区的指示器。

安装这些扩展后，用户可以通过 `gnome-tweaks` 进行配置，以启用、禁用或调整这些扩展的行为。这样，用户可以根据个人喜好和需求来定制他们的桌面环境，使其更符合自己的使用习惯。

3. 浏览器安装扩展

```
sudo apt install chrome-gnome-shell
```

`chrome-gnome-shell` 是一个用于集成 GNOME Shell 扩展的浏览器插件，通常用于 Google Chrome 和 Chromium 浏览器。这个插件允许用户通过浏览器直接管理和安装 GNOME Shell 扩展，而无需手动下载并复制到适当的文件夹。

具体来说，chrome-gnome-shell 提供了一个桥梁，让你可以在浏览器中轻松地浏览、查找和安装 GNOME Shell 扩展。以下是它的一些主要作用：

1. **在线浏览扩展** 插件会连接到 GNOME Shell 扩展的在线仓库，让用户能够通过浏览器查看所有可用的扩展。

2. **直接安装扩展** 用户可以通过浏览器一键安装 GNOME Shell 扩展，而无需手动下载并将文件复制到适当的目录。

3. **检查和更新扩展** 插件还提供了检查和更新已安装扩展的功能，确保用户始终使用最新版本的扩展。

安装 chrome-gnome-shell 插件后，你可以通过浏览器访问 GNOME 扩展网站，查找并安装你喜欢的扩展。这样的集成方式简化了扩展的管理流程，使用户更容易定制和增强他们的 GNOME 桌面环境。请注意，要使用这个插件，你需要确保你的 GNOME Shell 版本与扩展的兼容，并且你的浏览器中安装了对应的插件。

插件官网：https://extensions.gnome.org/

### 插件推荐

1. **User Themes** 允许用户使用自定义的 GNOME Shell 主题。

2. **Frippery Move Clock** 默认的时间是在顶部面板的中间显示的，安装这个插件后，时间就会显示到顶部面板的右边

3. **Dynamic Panel Transparency** 顶部面板的透明度会随着窗口的颜色而变化

4. **Panel OSD** 顶部面板的通知会显示在顶部面板的中间，而不是右下角

5. **Lunar Calendar** 顶部面板的日历会显示农历

### 主题

1. 主题下载

下载网站：https://www.gnome-look.org/browse/cat/
选择GTK3/4 Thems：下载如WhiteSur-Dark-solid.tar.xz；WhiteSur-Light-solid.tar.xz
![Alt text](<2023-11-13 16-36-47 的屏幕截图.png>)

2. 主题配置

将下载好的GTK theme解压之后放在home目录下的.themes目录（如果没有就创建一个）之下，然后打开GNOME Tweaks应用即可。

### icon

1. icon下载: https://www.gnome-look.org/browse/cat/
选择FUll Icon Themes：下载如WhiteSur.nor.tar.xz
![Alt text](<2023-11-13 16-34-37 的屏幕截图.png>)

2. icon配置
将下载好的icon theme解压之后移动到home目录下的.icons目录下（没有就创建一个）
然后打开GNOME Tweaks应用即可

### Cursor //光标

1. Cursor下载: https://www.gnome-look.org/browse/cat/
选择Cursor Themes：下载如macOS Big Sur
![Alt text](<2023-11-13 16-42-33 的屏幕截图.png>)

2. Cursor配置
将下载好的cursor theme解压之后移动到home目录下的.icons目录下（没有就创建一个）
然后打开GNOME Tweaks应用即可。

配置结果如下：
![Alt text](<2023-11-13 16-22-23 的屏幕截图.png>)
应用刚刚下载好的主题文件
将上述图片所示相应内容设置成自己下载好的主题即可。

### 配置dock栏

`Dash to Dock`是一个 GNOME 扩展。只需要通过浏览器安装即可，安装之后打开右键`show applications` 按钮（最下边的菜单按钮）并选择 `Dash to dock settings`来更改设置。

位置和大小->底部

### 壁纸和锁屏壁纸

壁纸，右键更换即可

锁屏壁纸：`Lock screen background`插件

### 字体

windows里的字体（通常是 .ttf 或 .otf 格式）在C:\Windows\Fonts中

两种方式：
1. 只对当前用户有效
将下载的字体文件复制到 ~/.fonts/ 目录（如果该目录不存在，可以创建），然后运行以下命令：`fc-cache -f -v`
这个命令会刷新系统字体缓存，让系统能够识别新安装的字体。

2. 对所有用户有效
```
sudo mkdir -p /usr/share/fonts/myfonts    #创建存放下载字体的文件夹
sudo chmod 744 /usr/share/fonts/myfonts/***.ttf    #设置文件权限，7为所有权限，4为只读
sudo mkfontscale    #控制字体旋转缩放
sudo mkfontdir      #控制字体粗斜体产生
sudo fc-cache -fv   #刷新系统字体缓存
```
