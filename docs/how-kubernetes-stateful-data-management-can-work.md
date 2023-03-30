# Kubernetes 如何管理有状态数据

> 原文：<https://thenewstack.io/how-kubernetes-stateful-data-management-can-work/>

Kubernetes 环境如何能够为存储、数据库和其他持久数据源提供挂钩，这仍然是许多潜在用户心中的一个问题。为此，一个名为 Kubernetes 社区上的[数据(DoKC)](https://dok.community/about/) 的新联盟成立了，以帮助组织找到在 Kubernetes 上处理有状态数据的最佳方式。

在最新一期的 New Stack Makers 播客中，该小组的两名成员讨论了在 Kubernetes 上运行有状态工作负载所面临的挑战，以及 DoKC 如何提供帮助。

这次对话的参与者有[梅丽莎·洛根](https://www.linkedin.com/in/mklogan)， [Constantia.io](https://constantia.io/) 的负责人，一家开源和企业技术营销公司，DoKC 的主管； [Patrick McFadin](https://www.linkedin.com/in/patrick-mcfadin-53a8046) ，来自 [DataStax](https://www.datastax.com/?utm_content=inline-mention) 的 [Apache Cassandra](https://cassandra.apache.org/_/index.html) NoSQL 数据库平台开发人员关系副总裁兼首席宣传员； [Evan Powell](https://www.linkedin.com/in/epowell) ，顾问、投资者和董事会成员[，MayaData](https://mayadata.io/?utm_content=inline-mention) ，Kubernetes-环境存储解决方案提供商。

TNS 总编辑乔布·杰克逊主持了这个播客。

[Kubernetes 状态数据管理如何工作](https://thenewstack.simplecast.com/episodes/how-kubernetes-stateful-data-management-can-work)

考虑到将应用程序和操作转移到 Kubernetes 集群所面临的巨大挑战，将存储和数据库附加到这样一个无状态且复杂的容器化环境中的想法似乎特别令人生畏。尽管如此，随着 DoKC 等团体提供的社区支持的出现，以及 Kubernetes 存储和数据管理工作工具的可用性，许多 DevOps 团队仍然在稳步前进。

“我们所看到的——这肯定是事实——是有一大群 Kubernetes 人说，你知道，有状态数据永远不属于 Kubernetes，”McFadin 说。“但就像所有其他事情一样，基础设施团队会说，‘拿着我的啤酒——我们无论如何都要做。’"

事实上，与过去相比，Kubernetes 的有状态数据存储和管理是一种不同的动物。“这些工作负载本身是‘云原生或松散耦合的’，我的工作负载和团队 A 不应该依赖于你在团队 B 中的工作负载，或者另一个工作负载和团队 C，”鲍威尔说。“因此，共享存储的整个模式，即“n”个工作负载都放入同一个数据桶中(这是传统共享存储的做法)，并不真正适合云原生数据的新世界。”

洛根说，DoKC 的目标一直是“将人们聚集在一起，找出如何在 Kubernetes 上运行稳定的工作负载”。“这是一个挑战…Kubernetes 最初并不打算运行有状态的工作负载，”Logan 说。“现在，早期(采用者)看到了一些成功，但仍有许多挑战。所以这个社区的成立是为了把人们聚集到 Kubernetes。”

对于那些对 Kubernetes 数据管理计划的社区支持感兴趣的人，DoKC 定期举行会议。洛根说:“我们的想法是让在 Kubernetes 上做数据的人或有东西可以分享的人，无论是作为从业者[提供]操作指南的高层次人士，还是‘嘿，这是我们对 Kubernetes 上的数据的未来的看法’。“因此，我们每周都会举办几次聚会，有时会更多，并邀请所有这些人来帮助分享知识。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>