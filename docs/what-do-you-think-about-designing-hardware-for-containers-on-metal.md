# 你如何看待在金属上为集装箱设计五金件？

> 原文：<https://thenewstack.io/what-do-you-think-about-designing-hardware-for-containers-on-metal/>

在我的公司, [RackN](http://rackn.com/) ,我们已经进行了很多关于金属集装箱的讨论。由于我们是硬件运营专家，我们的合作伙伴希望我们创建参考体系结构(RAs)。当团队在戴尔创建[撬棍时，我们构建](http://en.community.dell.com/techcenter/cloud/w/wiki/3277.dell-crowbar-open-source-cloud-installer)[open stack RAs](http://openstackdays.com/files/P4_Dell2014.pdf)的经验是围绕一个稻草人开始对话，而不是用凿子和木块工作。

## 容器化金属可能与虚拟化金属非常不同

最近，我们一直在争论少数大型服务器相对于大量小型服务器的优点。在这篇文章中，我将采用大量小型服务器的观点。

在这两种情况下，我们都假设:

*   这些容器使用基本的 Linux 操作系统直接在 metal 上运行(CoreOS 对 CentOS？让我们把它留到以后的文章中。)
*   没有虚拟化或共享存储。
*   你在规划一个容器调度系统，像 Kubernetes，Mesosphere，Cloudsoft，StackEngine，Docker Swarm 等。

首先，我们必须找出可能的限制:网络(net)、内存(RAM)、存储(磁盘)或计算(CPU)。现在，我们首先假设我们的容器工作负载主要处理用户请求或代理中间层服务请求。为了进行比较，我创建了一个包含其他规模工作负载的表格(见底部)。

### 1.容器并没有接管所有的工作负载(就像我们对虚拟化的假设一样)

这是我们最关键的假设。这意味着我们不必构建处理所有工作负载的容器，我们可以专注于容器编排的优势:短生命周期、智能放置、故障恢复和微服务架构。我们还应该预计，大型任务更有可能在容器之间进行拆分，而不是依赖于容器中的多个内核或线程(如数据库)。结果是容器主机可以有更少的 RAM、CPU 和磁盘，而网络仍然很重要。

### 2.预测容器编排系统是至关重要的

这是因为它允许我们设计一个更加分布式的系统，能够快速响应系统故障。从这个意义上来说，我们终于能够将宠物与牛的类比融入到我们的设计中了。如果调度程序对系统故障做出反应，那么我们的工作负载就自动变牛；因此，我们受益于一个更加分布式和更少单个容错的架构。

### 3.容器可以更好地处理超额订阅和密集打包

容器运行在共享环境中。他们可以依靠操作系统来平稳地处理资源分配，直到服务器的全部资源。相比之下，根据分配方式，虚拟机可能会在未充分利用的系统上耗尽 RAM 或 CPU。假设设计负载意味着我们不需要在单个系统上留下大量开销，因此备用容量在系统级别由非活动节点反映，而不是平均节点利用率百分比。

总的来说，我们正在寻找更多功能较弱的服务器。总的来说，购买相同的总 RAM 或计算是有意义的；然而，用许多较小的单元来做可能会有相当大的成本、可靠性和性能好处。

我们希望听到您对这些假设的看法。我们的下一步——进入系统的“速度和进给”——将建立在这些假设的基础上，因此我们需要您的意见。

### 辅助材料:工作量表

根据设计，工作负载被限制在最多两个“高”类别。

云软、CoreOS 和 Docker 是新堆栈的赞助商。

专题图片:[西蒙&的《](https://www.flickr.com/photos/simon__syon/)[奇幻——伦敦城市建筑](https://www.flickr.com/photos/simon__syon/14613178930/in/photolist-ogjmYS-tnincm-aA6B63-7bsvGw-kVFQL3-hFKT4k-nXRGyR-nsDb4a-cZ1Vo7-8rADJk-f1jmNA-fkMKAL-5oXvaf-hjHhFy-6aK3qM-aG4cbp-dZJedd-bygNrb-79Azik-aqfwSf-igwLc6-4Cx8Rv-9ySkSK-91ddV8-9b2Esb-aZYKMZ-b3ugz4-aHrQPa-8Jtrbu-r4e4mt-dEU932-6xvsC8-ebiH4u-dGYLsn-eaJFsQ-85wsE-seRtUu-rYPcAG-q1xQGT-ogz2Xi-qbWEjx-AbPAn-aqGWAy-55o3yC-qhfDi2-aCmAzD-4d2rRS-8v54S9-8EZSez-9attJj)》他的相机获得了 [CC BY-ND 2.0](https://creativecommons.org/licenses/by-nd/2.0/) 的授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>