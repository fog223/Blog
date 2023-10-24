# Ubuntu常用命令

### 输入法平台：ibus

IBus 全称 Intelligent Input Bus是下一代输入法框架（或者说“平台”）。 项目现托管于 Google Code - [ibus](https://code.google.com/p/ibus/) 此项目包含了世界多数语言的文字输入需求——由世界多个国家开发者维护。支持多种输入法。

---

### RIME／中州韵输入法引擎（Rime Input Method Engine）

**1、安装**

```
sudo apt install ibus-rime
```

---

**2、系统设置**

Ubuntu 22.04版本：设置->-键盘->输入源->加号->汉语->中文（Rime）

---

**3、配置**

```
cd ~/.config/ibus/rime/
sudo gedit default.custom.yaml
```

yaml中写入配置

```
chema_list:   
  - schema: luna_pinyin_simp #simp是简体，第一位是默认输入法 
menu:
  page_size: 9 #每页候选词个数
ascii_composer:
  switch_key:
    Shift_L: commit_code #左shift提交字母
```

写好保存，重启ibus
```
ibus restart
```