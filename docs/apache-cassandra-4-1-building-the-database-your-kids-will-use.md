# Apache Cassandra 4.1:构建您的孩子将使用的数据库

> 原文：<https://thenewstack.io/apache-cassandra-4-1-building-the-database-your-kids-will-use/>

Cassandra 4.1 将于 7 月发布，所以现在是回顾过去一年并反思我们作为一个项目的进展的好时机。我们承诺了每年一次的节奏，你猜怎么着？我们遵守了诺言！

如果你已经有一段时间没有看 Cassandra 社区了，那么它是一个繁忙的地方。我知道你们中的许多人都有几年前安装的 Cassandra 集群，但是完全忘记了。从本质上来说，一个好的数据库应该是枯燥和容易被遗忘的。总是在那里准备好的东西。我们邀请您回来看看有什么新东西。告诉我们你的绝对无聊的数据库。也许你的未来会升级？让我告诉你接下来会发生什么。

## 稳定是一个特点

 [帕特里克·麦克法丁

帕特里克是《在 Kubernetes 上管理云原生数据》一书的合著者。他目前在 DataStax 的开发者关系部门工作，并且是 Apache Cassandra 项目的一名贡献者。Patrick 曾是 Apache Cassandra 的首席布道者和 DataStax 的顾问，在那里他度过了构建一些最大的生产部署的美好时光。](https://www.linkedin.com/in/patrick-mcfadin-53a8046) 

Cassandra 4.0 标志着一个有 10 年历史的数据库的重要里程碑。该项目投入了大量资源来构建定义和验证稳定数据库的工具。这些工具都集成到构建和发布管道中，以确保任何未来的更改都经过彻底的测试，并且不会引入回归。

结果是有史以来最稳定的数据库之一。在过去的一年中，团队一直在以惊人的速度部署 4.0 集群，到目前为止，报告都是非常积极的。稳定性是数据库的杀手锏，如果世界依赖 Cassandra 存储关键数据，我们非常高兴它实现了这一承诺。

你知道数据库的另一个致命特征是什么吗？发布新功能。在 3.11 和 4.0 之间有一段令人遗憾的时间，但是有了一个坚实的基础，我们现在正以有规律的节奏前进。Cassandra 4.1 目前处于预发布阶段，正朝着我们每年发布主要版本的目标前进。在 4.0 中完成的所有验证工作都得到了回报，构建管道在 Cassandra 中构建新功能时给了贡献者信心。

## 4.1 闪亮的新东西:可插拔性

那么，我们从这个数据库中得到什么，并在一个稳定的核心上进行构建呢？Cassandra 4.1 的主题是启用特性插件。你会问，为什么插件是有用的新事物？这是在不改变核心代码的情况下向现有产品添加功能的结构化方法。对于 Cassandra，这意味着在不改变 Cassandra 的情况下添加重要的新功能。这将在数据库的主要版本之间推动不同种类的创新。

这个想法的早期推动者之一是 Instagram。他们构建了一个 Cassandra 版本，使用 RocksDB 作为底层存储引擎，名为 [Rocksandra](https://thenewstack.io/instagram-supercharges-cassandra-pluggable-rocksdb-storage-engine/) 。它从根本上改变了我们对 Cassandra 存储的看法，而没有改变网络和节点协调。它还提出了两个需要解决的不同问题。首先是 Cassandra 内部需要一个清晰的接口，这样当使用外部代码时，它们之间有一个可以理解的契约。

Rocksandra 团队必须依靠对 Cassandra 内部的深入了解来使其工作。第二是有一个可靠的测试框架。Instagram 了解其用例，并有自己的验收测试。然而，对于一个通用的数据库，需要有更大范围的功能测试。部分基于这些经验教训，这两个问题都在该项目中得到了解决。

4.1 中提供的一些新插件功能包括:

*   [存储](https://cwiki.apache.org/confluence/display/CASSANDRA/CEP-11%3A+Pluggable+memtable+implementations) —该功能谈到了 memtables，但这些被转换为底层存储，因为它们被映射为由 Cassandra 读写。期待看到一些关注特定用例的有趣实现，包括快速内存存储和列格式。
*   [网络加密](https://cwiki.apache.org/confluence/display/CASSANDRA/CEP-9%3A+Make+SSLContext+creation+pluggable) —在此变更之前，任何 SSL 证书都必须存在于本地文件系统中。这一更改允许外部密钥提供者(如 HashiCorp Vault)在大型部署中简化密钥管理。
*   [身份验证](https://cwiki.apache.org/confluence/display/CASSANDRA/CEP-16%3A+Auth+Plugin+Support+for+CQLSH) —对于管理大量基础架构的大多数组织来说，外部集中式身份验证是一项理想的功能。这一改变允许 Cassandra 命令行工具 CQLSH 使用 LDAP、Kerberos 和其他工具。
*   [模式](https://issues.apache.org/jira/browse/CASSANDRA-17044) —集群模式作为唯一选项存储在系统表中。对于全局协调，尤其是在 Kubernetes 中，现在可以选择外部模式存储，比如 etcd。
*   [护栏](https://cassandra.apache.org/_/blog/Apache-Cassandra-4.1-Features-Guardrails-Framework.html) —全球运营商欢欣鼓舞！现在，您有能力在生产环境中限制反模式。例如，限制可以添加到表中的索引数量。这已经与 [DataStax Astra](https://dtsx.io/3xDSOR7) 一起使用，这是我们管理的 Cassandra 服务，已捐赠给该项目。

## 而现在，未来！ACID 交易和更多

4.1 之后的 Cassandra 的未来将是 5.0，那些讨论已经如火如荼了。这是为增长而设计的数据库，也是为未来几年而构建的云原生应用程序。Apache Cassandra 的下一个 10 年是在过去 10 年的坚实基础上迎接挑战的 10 年。

最具变革性的 5.0 新功能可能会让你震惊，但我们开始了:卡珊德拉将添加[全酸交易](https://cwiki.apache.org/confluence/display/CASSANDRA/CEP-15%3A+General+Purpose+Transactions)。

如果你的阵营中有人说你永远不能使用 Cassandra，因为它“不支持交易”，那么准备在你的生活中为更多的 Cassandra 腾出空间。Cassandra 2.0 在 [Paxos](https://en.wikipedia.org/wiki/Paxos_(computer_science)) 的基础上增加了我们所说的“轻量级事务”。为了保持 Cassandra 提供的保证，同时不破坏性能，Paxos 是当时的正确选择。自 2013 年以来，出现了新的共识协议，如 Spanner 和 Raft，这两种协议在数据库领域都非常受欢迎，但它们需要的权衡与 Cassandra 用户期望的线性规模和正常运行时间保证不一致。

我们需要的是下一代分布式共识协议。这已经在一个被称为 Accord 的协议中被描述，该协议在一个往返行程中达成一致，并且不需要复杂的领导者故障转移机制。简而言之，它使卡珊德拉成为卡珊德拉，同时交付完整的 ACID 事务。我们现在正在构建它，因此如果您想加入对话，我们将非常感谢您的参与。

对于 Cassandra 来说，一个更具体但重要的方向是转向更加云原生。添加插件和调整 Cassandra 集群部署的能力是朝着正确方向迈出的一步。Kubernetes 中的无服务器数据库是未来的发展方向，而 Cassandra 在未来几年内很有可能成为这样的数据库。DataStax 发布了一份基于 Cassandra 的云原生数据库白皮书[,这可能是未来的蓝图。](https://dtsx.io/39cEuG2)

对于最终用户而言，这意味着无需手动操作即可实现扩展，以及多个应用程序共享同一基础架构的真正多租户。对于运营商，尤其是站点可靠性工程师，有原生的 Kubernetes 部署，将计算与存储分开，以便独立扩展。最重要的是:您只异步提供您需要的东西，以节省那些不断增长的基础设施费用。

## 庆祝的时间到了

去年，我们为 4.0 的发布开了一个派对，今年也不会有什么不同！卡珊德拉世界派对是一个时长一小时的在线活动，我们将在 7 月 20 日的三个不同时间举行，覆盖尽可能多的时区。亮点将是五分钟的闪电对话形式，用户社区可以快速地开始并讲述他们的故事！

我们希望你能加入我们，和社区的其他人一起庆祝。如果你准备好迎接挑战，我们很想听听你的故事。请告诉我们您的主题以及您所在的时区。希望在那里见到你！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>