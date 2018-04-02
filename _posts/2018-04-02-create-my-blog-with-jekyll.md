---
layout: post
title:  "Jekyll 搭建 Github Pages 博客"
date:   2018-04-02 14:11:04
categories: jekyll
tags: jekyll RubyGems Github_Pages
---

* content
{:toc}

一直以来觉得在各大博客平台或者笔记上写一些东西总是零零散散，对于一个账号密码记不住的人来说，写了等于没写，莫名心塞。。。无意发现在github上用jekyll可以搭建博客就小试了一把，体验不错，搭建过程就作为第一篇blog吧。


## 搭建过程

我用的是Windows系统，读了[jekyll官网的安装教程](https://jekyllrb.com/docs/installation/)，其实环境配置还是比较简单的呢！
主要步骤有：安装Ruby，安装RubyGems，安装jekyll。

### 安装Ruby

ruby有专门的[windows官网](https://rubyinstaller.org/downloads/)，下载安装Ruby+Devkit即可。

安装完成后配置环境变量，在命令提示符中，输入   ruby -v

得到ruby版本号即安装成功。


### 安装RubyGems

[RubyGems官网下载](http://rubygems.org/pages/download) zip即可，解压。

cd到RubyGems目录   

执行安装   ruby setup.rb


### 用RubyGems安装Jekyll

执行下面的语句进行安装    gem install jekyll   


### 创建博客

发现[HyG](https://gaohaoyang.github.io/)的博客风格简洁大方，所以在github上fork了他。

fork成功后进入settings进行设置修改仓库名为 你的Github账号名.github.io，然后 Rename；

接着修改博客配置：来到你的仓库，找到_config.yml文件，这是网站的全局配置文件，点击修改，然后编辑_config.yml的内容。

这一步参考[这个](https://www.jianshu.com/p/e68fba58f75c#Rename)中对_config.yml的介绍，可以尝试评论系统和网站统计。

修改完成后点击Commit changes 提交保存。

最后进入你的主页，你的个人博客搭建就完成了。


### 后续

这只是完全fork之后的版本，之后如果有不满意的地方还是会进行改进的呢！