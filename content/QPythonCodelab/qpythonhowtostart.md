Title: QPython - 如何开始
Date: 2014-08-08 10:25
Tags: howto, qpython, start
Slug: qpython-howto-start
Author: River


[TOC]

## 背景

QPython可以理解为为Quick Python,它是一个脚本引擎,目前可以在应用市场里找到两个QPython, 一个为QPython,另一个为QPython3,前者为Python2核心,后者为Python3核心,在本章节里面我们重点所介绍的是支持Python2的QPython版本. 本文重点介绍如何使用QPython. 


## A. 面板

在你已经安装了QPython之后,你可以像运行其他Android程序那样运行它,附件的截图 - A-1 是它启动后默认的样子. 

### 开始按钮

点了印有QPython logo的启动按钮之后,出现了菜单让你选择接下来的步骤:
- 读取包含有Python代码的QRCode图片(这是一种有趣的分发QPython代码的方式,此外你可以在[QPython的QRCode生成器](qpython.com/create.php)中贴入代码并生成QRCode图片)
- 运行手机上的脚本
- 运行手机上的QPython项目


在大于0.9.8的版本中，现在你可以通过运行pip_console来安装很多第三方库（主要是纯python代码实现的库）。

如果你希望点击开始按钮运行特定的程序，你可以在设置项目中设置Python脚本或项目作为默认的运行程序来实现。

### 开发者套件面板

如果你在启动后的界面向左滑动手指，你可以看到另一个主要界面，它是专为开发者设计的。

它包括以下工具：
- 控制台：没错，它就是你常用的Python控制台，让你方便地直接与解释器进行交互
- 编辑器：QPython有一个不错的文本编辑器，你可以在里面编写和运行Python代码
- 我的QPython：你能在这里找到你的脚本和项目
- 系统：管理库和组件，安装和卸载它们
- 包列表：在浏览器中打开QPyPi，你可以在这里安装一些包
- 社区：导向QPython问答社区，注册后你就可以提问或者回答问题

在开发者面板长按着控制台和编辑器，你可以在桌面上分别创建它们的快捷方式。

现在，让我们来看一看控制台和编辑器。

## B. 控制台和编辑器

### 控制台

就像我前面所说的，它包含了一个普通的Python控制台。许多人通常使用它来探索对象的属性，参考语法和测试他们的想法。你能直接输入命令，Python解析器将会执行他们，你可以通过点加按钮来打开更多的控制台，你也可以通过点击下拉菜单列表项目右侧的关闭图标来关闭所对应的控制台。


请注意，除非你已经关闭了控制台，否则消息栏目里总会出现控制台提示，点击提示能让你直达已开启的控制台。

### 编辑器

编辑器允许你直接输入和修改文字。这里你可以开发你的脚本，保存和执行。编辑器支持Python语法高亮并且显示行号。

在输入时，你可以使用工具栏目的两个按钮轻松地控制锁进层次。接下来的按钮是保存和另存，然后是运行，撤销、搜索、最近打开的文件和设置按钮。在上面，这里有两个按钮打开和新建。

在保存时，不要忘记添加.py后缀，因为编辑器不会自动为你添加。

## C. 我的QPython

你可以在我的QPython中找到脚本或项目。

在我的QPython中长按脚本或者项目，你可以在桌面创建对应项目的快捷方式，创建了快捷方式之后，你可以直接从桌面运行脚本或项目。

### 脚本

脚本：每个脚本都是一个独立的可执行的文件，它们位于 /sdcard/com.hipipal.qpyplus/scripts ，如果你创建了新的脚本，请放置于这个目录以便QPython能够将其纳入scripts分类。

当你在我的QPython中点击了一个脚本时，你可以选择：
- 运行：运行这个脚本
- 打开：使用内嵌的编辑器编辑脚本
- 重命名：重命名脚本
- 删除：删除脚本

### 项目

项目是一个包含了main.py作为默认启动脚本的文件夹，你能够把其他依赖的库和相关资源放置在其中，项目都位于 /sdcard/com.hipipal.qpyplus/projects 目录下，如果你创建了新项目，请将它放置于相同的目录下以便QPython能够将其纳入projects分类。

