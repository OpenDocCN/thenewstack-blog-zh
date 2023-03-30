# Joyent Manta 如何大规模简化对象存储

> 原文：<https://thenewstack.io/tns-analysts-show-101-joyent-manta-aims-simplify-object-storage-scale/>

不可否认，容器正迅速成为当今应用程序开发过程的基石，尽管最常用于存储容器的技术的采用仍然落后。以容器为中心的对象存储直到 2011 年末才引起托管容器提供商 Joyent 的注意，当时它开始开发其分布式对象存储和集成计算服务 [Manta](https://www.joyent.com/manta) 。

[Joyent 的首席技术官 Bryan Cantrill](https://twitter.com/bcantrill) 指出“灯泡在 2011 年末为我们点亮。重要的是，容器不仅仅与计算有关，如果您可以拥有这种权威的对象存储，您可以在其上安全地旋转一个容器，该容器可以看到底层对象，而不能看到其他对象，也不能破坏系统，在它自己的完全隔离的容器中。”

随着时间的推移，Joyent 继续开发软件和服务，如其容器即服务平台 Triton。这些项目引起了三星的注意，三星最近宣布[将收购 Joyent](https://www.joyent.com/blog/samsung-acquires-joyent-a-ctos-perspective) ，这将给 Joyent 带来额外的灵活性和可扩展性。

在第 101 集的[中，下面嵌入了新的堆栈分析师](https://thenewstack.io/podcasts/)，我们将深入探讨处理当今企业面临的海量数据的陷阱，Joyent 为什么要建立名为 [Thoth](https://github.com/joyent/manta-thoth) 的设施来自动化其故障转储管理，以及在大规模工作时，源上的对象计算对于充分利用数据是如何至关重要的。新堆栈创始人 [Alex Williams](https://twitter.com/AlexWilliams) 采访了 Cantrill，听听他对这些话题的想法。

[# 102:Joyent Manta 如何大规模简化对象存储](https://thenewstack.simplecast.com/episodes/102-how-joyent-manta-aims-to-simplify-object-storage-at-scale)

采访[也可以在 YouTube](https://www.youtube.com/watch?v=DkP2sdTsYa0) 上听到。

Cantrill 指出，许多组织已经创建了无法处理的海量数据。“现在，我们有如此大规模和海量的数据，以至于它实际上变得不可移动，如果您想离开这些数据并采用亚马逊冰川方法，这是很好的，在亚马逊冰川方法中，长期冷数据可能位于一个关闭的主轴上，仅用于灾难恢复。那么也许你可以使用这些更传统的解决方案，”坎特里尔解释道。

除了开源 Manta 之外，Joyent 还利用了分布式系统的力量，在其 Triton container 技术的基础上构建它，Triton container 技术也与 Manta 一起开源。Manta 利用 Oracle 的 [ZFS](https://docs.oracle.com/cd/E23824_01/html/E24456/storage-4.html) 来存储对象，直到它们被调用进行计算。

除了为对象存储引入分布式系统的能力，Joyent 后来意识到修改 Manta 的崩溃自动化对他们的开发团队至关重要。“我们写了一个叫做透特的设施，一个我们在曼塔上建立的系统。Thoth 允许我们对我们的核心和崩溃系统进行自动分析。当一个新的核心转储进入 Manta 时，我们可以自动分析它，看看它是否与各种已知错误的模式匹配，如果匹配，我们可以标记它，”Cantrill 说。

坎特里尔后来解释说，大规模处理大量数据的关键是找到源头。“你需要大量的数据来探索这些假设和挑战，你不希望为了适应它们而移动数据。你希望能够在它所在的对象上进行计算。”

[Joyent](https://www.joyent.com/) 是新堆栈的赞助商。

专题图片[途经](http://nos.twnsnd.co/image/148451757537)的[新老股](http://nos.twnsnd.co/)站点。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>