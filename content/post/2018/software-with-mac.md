---
title: "MAC常用软件安装"
description: "那些有关Command line的软件"
date: 2018-10-28T14:34:47+08:00
tags: [ "MAC", "常用软件", "技巧分享" ]
categories: [ "tools" ]
isCJKLanguage: true
include_toc: true
draft: false
---

> 本文记录我的Mac常用开发环境维护

## 起因

前几天电脑突然抽风，开机卡死，完全没有反应。试过各种方法，常规的清除 NVRAM 和 PRAM ，然后恢复之前的Time Machine，发现都不行，但发现安全模式可以进入，操作没问题，赶紧备份数据，然后抹盘重装，也卡在选择时区键盘等操作。联系客服，也给出基本类似的常规操作，未果，约了天才吧时间。择日去了陆家嘴的店，现场检查也都没问题，不过他们的工具在检查磁盘的时候卡死了，所以留下，说可能是主板问题，可能是显卡问题，价格都不便宜，具体看检查结果。没其他办法，只能抱着试一试的心理留下。隔了几天一个小哥电话给我说他装了系统没问题，也不知道什么原因，就好了👐🏻。好吧，不花钱也是好事，虽然折腾了一点，不过 Time Machine 不敢用了，只能一个个安装自己曾经用过的软件，下面记录下，以备不时之需。

## 开发工具

### 0x00 CLT安装

作为一个RD，一些顺手的开发工具肯定少不了，因为不用xcode，但是其他开发软件需要用到CLT（Command Line Tools），所以需要先安装CTL。

> The **Command Line Tools Package** is a small self-contained **package** available for **download** separately from Xcode and that allows you to do **command line development** in OS X. It consists of two components: OS X **SDK** and command-line tools such as **Clang**, which are installed in /usr/bin.

可以看出，CLT主要就是一些开发包，而因为我们很多常用基于Unix的软件安装需要用到GCC编译，所以在安装其他软件之前，我们先安装CLT以备不时之需。打开Terminal ，运行以下命令

```
xcode-select --install
```

根据提示弹出框，确认安装完成即可

### 0x01 Homebrew

因为Mac的 Appstore 基本都是提供面相C端，所以需要找一些macOS没有预装，或是 Appstore 上没有的软件，或是一些工具的话，Homebrew提供了一个非常好的一键安装方式。

> **The missing package manager for macOS**

这是Homebrew的定义，提供 macOS 缺失软件包的管理器。安装也非常简单，Homebrew是基于ruby的，因为Mac自带了ruby，所以我们可以在终端直接执行

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Homebrew提供两种软件的安装方式

- 主要是一些命令行的工具类Unix软件

  ```shell
  brew install tig
  ```

- Appstore 软件补充（打好包的dkg或是dmg文件）

```shell
brew cask install chrome
```

用Homebrew主要是可以帮你一键管理安装软件的依赖、升级、删除等一些列麻烦的事情。非常便捷，所以放在第一个。

### 0x02 Iterm2

> *iTerm2* is a terminal emulator for Mac OS X that *does amazing things*

要问我Mac上神器那么多，第一应该是什么，那肯定是Iterm2啊，使用最多也非常顺手，自定义方式多，开箱即用的配色方案总有一个满足你，天天苦逼工作的同事能保持心情愉悦的保证。所以第二个我们先安装Iterm2代替系统自带的Terminal。如果需要自定义不同配色方案，可以去 https://github.com/mbadolato/iTerm2-Color-Schemes 下载自己中意的。

- 打开链接https://www.iterm2.com/downloads.html 选择最新安装包
- 执行  **⌘ + i** 打开当前配置
- 点击 **Colors** 页面
- 点击 **Color Presets**
- 点击 **Import**
- 选择对应的 `.itermcolors` 文件
- 再次点击 **Color Presets** 选择对应配置文件

新版已经包含了 Solarized 主题，所以我只需要选择 Solarized Dark 主题即可（一直使用此主题，非常推荐）

当然，如果能找到一个高品质的图片当窗口背景，那就更好不过了

### 0x03 zsh + oh-my-zsh

好吧，我错了，其实第一神器应该当之无愧是zsh😄，不过zsh这家伙实在太调皮，一般人搞不定，所以在 oh-my-zsh 出来之前，只能说还是极客折腾的多，没有那么普遍的流行。所以我们今天主要安装对 zsh 加持的 os-my-zsh 和其相关设定。

