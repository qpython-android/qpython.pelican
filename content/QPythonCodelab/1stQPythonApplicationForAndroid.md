Title: 如何使用QPython开发Android应用
Date: 2014-07-03 10:25
Tags: howto, qpy, python, ssh, script
Slug: 1st-qpython-app-for-android
Author: River


[TOC]

## 背景

QPython可以理解为为Quick Python，它是一个脚本引擎，目前可以在应用市场里找到两个QPython, 一个为QPython，另一个为QPython3，前者为Python2核心，后者为Python3核心，在本章节里面我们重点所介绍的是支持Python2的QPython版本，不过正如Python3和Python2一样，本Codelab所介绍的方法，经过兼容性调整即可移植到QPython3上。


### 优势
相对于传统的Android Java开发过程，QPython可以提供更快捷的Python开发支持，它集成的Python解析器为Python脚本提供了一个便捷的运行环境支持，除了支持Python绝大部分系统库之外，它还支持Python世界中海量的第三方库，大部分库可以无经修改即可应用于QPython，部分C/C++等编译性语言混编的库可以通过NDK跨平台编译后应用于QPython。


除了拥有Python这个脚本引擎本身特性外，QPython还根据Android系统的特点深入扩展，实现了QRCodeReader（通过摄像头读取QRCode的代码片段），QEdit（掌上快捷Python编辑器）等功能；除此之外，QPython还扩展了对应的程序运行框架：约定了脚本和项目（可以保函多个资源的，由一个main.py作为程序入口）两种程序单元，并扩展了项目的定义，在项目的基础上定义了WebApp应用框架、GUI应用框架等。这些延伸能够极大地方便开发者在Android上灵活便捷地开发QPython应用程序。


本篇QPython Codelab通过教会大家如何使用QPython开发一个Android应用 - 《PM2.5早知道》


