---
layout: post
title:  "3D打印模型后处理"
date:   2018-04-18 12:21:40
categories: 3D Printing
tags: 3D_Printing Model_Coloring
---

* content
{:toc}

本周导师一个客户家6岁的儿子比较喜欢剑和铠甲，为此挑战了一把3D打印制造与后处理，主要是上色操作。映像中师兄之前给树上色，买过一些工具，很幸运，在济南到青岛的搬迁中它幸存了！

### 工具和效果展示

挑了一些我能用得到的工具，如下图：
![](https://i.loli.net/2018/04/18/5ad6ca9fdc73c.jpg)
可以说我用到的工具非常简陋，有一种补充一批材料一批工具的冲动，搞点大事情！

最后的效果图，感觉还行吧，现有工具情况下，我已经尽力!
![](https://i.loli.net/2018/04/18/5ad6cbb7ed47c.jpg)

### 3D打印模型后处理操作调研

首先我对模型后处理操作进行了调研，这个手艺主要的应用应该是手办，一个大概高20cm大小的手办，后续基本是采用人工上色，价格在5k+。

其次，采用人工上色的方法，主要步骤是打磨，上色。

打磨分为物理打磨和化学打磨两种，可以参考视频：[https://www.bilibili.com/video/av12330482/index_6.html](https://www.bilibili.com/video/av12330482/index_6.html)

常用的上色工具有马克笔，丙烯，田宫专用模型漆，软式粉彩和手摇式自动喷漆，可以参考视频：[https://www.bilibili.com/video/av12330482/index_7.html](https://www.bilibili.com/video/av12330482/index_7.html)

上色步骤和流程，可以参考视频：[https://www.bilibili.com/video/av12330482/index_8.html](https://www.bilibili.com/video/av12330482/index_8.html)。
视频中提到气泵和喷笔我是没有的，为此采用画笔涂，用画笔很容易造成上色不均匀，再者，白色的底漆也木有，难受了~

实践所得的一些经验，可以参考：[https://www.zhihu.com/question/28919308/answer/51178453](https://www.zhihu.com/question/28919308/answer/51178453)。
 - 最好是先涂上一层浅色底色打底（浅灰色或白色），再涂上主色。不过为了避免表面堆积的油漆过厚换用喷笔来喷上颜色，效果会更理想。
 - 平头笔刷在移动时应朝扁平面刷动。下笔时由左至右，保持手的稳定且均匀的力道移动，下笔时，笔刷和表面的角度约70度左右，轻轻的涂上，感觉上好象是让笔刷中的油漆轻松的流出在表面上，动作越轻笔痕会越不明显。 
 - 涂装时，应该判断什么时候再沾上油漆涂下一笔。尽量保持画笔在湿润的状态进行，含漆量保最佳湿度，才能有最均匀的笔迹。
 - 一般要等第一层要干未干的情况下再加上第二层的新鲜油漆，这样比较容易消除笔触痕迹。
 - 第二层的笔刷方向和第一层成为垂直直角，此称之为—十字交叉涂法。
 - 手涂漆时最忌讳胡乱下笔，这种方式非常容易产生难看的笔刷痕迹，并且使油漆的厚度极不均匀，速整个表面看起来是斑斑驳驳。
 - 如果碰到明显看出每笔的痕迹情形时，不要急着想要擦掉它，待其完全干燥，表面残留的油漆粒子会少点。干燥后再用一次十字交叉涂法，可把不均匀的现象降低。如果水平、垂直各涂一次后，仍呈现出颜色不均匀的现象，可以待其完全干燥后，再细水砂纸轻轻打磨掉再涂色。


实际像手办这样的精细上色步骤会更细更多一些，可以参考：[http://www.sohu.com/a/102317424_254021](http://www.sohu.com/a/102317424_254021)

除了人工上色以外还有一些别的工艺，如：浸染、电镀、喷镀等，可以参考：[http://www.3ddayinji.cn/how-to-color-3d-models/](http://www.3ddayinji.cn/how-to-color-3d-models/)

### 给3D打印模型上色是不是一个好的科研问题？？？

隐约记得浙大的周昆大佬有过这方面的工作，查了一下，是SIGGRAPH 2015的。

 - Youtube的视频链接：[https://www.youtube.com/watch?v=YlUhPrAqiY0](https://www.youtube.com/watch?v=YlUhPrAqiY0)

 - 论文链接：[http://delivery.acm.org/10.1145/2770000/2766932/a131-zhang.pdf?ip=223.80.110.111&id=2766932&acc=ACTIVE%20SERVICE&key=BF85BBA5741FDC6E%2EBA9BBD89F2E1EC6A%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35&__acm__=1524028641_518be839a7dc22a8999d75c010c43395](http://delivery.acm.org/10.1145/2770000/2766932/a131-zhang.pdf?ip=223.80.110.111&id=2766932&acc=ACTIVE%20SERVICE&key=BF85BBA5741FDC6E%2EBA9BBD89F2E1EC6A%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35&__acm__=1524028641_518be839a7dc22a8999d75c010c43395)

 - 已经申请国际专利：[https://patents.google.com/patent/US9919549B2/en](https://patents.google.com/patent/US9919549B2/en)

拜读大佬的工作之后，你有什么想法吗？？？