#### 安装zsh

Mac 系统自带zsh，可以通过

```shell
cat /etc/shells
```

查看系统支持 shell 及排序，修改为 zsh 的话，可以通过以下命令

```shell
chsh -s /bin/zsh
```

这个命令会默认回修改当前用户登录后的使用 shell 脚本。

#### 安装 oh-my-zsh

打开 oh-my-zsh 的主页，也能看到介绍是 **framework** for managing your zsh configuration ，所以足以见得玩好zsh是多么麻烦的一件事。安装非常方便，打开 Iterm2 ， 输入

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

或者

```shell
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

分别是通过curl的方式和wget的方式获取对应安装脚本并在本地执行。

#### 皮肤配置

当然，如果你要是用一些非常炫酷的主题的话，需要 `powerline` 支持，比如基本第一次入 zsh 坑的 `agnoster` 主题，因为没有powerline 字体的加持的话，会出来很多?之类显示不了的特殊字符。我们先安装powerline 字体

```shell
git clone https://github.com/powerline/fonts.git --depth=1
cd fonts
./install.sh
# 需要删除这些打过patch的字体的话，执行
./uninstall.sh
```

然后打开 Iterm2 

- 执行 **⌘ + i** 打开当前配置
- 选择 **Text** 
- 点击 **Change Font** ，选择自己喜欢的字体 + PowerLine，比如我选择的是 `Monaco For PowerLine`
- 重新打开 Item2

#### 插件配置

官方插件一览 https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview ，正常情况，zsh插件自带了 git ，提供了命令行下 git 的一些常用操作，可以通过 tab 弹出，或者对应缩写的 alias 的支持。我常用的几个插件如下

| 插件                    | 功能                                                    | 安装                                                         |
| :---------------------- | ------------------------------------------------------- | ------------------------------------------------------------ |
| git                     | git 友好提示                                            | 自带，已添加进`.zshrc`的plugins中                            |
| zsh-autosuggestions     | 输入语法提示                                            | `git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions` |
| zsh-syntax-highlighting | 输出语法高亮                                            | `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting` |
| history                 | 带时间格式的历史输出                                    | 自带，添加进`.zshrc`的plugins中                              |
| autojump                | 知道曾经的部分路径关键字就可以自动路径跳转，`j xxx`即可 | 需要先安装`brew install autojump`，然后添加进`.zshrc`的plugins中（自带的autojump主要是为了找到安装对autojump执行shell文件） |
| urltools                | 可以命令行对url 加解密`urlencode`、`urldecode`          | 自带，添加进`.zshrc`的plugins中                              |

安装后的`.zshrc`配置文件的plugins模块如下

```zsh
plugins=(
 git
 autojump
 urltools
 zsh-syntax-highlighting
 zsh-autosuggestions
)
```

其中，如果 `autojump` 不想单独安装对话，可以用 zsh 自带的 `z` 替换，不过我用喜欢了autojump，`j` 输入感觉更加方便。zsh-autosuggestions 提供的补全是默认的 →（右箭头），不喜欢可以在 `.zshrc` 中修改键位绑定，在 `source $ZSH/oh-my-zsh.sh` 之后添加（我是用 Ctrl+空格 完成补全）

```shell
bindkey '^ ' autosuggest-accept
```

### 0x04 其他软件

这里再列几个便捷常用的，安装方式都是 `brew install xxx`

- `tig` ：上面举例里面有过的，一个非常可视化的查看 git log 的命令行软件

- `bat` ：增强版的 `cat(1)` 命令，提供代码高亮和行数，`A cat(1) clone with wings. `官网的解释可以说非常形象了
- `tree`：树形结构查看文件夹目录，非常实用，不知道为什么没有预装
- `telnet`：因为明文传输的问题，苹果就非常高傲的从 [High Sierra](https://discussions.apple.com/community/mac_os/high_sierra) 把这个工具删了，虽然可以用 `nc` 代替，但是因为习惯，很多脚本还在使用，所以如果还是装回来
- `figlet`：非常有意思的一款生成文字banner的小工具，可以用于shell启动或是程序启动中用来增添乐趣

暂时列到这里，还有些软件后续有空再来补充💪😹