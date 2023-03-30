# 戴尔 EMC 的 ScaleIO 为协调容器提供可扩展的状态存储

> 原文：<https://thenewstack.io/dell-emcs-scaleio-provides-scalable-stateful-storage-orchestrated-containers/>

容器调度程序和基于软件的存储是一个很好的组合，可以减轻在云中运行持久应用程序的操作复杂性，戴尔 EMC 的 [{code}实验室](http://web.archive.org/web/20180220231349/https://thecodeteam.com/)的开源工程师 [David vonThenen](https://github.com/dvonthenen) 上周在 ApacheCon 北美会议上断言。

为了说明他的观点，vonThenen 展示了他创建的一个软件定义的存储框架，称为 [ScaleIO](https://github.com/codedellemc/scaleio-framework) ，带有 [Apache Mesos](http://mesos.apache.org/) 。

戴尔 EMC 团队的 [{code}支持不同的编排平台使用后端不同来源的存储。ScaleIO 可以免费下载。](http://web.archive.org/web/20180220231349/https://thecodeteam.com/)

在他的[演讲](https://www.youtube.com/watch?v=ph8KlAXX49I&index=30&list=PLbzoR-pLrL6pLDCyPxByWQwYTL-JrF5Rp)中，vonThenen 指出了 Mesos 中一个被称为[框架](https://thenewstack.io/developing-user-interfaces-for-mesos-frameworks-and-why-they-are-needed/)的特性，它允许你根据你的特定应用需求来安排任务。将 Mesos 中的提供-接受模式与基于软件的存储相结合，可实现托管任务的部署，同时保持高可用性、横向扩展和自动化。

[Mesos 框架](http://mesos.apache.org/documentation/latest/frameworks/)由一个调度器和一个执行器组成。调度程序可以接受和拒绝资源。该任务然后被部署为一个容器，也就是执行者。该框架与应用程序紧密耦合，除了配置和部署应用程序之外，还可以实现健康检查和监控等功能。

2016 年 9 月发布的 ScaleIO 版本为 0.3.1。这是横向扩展数据块存储。这都是软件:你安装 rpm，你在你选择的任意多个节点上安装 deb。他解释说，你可以在超融合配置或双层配置中做到这一点。

当您添加节点时，因为它都是基于软件的，元数据管理器自动知道它需要重新平衡数据。如果您因维护或硬件故障而取出节点，该节点上的任何数据都会自动重新平衡。

“所有的维护操作都完全由你负责，”他解释说，并补充说，你甚至不必考虑所有与节点故障相关的操作任务，因为它们是自动完成的。

它还有一个弹性架构。如果您需要更多 IOPs，可以添加节点。与传统阵列中的一个控制器不同，作为 ScaleIO 卷的消费者，它将一次性对终端节点的数据进行条带化。

他指出，Rancher 有一个竞争产品，并补充说他描述的功能可以在任何基于软件的平台上完成。

[https://www.youtube.com/embed/ph8KlAXX49I?feature=oembed](https://www.youtube.com/embed/ph8KlAXX49I?feature=oembed)

视频

如果您有一个 Mesos 高度可用的三节点集群，以及底层的各种计算，当您部署框架时，它将为每个代理节点提供从基于软件的存储平台调配和使用存储的能力。

如果它印在每个代理节点上，您可以从其中一个节点配置存储，并且在另一台计算机上进行故障转移时也可以使用该存储。您可以将该卷重新连接到另一个节点，这样您就拥有了所有数据。这是容器的高可用性。

当您将新的 Mesos 代理节点引入主集群时，一旦该代理将其资源注册到 Mesos，代理就会将其资源发送到基于存储的框架，并立即赋予该节点访问基于存储的平台的能力。

因为一切都是基于软件的，在这种情况下，ScaleIO 可以为您处理所有操作任务，并且它可以线性扩展，所以您不需要担心磁盘故障和其他问题的存储阵列的操作复杂性。

如果出现硬件故障，请将节点取出。它会自动重新平衡。然后修复节点并将其引入。因为它完全基于 RPM 和 deb，所以您可以在任何地方部署它。他说，因为 ScaleIO 被设计为在裸机上运行，所以它将在虚拟机或任何公共云上运行，包括 Azure，因为它支持 Windows。

## 变得有状态

尽管容器最初是无状态的，他指出 Docker Hub 上 20 个最流行的容器中有 10 个是有状态的，包括 Postgres、MongoDB、Elasticsearch 等等。

传统上，如果你已经创建了 Postgres，你可以在容器中写数据。然而，如果 Postgres 关闭，你就失去了你的数据库。

vonThenen 说，指挥者——Docker Swarm、[、Kubernetes](/category/kubernetes/) 、Mesos——意识到你正在一台特定的计算机上运行这个容器。计算机通常有一个直接连接磁盘。

“因此，让我们重新路由数据，这样当我们写入 Postgres 数据库时，我们写入的是本地磁盘，而不是容器本身，因此当您关闭容器，然后重新打开它时，它可以将本地磁盘装载重新连接到您的容器，并拥有您的所有数据。这意味着你正在将所有数据写入本地磁盘，”他说。但是，如果您有一个硬盘故障或主板上的系统出了问题呢？因为这些都在那台计算机本地，所以你已经丢失了所有数据。

“我们很久以前就知道，如果你想让数据高度可用，就需要把它放在某个外部存储器上，”他说

ScaleIO 和 VMware 的 [vSAN](https://www.vmware.com/products/virtual-san.html) 基本上做同样的事情:它们获取您的直连磁盘，将它们贡献给全局池。数据在该全局池中分条。您可以从该池中调配存储或卷，也可以将卷从一个节点移动到下一个节点。即使您使用本地聚合磁盘，因为它可以从每个节点访问，所以它看起来像外部存储，即使它使用本地存储作为存储平台的后端。

至于这将走向何方，他说:“如果我们有一个框架来配置和部署应用程序和 API 以监控和管理应用程序，我们应该能够通过这个框架在存储平台上进行健康和补救。”

使用基于软件的存储平台和由 API 驱动的云平台，应用程序应该能够执行自动扩展实例、拨入磁盘 IOPs 和配置新硬盘等操作。

“如果你有一个特定于你的应用程序的框架，它会让你的应用程序有能力做一些原本不打算做的事情，”他说。

在他的演示中，他展示了如何在所有节点上部署基于软件的存储，并添加数据以使该存储平台看起来达到 98%的使用率，这通常是一个噩梦般的场景。但是，由于基于软件的存储框架执行自动平衡，因此该框架本身可以添加新磁盘、调配更多存储来扩展存储池的容量，从而使存储池不再满。

Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>