### 如何获得帮助
开发者在使用QPython开发时可以借助其社区和Wiki等网站，此外，也可以通过社区或者支持邮件的方式直接与其开发者沟通:
- [QPython Question](http://qpython.com/)
- [QPython Wiki](http://wiki.qpython.org/)
- 开发者支持邮箱 support@qpython.org


## 目标

在进阶之前，我们明确本项目《PM2.5早知道》的项目目标，它是一个PM2.5预报程序，它可以帮助我们知道我们所在地点的PM2.5情况，为出行防护做准备。

我们将使用QPython的WebApp应用框架开发，这样只需要掌握Web开发以及Python开发技能即可顺利实现目标。

![PM2.5早知道 - 设计](https://raw.githubusercontent.com/qpython-android/qpython-android.pelican/master/content/QPythonCodelab/assets/pm2.5.png)



## 进阶

在真正启动之前，确定你基本满足以下列表展示的配置

基础配置
-----
### 码农一枚
程序猿，懂得一点Python开发和Web开发想必是极好的。（如果你不懂也没关系，学完就懂）

- Python,JAVA,C,C++,HTML,JS,CSS 少量经验
- 精通A-Z 26字母, 熟练Cnglish 


### 能正常安装QPython的Android手机

手机: 电信协议 三星 Note2 N7108ZMDMF1:

- Android 4.1.1 JRO03C
- 刷的是 MIUI-3.3.15 野生版
- CPU 四核 1.6GHz
- 内存 2G
- 存储 16G

### 开发主机（手机键盘操作神人可省略）
Web程序员的程序开发环境也可以说是必需的，当然如果你是手机键盘操作神人，可以用手机用发短信的小手把程序开发出来，可省略该设备同时接受大家的膜拜

本人主要使用 MBP 12下半年版 
- OS X 10.9.1
- Core i7 2.2GHz
- 8G 内存
- 500G 机械硬盘


QPython入门
-------
QPython WebApp应用框架能够让具有Web开发背景的开发者快速构建Android本地应用。作为开发者，充分掌握你手中的利器，才能做到庖丁解牛，游刃有余地推动项目，接下来，你只需要30分钟，即可掌握QPython以及WebApp应用框架。

### QPython的使用
QPython是我们项目的运行容器，我们所开发的项目需要运行在QPython之上（当然QPython也提供其他不同定位的程序开发支持，可以在以后的Codelab教程中逐一展示），因此你需要掌握以下使用技巧:

- 了解QPython的基本功能，能使用开始按钮以及开发者工具面板
- 你需要知道如何把项目上传或更新到QPython中
- 你需要掌握如何使用QPython运行项目
- 程序运行出错，如何查看错误信息，这个是作为开发者必备的技能
- 有些小的改动，比起上传或者更新整个项目而言，使用自带的QEdit方便第修改源代码可能会更简单
- 如果你想使用第三方库，你需要知道如何使用QPython来安装第三方库


更多详情可以参考[如何使用QPython](http://wiki.qpython.org/doc/how-to-start/)，以及[如何使用QPython开发第一个HelloWorld](http://wiki.qpython.org/doc/hello-world/)

### QPython的WebApp框架
为了让Web开发者能够快速上手Android应用开发，QPython推出了WebApp框架，它包括两个部分
- 基于Bottle框架的可定制本地Web服务器
- 构建于Android系统的WebView容器，

实现上述两个特性，就我们能够轻松地让QPython运行本地WebApp，避免传统服务端WebApp的网络传输瓶颈问题，获得更佳用户体验，此外，通过让Python能作为Backend语言，拥有更强大的包括网络、图像、运算等多种处理能力。再加上强大的Python第三方库支撑，拥有Python/Web开发经验的人即可轻松开发体验良好的WebApp

更多详情可以参考[QPython WebApp帮助](http://wiki.qpython.org/dev/webapp_sample/)


应用设计
---------
掌握了QPython基础使用以及其WebApp框架后，我们可以开始针对我们的项目目标设计应用系统


### 应用的使用流程分析
- 输入：输入部分及为根据用户地理位置
- 输出：用户所在城市的PM2.5数值以及对应的防护措施建议
- 业务处理：通过地理位置坐标获得所在城市，通过请求PM2.5接口数据源获得PM2.5数值，再根据等级区分展示对应的防护措施建议


### 关键数据来源
- 地理位置信息：通过QPython的SL4A接口可轻易获得
- 根据地理位置查询所在城市
- PM2.5数据来源：根据PM2.5API可以查询到所在城市的PM2.5数值情况

了解QPython的地理位置的[SL4A接口](http://wiki.qpython.org/sl4a/)，掌握[PM2.5的数据来源接口](http://pm25.in/api_doc)，[Google的根据地理坐标查询所在城市](http://code.google.com/intl/zh-CN/apis/maps/documentation/geocoding/)

### 应用的交互设计
- 主要为根据不同的PM2.5展示做不同的预警展示，并能满足用户查看详情的需求
- 技术实现方面我们选定使用Bootstrap作为前端框架：Bootstrap能根据设备的宽度的不同提供适配的界面框架。


## 推进过程以及FAQ
### 如何开始
- 在开发机器上安装bootstrap, bottle，象Web开发一样去开发, 本地调试后
- 以上传到QPython运行目录/sdcard/com.hipipal.qpyplus/projects/<ProjectDir>
- 通过QPython的运行按钮运行查看效果

将在个人电脑上开发的项目上传到手机上有以下方法
- 启动QPython自带的FTP服务：在设置中可以看到FTP服务，开启FTP服务后会显示当前侦听的地址、端口以及帐号，你可以通过FTP客户端将项目目录上传到QPython运行目录
- 如果你的电脑安装了Android开发套件，你也可以连接手机到开发机后，执行 adb push <本地目录> /sdcard/com.hipipal.qpyplus/projects/PM2.5 来把项目上传到QPython的项目目录

### 用Web开发模式开发QPython WebApp
我们可以使用标准的本地Web开发流程去推进应用开发，左侧为浏览器， 中间为VIM窗口，右侧我们启动bottle开发的Web进程（QPython内建支持Bootle Web框架）

在你的开发机上下载Bootstrap, 并配置Python+bottle运行环境，按照QPython WebApp的规范建立项目目录


获得[Bootstrap](http://getbootstrap.com)，获得[Bottle](http://bottlepy.org)

[了解QPython中WebApp中文件的结构](http://wiki.qpython.org/dev/webapp_sample/)

![本地Web开发](https://raw.githubusercontent.com/qpython-android/qpython-android.pelican/master/content/QPythonCodelab/assets/develop_with_pc.png)

### 上传到QPython运行
- 你可以将项目上传到手机的QPython项目目录
- 点击开始按钮即可看到PM2.5选项
- 启动后可以看到运行效果

![QPython运行WebApp - 1](https://raw.githubusercontent.com/qpython-android/qpython-android.pelican/master/content/QPythonCodelab/assets/run_project.png)
![QPython运行WebApp - 2](https://raw.githubusercontent.com/qpython-android/qpython-android.pelican/master/content/QPythonCodelab/assets/pm25_index_debug.png)

### 如何使用全屏幕模式
如果应用的入口文件main.py文件中没有#qpy:fullscreen，则应用默认会具备QPython的导航，如果想要WebView组件按照全屏模式运行，则在main.py中增加#qpy:fullscreen即可


![使用默认编辑器快捷修改源文件](https://raw.githubusercontent.com/qpython-android/qpython-android.pelican/master/content/QPythonCodelab/assets/add_fullscreen.png)
![QPython全屏运行WebApp](https://raw.githubusercontent.com/qpython-android/qpython-android.pelican/master/content/QPythonCodelab/assets/pm25_index_fullscreen.png)


UI开发
---------
我们能在UI开发过程实现界面流程，结合模拟数据，展示了应用业务。以下截图分别是在开发机上WEB浏览器中运行的截图和在Android手机中用QPython运行的截图。

![PM2.5早知道 - 运行在浏览器中](https://raw.githubusercontent.com/qpython-android/qpython-android.pelican/master/content/QPythonCodelab/assets/pm2.5_web.png)
![PM2.5早知道 - 运行在QPython之中](https://raw.githubusercontent.com/qpython-android/qpython-android.pelican/master/content/QPythonCodelab/assets/pm2.5_mobile.png)

功能开发
---------
在UI开发的基础上进行能攻开发，即可得到我们最终的版本，下列为几个关键过程的参考代码：
### 获得地理坐标

    Droid = androidhelper.Android()
    location = Droid.getLastKnownLocation().result
    location = location.get('network', location.get('gps'))

### 获得所在城市示范代码
    ud  = urllib.urlopen('http://maps.google.com/maps/api/geocode/json?latlng=%s&sensor=true' % location)
    json_result = ud.read()
    ud.close()
    """ process json_result """

### 获得所在城市PM2.5
    ud = urllib.urlopen('http://www.pm25.in/api/querys/pm2_5.json?city=%s&token=%s' % (city, token))
    json_result = ud.read()
    ud.close()
    """ process json_result """

### 根据PM2.5数值给出建议
    if pm25_quality == '优':
        ...
    elif pm25_quality == '良好':
        ...
    elif pm25_quality == '不好':
        ...
    elif pm25_quality == '差劲':
        ...
    else:
        ...


将关键代码实现后输出即可实现我们本次的目标


你可以获得[PM2.5早知道项目源代码源代码](https://github.com/qpython-android/SourceCodelab.PM25)

此外，你还想增加什么功能？天气预报, PM2.5变化趋势图以及预测 ？Just do IT !


增加快捷链接
---------
开发项目完成后，是否希望在你的手机上有快速启动的入口，而不需要经过层层点击才能启动？
最简单的方法是你可以在我的QPython浏览界面中，长按该项目图表，则能够在Android桌面创建一个快捷链接。


![长按创建快捷连接](https://raw.githubusercontent.com/qpython-android/qpython-android.pelican/master/content/QPythonCodelab/assets/add_shortcut.png)
![成功创建快捷连接](https://raw.githubusercontent.com/qpython-android/qpython-android.pelican/master/content/QPythonCodelab/assets/shortcut_created.png)


此外，如果你想设置其为QPython启动按钮首选启动的应用程序而不显示当前的启动菜单，你可以在设置中，通过设置默认程序为你开发的程序即可完成。


发布
----
应用开发出来了，不发布出去让大家爽爽？目前QPython的程序发布有以下途径

除了原始但是好用的的手工copy方式之外，你还可以通过QPython的方式

### 自己实现安装程序，通过QRCode的方式分发
你可以自定义安装程序，然后生成QRCode，让其他人扫描QRCode并运行的方式安装上你的App。

[使用QRCode工具声称QRCode代码](http://qpython.com/create.php)，然后将QRCode图片另存到本地再发布

### 自定义安装包，使用QPython的安装接口，对外分发
QPython的market提供了几个Javascript函数定义，你能够方便地在自己的网页中调用，让使用QPython内嵌浏览器访问这些页面中可以方便地安装上.

参考[怎样调用Javascript来安装第三方Package](http://wiki.qpython.org/hacker/pypi_js/)

### 可以Build独立的Native应用发布到Google Play么
目前官方暂时还不支持该方式，但官方团队已经将释出QPySDK其放入其接下来的发展计划

### 发布到QPython商店
目前官方暂时还不支持该方式，是否推出官方QPython商店尚未有明确计划



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
