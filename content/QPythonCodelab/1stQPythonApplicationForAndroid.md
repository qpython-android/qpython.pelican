Title: 如何使用QPython开发Android应用
Date: 2014-01-26 12:42
Tags: howto, qpy, python, ssh, script
Slug: 1st-qpython-app-for-android
Author: River


[TOC]

## 背景

QPython可以理解为为Quick Python，它是一个脚本引擎，目前可以在应用市场里找到两个QPython, 一个为QPython，另一个为QPython3，前者为Python2核心，后者为Python3核心，在本章节里面我们重点所介绍的是支持Python2的QPython版本，不过正如Python3和Python2一样，本Codelab所介绍的方法，可以简单修改即可移植到QPython3上。


相对于传统的Android Java开发过程，QPython可以提供更快捷的Python开发支持，它集成的Python解析器为Python脚本提供了一个便捷的运行环境支持，除了支持Python绝大部分系统库之外，它还支持Python世界中海量的第三方库，大部分库可以无经修改即可应用于QPython，部分C/C++等编译性语言混编的库可以通过NDK跨平台编译后应用于QPython。


除了拥有Python这个脚本引擎本身特性外，QPython还根据Android系统的特点深入扩展，实现了QRCodeReader（通过摄像头读取QRCode的代码片段），QEdit（掌上快捷Python编辑器）等功能；除此之外，QPython还扩展了对应的程序运行框架：约定了脚本和项目（可以保函多个资源的，由一个main.py作为程序入口）两种程序单元，并扩展了项目的定义，在项目的基础上定义了WebApp应用框架、GUI应用框架等。这些延伸能够极大地方便开发者在Android上灵活便捷地开发QPython应用程序。


我们相信，集成并发扬了Python脚本语言的优良传统后，QPython在Android开发者的世界中占有一席之地，帮助光大爱好者快速开发，早日收获Android开发的成就感。 本篇QPython Codelab通过教会大家如何使用QPython开发一个Android应用。这个项目叫做《PM2.5早知道》


QPython仍属于初创期，在编写时很多问题可以参考其社区和Wiki等网站，此外，也可以通过社区或者支持邮件的方式直接与其开发者沟通:
- [QPython Question](http://qpython.com/)
- [QPython Wiki](http://wiki.qpython.org/)
- 开发者支持邮箱 support@qpython.org


## 目标

在进阶之前，我们确定今天要达成的目标，即《PM2.5早知道》项目，它是一个PM2.5预报程序，它可以帮助我们知道我们所在地点的PM2.5情况，为出行防护做准备。

我们将使用QPython的WebApp应用框架开发，这样只需要掌握Web开发以及Python开发技能即可顺利实现目标。



## 进阶

在真正启动之前，展示以下所需的配套环境


环境准入
-------

## 湿件及技术背景
30+岁老程序猿，懂得一点Python开发和Web开发想必是极好的。如果你不懂也没关系，学完就懂

- Python,JAVA,C,C++,HTML,JS,CSS 少量经验
- 精通A-Z 26字母, 熟练Cnglish 


## 硬件
### 能正常安装QPython的Android手机

手机: 电信协议 三星 Note2 N7108ZMDMF1:

- Android 4.1.1 JRO03C
- 刷的是 MIUI-3.3.15 野生版
- CPU 四核 1.6GHz
- 内存 2G
- 存储 16G

### 主机: MBP 12下半年版 
Web程序员的程序开发环境也可以说是必需的，当然如果你是神人，可以用手机用发短信的小手把程序开发出来，那就必需接受大家的膜拜

- OS X 10.9.1
- Core i7 2.2GHz
- 8G 内存
- 500G 机械硬盘


QPython入门
-------
作为架构师，你需要掌握你手中的利器，才能做到庖丁解牛，接下来，你只需要30分钟，即可了解QPython WebApp应用框架


QPython WebApp应用框架
-----
### QPython的使用
掌握QPython的使用，弄明白怎么开发程序并上传

### QPython的WebApp框架
掌握QPython WebApp框架


应用设计
---------
完成了对QPython的掌握之后，开始实现应用程序设计


### 应用的使用流程分析


### 关键数据来源


### 应用的界面设计


## 推进过程以及FAQ

我们采取小版本迭代，小步推进的方式推进该项目，

Demo 版本
---------
Demo 版本实现了界面流程，使用模拟数据，使得应用业务逻辑可行


Final 版本
---------
在Demo 版本的基础加入真数据，并对一些细节进行适配调整，即可得到Final版本


设置为启动QPython及进入或者增加快捷链接
---------
开发完成后，希望其有快速启动的入口，而不需要经过层层点击才能启动。
最简单的方法是你可以在我的QPython浏览界面中，长按该项目图表，则能够在Android桌面创建一个快捷链接。
此外，如果你想设置其为QPython启动按钮首选启动的应用程序而不显示当前的启动菜单，你可以在设置中，通过设置默认程序为你开发的程序即可完成。


发布
----
都开发出来了，不发布出去让大家爽爽？目前QPython的程序发布有以下途径

除了原始但是好用的的手工copy方式之外，你还可以通过QPython的方式

### 自己实现安装程序，通过QRCode的方式分发
你可以自定义安装程序，然后生成QRCode，让其他人扫描QRCode并运行的方式安装上你的App。

### 自定义安装包，使用QPython的安装接口，对外分发
QPython的market提供了几个Javascript函数定义，你能够方便地在自己的网页中调用，让使用QPython内嵌浏览器访问这些页面中可以方便地安装上.

### 尚不支持的发布到QPython商店
目前官方暂时还不支持该方式


## 总结

让人惊喜的特性
----
+ 开发确实很简单，很快
+ 分发过程很有意思


时间帐单:
----

简单回顾一下整个从完全小白到折腾出当前扫盲文章的时间投入:

+ NH: 经ZQ大妈忽悠许久，实在推托不了了，于是开始酝酿该文章
+ 1H: 所有相关资料收集,概览
+ 4H: 整理为文章

## Changelog

- 140626 River 创建
