# 集群容器存储的 Portworx 体系结构

> 原文：<https://thenewstack.io/portworx-architecture-container-storage-clusters/>

[集装箱集群存储的 Portworx 技术架构](https://thenewstack.simplecast.com/episodes/the-portworx-technical-architecture-for-storage-in-container-clusters)

在今天的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中，我们邀请到了 [Portworx](https://portworx.com/) 首席技术官 [Goutham Rao](https://www.linkedin.com/in/gouthamrao/) 以及 GE Digital 软件工程总监 [Balajee Nagarajan](https://www.linkedin.com/in/balajeen/) 和 GE Digital 大数据平台高级总监[Venkatesh Sivasubramanian](https://www.linkedin.com/in/venkiz/)。在今年的中尺度会议上，该小组花了一些时间在播客上谈论与容器编排器和存储环境的集成，以及这些如何影响 ge 和 Portworx。

通用电气基于云的 Predix 平台服务正在利用 Portworx 技术，发现该软件的安全性和技术架构有利于在工业化环境中运行容器。Rou 指出，这种匹配对那些运行多个容器的应用程序特别有利，因为它允许开发人员花更少的时间编写“粘合代码”来将所有组件跨卷连接在一起。

Rao 继续解释 Portworx 如何允许应用程序在同一硬件上共存，因为它不需要物理磁盘并将其提供给应用程序，而是提供一个虚拟存储卷。“一个应用程序绝不是一个容器。要尝试获取一个卷，并以某种方式神奇地将其编排到分布式应用程序环境中，最终 PaaS 的架构师不得不在它周围添加大量粘合剂。”

在对话接近尾声时，Rao 提到 Portworx 宣布将在未来增加一个支持[容器存储接口](https://github.com/container-storage-interface/spec)的版本，“旨在使与容器编排器的集成更加简单，无需人工干预。”

[https://www.youtube.com/embed/dtpVIj2zBi0?feature=oembed](https://www.youtube.com/embed/dtpVIj2zBi0?feature=oembed)

视频

### 在这个版本中:

[1:38:](https://thenewstack.simplecast.com/episodes/the-portworx-technical-architecture-for-storage-in-container-clusters?t=1:38) 介绍 Portworx 及其功能。
[3:10:](https://thenewstack.simplecast.com/episodes/the-portworx-technical-architecture-for-storage-in-container-clusters?t=3:10)GE 数码基于云的 PaaS，Predix 之间的连接。还有波特沃克斯。
[6:05:](https://thenewstack.simplecast.com/episodes/the-portworx-technical-architecture-for-storage-in-container-clusters?t=6:05) 客户在集装箱存储环境方面面临的一些挑战。
[13:46:](https://thenewstack.simplecast.com/episodes/the-portworx-technical-architecture-for-storage-in-container-clusters?t=13:46)Portworx 如何构建其技术架构以提供它所提供的服务。
[16:49:](https://thenewstack.simplecast.com/episodes/the-portworx-technical-architecture-for-storage-in-container-clusters?t=16:49)Portworx 如何看待其存储技术平台的成熟。
[17:55:](https://thenewstack.simplecast.com/episodes/the-portworx-technical-architecture-for-storage-in-container-clusters?t=17:55) 在未来六个月内解决高可用性和有状态容器问题。

![](img/b84766d381127d3a3ad0077ab6d11bf9.png)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>