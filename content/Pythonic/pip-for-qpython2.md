Title: 如何自在的折腾QPy
Date: 2014-05-28 17:58
Tags: howto, qpy, Pythonic, pip, 
Slug: pip-for-qpython2
Author: River

[TOP]

## 背景

QPython2 尚不支持pip, 要安装很多包都很麻烦，这个问题困扰了很多用户，于是在炎热的酷暑5月底，开始倒腾QPython2上的pip


## 过程

pip 体系依赖于distutils, setuptools 等诸多Python package, 要想成功地在QPython2上跑起，首先需要解决这些问题, 所幸pip整个体系都是使用pure Python实现，因此这一步骤就比较简单。

解决了上述问题之后，面临的一个小难题是路径的问题, 作为非官方得Python for Android, 我们需要在pip以及其依赖的packages中加入相关的路径处理即可。

完成了上述工作之后，接下来面临的问题是setuptools/distutils 安装packages时对于系统的依赖，比如执行chmod在android系统的实现就与普通的linux不一样。

主要完成了上述过程之后，就剩下优化问题了，如果需要考虑体积大小，则考虑加入PYTHONDONTWRITEBYTECODE环境变量忽略.pyc或者pyo

最后, 请读者耐心等待0.9.8版本的发布吧，能让你瞬间拥有强大的Python世界的Packages资源