当你在我的QPython中点击了一个项目时，你可以选择：
- 运行：运行这个项目
- 打开：打开这个项目
- 重命名：重命名项目（修改项目文件夹名称）
- 删除：删除项目（从sdcard中删除）


## D. 系统

在系统中你可以管理已经安装的库和组件，系统模块包含了你已经安装的Python库。此外，你还可以在系统中安装一些全局库，你可能无法在Packages Index中找到它们，比如_ssl, _csv等模块。

### 库

库的部分包含了全局库和上面提到的已经安装的库。点击它们时你可以查看详情，此外你也可以删除它。

通常，库可能会被安装到下下列路径：

/sdcard/com.hipipal.qpyplus/lib/python2.7/site-packages （纯Python库通常会被安装到这里，如果你希望手工安装一些库，也可以将它们放置于该目录）和

/data/com.hipipal.qpyplus/files/lib/python2.7/site-packages/ ( 混合c或者c++实现的以.so为后缀的库通常会被安装到这里，此外如果你使用了pip_console.py安装的库，也有一些会被安装到这个目录下）

### 怎么安装第三方库

正如上文所提到，如果你想简单地安装第三方纯Python实现的库，你可以简单地将它们拷贝到第一个路径下。

如果你想安装混合c/c++编程的库，你首先在Android的NDK交叉编译环境中编译它们（这个比较有挑战和难度），然后，你可以
- 拷贝到 /sdcard/com.hipipal.qpyplus/lib/python2.7/site-packages 中试试，如果它工作了，那就非常幸运了，你就可以忽略其他步骤了
- 如果第一步实现后无法正常工作，你需要通过创建一个QPython组件的方式来将它们安装到手机的内置存储空间。
- 其他步骤待续

### 组件

一个组件可以包含需要放置到不同存储区域（sdcard和内置存储）的库，比如说PIP组件，它包含有pip命令行工具，它需要被安装到 /data/data/com.hipipal.qpyplus/files/bin 目录，然后pip相关的库，需要被安装到 /data/data/com.hipipal.qpyplus/lib/python2.7/site-packages/ 目录：

默认情况下你无法直接操作手机的内置存储空间，因此你不能简单地拷贝库到这些地方，这样你就需要：
- 根据QPython组件的打包协议来创建好一个QPython组件，-
- 将它放到 /sdcard/com.hipipal.qpyplus/lib 目录中
- 在QPython的系统＝》组件中使用安装将其安装到设备上

组件功能如此强大以至于你能够替换QPython的Python核心。

## E. 包列表

该模块尚未特别完善，我们正在努力完善它。

你能够通过包列表来安装许多库，它也包含详细的开发介绍，目前它包含4个分类。你可以通过安装各种库来扩展QPython。

### 使用WebApp快速开发App

QPython内建的Bottle库能让你快速开发WebApp，使用Web的开发模式快速实现自己需要的体验优异的App, 是不是很酷？

### 使用SL4A的Android特性脚本开发

这个类别包含了对于Android特性开发的支持，你可以使用Python去访问GPS、媒体播放器、重力感应、蓝牙等有趣的特性

### 使用Django开发复杂的本地Web应用

借助于强大的Django，你可以快速实现各种复杂的本地Web应用

### 使用Kivy开发GUI程序

如果你想使用QPython开发游戏，你可以从这里获得大量的帮助

## F. 社区

QPython的社区一直在持续建设中，欢迎你尽快加入，在帮助他人的同时也获得成长。

- QPython问答社区：http://qpython.org
- QPythonSegmentfault：http://segmentfault.com/t/qpython （中文问答社区）
- QPythonFacebook：http://www.facebook.com/qpython
- QPythonTwitter：http://twitter.com/qpython
- QPythonWeibo：http://weibo.com/qpython
- QPythonWeixin：qpython

你可以从社区中获得真人帮助。QPython社区中都是热心的人，所有的问题都会被分享和回答（如果它们清楚），此外我们鼓励你去自己动手，探索和分享有趣的Python程序世界。

... 待续
