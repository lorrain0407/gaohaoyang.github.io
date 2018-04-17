---
layout: post
title:  "CGAL 64位配置"
date:   2018-04-17 15:01:12
categories: CGAL
tags: CGAL
---

* content
{:toc}

第二次配置了，然而感觉似乎并没有占到先前一年前配置过一次的优势，从第0步就很坎坷也是醉醉的，cgal官网都进不去……不过都用最新软件配置成功还是很开心的，为此觉得写一个教程很有必要，造福后人吧。

### 安装VS2015

首先是VS015的安装，迷之尴尬。下载了下图这个版本，点击vs_professional.exe，傻瓜操作，记得是自定义安装选择就好了。
![这里写图片描述](http://img.blog.csdn.net/20170818095457263?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY3V0ZWZhcml5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

![这里写图片描述](http://img.blog.csdn.net/20170818095516341?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY3V0ZWZhcml5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

![这里写图片描述](http://img.blog.csdn.net/20170818095530968?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY3V0ZWZhcml5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
安装完boost编译过了，CMake找不到编译器，特此更新了一遍就OK了，不多说（说多了都是泪啊，安装和更新都需要好久）。

下图就是相应的软件所下载和安装的位置，C盘跑起来快一些就都放这了，占着固态硬盘还有100多G也是啥都不怕了。

![这里写图片描述](http://img.blog.csdn.net/20170818095715614?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY3V0ZWZhcml5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

### 安装QT

接着安装64位QT，到QT官网上下载的qt-opensource-windows-x86-msvc2015_64-5.7.0.exe， 下载地址[https://www.qt.io/download-open-source/#section-2](https://www.qt.io/download-open-source/#section-2)。然后到微软的网站上下载了一个Qt5Package.vsix文件，下载地址：[https://visualstudiogallery.msdn.microsoft.com/c89ff880-8509-47a4-a262-e4fa07168408](https://visualstudiogallery.msdn.microsoft.com/c89ff880-8509-47a4-a262-e4fa07168408)，安装之后，在vs2015中才会有一个QT5菜项。亲身试验vs2015中Visual Studio Add-in 1.2.5 for Qt5不能使用了，并不知道为什么。安装Qt5Package.vsix后，vs2015中会有一个菜单QT5，有一个菜单荐Qt Options，点开可以add，QT的版本号和路径，可以改变或设置项目的QT版本号，还有一个QT Project Settings菜单项。配置了系统环境变量QTDIR，指向了C:\CGAL\QT\5.7\msvc2015_64，并且把C:\CGAL\Qt\5.7\msvc2015_64\bin添加到了path路径中。

### 安装boost

接着配置boost，boost官网是[http://www.boost.org/](http://www.boost.org/)，可以从官网上找到链接跳到[https://sourceforge.net/projects/boost/files/boost/1.62.0/](https://sourceforge.net/projects/boost/files/boost/1.62.0/)进行下载，我下载的是boost_1_62_0.zip。下载后解压到目录C:\CGAL\boost_1_62_0，里面有一个bootstrap.bat 文件。以管理员权限启动命令行cmd，进入到C:\CGAL\boost_1_62_0。直接运行bootstrap.bat。然后C:\CGAL\boost_1_62_0目录中，会生成b2.exe和bjam.exe， 如果直接运行b2.exe或者bjam.exe会生成根据操作系统上默认的编译器编译出boost的相关的库，应该是32位的吧。而我需要64位的，用于vs2015的，我就在命令行中接着运行bjam.exe address-model=64,其中 address-model=64保证编译的是64位的库。如果要指定编译器，比如系统上同时安装有vs2012和vs2015，想用vs2015编译库，可运行bjam.exe –toolset=msvc-14.0，如果需要编译64位的话，运行bjam.exe –toolset=msvc-14.0 address-model=64。其中参数–toolset=msvc-14.0指定使用vs2015对应的编译器，vs2013是msvc-12.0，vs2012是msvc-11.0 。这样就编译好了，生成stage/lib目录，lib目录中就是编译好的库。还需要配置环境变量，添加系统环境变量BOOST_ROOT，指向bootstrap.bat所在的目录，我的为C:\CGAL\boost_1_62_0，添加系统环境变量BOOST_LIBRARYDIR，我的为C:\CGAL\boost_1_62_0\stage\lib。

### 安装CMake

然后安装CMake，下载地址是[https://cmake.org/download/](https://cmake.org/download/)，我选择了cmake-3.7.0-rc2-win64-x64.msi，开始傻瓜操作了，注意第二步选择按下图就好了。安装完毕后确认一下系统环境变量path中有没有C:\CGAL\CMake\bin，若没有需要手动添加进去。
![这里写图片描述](http://img.blog.csdn.net/20170818095854711?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY3V0ZWZhcml5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

### 安装CGAL

接着配置CGAL，CGAL的官网站是[http://www.cgal.org/download/windows.html](http://www.cgal.org/download/windows.html)，其中有链接跳转到[https://github.com/CGAL/cgal/releases](https://github.com/CGAL/cgal/releases)，进行下载，我下载的是CGAL-4.9-Setup.exe文件，双击会让选择32bit还是64bit，我要64位的所以选择了64bit的进行安装(实际上是解压)，我使用它的默认解压路径，解压到了C:\CGAL\CGAL。建议安装在C盘，安装时注意按下图选择相关选项，其他默认就好。
![这里写图片描述](http://img.blog.csdn.net/20170818095959350?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY3V0ZWZhcml5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

安装完成后保证C:\CGAL\CGAL\auxiliary\gmp\lib在系统环境变量Path中，并添加环境变量CGAL_DIR，我的为C:\CGAL\CGAL。

### 安装libQGLViewer

接着安装libQGLViewer，下载地址是[http://libqglviewer.com/installWindows.html](http://libqglviewer.com/installWindows.html)，我选择的是libQGLViewer-2.6.4.zip。这个只有需要用CGAL的3D功能时才要装，只用2D的话可以跳过。或者可以用libQGLViewer作为QT creator的 3d绘图窗口插件。这个主要是参考官网[http://libqglviewer.com/installWindows.html](http://libqglviewer.com/installWindows.html)弄的。官网方法有很多种，我是用qt creator 直接编译的，打开C:\CGAL\libQGLViewer-2.6.4\QGLViewer里的 QGLViewer.pro 直接编译,应该就出来QGLViewer2.dll、QGLViewer2.lib（release版）和  QGLViewerd2.dll、QGLViewerd2.lib（debug版）了，将dll拷贝至系统文件夹 32位是C:\Windows\System32，64位是C:\Windows\SysWOW64，两个都拷贝一下也成。为qt creator安装designer plugin，
打开C:\CGAL\libQGLViewer-2.6.4\designerPlugin 下的 designerPlugin.pro 直接编译
将生成的qglviewerplugin.dll拷贝至QT目录下C:\CGAL\QT\5.7\msvc2015_64\plugins\designer，再将QGLViewer2.dll拷贝至C:\CGAL\QT\5.7\msvc2015_64\bin。然后配置了环境变量QGLVIEWERROOT，指向了C:\CGAL\libQGLViewer-2.6.4，并且把C:\CGAL\libQGLViewer-2.6.4\QGLViewer添加到了path路径中。

### CMake配置和运行

最后，用Cmake配置CGAL库，打开CMAKE，“Where is the source code:”栏目填CGAL的解压路径，我的是C:\CGAL\CGAL。”Where to build the binaries”栏目填要把build库等文件放在的目录，我填的是C:\CGAL\CGA\build。然后，点Configure按钮，我没遇到错误，会弹出编译器选择话框，我选的是vs2015 64位的，然后点Generate，会在C:\CGAL\CGAL\build目录下生成CGAL.sln文件。我双击用vs2015打开CGAL.sln，分别在Debug和Release模式下，点“生成”菜单下的“生成解决方案”，编译出对应的库在C:\CGAL\CGAL-4.8.1\build\lib目录下，此时需要将C:\CGAL\CGAL\build\bin添加到了path路径中。
![这里写图片描述](http://img.blog.csdn.net/20170818100126936?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY3V0ZWZhcml5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

哈哈哈，如果顺利的话你就可以按最后一步类推运行cgal里面的demo了，希望每个新手都配置顺利，Enjoy it~~~~
![这里写图片描述](http://img.blog.csdn.net/20170818100156283?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvY3V0ZWZhcml5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)