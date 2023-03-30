# 21 世纪 20 年代将由横向扩展数据来定义

> 原文：<https://thenewstack.io/the-2020s-will-be-about-scale-out-data/>

如果说 2000 年代是网络在互联网上发展的时代(我称之为读/写时代，其他人则称之为“Web 2.0”)，2010 年代是计算层的时代，那么 2020 年代将是数据层的革命。

这是根据 DataStax 首席战略官 Sam Ramji 的说法，他在上周的 [The New Stack 虚拟煎饼早餐网络研讨会](http://ww2.datastax.com/Bv003I1Zz000y04F0zVZTz5)上概述了他的愿景。

具体来说，拉姆奇谈到了这些趋势如何在互联网上“扩大规模”。正如新的堆栈读者[将会知道的](https://thenewstack.io/the-history-of-the-new-stack-scale-out-architecture/)，横向扩展架构是指通过添加更多的机器来为应用程序增加更多的功能，而不是“纵向扩展”方法，后者依赖于通过添加更快的 CPU 或更多的内存来升级机器。当然，横向扩展是我们现在所处的云世界的基石。

[煎饼播客:卡珊德拉和对 Kubernetes 数据平面的需求](https://thenewstack.simplecast.com/episodes/pancake-podcast-cassandra-and-the-need-for-a-kubernetes-data-plane)

在我们深入研究拉姆奇的预测之前，有必要快速回顾一下我们是如何走到这一步的。

2010 年见证了几个主要互联网平台的成熟:社交、移动和云计算。从基础设施的角度来看，云是最重要的。所有的大玩家现在都有庞大的云计算基础设施——亚马逊、谷歌、微软、苹果和脸书。随着容器在十年中期的出现(New Stack 创始人 Alex Williams 是第一批报道的人之一)，人们发现了一种更高效、更可扩展的管理云应用的方法。

下一次革命是开源容器编排平台 Kubernetes，它支持计算平台的更多“横向扩展”。Kubernetes 是从一个名为“Borg”的谷歌内部平台发展而来的，在过去几年经历了快速增长。根据云本地计算基金会(CNCF)最近的调查，78%的受访者现在在生产中使用 Kubernetes 比去年的 58%有了飞跃。

现在 Kubernetes 在云本地公司中如此流行，注意力开始集中在数据层。Apache Cassandra 已经成为云原生世界的首选开源数据库，DataStax 是基于 Cassandra 提供商业解决方案的创业公司之一。

什么是阿帕奇卡珊德拉？这是一个高度可扩展的分布式开源数据库，最初由脸书开发，于 2008 年 7 月作为开源项目发布。这是一个所谓的 [NoSQL 数据库](https://thenewstack.io/databases-and-microservices-a-technology-and-methodology-primer/)，一种“专门为可伸缩应用程序构建的”非关系数据库如今，网飞、康卡斯特、易贝、Hulu 和 Intuit 等公司都在使用 Cassandra。它最大的用户之一是苹果，[运行着](https://mobile.twitter.com/cra/status/1197023973071974400) 150，000 个 Cassandra 实例，存储着数百 Pb 的数据。

Ramji 和其他人正在推动的想法是，Cassandra(数据平面)是 Kubernetes(控制平面)的自然补充。两者都是开源的，都是分布式的，都是高度可扩展的。正如拉姆奇在[的另一次采访](https://www.tfir.io/interview-with-sam-ramji-chief-strategy-officer-datastax/)中所说，“卡珊德拉和库比就像花生酱和巧克力一样……对于云原生世界来说，这是数据和计算的完美组合。”

如果有人知道 Kubernetes 和 Cassandra 如何结合使用，那就是 Ramji。他在谷歌期间(2016 年末至 2018 年年中)领导了 Kubernetes 团队，现在他负责以 Cassandra 为重点的初创公司 DataStax 的战略。

Ramji 在虚拟煎饼网上研讨会上说:“Apache Cassandra 已经获得了十多年来来之不易的经过战斗考验的代码改进。所以他认为，它已经准备好成为大型云项目的分布式数据库选择。

虽然值得注意的是，Cassandra 需要进一步适应 Kubernetes 的规模，因为它不是该平台的原生版本。为此，DataStax [上个月推出了开源的 Kubernetes 操作系统](https://thenewstack.io/datastax-open-sources-a-kubernetes-operator-to-ease-cassandra-management/)。“操作者”是一种工具，它使得在 Kubernetes 上部署和管理应用程序变得更加容易。

网上还有其他针对 Cassandra 的 Kubernetes 操作符，更不用说在横向扩展架构市场上针对 DataStax 的大量竞争了。[蟑螂实验室](https://www.cockroachlabs.com/blog/scaling-distributed-database/)、 [Redis 实验室](https://thenewstack.io/redis-labs-on-why-nosql-is-a-safe-bet-for-todays-multi-environment-deployments/)和 [MongoDB](https://thenewstack.io/mongodb-extends-database-support-for-aws-as-both-a-partner-and-competitor/) 都有云原生数据库产品。

思考 Kubernetes 和 Cassandra(或者一个可伸缩的数据库)的结合会带来什么样的未来应用是很有趣的。拉姆奇正在关注人工智能和机器学习应用程序。现在网络和计算层已经解决，他认为在未来十年“有机会让数据变得真正简单、真正可管理，并为未来的应用程序创造一个游乐场，这将包括人工智能和人工智能应用程序。”

这是因为要创建真正有效的人工智能和人工智能应用，你需要一个可以积极扩展的数据库。

“你看看这些系统给现代基础设施带来的负载，”拉姆奇说，“仅仅是在一组静态图像数据上进行训练，你就可以看到每秒钟数千兆字节的持续需求——更不用说视频、音频和任何其他你可能想做的图像识别了。”

如果你加入 Kubernetes，这将是人工智能和人工智能应用的未来。

“因此，系统对原始吞吐量的需求，*乘以*扩展到像 Kubernetes 这样的云基础架构的能力，”Ramji 说，“这确实让我们提前看到了一点，对吧？有句最经典的名言是什么来着:未来已经到来，只是分布不均匀。”

谷歌就是一个基于云原生技术的人工智能和人工智能应用的例子。在谷歌的例子中，控制平面是 Borg(Kubernetes 的母亲),数据平面是它自己的大规模可扩展数据库管理系统 Google Cloud Spanner。

“所以当你看到谷歌为什么能够建立一个现代人工智能和机器学习业务时，”拉姆奇说，他指的是谷歌搜索、广告、Gmail 和其他产品，“这是因为它有这个博格控制平面，而你有 Spanner 作为你的数据平面。因此，这两者的结合使得计算和数据变得如此普遍可寻址，如此容易访问，以至于你可以做任何你可以想象的事情。”

有趣的是成千上万的 T2 其他 T3 企业和创业公司可以用同样的技术做什么(只是这次是开源的)。换句话说，未来十年领先的人工智能和人工智能应用很有可能建立在 Kubernetes 和 Cassandra 之上。

DataStax、CNCF、Redis Labs 和 MongoDB 是新堆栈的赞助商。

图片来自 Pixabay。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>