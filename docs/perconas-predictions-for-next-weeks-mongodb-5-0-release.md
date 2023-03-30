# Percona 对下周 MongoDB 5.0 发布的预测

> 原文：<https://thenewstack.io/perconas-predictions-for-next-weeks-mongodb-5-0-release/>

高性能数据库专家[Percona](https://www.percona.com/)——除其他外，提供其[自己的 MongoDB](https://www.percona.com/software/mongodb) 面向文档的数据库程序发行版——对下周由 [MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) 公司举办的用户大会 MongoDB.live 活动感到兴奋，该公司管理以前的开源数据库系统。根据 Percona 团队从当前 MongoDB 代码和 [MongoDB 吉拉问题跟踪器](https://jira.mongodb.org/plugins/servlet/samlsso?redirectTo=/)中收集到的信息，他们在周四[他们自己的活动](https://www.percona.com/resources/videos/take-sneak-peek-mongodb-50-percona)之前与新堆栈进行了交谈，该活动深入探讨了潜在的即将推出的功能。

5 月，MongoDB 发布了 5.0 版本的[发布候选，目的是在 7 月 13 日 MongoDB 现场活动的第一天，即正式发布(GA)之前测试和捕捉 bug。Percona 团队强调了他们认为将出现在 5.0 版本中的特性，其中一些与这些候选版本重叠，而另一些则没有。](https://docs.mongodb.com/v5.0/release-notes/5.0/)

请注意，由于 MongoDB 在过去几年中已经从[开源许可](https://thenewstack.io/open-source-licenses-who-holds-the-power/)转变为[源代码可用许可](https://en.wikipedia.org/wiki/MongoDB)，并且该技术背后以自己命名的公司已经公布了较少的路线图和发布计划，因此这是一篇关于该平台一些重要功能的猜测和可能性的文章。然而，MongoDB 团队已经确认，下周的 5.0 将继续为更多工作负载发展 MongoDB，包括时序功能、无服务器实例和集成分析，以及扩展搜索和移动产品功能。

当然，新的堆栈将覆盖正式的 GA 版本，所以请下周再来查看，但这篇文章只是对世界上最受欢迎的 NoSQL 数据库产品之一的潜力的有趣一瞥。

## MongoDB 重新共享

当然，最受欢迎的潜在功能更新解决了非常具有挑战性的重散列问题。配置服务器上的[创建 reshardCollection 命令](https://jira.mongodb.org/browse/SERVER-48677)和[创建带有函数存根的 ReshardingCoordinatorStateMachine 的类](https://jira.mongodb.org/browse/SERVER-49569)的两张票大约在一年前就关闭了，但没有包含在上述发行说明中。上个月，围绕重散列的其他代码更改和工作仍在继续。这并不奇怪，因为这是一项复杂的任务，会影响 MongoDB 中核心功能的许多不同部分。

MongoDB 最重要的特性之一是它的水平伸缩能力。它通过添加主机，然后在这些主机之间分配数据和负载，并利用它们的额外资源来实现这一点。这被称为[分片](https://www.mongodb.com/features/database-sharding-explained)，它发生在集合或表级别。

为了分片，选择一个[分片键](https://docs.mongodb.com/manual/core/sharding-shard-key/)，用于在分片或节点间分发集合的文档。数据被分割成块，每个块包含一部分分片数据，从而包含集合中的一部分文档。然后，这些块被均匀地分布在碎片上。碎片键选择对数据库的可伸缩性和性能有很大的影响。

早在 2015 年，MongoDB 就写了选择碎片键[的重要性:“如果你选择了错误的碎片键，你完全可以毁掉你的集群的性能。”](https://www.mongodb.com/blog/post/on-selecting-a-shard-key-for-mongodb)

正如 Percona 的 MongoDB 技术负责人 Kimberly Wilkins 所说:“许多人没有意识到预先花时间和精力选择最佳的碎片密钥是多么重要。他们不会考虑他们的所有访问模式，也不会考虑他们的数据今天是什么样子，明天会是什么样子。”

她说，在选择碎片密钥时，数据的某些重要特征并不总是被考虑在内，包括:

“他们通常很匆忙，或者认为以后可以改变。这在将来会给他们带来问题，”Wilkins 说，回顾了她在 Oracle 和 MongoDB 中支持生产数据库的职业生涯。自 2014 年开始使用 MongoDB 数据库以来，她一直与客户合作，专门帮助他们为其工作负载选择最佳的碎片键。她称这种重新共享集合并减轻负面性能影响的能力“非常令人兴奋”

直到[去年的 4.4 版本](https://thenewstack.io/mongodb-4-4-promises-less-work-for-database-developers/)，你永远被碎片钥匙卡住了。甚至 MongoDB 也将这五个不同的关键考虑因素的选择称为“更多的艺术而不是科学”MongoDB 4.4 允许可细化的碎片键，这提供了修改当前碎片键的能力，以提供更多的可分性和细粒度的数据分布。

Wilkins 举了一个应用程序捕获社交媒体数据的例子。你可以根据数据来自哪个社交媒体应用来选择碎片密钥——例如，Twitter、Instagram、脸书和抖音。但是突然抖音爆炸了。数据的这种突然的指数级增长会使保存抖音数据的碎片过载，导致整个应用程序出现真正的规模和性能问题。

重散列将允许您完全改变现有集合上的 shard 键，并在您的 shard 之间更有效地重新分配数据。通过选择更符合您的应用程序需求和数据特征的新碎片键，您将能够克服以前的碎片键造成的负面性能影响。Wilkins 说，这是一个多年来一直在开发的功能，因为直到现在，手动实现对 shard key 的任何更改都非常复杂。它基本上包括克隆一个现有的集合，然后基于新的分片键跨分片重新平衡克隆的集合的块和数据。然后，您必须删除原始集合，并更新配置数据库中的元数据。

所有这些都必须在不影响底层性能的情况下完成，这就是为什么到目前为止，大多数团队都聘请外部顾问。

## MongoDB 同步和可恢复索引

[MongoDB 索引](https://docs.mongodb.com/v5.0/release-notes/5.0/#indexes)是 5.0 发行说明的一整节。一个关键的更新指向了一个关闭的标签，它谈到了对跨副本集成员的[同步索引构建](https://jira.mongodb.org/browse/SERVER-45001)的改进。这项工作涉及针对两阶段索引构建的[共识协议](https://www.mongodb.com/presentations/world18-pv0-to-hero-a-brief-history-of-the-consensus-protocol)，特别允许两阶段索引构建以提交法定人数运行，并要求在标记为完成之前在大多数辅助节点上完成索引创建。

Percona 的 MongoDB 产品负责人阿基拉·黑钢告诉新的堆栈，这种同步索引“表明 MongoDB 将更加认真地维护副本集之间的索引一致性。以前，您可以在主服务器上建立索引，但可能无法在副本集的所有成员上建立完整的索引。如果发生了选举或其他灾难恢复事件，并且丢失了一个辅助索引，新索引被选为新的主索引，那么性能就会完全崩溃。”

他继续说，以前，随着时间的推移，强制所有节点建立索引的风险相对较小，但是这会降低数据库的速度。然而，这种风险随着当今越来越大的数据集和集合规模而增长。

他说，这次更新将延续 4.0 和 4.2 版本的趋势，重点是增加分布式系统中某些保证的强度。这也是一个更适合数据库管理员而不是应用程序开发人员的特性。

黑钢说，另一组重要的版本将围绕[可恢复索引构建](https://jira.mongodb.org/browse/SERVER-48417)，它允许你的工作在关机后恢复，减少构建的痛苦。

“意外丢失节点或因为您正在进行维护重启而丢失节点，将不再导致您丢失索引构建过程中已经完成的工作。硬盘容量的增加意味着很多很多人在每个节点上放了很多兆兆字节，”他说。"如果你正在阅读和索引你的全部收藏，那真的需要时间."

有了这个新的可恢复索引构建，您可以停止和启动索引过程构建，在需要时恢复。

Wilkins 说，除了分片之外，MongoDB 的主要好处之一一直是其性能的提高。这种性能来自于关系数据库固有的“缺乏联合和连接”。MongoDB 使用索引，但她说构建这些索引会影响性能，并导致您的应用程序在构建过程中受到影响。

她说，“想象一下，如果你刚刚花了 3、4 或 10 个小时在一个数万亿字节的集合上建立一个索引，而在索引建立完成之前发生了一些事情，你不得不从头开始。可恢复的索引构建克服了这个问题。这是另一项长期要求，在添加原本旨在提高性能的索引时，它将防止负面影响实例。”

这就是为什么 Percona 团队挑选出这两个索引更新对社区特别有影响和重要。

## MongoDB 时间序列集合

黑钢已经与 MongoDB 合作了十多年，他将时间序列集合的添加描述为一个“真正的大变化”毕竟，时间序列处理时间和价值的一对一关系，这对于分析从交易历史到疾病诊断到监控和可观察性的任何事情都是必不可少的。

目前，在 MongoDB 中，您可以指定一个日期字段，然后所有数据将按桶重新排列。有了这次更新，重新排列数据以将所有值放入一列变得简单了。

“这真的颠覆了 WiredTiger 标签和用户在 MongoDB 中看到的内容之间的关系，”黑钢说。

黑钢预测，这种变化不会像从一开始就为时间序列设计的数据库那样执行，但是，它会使 MongoDB 中的任何时间序列操作更快——这是 MongoDB 特性集的一个非常受欢迎的补充。

这是 Percona 观察到的路线图中的另一个请求，也是在大约一年前完成的，但不在 5.0 发行说明中。但是，在这种情况下，应该注意的是，仍然有几个方面的时间序列收集仍然显示为正在工作，包括这个目前悬而未决的[相关的错误](https://jira.mongodb.org/browse/SERVER-54042)。不过这已经确认是 5.0 的一部分了。

最后，在 MongoDB 5.0 发布之前，我们无法确定它会带来什么，但我们期待下周的 GA 发布。与此同时，我们将于 7 月 13 日和 14 日在 MongoDB.live 与您见面——注册仍然开放。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>