# Kubernetes 需要深度系统集成

> 原文：<https://thenewstack.io/kubernetes-needs-deep-system-integrations/>

编者按:这篇文章是与 Kubernetes 社区上的数据(DoKC)合作撰写的，这是一个开放管理的技术专家团体，支持在 Kubernetes 上运行数据的技术的出现。了解更多信息

[dok.community](https://dok.community/)

.

谷歌云平台倡导者 [Kelsey Hightower](https://twitter.com/kelseyhightowe) 最近[分享了](https://twitter.com/kelseyhightower/status/1409297909774831618)谷歌团队克服重重困难，为甲骨文数据库创造了一个 [Kubernetes 操作员](https://github.com/googlecloudplatform/elcarro-oracle-operator)。“我们到了，我们正式跨越了鸿沟”高塔在推特上写道。

但是我们真的做到了吗？

虽然将有状态的工作负载放入 Kubernetes 曾经是一项具有挑战性的任务，但现在有状态的工作负载不再是这样了。Kubernetes 生态系统一直在努力改进有状态集，尽管它并不完美，但它适用于大多数有状态工作负载。

 [里克·瓦斯奎兹

里克·瓦斯奎兹是一名实践型技术从业者，拥有世界上一些最大的开源数据库部署的经验。](https://www.linkedin.com/in/rickvasquezii/) 

看看利用云原生范式的成功公司，突出的是它们的垂直集成程度。以最佳方式利用硬件，同时仍能为用户提供他们所要求的体验。

例如，[亚马逊 Web 服务](https://aws.amazon.com/?utm_content=inline-mention)’[Nitro](https://aws.amazon.com/ec2/nitro/)的必要性就这样诞生了——需要在堆栈中深度集成，以有效完成高性能虚拟化。Google [增加了其托管的开源产品的块写入大小，以更好地与底层媒体保持一致。微软利用 SAP 构建定制机箱，以在此之前市场上无法获得的方式支持 HANA。](https://www.google.com/url?q=https://www.youtube.com/watch?v%3DzYU_c5xdUCs%26t%3D116s&sa=D&source=editors&ust=1628199481006000&usg=AOvVaw2xpitUzPyYkqH3EIbfP-uk)

> 有目的的深度生态系统集成是一部制胜之作，也是超大规模企业不断呼吁的一部作品。

有一些关于公司将他们的产品与 Kubernetes 进行深度整合的精彩故事，大多数都是依靠分布式计算解决问题的 NewSQL 项目。CockroachDB、来自 PingCap 的 TiDB、YugabyteDB 等很多都是在云原生世界开始开发的，并且兼容最流行的有线协议，那么为什么我们还没有看到向它们的大规模迁移呢？简单的答案是，它们从根本上处理数据存储的方式不同于传统的 DBMS。从业者通常没有将他们的 DBMS 推到垂直扩展的极限，也看不到水平可伸缩性的需要，通常认为它带来了更多的复杂性而不是好处。

我们看到像 OnGres 的 StackGres、Percona 的 Kubernetes 运营商、Apache Cassandra，甚至[的 MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) 和[的 Oracle](https://developer.oracle.com/?utm_content=inline-mention) 这样不可思议的项目正在进入 Kubernetes 游戏。

还有像 MariaDB 这样的公司，他们致力于垂直集成到 Kubernetes 中，拥有六个以上的存储引擎，每个引擎都有独特的部署风格，有些能够进行 MPP 操作，有些能够进行无共享的横向扩展。即使你是一名 MariaDB 顾问，也有很多东西需要学习，利用 Kubernetes 是一种不那么秘密的方法，无论 MariaDB 如何部署，它都能使 SkySQL 飞速发展。现在 MariaDB，开源所有这些好东西！

我一直主张主流数据库提供商不仅需要创建 Kubernetes 操作者，还需要直接开发具有 Kubernetes 意识的数据库，甚至更好的是，实际的深度集成。

我想这是一个很长的说法，该你走了，先知。不要让我们失望！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>