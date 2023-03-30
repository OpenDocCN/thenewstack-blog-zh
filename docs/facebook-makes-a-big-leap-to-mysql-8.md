# 脸书向 MySQL 8 迈出了一大步

> 原文：<https://thenewstack.io/facebook-makes-a-big-leap-to-mysql-8/>

尽量不要将重要基础设施软件的升级推迟到多个版本，如果您确实要对开源项目进行定制代码更改，请做好准备，当软件的更新版本出现时，再集成这些补丁。

这些只是你可能从脸书周四发布的博客文章中收集到的几个教训，该文章记录了该公司从其一直使用的[甲骨文](https://developer.oracle.com/?utm_content=inline-mention)开源 MySQL 数据库系统的古老 5.6 版本到 MySQL 8.0 版本的有时充满危险的大规模跨越式迁移。

是的，尽管事实上脸书已经创建了 [Cassandra](https://thenewstack.io/apache-cassandra-persistent-data-storage-for-scalable-microservices-applications/) ，一个可扩展的 NoSQL 商店，现在由 [Datastax](https://www.datastax.com/?utm_content=inline-mention) 管理，根据帖子的作者，脸书生产工程经理[帕拉德普·纳亚克](https://www.linkedin.com/in/pradeep1288/)和脸书软件工程师赫尔曼·李的说法，这个社交媒体巨头仍然使用名副其实的 MySQL 传统关系数据库来存储数 Pb 的有价值的用户信息。到目前为止，一家公司已经花了近一年的时间从 2013 年首次发布的 5.6 版本迁移到 MySQL 8.0，对 MySQL 8.0 的支持将于今年结束。甲骨文在 2018 年推出了 MySQL 8.0。

## 5.7 很难通过

![](img/39d72d15deca19473bde632a09f1e576.png)

该公司跳过了完全升级到 MySQL 5.7 版本，这是 5.6 到 8.0 之间的主要版本。工程师们写道，当时，脸书正在为 MySQL 构建名为 MyRocks 的定制存储引擎，不想中断实现过程。MyRocks 是对 [RocksDB](https://rocksdb.org/) 的 MySQL 改编，这是一个针对快速写入性能[进行优化的存储引擎，Instagram 为优化 Cassandra](https://thenewstack.io/instagram-supercharges-cassandra-pluggable-rocksdb-storage-engine/) 而构建。脸书本身正在使用 MyRocks 来支持其“用户数据库服务层”，但需要 MySQL 8.0 中的一些功能来完全支持这种优化。

然而，跳过版本 5.7 会使升级过程变得复杂。“跳过 5.7 这样的主要版本带来了问题，我们的迁移需要解决这些问题，”工程师在博客中承认。服务器不能简单地就地升级。他们不得不使用逻辑转储来捕获数据，并从头开始重建数据库服务器—在某些情况下，这项工作需要几天时间。从 5.6 到 8.0 的 API 变化也必须根除，在一个副本集中支持两个主要版本是非常棘手的。

在这项工作开始时(仍在进行中)，该公司有 1，700 个最初为 5.6 编写的代码补丁需要以某种形式移植到 8.0。一些在 5.7 中被弃用的 API 在 8.0 版本中被完全删除，这意味着脸书开发人员不得不重写依赖这些旧 API 的应用程序代码。

更新团队将所需的补丁分类到多个不同的桶中，将相同功能的多个补丁组合在一起。脸书的一些补丁根本不需要结转，因为它们提供的功能后来被 8.0 本身覆盖了。还有一些非服务器特性需要移植，比如支持构建环境的特性、修改 MySQL 工具(如 mysqlbinlog)的特性，或者增加功能(如异步客户端 API)的特性。

一些最复杂的功能需要对 8.0 进行重大修改才能正常工作。到这篇博文发布时，该团队已经评估了 2，300 个补丁，其中 1，500 个进入了 8.0。

## 把它移过去

实际的迁移工作包括将多个 mysqld 实例(实际的 MySQL 核心守护进程)聚集成更大的复制集，使用特制的软件来自动执行在大型复制集组上进行转换的过程。每个复制集(可能跨越不同的数据中心)都有一个主实例和许多辅助实例。转换策略是使用 mysqldump 通过逻辑副本创建和添加 8.0 辅助节点，然后采取以下步骤进行转换:

*   在 8.0 辅助节点上启用读取流量。
*   允许 8.0 实例升级为主实例。
*   为读取流量禁用 5.6 实例。
*   删除所有 5.6 实例。

为了验证迁移是否可行，团队编写了自动化软件的集成测试，该测试在一个测试环境中运行，该环境暴露了许多小的边缘案例风格的错误。对于 MyRocks 迁移，该团队构建了一个 MySQL 影子测试框架，该框架捕获生产流量并将其重放给测试实例。

Nayak 和 Lee 断言，迁移工作仍在继续，但脸书已经享受到了 MySQL 8.0 的好处。例如，一些应用程序正在使用新的特性，如[文档存储](https://www.mysql.com/products/enterprise/document_store.html)和改进的[日期时间支持](https://dev.mysql.com/doc/refman/8.0/en/mysql-nutshell.html)。

“总的来说，新版本大大扩展了我们在脸书可以用 MySQL 做的事情，”他们写道。

关于所有的细节，请点击这里查看[的博客文章](https://engineering.fb.com/2021/07/22/data-infrastructure/mysql/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>