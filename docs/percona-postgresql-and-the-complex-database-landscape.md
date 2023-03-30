# Percona、PostgreSQL 和复杂的数据库环境

> 原文：<https://thenewstack.io/percona-postgresql-and-the-complex-database-landscape/>

根据 [Percona](https://www.percona.com/) 的一项新的[调查](https://www.percona.com/open-source-data-management-software-survey)，随着越来越多的组织在多个环境中使用多个数据库，开源数据库的世界只会变得更加复杂。

“长期以来，我们一直努力尝试降低公司系统的复杂性，尤其是在数据库领域。佩尔科纳首席体验官[马特·扬科维奇](https://www.linkedin.com/in/myonk/)说:“现在发生的事情与简化正好相反，它让事情变得更加复杂，也让事情变得更加支离破碎。

调查结果包括:

*   超过 90%的调查对象在他们的组织中使用一种以上的数据库技术，85%的人使用一种以上的开源数据库技术。
*   到目前为止，超过一半的人避开了公共云，选择了允许轻松部署和扩展的替代方案，但在一个更“动手”的环境中。
*   然而，超过 38%的受访者表示，他们正在使用一个以上的云部署，包括单个或多个提供商。
*   超过 60%完成调查的公司不使用数据库即服务(DBaaS)。
*   超过 25%的受访者使用容器，但不一定是为了运行数据库。许多回答者不知道他们是否为他们的数据库使用容器。
*   许多公司正在测试在他们的数据库环境中使用 Kubernetes，但是只有三分之一的受访者在生产中使用它。报道的实验水平表明这个数字将会增加。

根据 Yonkovit 的说法，一个有趣的发现是有多少数据库是重叠的。

“Postgres 和我的 SQL 之间一直存在巨大的鸿沟。自从这两种产品问世以来，这一直是一场激烈的争论。但我们发现，44%的受访用户实际上两者都用，”他说。

尽管多云和混合环境正在增长，但 DBaaS 的使用率仍然较低，这在一定程度上归因于 Yonkovit 对供应商锁定的担忧。DBaaS 的可移植性仍然存在问题，DBaaS 技术不一定能很好地协同工作，这给 Percona 带来了潜在的商机。

本周，Percona 在阿姆斯特丹的 Percona Live Europe[上发布了它的 PostgreSQL](https://www.cvent.com/events/percona-live-open-source-database-conference-europe-2019/event-summary-6321c2468b1b43328f97212f3e53f4de.aspx) 。

[dbinsight](https://www.dbinsight.io/) 的首席分析师 Tony Baer 将 Percona 描述为[“牧羊人”](https://www.zdnet.com/article/percona-herds-the-open-source-cats/)，它实现了 MySQL 和 MongoDB，消除了不兼容和参差不齐的文档的粗糙边缘，并添加了自己的企业部分。

Yonkovit 说:“Postgres 确实是所有最流行的开源数据库中最开放的。因此，许可是非常开放的，很容易做出贡献，它有大量的追随者和大量的贡献者。…生态系统中有许多出色的扩展、功能和开源工具。所以有很多可以借鉴的地方，但问题是，很多都不一定能一起工作。

“很明显，很多这些组件已经存在，你只需要以一种设计好的方式打包它们，使它们能够协同工作，并最大限度地减少这些组件和扩展之间的错误和摩擦。”

他说，在一年多前 Percona 推出对 Postgres 的支持后，客户说他们正在寻找真正开放的东西，而不是将他们局限于 EnterpriseDB 这样的供应商。

该发行版基于 PostgreSQL 的 v11.5，采用了一些最流行的扩展来平滑。它们包括:

*   pg_repack ，一个流行的第三方扩展，用于重建 PostgreSQL 数据库对象，而不需要表锁。
*   **pgaudit** ，第三方扩展，通过 PostgreSQL 中的标准日志记录功能提供深入的会话和/或对象审计日志记录。
*   **pg back back**，一款备份工具，替代内置 PostgreSQL 备份产品进行扩展。它使用流压缩来帮助公司最大限度地减少存储需求，并使用增量恢复来显著减少完成恢复所需的时间。
*   **Patroni** ，PostgreSQL 实现的高可用性解决方案，它提供了设置复制的能力，然后能够在需要时进行故障转移和提升备用数据库。

Yonkovit 说，所有关于扩展的工作都将被发布回社区。它将每三个月发布一次新的扩展。

该公司的[监控和管理工具](https://www.percona.com/software/database-tools/percona-monitoring-and-management)也将支持 PostgreSQL，以及 MySQL、MongoDB 和 MariaDB。自 2016 年首次推出以来进行了重写。它提供详细的查询分析；服务级别仪表板；标记以便于对服务器进行分组分析；一个 API 来添加、更改或删除节点，增强安全性等等。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>