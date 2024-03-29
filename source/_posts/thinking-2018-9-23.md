---
title: 操作系统——关于新的思考和新的目标
date: 2018-09-23 17:38:00

tags:
- Operating System
categories: 
- Computer Science
- Operating System
---



{% note default %}
计算机操作系统是最复杂的软件之一。
{% endnote %}

<!-- more -->

### 2018年9月23日的思考——新的目标

> 先来说一下为什么懒散的我很长时间没有动博客今日却心血来潮。此刻我电脑上有一个进程正在下载着`i386`的ubuntu镜像，今天的主题和这个镜像有关，它只是一个开发环境。开发什么呢，或者说这仅仅是一个实验，来自`MIT`操作系统的实验，这只是听某位学长偶然提及的。没错，核心主题就是**操作系统**，这个实验的训练价值确实有一定可取性，但学长更为推荐的是一本书：`《linux内核完全剖析》`，如果你有操作系统方面的研究兴趣的话可以借鉴一下。我认为操作系统的研究价值有二：其一是知识价值，计算机最基础的知识之一。其二如下。


#### 为什么是操作系统

> 在暑假以及开学的2周里，我把操作系统的知识点回顾了一遍。也看了一部分`linux0.11`的源码，虽然至今仍未进入其`main`函数。

为什么是操作系统？我认为操作系统是软件或者计算机硬件之上最重要的一部分。或许你认为当前最火的计算机技术有很多，比如说人工智能、大数据分析、云计算等等。没错，对于人工智能来说，如果你仅停留在如何调用`TensorFlow API`的层面上，那和普通咸鱼有什么区别。当然如果你能够解析内部实现原理，比如各种神经网路、误差缩减方法实现，而且能够进一步优化或者设计一种新的方法，那才是真正的工程师。将所有的开发技术抽象而言，都是工具。我认为对于这一方面有三个层次：使用工具，改造工具，创造工具。使用工具的人是普通咸鱼，能够改造工具的人是高级咸鱼，能够创造工具的才能称之为工程师。话说回来，为什么是操作系统？

这只是一个猜想：

操作系统存在于哪？存在于终端之上————电脑、手机、智能手表等等，常见的也就这几种。但是以后会有什么其他类型的终端？眼睛框上有个终端？加上增强现实，就像科幻电影里那样。项链上有个终端？戒指上有个终端？而且对于不同的终端有不尽相同的操作系统，这就是操作系统与终端的搭配。

#### 操作系统需要什么

> 操作系统是干什么的？用于管理硬件的软件。需要的就是如何管理硬件，如何有效的利用好各个硬件。如何更有效率的使用好CPU——CPU管理，有效率的使用好内存——内存管理，有效率的使用好外设——外设管理，更好的让用户操作——文件管理。

计算机至少需要一个处理器、一个存储设备、一个输入设备和一个输出设备。最基础的就是管理这些东西而已。