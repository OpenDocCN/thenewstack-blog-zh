# BalenaOS 如何在太空中运行第一个码头集装箱

> 原文：<https://thenewstack.io/how-balenaos-ran-the-first-docker-containers-in-space/>

六月的一个早晨，凌晨 4 点 21 分，一枚 2700 公斤(约 6000 磅)的火箭在瑞典发射，它携带了超过 272 公斤的科学实验。它庄严地升向 300 多公里(148 英里)的天空，然后完美地返回地球。着陆后，直升机成功回收了科学实验，并送回进行进一步分析。

一项实验涉及一个树莓 Pi Zero，一个 1GHz ARM11 内核的 5 美元小主板，以及一个容器引擎。“据我们所知，这是第一次将莫比/码头集装箱发动机飞向太空！”著名的物联网软件供应商 [Balena](https://www.balena.io/) 在[的博客文章](https://www.balena.io/blog/beyond-the-cloud-docker-containers-in-space/)中补充说，它的操作系统 [BelanaOS](https://www.balena.io/os/) 被选中运行 Docker 容器。

看到今天的太空研究人员很好地利用我们所有的技术——甚至是简陋的现成部件[——同时将它们与最先进的火箭科学、操作系统和强大的传感器相结合，令人兴奋。这是一种尝试新方向的方式，无论是探索太空还是我们使用的材料。虽然提供了一些关于未来可能会是什么样子的鼓舞人心的暗示，但它也给了我们一些已经在使用的技术一个令人惊讶的新视角。](/tag/Off-The-Shelf-Hacker)

[https://www.youtube.com/embed/JlcReUwZXFU?feature=oembed](https://www.youtube.com/embed/JlcReUwZXFU?feature=oembed)

视频

## 实验的起源

其中一名实验者是 Nico Maas，他是一名“IT 系统电子人”，是欧洲航天局“哥伦布”模块(2008 年发射到国际空间站)的地面控制员。

马斯的[网页](https://www.nico-maas.de/?page_id=2)报道称，他在德国航空航天中心(DLR Cologne)的微重力用户支持中心工作，该小组负责在不同的重力挑战环境中准备和操作实验，包括在国际空间站上的实验[，提供失重时刻的](https://www.dlr.de/rb/en/desktopdefault.aspx/tabid-4537/)[“抛物线”飞行](https://www.dlr.de/rb/en/desktopdefault.aspx/tabid-4536/7433_read-11192/)，甚至在火星上进行的[摩尔温度传感器实验](https://www.dlr.de/blogs/en/all-blog-posts/The-InSight-mission-logbook.aspx)。

MUSC [操作](https://www.dlr.de/rb/en/desktopdefault.aspx/tabid-4535/)用于太空科学利用的主要设备，包括用于材料科学、生物学和地外科学技术的设备。“太空集装箱实验就是从那里开始的。10 月，AIP 科学仪器评论发表了一篇由 Maas 合著的新论文，解释了 MUSC 的目标是为研究火箭测试“一个新的商业现成的机载计算机平台”。

> 对于这个实验，不同的应用程序在不同的容器中运行，因此一个应用程序的崩溃或故障将被隔离，不会影响其他应用程序，

这不是第一次流行的微控制器板飞向太空。论文还引用了 ARDUSAT ，这是一颗基于 Arduino 的“cubesat”纳米卫星，允许学生创建他们自己的基于卫星的空间实验。但论文摘要解释说，这项实验的基本原理是“用一个更强大的系统取代老化的微芯片 ATMEGA328P，作为商业现成机载计算机的事实上的标准，用于不同类型的高速传感器和图像采集应用。”

Balena 的博客文章指出，ATmega328 微芯片是目前在一些 Arduino 板上使用的芯片，但“涉及高吞吐量数据采样和加密的更复杂的项目”可能需要更高的计算能力。本文给出了一个高速传感器和图像采集应用的例子。对于这个实验，不同的应用程序在不同的容器中运行，因此一个应用程序的崩溃或故障将被隔离，不会影响其他应用程序。因此，相机应用程序在一个容器中运行，而时间同步应用程序在另一个容器中运行。

在科隆德国航空航天中心的空间材料物理研究所进行了一些真空测试后，该团队准备在真实世界的严酷空间中测试他们的装置。研究人员将他们的新项目命名为*apex*——这个名字来自“高级处理器、加密和安全实验”，同时自豪地指出，他们的简单设计包括一个带闪存的冗余微控制器系统。

## 云之外

Balena 的博客对这项任务做了一个很好的总结:火箭携带了连接到 Raspberry Pi Zero 的高清摄像头，带有两个 ESP32-PICO-D4 微控制器“和一系列通过 i2c 总线连接的传感器”还有一个特殊的连接，允许它与火箭的服务舱接口，这样它就可以接收信号，通知它实验中的关键数据收集时刻，从发射时刻的指示器开始。

该博客指出:“在对板载 SD 卡的写入周期中，突然断电或掉电很有可能损坏文件系统，并导致设备无法启动和运行。”当然，在此类以数据捕获为主要目的的应用程序中，写入周期几乎是连续的，这进一步增加了损坏的风险

但幸运的是，所有在容器中运行的软件都由 Balena 自己实现的莫比/Docker 容器引擎 [balenaEngine](https://www.balena.io/engine/) 控制。

为什么是 BalenaOS？Balena 的博客文章吹捧他们的操作系统是“为可靠性、容错性、恶劣的网络条件和意外关机而设计的——非常适合这种环境。”BalenaOS 使用 Yocto 项目(Linux 基金会致力于改善嵌入式和物联网设备的软件开发流程)中的可定制 Linux 组件，然后针对它们支持的设备优化这些组件——其中之一当然是 Raspberry Pi。“在 balenaOS 中，所有的应用程序逻辑和服务都封装在 Docker 容器中，”他们为 Raspberry Pi 3 B/B+提供的[帮助页面](https://www.balena.io/os/docs/raspberrypi3/getting-started/)解释道。BalenaOS 网站提到他们使用 Docker 是因为它“使用容器化的力量[为你的软件](https://www.balena.io/docs/reference/OS/overview/1.x/)提供一个一致的环境，在里面运行的性能代价比虚拟化小得多。”

任务成功完成——尽管这引出了接下来会发生什么的问题。展望未来，该论文称，研究团队希望进行更多的实验，可能是为了提高他们的数据吞吐量，同时保持相同水平的冗余和弹性。他们写道，实现这一目标的一种可能方式是使用[“基于法定人数”的技术](https://en.wikipedia.org/wiki/Quorum_(distributed_computing))(在多数情况下达成一致相当于拥有“法定人数”的投票者，从而使结果有效。)

这是一个需要思考的问题，看起来也是一个有趣的实验，而马斯是唯一有资格做这个实验的人。他的 [GitHub 简介](https://github.com/nmaas87)将他列为“树莓派极客”，同时还提到他也是 [Docker 校园大使](https://www.docker.com/blog/announcing-docker-student-developer-kit-campus-ambassador-program/)——一名接受 Docker 特殊培训的学生，“帮助他们的同龄人学习……”但看到我们现代世界的简单日常技术被提升到地球上空，为未来更多的实验——和实验者——开辟了一条道路，这令人鼓舞。

也许集装箱的一小步有一天会被视为人类的一大步。

* * *

# WebReduce

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>