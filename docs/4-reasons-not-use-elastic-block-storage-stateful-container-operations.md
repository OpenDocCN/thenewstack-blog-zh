# 不将 AWS 弹性块存储用于有状态容器操作的 4 个理由

> 原文：<https://thenewstack.io/4-reasons-not-use-elastic-block-storage-stateful-container-operations/>

[](http://www.portworx.com)

 [苟饶，Portworx

苟饶，Portworx 联合创始人兼首席技术官，曾任戴尔数据保护部门和思杰系统 ASG 公司首席技术官；Ocarina Networks 和 Net6 的联合创始人兼首席技术官；也是英特尔和洛克希德·马丁公司的主要架构师。他拥有计算机科学学士(班加罗尔大学)和硕士(宾夕法尼亚大学)学位。](http://www.portworx.com) [](http://www.portworx.com)

作为一家专门帮助客户[在容器](https://portworx.com/)中运行有状态服务的公司的首席技术官，我经常被问到，“难道我不应该只使用[亚马逊 EBS](https://aws.amazon.com/ebs/) (弹性块存储)作为容器持久层吗？”简而言之，我的答案是否定的。这篇文章将分享你在 EBS 上停留而低估应用性能的四个原因。需要澄清的是，这并不是反对在 Amazon Web Services 上运行的理由。我们爱 AWS！它是关于通过 Docker、Kubernetes 或 Mesos 插件(如原生 EBS 插件、Flocker 或 Rexray)使用 EBS 作为持久层所带来的具体性能损失。本文的第二部分将探讨克服这些问题的方法。就目前而言，简单了解它们就足够了。

对于希望转向云本地开发和部署的组织来说，这是一个至关重要的问题。随着企业继续采用容器，架构师和 DevOps 团队正在寻找运行有状态应用程序的方法，作为其容器平台的一部分。到目前为止，结果很有希望。各行各业的企业，如 GE Digital、DreamWorks 和 Lufthansa，正在成功地将他们的整个应用程序容器化，而不仅仅是无状态的部分。

## 1.缓慢的装载时间和停滞的卷=缓慢的部署

EBS 是一个存储区域网络(SAN ),因此，将物理块设备或驱动器连接到 Amazon EC2 实例需要一定的时间。就 Linux 内核而言，这些驱动器不够灵活，占用大量资源，并且将它们连接到主机是一项昂贵的操作。

在最好的情况下，在 EC2 实例上启动有状态容器需要 30 秒到两分钟。这是因为当容器被部署并且需要一个卷时，该卷必须在 EBS 上被供应，然后在容器可以启动之前被附加到主机。连接操作本身是一个漫长的过程，需要时间。

正如 Nordstrom 的首席软件工程师汤姆·杰克逊在他精彩的容器世界演讲中所描述的，缓慢的装载时间只是一个问题。另一个更严重的问题是，EBS 卷可能经常陷入“附加”状态。粗略地在谷歌上搜索一下[卡住的 EBS 卷](https://www.google.com/search?q=stuck+EBS+volumes)，就会发现许多人都有同样的问题。卡住 EBS 卷的可怕后果是主机重新启动，所以现在“在毫秒内旋转的轻量级容器”将需要五分钟或更长时间才能上线。

这不是我们承诺的灵活性。

此外，如果 EC2 实例带着一个卷死去，也会发生类似的不好的事情，并且它们通常会导致耗时的主机重新启动。

## 2.缓慢的故障转移意味着没有高可用性

显然，每个有状态容器一个 EBS 卷的模型会带来启动损失。将 EBS 与卷驱动程序一起使用时，这种损失对故障转移意味着什么？让我们看看，如果我们使用 Kubernetes 通过 EBS 卷驱动程序对备份到 EBS 卷的有状态容器进行故障转移，会发生什么情况。

因为我们在 EBS 驱动器和容器之间强制实施一对一的关系(因此我们获得了自动故障转移)，所以每次容器移动时，我们都会触发以下容易出错的事件序列:

*   EBS 卷与无响应的 EC2 实例分离。
*   EBS 卷将连接到新节点。
*   EBS 卷装载到新容器中。

这些步骤中的每一步都需要结合对 AWS 服务器的 API 调用和/或在节点上以 root 用户身份运行命令。

当这些事件发生时，可能会出现各种问题:

*   对 AWS 的 API 调用失败(由于一些虚假的原因)。
*   EBS 驱动器无法从旧节点卸载或分离(出于某些虚假原因)。
*   新节点已经连接了太多 EBS 驱动器。
*   新节点已用完装载点。

在最好的情况下，我们看到故障转移需要几分钟时间。在最糟糕的情况下，仅仅是移动一个有状态的容器，我们就会看到 10 分钟左右的停机时间。那不是高可用性(HA)。

此外，即使我们可以等待 10 分钟进行故障切换，卷也不能跨可用性区域移动，这使得这种阿哈方法对于重要的应用程序来说不可行。

## 3.可怜的 I/O，除非你想花很多

假设您不关心挂载时间，HA 不是您的应用程序的要求。性能呢？众所周知，除了作为单点故障之外，San 还不能提供直连存储的 I/O 和吞吐量性能。Cassandra 专家 DataStax 有一篇很棒的文章，概述了 EBS 等网络连接存储对于这一特定应用的[限制，但问题不仅仅是 Cassandra 的问题。是的，EBS 提供了专用的 IOPS 选项，但是这些选项非常昂贵，您仍然会遭受容器启动惩罚，因此不得不放弃 HA。使用本地存储空间直接(SSD)的存储优化 EC2 实例服务器比在亚马逊的 EBS 上为专用 IOPS 支付额外费用更便宜。](http://www.datastax.com/dev/blog/impact-of-shared-storage-on-apache-cassandra)

## 4.通过存储连接器的卷编排是脆弱的

到目前为止，我们只关注了 EBS 本身的局限性。然而，还有一个与容器化应用程序如何管理 EBS 相关的问题。当我们运行一个容器化的应用程序时，调度程序——Kubernetes、Swarm、DCOS——与卷插件管理器或连接器交互，以创建/装载/卸载/删除卷。连接器的示例包括用于 Kubernetes 的本机 EBS 驱动程序和 EMC 的 Docker、Flocker 或 RexRay。

这些连接器管理容器与卷的使用和关联。当容器启动时，调度程序向卷管理器发出请求以安装卷；当容器离开时，它们请求的卷被卸载。这并不是万无一失的，主要是因为卷管理器通常是外部进程(或容器),调度程序和卷管理器之间的交互是松散耦合的。这意味着可能会“丢失”一个卸载请求，从而导致不良副作用。

例如，因为块设备在任何给定点只能连接到一个设备，所以容器不能在任何其他节点上启动。这又意味着服务/数据不可用。

不幸的是，这个问题不能用处理 EBS 的卷管理器来解决。问题在于存储导出的方式—通过 iSCSI、网络块设备(NBD)或任何其他脱离网络的机制。如果卸载请求丢失，卷插件管理器会错误地认为块设备正在使用中，并且存储提供商无法确定它是否确实在使用中。

另一方面，不依赖连接器的系统总是可以确定卷是否在使用，因为它们知道是否有任何进程打开了块设备。

## 最后的想法

在过去的 20 年里，亚马逊在改变企业 IT 方面做的比其他任何公司都要多；这无异于一场革命。但是当谈到 Docker 容器的持久层时，EBS 还有很多不足之处。显然，从启动时间、HA、性能和可靠性的角度来看，在 EBS 上运行 Dockerized 应用程序还有许多不足之处。同样重要的是，EBS 不提供现代应用程序所需的重要容器数据服务，如跨 AZ(可用性区域)故障转移、跨云迁移、异地备份和容器粒度加密。EBS 只是一个存储解决方案，而不是为 DevOps 构建的数据服务平台。当您评估下一个有状态容器项目时，我鼓励您问自己:“我真的想满足于 EBS 吗？”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>