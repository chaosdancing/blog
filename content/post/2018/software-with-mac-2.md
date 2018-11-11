---
title: "MAC常用软件安装2"
description: "那些有关桌面应用的软件"
date: 2018-11-11T10:00:55+08:00
tags: [ "MAC", "常用软件", "技巧分享" ]
categories: [ "tools" ]
isCJKLanguage: true
include_toc: true
draft: false
---

> 上篇我们说了命令行的一些软件，这里我们重点说一下一些桌面应用的必备软件

## 开发工具

### 1、JetBrain 工具包
作为一个研发狗，开发工具肯定是不能少的，我觉得无论那种语言的，JetBrain的工具必不可少，我常用的是[IntelliJ IDEA](https://www.jetbrains.com/idea/)和[DataGrip](https://www.jetbrains.com/datagrip/)。选择上应该有三

- 不缺钱的最好支持下，JetBrain在中国也有代理，支持多重付款方式，个人用户149刀一年，还是比较贵的
- 如果舍不得花钱的话，其也很贴心的提供了社区版，功能也基本够用（只是少了一些自带的重复代码检测啊/脚本支持啊/一些框架的支持等等）
- 又没钱又想用全部功能，只能下下策找下破解服务器或自己搭建一个，究竟这样好不好也不予置评了😂

### 2、编辑工具
从Sublime Text到Atom，再到VS Code，亦或是vim，每个人都有自己的偏好和选择，这里简单说一下我的理解和选择。
#### Sublime Text
![sublime](https://ws3.sinaimg.cn/large/006tNbRwgy1fx3y8jk39sj30740740te.jpg)

- 地址：https://www.sublimetext.com/
- 收费：$80 (也可免费使用会有收费提示)
- 开发者：个人（前Google 员工）
- 支持平台：三端

自我介绍：

>A sophisticated text editor for code, markup and prose

Sublime Text从07年开始到现在，已经是一个十分成熟的软件了，当年记得免费特性洗了很多TextMate的用户，自己本身也十分优秀，常年霸占编辑器排行榜前几位。`⌘ + P` 安装必备软件包也成了安装软件后端第一个操作，在Sublime Text3已经将很多软件预装了。
不过从其最初自我介绍的`The text editor you'll fall in love with`到现在的`A sophisticated text editor for code, markup and prose`，看出他的也行，也看出它是个老而弥坚的编辑器了~

#### Atom

![atom](https://ws1.sinaimg.cn/large/006tNbRwgy1fx3y7psesbj30go05kjre.jpg)

- 地址：https://atom.io/
- 收费：免费 (MIT Licence)
- 开发者：Github
- 支持平台：三端
自我介绍：

>A hackable text editor for the 21st Century

Atom1 14年的横空出世，因为开发者的原因和推广，得到了非常大一波的流量，从其自我介绍就知道，重点在于hackable，这是一个你只要想做什么都能做到的软件，高度定制化。不过有一个缺点就是性能还是不是特别好，很多实用功能和插件，都是移植于Sublime Text的。

#### VS Code

![vscode](https://ws1.sinaimg.cn/large/006tNbRwgy1fx3y42gc8ej3074074gli.jpg)

- 地址：https://code.visualstudio.com/
- 收费：免费
- 开发者：Microsoft
- 支持平台：三端

>Code editing. Redefined.

微软的Visual Studio Code（简称VS Code），其实说是编辑器，还不如说是微软向轻量级的IDE进攻的一种方式，听说VS Code这个开源产品点部门人数达到了100多之众，可见对于这款产品的重视。可能因为微软多年的IDE上的积累，VS Code用起来非常不错，甚至于作为一些轻量级工程的IDE使用也得心应手。一些重要的软件包都是出于微软官方，质量和效率都能得到保证。现在是我的第一选择，要非要调出一点问题，那便是符合微软产品系列的配色太丑了...不过还好不是特别在意这个

#### VIM / Neovim

![vim](https://ws3.sinaimg.cn/large/006tNbRwgy1fx3y94ub80j3074074t97.jpg)

- 地址：http://www.vim.org/ / https://github.com/neovim/neovim
- 收费：免费 (GPL compatible licence) / (Apache 2.0 license)
- 开发：Bram Moolenaar / 社区
- 支持平台：三端

提前说一下，是使用vim 8 还是neovim，有些同学非常纠结。怎么说呢，大家知道，vim是vi的颠覆者，或者说是集大成的进化体。同样，neovim的目标也是 `Neovim is an ambitious (yet careful) refactor of Vim` ，虽然现在看起来前途还很坎坷，目标还比较遥远，但总得有人来做是吧。

来现在vim用的较少，不过很多编辑修改还是vim更加方便一点。其实呢，vim可以说是One for everything了，超过1.7w 的 plugins，基本上是你想要什么，就能做什么了。vim发展了这么多年，插件配置工具又非常多，出名的包括 `Vundle`、`NeoBundle`、`VimPlug`、`Pathogen`、`dein.vim`等，一些是原有的安装方式，一些是通过github来管理版本，总之都是为了一个目的，简化用户对于插件安装对操作。如果不是重度使用者，比起自己照着教程亦步亦趋的一个个配置，我是推荐一些开包即用的vim工具包使用，免去自己维护和调试的成本。

那就是SpaceVim(https://spacevim.org/)，他自己的定义也是`Modern vim distribution`，就起表现来看，也是很到位了。底层支持vim/neovim，任君选择。安装方式

```shell
curl -sLf https://spacevim.org/install.sh | bash
```

每次启动banner都非常有爱，通过layers的概念，解耦了插件调用，预装了非常多的常用插件 (https://spacevim.org/layers/)，修改增加也非常方便，强烈推荐

![spacevim](https://ws4.sinaimg.cn/large/006tNbRwgy1fx3z4ohtuuj311y0lctcd.jpg)

## 3、效率工具

### Snap
![snap-icon](https://ws2.sinaimg.cn/large/006tNbRwgy1fx47j3k51fj3078075t8u.jpg)

配置快捷键启动软件，是我用过的最简单方便的软件，免费。作为一个6年前的软件，已经非常赞了。

- 添加软件，指定快捷键启动
- 指定快捷键 + 数字键 启动Dock App
- 免费
- 推荐度 ★★★★★

![snap](https://ws1.sinaimg.cn/large/006tNbRwgy1fx45g1zacwj30tu0sytcc.jpg)

同类产品 Manica ，不过Manica不能同时支持Dock App和自定义，只能选择其一，所以不是特别推荐。

### Xnip

![xnip](https://ws1.sinaimg.cn/large/006tNbRwgy1fx47ieo6xej306s06cwem.jpg)

快速截图工具，现在大部分聊天软件都自带了，不过还是喜欢这款，软件很小，可以不用任何技巧，截出带阴影的高逼格截图。还支持滚动截图，不过如果需要去除水印，需要升级到专业版。推荐快捷键 `Ctrl + Shift + A`

- 轻量级标注功能
- 免费
- 推荐度 ★★★★✩

同类产品还有腾讯出品的『截图』、个人生产功能与Windows严格保持一致的『Snipaste』，功能都大差不差，看自己喜好。这里说下Snipaste特殊功能，支持截图的区域Pin到屏幕任何地方，再继续截图。

### Paste

![paste-icon](https://ws1.sinaimg.cn/large/006tNbRwgy1fx47k4240dj306t06ht8t.jpg)

多端无限拷贝历史管理工具

- 收费（有试用期）
- 推荐度 ★★★✩✩

![paste](https://ws1.sinaimg.cn/large/006tNbRwgy1fx46e927v0j31kw0i7wlw.jpg)

### CheatSheet

![CheatSheet](https://ws2.sinaimg.cn/large/006tNbRwgy1fx47kurqucj306f06bjrk.jpg)

如果你时常有打开软件，又忘记一些快捷键的话，这款软件对你会十分有帮助。再使用的软件界面，长按 `⌘` ，会浮窗打开此软件所有快捷键信息

- 免费
- 推荐度 ★★★★✩

### MindNode

![MindNode](https://ws1.sinaimg.cn/large/006tNbRwgy1fx47ljvdadj306b069mxb.jpg)

脑图很方便，之前一直用 Xmind，不过之前颜值一直不太高，后来转到 MindNode 就一直没有换过，功能没有Xmind全，版本直接从2到5，还在Appstore上上架了新的软件，不过也就多了标注等功能，但是非常推荐。

- 收费（有试用期）
- 推荐度 ★★★★✩


### Recents

![MindNode](https://ws3.sinaimg.cn/large/006tNbRwgy1fx47mqzi22j306306574e.jpg)


有时候打开软件想要找到此软件最近打开了哪些项目、文件，操作需要打开软件，选择菜单栏的文件，最近开打，然后选择。这个软件让你能够一步到位，非常方便。

- 免费
- 推荐度 ★★★★✩

![recent](https://ws2.sinaimg.cn/large/006tNbRwgy1fx46so7nn5j31240pgdhj.jpg)

### Alfred
曾经的重度依赖，因为 WorkFlow 安装各种破解。后来想想也不太好，还真还不便宜，只能减少自己对 WorkFlow 的依赖，同时 Mac 自带的 Spotlight 也能逐渐满足我的需求，所以基本就脱离了。


## 4、Chrome

现在说到浏览器，肯定离不开Chrome了，这家伙除了带动所有浏览器版本都变成升级狂以外，没啥缺点了。这里列一下经常用到的插件。

- **Vimium** ：强烈推荐，如果是有使用vim基础的，用这个浏览页面简直就是6的飞起，效率非常高
- **Adblock Plus** ：大名鼎鼎的广告拦截
- **Proxy SwitchyOmega** ：不细说了，配合 Shadowsocks NG + Google Cloud + BBR 基本无敌🤩
- **Chromium Wheel Smooth Scroller** ：让你的页面滚动如丝般柔滑

今天先写到这儿吧，没有经过系统训练，写这个玩意还是很累🙃，有空了了再来更新。

