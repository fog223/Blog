# Ubuntu安装配置Rime输入法

### 非搜狗输入法的原因：

搜狗输入法与Clion冲突

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

Ubuntu 20.04版本：设置->区域与语言->输入源->加号->汉语->中文（Rime）

Ubuntu 22.04版本：设置->键盘->输入源->加号->汉语->中文（Rime）

---

**3、配置**

```
cd ~/.config/ibus/rime/build/
sudo gedit default.yaml
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

横排设置
在```~/.config/ibus/rime/build/ibus_rime.yaml```中添加
```
style:
   horizontal: true
```

然后重新部署（不同步）
