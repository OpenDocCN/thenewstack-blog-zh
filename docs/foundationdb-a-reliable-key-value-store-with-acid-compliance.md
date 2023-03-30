# FoundationDB:符合 ACID 规范的可靠的键值存储

> 原文：<https://thenewstack.io/foundationdb-a-reliable-key-value-store-with-acid-compliance/>

[KubeCon + CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/) 赞助了这个播客。

[FoundationDB 的遗产继续着新的改进](https://thenewstack.simplecast.com/episodes/foundationdbs-legacy-continues-with-new-improvements)

开源 FoundationDB 数据存储“可以说属于键值存储或键值数据库的类型，”雪花计算的 Ashish Motivala 说。Motivala 说:“FoundationDB 与大量其他数据库 value stores 之间的区别在于，它提供了 ACID 合规性，这意味着它提供了所有事务性支持，这与许多其他数据库不同。”。“它提供的另一件事是我在过去的其他数据库中从未见过的可靠性水平。对我来说，这两件事真正定义了什么是 FoundationDB。”

Pang 说，FoundationDB 还充当单键值存储，“使您能够在代码中编写逻辑，与存储进行事务性交互”。“这只是一个在我脑海中统治一切的数据仓库，”庞说。

Alex Williams，The New Stack 的创始人兼主编，最近在最新一集的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中与雪花的 Motivala 和来自 [VMware](https://www.vmware.com/) 的 [Clement Pang](https://www.linkedin.com/in/clementpang) 进行了交谈。两人都是基金会数据库峰会的委员会成员。他们描述了 FoundationDB 的历史，以及它为寻求通过使用开源替代方案在多云环境中和跨不同地理区域扩展其数据库的组织提供的新改进。

FoundationDB 的潜在好处是它可以作为不同数据模型的通用底层。庞描述了在 2013 年 [Wavefront](https://www.wavefront.com/) 创建时，他最初是如何“非常怀疑的，因为我认为，声称这个单一的数据存储可以只是基础层…使您能够在其上构建各种存储需求只是一个太大的承诺。”

然而，庞说，当他看到开发人员如何通过单个 API 在他们的笔记本电脑上使用它，然后将其移植到生产中时，“具有完全相同的外围 API 连接、所有配置等等”，他对 FoundationDB 的怀疑很快就消失了

“它只是消除了构建应用程序的许多复杂性，当然，当我们创办一家公司时，我们不希望只是为了技术而投入一整套技术，”庞说。"这就是我们的 FoundationDB 的起源."

Motivala 表示，当雪花公司成立以提供分析数据库和云分析数据库时，Motivala 描述了对数据库的需求，即数据库能够存储组织无法存储在自己的分析数据库中的所有信息。Motivala 说:“我们很快意识到，在一个快速发展的初创公司中进行开发是非常困难的，因为你一直在添加新对象和新实体，以保持 MySQL 的正常运行，并通过它在系统中进行修改。”

Motivala 说，在用 FoundationDB 测试了雪花的数据库后，他和他的团队很快发现 FoundationDB 满足了他们大规模和复杂的数据库需求。“你瞧，从那以后，我们现在在任何地方运行数千个 FoundationDB 实例，”Motivala 说。

FoundationDB 也正在开发中，以继续满足越来越多地在多云环境中运行的微服务和 Kubernetes 架构的需求。

“在选择 FoundationDB 时，我们没有选择特定云供应商的产品，这意味着通常会有很大的局限性……而 FDB 给我们的是运行数据层的能力，无论是在 AWS 上，甚至是在本地或不同的云中，也无论是在裸机上进行编排还是在 Kubernetes 中使用，”Pang 说。“你知道所有这些都是开放的，开发者和运营人员可以自由决定。”

最近发布的 FoundationDB 6.0.15 的主要特性包括跨区域复制方法的体系结构转变，FoundationDB 表示，这改进了作为生产系统进行管理的方式，更好的 TLS 改进了操作灵活性，更快的故障恢复。

“做了大量的工作，以确保有可能实际上有一个全球一致的数据存储与应用程序拓扑结构，包括异步服务器应用程序技术等等，”庞说。

退一步讲，Pang 描述了 FoundationDB 如何为寻求高级事务数据库功能的初创公司提供机会。“这种复杂性和部署策略(它可以提供)在过去是任何创业公司都不可能考虑的，”庞说。“我不认为市场上有任何东西看起来像那样。”

### 在这个版本中:

*   [1:52:](https://thenewstack.simplecast.com/episodes/foundationdbs-legacy-continues-with-new-improvements?t=1:52)foundation db 的定义。
*   [5:34:](https://thenewstack.simplecast.com/episodes/foundationdbs-legacy-continues-with-new-improvements?t=5:34) FoundationDB 的核心可以跨分布式基础架构扩展一次，对吗？
*   [10:52:](https://thenewstack.simplecast.com/episodes/foundationdbs-legacy-continues-with-new-improvements?t=10:52) 您对 FoundationDB 以及分布式架构(如 AWS 和 Kubernetes)的不同适用性有何看法？
*   [14:57:](https://thenewstack.simplecast.com/episodes/foundationdbs-legacy-continues-with-new-improvements?t=14:57) 探索 FoundationDB 的历史。
*   过去的一年里，你都在做些什么？
*   [27:27:](https://thenewstack.simplecast.com/episodes/foundationdbs-legacy-continues-with-new-improvements?t=27:27) 对于组织的愿景，你真正想弄清楚的是什么？

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>