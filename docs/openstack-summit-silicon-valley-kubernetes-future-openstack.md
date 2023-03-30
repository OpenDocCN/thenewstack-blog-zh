# OpenStack 峰会硅谷:Kubernetes 和 OpenStack 的未来

> 原文：<https://thenewstack.io/openstack-summit-silicon-valley-kubernetes-future-openstack/>

[OpenStack 基金会](http://www.openstack.org/)的执行董事 Jonathan Bryce 指出:[open stack 的未来将是支持我们今天可能甚至不认识的所有类型的应用。](https://twitter.com/jbryce)

“下个世纪我们人类所做的一切将越来越依赖于不断增长的计算和数据处理能力。布莱斯在本周于加州山景城举行的 Open Stack 硅谷 2016 会议上说:“我们将取得的每一项进步都将依赖于计算机的能力。

他指出，OpenStack 确实为这一进步做好了准备，因为组织必须改变他们关于提供计算能力的思维方式，以考虑大规模扩展。“我们正处于一个非常好的时机，在为世界提供所需的计算能力方面发挥重要作用，”他说。

此外，重要的是，我们将需要的计算能力不会被锁定在少数供应商手中，布莱斯补充道。Bryce 从最近对 1，100 名用户的 OpenStack 调查中分享了一个有趣的统计数据，即 98%的人选择 OpenStack 是因为标准化的 API 平台，允许他们不被锁定到任何一个提供商。

调查还发现，在接受调查的 1，100 家组织中，有 65%在生产中使用 OpenStack。

他指出，许多供应商正以一种“赢家通吃”的方式对待计算，胜利者获得市场。但是这种传统的 IT 方法不适用于这样的大型企业。布莱斯说，思维模式应该从“对抗”转向“和”，让每个公司都受益。布莱斯说，那些玩零和游戏的公司没有考虑到他们的用户。

相反，进步将通过合作来实现。布莱斯指出，OpenStack 有许多新兴的用例，包括物联网、机器学习、人工智能、深度分析。“我们必须考虑如何继续支持新的和不同的工作负载，这一点非常重要。我们不能围着马车转，说这是我们要做的，我们只会这样做，”他说。

回顾过去，Bryce 描述了美国电话电报公司[如何使用 OpenStack 从根本上改变其网络运行方式](https://thenewstack.io/att-moves-nfv-platform/)。

布莱斯说:“这是一个新的用例，六年前我们开始 OpenStack 时，我们根本没有意识到这一点。“你不能采取与开始时相同的方法来满足这些新的使用情形。你可以遵循同样的模式，但你必须支持这些新的用例。”

* * *

OpenStack 和 Kubernetes 之间正在进行的合作似乎在活动中引起了很多关注。

“这两种技术有很多相似之处，”谷歌产品经理兼 Kubernetes 联合创始人克雷格·麦克卢奇在一次小组讨论中说。

起初，这个想法似乎不寻常。如果您有像 Kubernetes 这样的云原生部署工具，为什么还需要像 OpenStack 这样的基础设施管理软件呢？还是反过来？

但是这种配对实际上是有意义的。

“这两种生态系统都存在很多问题，”麦克卢奇说。首先，OpenStack 仍然难以操作，尤其是考虑到它可以运行的所有服务。Kubernetes 可以大大简化这个过程。

“OpenStack 可以被视为一个非常复杂的系统，它只是一组服务。因此，人们很自然地会想，如何给这个生态系统带来更自然的云原生管理，”McLuckie 说。McLuckie 解释说，Kubernetes 还可以为 OpenStack 带来更高效的调度。

但他指出，OpenStack 也可以为 Kubernetes 带来更多。OpenStack 可以为更传统的服务提供扩展，比如块和对象存储。“OpenStack 有一套非常强大的服务，可以自然地补充这些技术。在处理实体基础设施方面没有太多的工作，”他说。

* * *

SAP 是一家使用 Kubernetes 管理大型 OpenStack 部署的公司。当天晚些时候，SAP IT 总监 [Markus Riedinger](https://twitter.com/urfuwo) 展示了这家企业软件巨头基于 OpenStack 管理全球云基础设施的雄心。该公司正在构建一个大规模的云，为客户提供云服务，并提供内部服务。

Riedinger 说，Kubernetes 是保持 SAP 云运行的秘方。“我们不能让数据中心离线来升级 OpenStack，”里丁格说。该公司有一套“预制”的 Kubernetes pods，可用于扩展商用硬件的容量，创建一个可以自动扩展、无需停机即可升级的系统，并在服务失败时自动重新部署服务。

系统设置经过精心设计，控制平面和数据平面完全分离。在一个演示中，里丁格删除了一个 OpenStack Nova pod，它几乎立即就被重新建立起来，而这一切都没有中断用户对数据的访问。

SAP 网络管理员也喜欢这种方法，因为它不需要软件定义的网络，也不需要任何专有驱动程序。所有网络都是通过 VLAN 设备完成的，并得到所有网络设备供应商的支持。

该公司已经[发布了它用来连接这些云的代码](https://github.com/sapcc)。虽然尚未准备好投入生产，但 Riedinger 希望其他人会仔细阅读该代码，从而引发一场关于 Kubernetes 如何用于自动部署大型 OpenStack 云的讨论。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>