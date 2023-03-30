# Weaveworks 为普罗米修斯带来了横向扩展

> 原文：<https://thenewstack.io/weaveworks-horizontal-scaling-prometheus/>

最初由 SoundCloud 工程师团队开发，包括朱利叶斯沃尔茨和 T2 布莱恩巴西，普罗米修斯已经成为基于微服务架构的监控软件之一。在新一集的 [The New Stack Makers](https://thenewstack.io/podcasts/Makers) 播客中，Weaveworks 首席运营官 [Mathew Lodge](https://www.linkedin.com/in/mathew) 讨论了 Weaveworks 新的多租户、可横向扩展的 Prometheus as-a-Service 项目 [Weavecortex](https://github.com/weaveworks/cortex) 如何改变开发人员处理数据的方式。他在 Kubecon 2016 上与 TNS 创始人 Alex Williams 和共同主持人 [Lee Calcote](https://www.linkedin.com/in/leecalcote) 、网络安全管理软件产品云技术负责人进行了交谈。

[Weaveworks 正在给普罗米修斯](https://thenewstack.simplecast.com/episodes/weaveworks-is-bringing-horizontal-scaling-to-prometheus) 带来水平缩放

[https://www.youtube.com/embed/QdO7b7N2Vbw?feature=oembed](https://www.youtube.com/embed/QdO7b7N2Vbw?feature=oembed)

视频

传统上，整体监控侧重于服务器和虚拟机。然而，随着容器的兴起和向更加云原生的开发方法的转变，许多团队发现他们自己难以监控他们的栈。“它不太适合高度集装箱化的环境。许多监控工具都无法跟踪集装箱的位置。洛奇说:“你必须玩的游戏是，‘找到集装箱’。

寻求实施 Prometheus 的人面临的一个挑战是，它将所有数据存储在一个磁盘上。“这就是我们试图用皮层解决的问题。这是普罗米修斯的横向扩展版本。您可以添加 cortex 的实例，它将分散负载、查询和数据收集。它将 It 变成了一个可横向扩展的多租户解决方案，”Lodge 说。

“我们所做的是瘫痪和扩展查询，所以即使数据分散在多个碎片上，它们仍然会快速执行，”Lodge 指出。

这种多维数据方法是 Prometheus 的亮点，尤其是当开发人员需要他们系统的细粒度描述时。“在一个动态的环境中，能够将所有这些东西关联在一起真的很有用。Lodge 解释说:“能够在这个粒度级别上下移动是多维查询模型的优势之一。

思科是新堆栈的赞助商。

#### 2016 年 11 月 30 日 // NYC @ Intrepid Sea，Air &太空博物馆—3 号衣架

#### 2016 年 11 月 30 日 // NYC @无畏海空&太空博物馆—3 号衣架

在我们讨论监控的发展和可组合堆栈的新概念时，与新堆栈进行简短的讨论。

**Only $150 with Code: pancakes. [Register Now!](https://ti.to/grafanacon/2016/)**<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>