# 微软为 Linux 和容器准备 SQL Server 2017

> 原文：<https://thenewstack.io/sql-server-2017-brings-microsofts-database-linux-container-worlds/>

微软的第一个候选版本 [SQL Server 2017](https://www.microsoft.com/en-us/sql-server/sql-server-2017) 于本周推出，为该版本的主要新功能增加了一些较小的更新，该版本距离 SQL Server 2016 仅一年多一点。最著名的新特性是支持 Linux (RHEL、SUSE Enterprise Linux 和 Ubuntu)，以及运行在 Windows、Linux 和 macOS 上的容器；这包括与 Pacemaker 等本机 Linux 集群工具集成的始终在线可用性组，以实现高可用性。

RC1 通过使用域凭证和使用[传输层安全](https://tools.ietf.org/html/rfc5246) (TLS)加密方案(1.0、1.1 或 1.2)来加密从客户端应用程序传输到 Linux 上的 SQL Server 的数据，将对 Windows 或 Linux 客户端的微软活动目录认证系统的支持添加到 Linux 上的 SQL Server。

[机器学习](/category/machine-learning/)也是一个重点，项目经理[托尼·彼得罗相](https://github.com/tonypet)告诉新堆栈。SQL Server 2017 可以使用 R 或 Python 运行数据库内分析，而无需提取和转换数据来使用它。

“为了在 SQL Server 2017 中添加对 R AI 和机器学习工作负载的支持，我们建立了一个可扩展性模型，”他解释道，“因此我们可以在 R 环境和 SQL 之间的数据交换的快速路径上使用 SQL Server 执行 R 运行时。这意味着您可以将 R 脚本作为代码的一部分来执行，但有了这种可扩展性，启用 Python 的额外工作就相当少了。”

这不仅证明了可扩展性模型是灵活的，还意味着“我们避开了数据科学家之间关于 R 与 Python 孰优孰劣的争论；我们将两者兼而有之。”RC1 还为 Windows Server 上的 R 服务添加了本地评分和外部库管理。

SQL Server 2017 是一个很好的例子，说明了微软首先在 Azure 中构建功能，然后将它们带到其内部服务器产品中。除了[与](https://blogs.technet.microsoft.com/dataplatforminsider/2017/04/20/graph-data-processing-with-sql-server-2017) [Azure SQL 数据库](https://azure.microsoft.com/en-us/services/sql-database/?v=16.50)相同的图形数据特性之外，SQL Server 2017 还获得了为 Azure 数据库开发的[自适应查询处理](https://docs.microsoft.com/en-us/sql/relational-databases/performance/adaptive-query-processing)性能改进，以通过监控先前查询的运行情况来优化查询的运行方式(这对查询性能有重大影响)。

“这有助于我们在执行并行查询和并发查询时更有效地使用资源，”Petrossian 解释道。“优化器可以根据获得的执行统计数据来调整其行为，而不仅仅是试图预测未来会发生什么。因此，客户将能够运行更大的查询和更多的并发查询。”

最初，它有三种模式，两种是批处理模式，一种是交错执行模式。现在 SQL Server 已经有了自适应优化的基础结构，未来的版本将在整个数据库引擎中扩展这一基础结构。

## 生产就绪

彼得罗相说，RC1 已经接近最终版本。“我们已经基本完成了工作，除非我们发现一些严重的错误，否则就这样了。”

和往常一样，新版本在正式发布之前不会得到完全支持，但是如果您想要新特性，客户可以在生产中使用它。一些客户已经在这么做了，其中一些得到了微软的正式支持，以帮助测试新版本，作为早期采用计划的一部分。Petrossian 告诉我们，“我们也有几个客户只是自己做了，没有告诉我们，”尽管他指出这些是“较小的工作负载，正在尝试。”

金融分析公司 [dv01](https://www.dv01.co/) 最初在 Python、Amazon RDS PostgreSQL 和 Redshift 数据仓库上创建了债券和贷款的报告和分析 SaaS 工具，但遇到了性能和规模问题，一些查询花费的时间超过了 30 秒的超时限制。很快，工程师们花更多的时间调优数据库查询，而不是构建新功能。

[为了获得更好的性能和数据库内分析](https://customers.microsoft.com/en-us/story/dv01)，他们转向了 SQL Server 2016，这意味着在 Azure 上使用 Windows Server。查询时间减少到 1-2 秒，更好的数据压缩将所需的存储量减少了两到三倍，此外，数据在内存和磁盘上都进行了加密。由于他们的其他系统运行在 Linux 上，大多数工程师使用 MAC，经过几个月的测试，他们将 40 个生产数据库迁移到运行在 Linux 上 Docker 中的 SQL Server 2017 CTP2。

Petrossian 解释说，正是这种情况促使微软将 SQL Server 引入 Linux。“除了人们使用 Linux 这一显而易见的原因之外，我们的一大动力是，许多容器和私有云技术都构建在 Linux 基础架构之上，我们希望 SQL Server 成为现代 IT 生态系统的一部分，无论是在公共云还是私有云，也无论它在哪里。现在，我们已经在 Docker 中运行了 SQL Server，您可以将 SQL Server 部署在由 Kubernetes 等管理的容器服务中。”

“对于生产用途，我们说客户可以在 Docker 容器中小心使用 SQL Server 的 Linux 映像。我们并不是建议人们将 500TB 的数据库放在一个容器中，而是有很多较小的工作负载在容器中运行，”他说。

Windows 对 SQL Server 容器化的支持在 RC1 还不太先进。“我们在 Windows 容器中也有 SQL Server 我们正在努力。在 Windows 方面，我们建议将其用于 devtest，但不要用于生产；在一些方面，我们仍然需要进一步完善，做更多的工作。”

Petrossian 说，容器支持甚至会引起传统 Windows 服务器客户的兴趣。“我认为，当谈到便利性和开发人员的工作方式时，随着它的发展，人们会看着他们的同行，说‘这似乎是一种简单的工作方式。’如果你能在 Linux 上做到，为什么不能在 Windows 上呢？"

他将对容器的谨慎与虚拟化的早期进行了比较。“我记得人们说过，由于性能等原因，没有人会在虚拟机中运行数据库。当然，时间已经证明这是错误的，人们一直在数据库中运行虚拟机。您会听到很多关于容器的相同问题:性能如何，容器是短暂的，那么存储会发生什么变化？所有这些都已修复或正在修复或正在改进，我们认为容器在获得采用方面将与虚拟机有相似的途径，但速度要快得多。”

有了这一新版本，SQL Server 不再被排除在 IT 基础架构的这一转变之外。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>