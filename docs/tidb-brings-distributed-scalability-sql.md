# TiDB 为 SQL 带来了分布式可伸缩性

> 原文：<https://thenewstack.io/tidb-brings-distributed-scalability-sql/>

一系列新的数据库已经出现，如 [Google Spanner](https://thenewstack.io/google-cloud-spanner-view-field/) 、 [FaunaDB](https://thenewstack.io/faunadb-harnesses-serverless-cloud/) 、[蟑螂](https://thenewstack.io/cockroachdb-unkillable-distributed-sql-database/)和 [TimeScaleDB](https://blog.timescale.com/time-series-data-why-and-how-to-use-a-relational-database-instead-of-nosql-d0cd6975e87c) ，它们专注于解决困扰标准 SQL 的规模问题。现在，另一个进入者，总部位于中国北京的 PingCap 的开源 TiDB 项目，旨在使其像 NoSQL 系统一样可扩展，同时保持 ACID 事务。

PingCap 联合创始人兼首席执行官齐(Max)刘(T13)表示，PingCap 对 MySQL 协议的支持意味着用户可以重用许多 MySQL 工具，并大大降低迁移成本。在大多数情况下，您可以使用它来替换 MySQL for applications，而无需更改任何代码。它是水平扩展的。只需增加更多的机器就能增加产能。

刘去年 10 月在阿姆斯特丹的 Percona Live 会议上展示了 TiDB。该项目当时处于测试阶段；从那时起，它就开始释放候选人。周四，PingCap 联合创始人兼首席技术官 Edward Huang 将在加州圣克拉拉的 Percona Live 活动上发表关于 TiDB 的演讲。

他们吹捧 TiDB 提供了 SQL 和 NoSQL 世界的精华。他们专注于制作:

*   使用方便；
*   确保没有数据丢失；它是从失败中自我修复的；
*   跨平台，可以在任何环境下运行；
*   和开源。

它还允许在线模式更改，因此模式可以随着您的需求而发展。您可以添加新的列和索引，而不会停止或影响正在进行的操作。

作为一个开源项目，它有 100 多个贡献者，刘在一次电子邮件采访中说。

PingCap 从 [Google F1](https://research.google.com/pubs/pub41344.html) 分布式数据库和 Spanner 中汲取了 TiDB 的灵感。谷歌在自己的专有系统上构建了 Spanner，它不是开源的，这对一些人来说是不利的。

“有了 Spanner，你就承诺在 [Google Compute Engine](https://cloud.google.com/compute/) (GCE)中运行服务，并且可能在服务的生命周期中一直在那里运行。如果你选择运行自己的堆栈，你就不会有障碍，”[蟑螂实验室](https://www.cockroachlabs.com/)的首席执行官[斯潘塞·金博尔](https://github.com/spencerkimball)之前告诉新堆栈。

## 跟踪所有的自行车

TiDB 采用松耦合的方法。它由 MySQL 服务器层和 SQL 层组成。它的基础是开源分布式事务键值数据库 [TiKV](https://github.com/pingcap/tikv) ，另一个 PingCap 项目，它使用编程语言 [Rust](https://www.rust-lang.org/en-US/) 和分布式协议 [Raft](https://www.infoq.com/presentations/raft) 。TiDB 是用 Go 写的。TiKV 内部有 MVCC(多版本并发控制)、Raft，对于本地键值存储，它使用 [RocksDB](http://rocksdb.org/) 。它也使用火花连接器。

TiDB 从扳手上作了两个区分，刘说:

而 Spanner 的底层依赖于 Google 的 [Colossus](https://www.wired.com/2012/07/google-colossus/) 分布式文件系统，TiDB 确保日志安全存储在 Raft 层。TiDB 不依赖于任何分布式文件系统，这大大降低了写入延迟。

“我们也看到了 SQL optimizer 的巨大潜力，但谷歌似乎没有在其 F1 论文中深入这一方面。在设计我们的项目时，我们旨在探索优化程序的能力，”他说。

Spanner 因使用原子钟在地理上分散的数据中心之间获得时间同步而受到关注。TiDB 不使用原子钟和 GPS 时钟。相反，它依赖于 Percolator 中引入的时间戳分配器，Percolator 是 Google 在 2006 年发表的一篇论文。

它支持流行的容器，如 Docker。该团队正在努力与 Kubernetes 合作，但对于这项工作，刘向阿姆斯特丹的观众指出了困难。

他说，他们现在面临的最大问题是延迟，尤其是地理上分散的数据中心之间的延迟，他希望在不久的将来解决这个问题。

PingCAP 由高级分布式系统工程师黄于 2015 年 4 月创立；[秋翠](https://www.linkedin.com/in/qiu-cui-39111467/)，高级系统工程师；刘也是一名基建工程师。它有 48 名工程师在北京工作，其他人在中国其他地方远程工作。

它的客户包括移动游戏提供商 GAEA T1，该公司使用 TiDB 来支持其跨平台实时广告系统，该系统需要高容量的数据容量，并在某些时段出现峰值负载。TiDB 支持自动分片，底层 TiKV 自动在集群中分发数据，这有助于 GAEA 降低运营和维护成本，刘说。

另一个客户是无现金和无车站的自行车共享平台[摩拜单车](http://www.mobike.com/global/)，它使用 TiDB 进行数据分析，并取代 MySQL 数据库进行在线订单，[现在数量超过 4 亿辆](https://thenewstack.io/will-dockless-bike-sharing-flood-cities-piles-bikes/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>