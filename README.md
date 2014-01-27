# qpython-android.pelican

Pelican for qpython-android.github.io as project


## usage
How to update the site contents

main loop:

1. git clone
1. edit some .md in `content/`
1. `fab build` for test local
1. `fab pub2hub` published all
1. git add->ci->push collection local edit 


in fact, usually just `2~4` steps

### repo. relation

- fork https://github.com/appscript/gscript.main into local
- or becamed https://gitcafe.com/appscript member hold the repo. ACL
- the sub-dir means:

        +- _plugins/
        +- _themes/
        +- content/
        |    +- Events       首字母大写的是分类目录 收集对应文章
        |    +- Volunteer    ...志愿者
        |    +- _extra       扩展功能文件 e.g robots.txt
        |    +- _files       站内文件
        |    +- _images      站内图片
        |    `- pages        类似 about 的导航栏文档
        +- output/      subRepo. 
        |               https://github.com/appscript/appscript.github.io
        +- README.md         本文
        +- fabfile.py        定制的 fab 本地部署支持脚本
        +- pelicanconf.py    Pelical 主配置
        `- publishconf.py    Pelical 发布配置


#### 文章格式

- 标准 Markdown 格式
- 以 .md 为后缀
- 文件名不得使用中文/空格/符号
- 内容模板:

    Title: 中E可以混杂的标题
    Date: 2013-12-09
    Tags: people, shanghai
    Slug: sting-chen
    Author: Zoom.Quiet

- 其中:
    - `Date:` 如果没有将使用文件的系统时间
    - `Tags:` 使用逗号作间隔, 不宜过多,建议三个为界,以人物/行为/目标领域 为方向进行定义
        - 参考: [如何规划blog的标签（tag）和分类 - 心内求法 - 博客园](http://www.cnblogs.com/holbrook/archive/2012/11/05/2755268.html)
    - `Slug:` 是实际输出的页面文件名, 建议全部小写E文, 使用中划线, 不使用特殊符号


### deploy

支持本地调试! 使用 `fabric` 进行管理, 支持的命令:

    fab 
    Available commands:

        build       编译所有页面
        pub2hub  从本地 /outpu 子仓库中 git push 网站到 gscript.github.io
        serve       启动本地服务 localhost:8000
        reserve     重编译所有页面再启动本地服务


`注意!` 向主机部署,需要有相关权限,并在本地配置好对应 SSH 信息


### design

基于 [pelican-bootstrap3](https://github.com/getpelican/pelican-themes/tree/master/pelican-bootstrap3) 深度定制

- 配置: `pelicanconf.py`
- 样式: `_themes/pelican-bootstrap3/`
- 插件: `_plugins/`


## Changelog

- 140120 @ZoomQuiet inti.
