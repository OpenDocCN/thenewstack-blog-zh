# Kubernetes 时代的数据管理是什么？

> 原文：<https://thenewstack.io/what-is-data-management-in-the-kubernetes-age/>

数据管理为那些寻求向 Kubernetes 和云原生环境转变的组织带来了挑战。在本期[New Stack Analysts](https://thenewstack.io/podcasts/analysts)播客中，TNS 创始人兼发行人 [Alex Williams](https://thenewstack.io/author/alex/) 虚拟地与嘉宾分享煎饼和糖浆，讨论 [Apache Cassandra](http://cassandra.apache.org/) 、 [gRPC](https://github.com/grpc) 以及其他工具和平台如何在管理 Kubernetes 上的数据中发挥作用。

播客主要介绍了来自微服务服务提供商 [effx](https://www.effx.com/) 的软件工程师和 OSS 贡献者[Mya Pitzeruse](https://www.linkedin.com/in/mjpitz/)； [Sam Ramji](https://www.linkedin.com/in/sramji/) ，Datastax 的首席战略官；以及 [Tom Offermann](https://www.linkedin.com/in/tom-offermann/) ，observability 服务提供商 [New Relic](http://newrelic.com/?utm_content=inline-mention) 的首席软件工程师，作为嘉宾就 Kubernetes 上数据管理的发展和有待完成的工作提供了深刻的观点。

[Kubernetes 时代的数据管理是什么？](https://thenewstack.simplecast.com/episodes/what-is-data-management-in-the-kubernetes-age)

Pitzeruse 说，“世界上无状态方面的许多经验教训正开始进入有状态方面”。“因此，我们看到了一些真正健康的增长，[例如]在这些更短暂的计算平台(如 Kubernetes 或 Nomad，甚至是云中的托管平台)内运行这些真正复杂的有状态系统，”Pitzeruse 说。

事实上，最初的想法“是，随着我们对计算的需求增加，人们将使用越来越多的云状态服务，但你不必在 Kubernetes 内部填充这些服务，”拉姆奇说，他是谷歌云平台的产品管理副总裁，在 Kubernetes 开发期间负责监管 Kubernetes 和云 DevOps。

“我们认为‘我们只需关注计算，数据会自行处理，但事实却是……这让我们更加倾向于‘嘿，为什么数据不能像计算层一样易于使用呢？”拉姆奇说因此，现在将状态引入 Kubernetes 环境是一个巨大的挑战和机遇。"

然而，虽然管理 Kubernetes 上的有状态数据仍然是一个关键的挑战——如上所述——但是在 Kubernetes 最初开发的时候就已经开始工作了。“Kubernetes 的早期活动实际上是围绕着无状态服务的，”Offermann 说。“现在，我认为我们已经准备好解决如何管理有状态服务的问题了。你如何管理数据库？你如何管理 Kubernetes 上的数据存储？这非常令人兴奋。”

支持数据管理的新工具和平台在很大程度上支持数据在 Kubernetes 上的共享和传输。Pitzeruse 说:“由于许多传统系统都被绑定到单台机器上，因此很多信息都涉及到如何高效地移动数据，随着这种新的计算时代的到来，我们需要开始着手处理数据工作负载，并将它们分散到不同的机器上。”

[https://www.youtube.com/embed/ccd9RZoW6xQ?feature=oembed](https://www.youtube.com/embed/ccd9RZoW6xQ?feature=oembed)

视频

对于这次演讲，威廉姆斯还提供了一个“Kubernetes 煎饼”作为奖励，对于那些在推特上提问的幸运播客听众来说，TNS 通过提供一套《星球大战》锅铲扩展了煎饼制作的氛围。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>