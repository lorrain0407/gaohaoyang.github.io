---
layout: post
title:  "GitBook使用"
date:   2018-04-03 11:00:32
categories: gitbook
tags: gitbook point_to_offer
---

* content
{:toc}

试图回想一周前刷的题，好像有些忘了。一个个在网站上找出来回忆需要点击很多次，可谓非常麻烦。之前是有一些笔记的，但总觉得不够系统不够清晰，发现gitbook这样好用的东西，就想试试。

效果：[ https://liulin1.gitbooks.io/gitbook-point_to_offer-solutions/content/]( https://liulin1.gitbooks.io/gitbook-point_to_offer-solutions/content/)

Github：[https://github.com/lorrain0407/gitbook-point_to_offer-solutions](https://github.com/lorrain0407/gitbook-point_to_offer-solutions)



## 配置过程

我用的是Windows系统，读了[gitbook官网的安装教程](https://github.com/GitbookIO/gitbook/blob/master/docs/setup.md)，其实还蛮简单的呢！
主要有以下几步：

### 安装nodejs

[nodejs官网](https://nodejs.org/en/)，下载安装即可。

安装完成后检查环境变量，在命令提示符中，输入   node -v

得到node版本号即安装成功。（设置新的环境变量后要重启呢！）

### 用npm安装gitbook

输入以下命令，全局安装gitbook。

```shell
$ npm install gitbook-cli -g
```

### 创建gitbook

选择一个目录，新建文件夹，cd进入到该文件夹目录下，输入如下命令：

```shell
$ gitbook init
$ gitbook build
$ gitbook serve
```

1)gitbook serve 之后可以在本地输入http://127.0.0.1:'端口号'/ 浏览

## 设置gitbook样式

你可以通过一些[插件](https://plugins.gitbook.com/plugin/prism)等，增加搜索功能或者修改其中的CSS/JS文件来设置喜欢的样式，甚至还可以[自定义](https://help.gitbook.com/content/how-can-i-include-css.html)呢~

参考：[https://blog.lszero.com/coding4fun/algorithm/gitbook-for-leetcode-solutions.html](https://blog.lszero.com/coding4fun/algorithm/gitbook-for-leetcode-solutions.html)

## GitBook.com的托管使用 与 gitbook编辑器

参考：[http://www.chengweiyang.cn/gitbook/gitbook.com/newbook.html](http://www.chengweiyang.cn/gitbook/gitbook.com/newbook.html)

登陆[GitBook.com](https://www.gitbook.com) 后，在用户页面，可以管理现有书籍以及创建新的书籍。

我创建书籍时选择了github，这样只需将之前的gitbook push到github的仓库中，再绑定到gitbook就可以了。

之后直接使用文本编辑器，编写Markdown文档，然后，使用Git提交到书籍的远程项目，当然，提交前，最好在本地使用gitbook预览效果；提交后，GitBook.com会自动生成更新书籍的内容。

我试了[gitbook编辑器](https://www.gitbook.com/editor)，感觉对git不友好，还是放弃了。建议大家直接写Markdown文档就OK。

###后续 

一心刷题，并总结。加油！