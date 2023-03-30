# AppFormix 利用英特尔片上技术精确定位噪音邻居问题

> 原文：<https://thenewstack.io/appformix-pinpoints-noisy-neighbor-problems-intel-chip-technology/>

当定义如何在向外扩展的分布式平台上解决嘈杂的邻居问题时，容器编排带来的深层复杂性浮出水面。

就容器而言，噪音邻居问题是指一个容器、容器单元或虚拟机(VM)中的工作负载占用了机器的大部分资源，这对运行在同一服务器上的其他工作负载非常不利。

但是服务器管理员如何知道哪个容器或虚拟机是有噪声的呢？

在英特尔上周在旧金山举办的云日活动上，我们从性能监控公司 [AppFormix](http://www.appformix.com/) 的首席执行官 Sumeet Singh 那里了解到了解决这一问题的新方法。该公司已经开发出一种方法，使用英特尔新的[资源管理器技术](http://www.intel.com/content/www/us/en/architecture-and-technology/resource-director-technology.html) (RDT)，最初在英特尔的至强 E5 v4 芯片上提供，直接从处理器本身查明有噪声的容器和虚拟机。请听下面的采访:

[AppFormix CEO 苏米特·辛格:监控集装箱和吵闹的邻居](https://thenewstack.simplecast.com/episodes/appformix-ceo-sumeet-singh-monitoring-containers-and-noisy-neighbors)

RDT 提供对应用程序、虚拟机和容器使用的缓存和内存带宽的可见性。

该技术解决了横向扩展系统的复杂性以及这些分布式平台带来的新管道需求。管道本身很复杂，但平台必须足够简单，便于开发人员使用。如果缺乏简单性，就会有在整个组织中采用失败的风险，并失去在许多不同的分布式集群中开发可编程基础设施的机会。

Singh 指出，容器密度直接暴露了嘈杂的邻居问题，这是共享应用程序环境的结果。相比之下，当多个虚拟机共享同一个主机时，虚拟化环境中会出现嘈杂的邻居问题。在基于容器的集群中，用户会面临类似的风险，因为缓存和内存问题也会降低进程速度。

英特尔通过其新的至强芯片提供了在处理器上封装更多容器的能力。它允许在公共云或私有云上不可避免地进行扩展。在这个现代环境中，用户将在共享基础设施的某个点上旋转容器。这可能会导致嘈杂的邻居问题，因为在同一主机上有数千个容器。在某些情况下，用户无法获得预期的性能，也无法确定如何解决问题。

以下是关于 AppFormix 如何使用 RDT 的更多信息:

特色图片:带英特尔 RDT 计数器的 AppFormix 仪表盘。

英特尔是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>