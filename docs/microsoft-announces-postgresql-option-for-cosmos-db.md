# 微软宣布 Cosmos DB 的 PostgreSQL 选项

> 原文：<https://thenewstack.io/microsoft-announces-postgresql-option-for-cosmos-db/>

今天在西雅图的 Ignite 会议上，微软首席执行官塞特亚·纳德拉宣布了对 T4 Azure Cosmos DB T5 的新的 PostgreSQL T3 支持。虽然 Cosmos 已经为 NoSQL 数据库技术支持了大量的[接口和 API](https://learn.microsoft.com/en-us/azure/cosmos-db/choose-api)，但此次发布标志着真正的*关系型*数据库解决方案首次在该平台上提供。微软表示，它还使 Azure 成为第一个在同一服务上支持关系和 NoSQL 选项的云平台。

我将在这里用一些技术深度来报道这条新闻。对于那些想要更深入了解的人，Cosmos DB 团队告诉我，他们将在 10 月 18 日举办一场两小时的在线活动[,内容涉及新 Postgres 产品的策略、概念和操作方法。](https://aka.ms/AzureCosmosDBLiftOff)

## 两个数据库合二为一？

TNS 采访了微软公司副总裁 Rohan Kumar，Azure Data，了解了一些有趣的架构细节。言归正传:Kumar 解释说，Azure Cosmos DB for PostgreSQL(微软的产品名称，如果有的话)是一种混搭，Cosmos DB 奠定了基础设施的基础，微软的分布式 PostgreSQL 引擎是在 2019 年[收购](https://blogs.microsoft.com/blog/2019/01/24/microsoft-acquires-citus-data-re-affirming-its-commitment-to-open-source-and-accelerating-azure-postgresql-performance-and-scale/) [Citus Data](https://www.citusdata.com/) 时获得的。“我们……采用了 Citus 的分布式查询处理引擎……并有效地将其覆盖在 Cosmos DB 之上,”Kumar 说。

这使得 Cosmos/Postgres 产品不同于任何 Cosmos API 选项，无论是核心 SQL、 [Azure 表存储](https://azure.microsoft.com/en-us/products/storage/tables/)用于键值访问、 [MongoDB](https://github.com/mongodb/mongo/blob/master/README.md) 用于文档存储应用程序、 [Gremlin](https://tinkerpop.apache.org/gremlin.html) 用于图形数据库工作负载，还是 [Cassandra](https://cassandra.apache.org/) 用于宽列存储实现。所有这些选项本质上都围绕同一核心技术提供了不同的语言/有线协议/API 组合，而 Postgres 选项提供了一个完全不同的查询引擎。也许这就是为什么它被称为 PostgreSQL 的 Cosmos DB，而不是相反。

## 兼容性程度

这里有一些重要的分支需要评估。首先，根据 Kumar 的说法，这“实际上是 Postgres 引擎”,而不仅仅是一个兼容层。Kumar 继续解释道，吸引微软加入 Citus 的是“他们并没有真正放弃与 Postgres 的兼容性。这很重要，因为你知道，如果你把 Postgres 引擎完全换掉，它就不再是 Postgres 了。”Kumar 补充道:“我们真的很喜欢他们使用 Postgres 的可扩展性模型来维护兼容性的方法，同时支持…一个隐藏在幕后的数据库。”(分片是跨多台服务器扩展和分区数据库的一项基本技术。)

这也意味着与大量 Postgres 扩展的兼容性也将出现。当然，由于 Cosmos DB 是一个托管平台，实际可用的扩展将是微软选择的。我特别问了一个问题——[PostGIS](https://postgis.net/)，一个非常流行的 Postgres 地理空间数据库扩展。Kumar 说，PostGIS 确实会得到支持，其他几个也会得到支持，并根据“它们的用途”进行优先排序。

Citus 引擎的使用还意味着对 Postgres 的 SQL 方言的完全支持，以及考虑到数据库的关系性质，完全的 ACID 合规性——即完全的查询一致性，而不是许多 NoSQL 平台中支持的“最终一致性”模型，甚至也不是其他 Cosmos DB 接口中提供的滑动比例一致性。

虽然 Kumar 说“今天我们基本上支持全局分布式读语义”，但还有一些其他的 Cosmos DB for Postgres 不会得到的习惯性 Cosmos 特性，至少在最初是这样。但库马尔说，“我们正在努力进一步增强和增加越来越多的能力。”他还告诉我，Cosmos for Postgres 用户将获得与所有 Cosmos DB 客户相同的[服务水平协议](https://azure.microsoft.com/support/legal/sla/cosmos-db/v1_4/)(SLA)。

## 哪些 Postgres？

这个故事还有一点非常有趣。PostgreSQL 的 Cosmos DB 将取代 PostgreSQL 的 [Azure 数据库——超大规模](https://learn.microsoft.com/azure/postgresql/hyperscale/overview)。事实上，微软告诉我，“所有[PostgreSQL —超大规模]客户和工作负载将自动转移到 Azure Cosmos DB for PostgreSQL。”这是一件大事。这意味着 PostgreSQL 的 Cosmos DB 现在将成为*Citus 分布式 Postgres 选项。这也意味着 Cosmos DB 正逐渐成为 Azure 的统一超大规模数据库平台。*

这就引出了一个问题:对于那些想将传统 Postgres 应用云化并迁移到 Azure 的用户来说，升级到 Cosmos DB for PostgreSQL 有可能吗？这种难以理解的“只需更改连接字符串并运行相同的代码”场景在这里能得到支持吗？

Kumar 的回答基本上是，虽然客户*可以*执行这种迁移，但他们不一定会看到这样做的好处或成本效益，除非他们的应用程序需要像 Cosmos DB 这样的全球分布式数据库，或者会有这种需求。因此，虽然 Kumar 没有用太多的话来说，但看起来客户应该将 PostgreSQL 的[Azure Database](https://learn.microsoft.com/azure/postgresql/hyperscale/overview)和 PostgreSQL 的 Cosmos DB 视为一对兼容的选项，每个选项都解决不同的数据库规模用例。

## 不要忽视基础

而说到 Azure 数据库，那么 [Azure SQL 数据库](https://azure.microsoft.com/products/azure-sql/database/)([SQL Server](https://www.microsoft.com/sql-server/)的云实现)及其 [T-SQL](https://learn.microsoft.com/sql/t-sql/language-reference) 语言呢？为什么微软不选择*那种*方言和接口作为它在 Cosmos 上的第一个关系头？不管怎样，微软有计划添加它吗？

我也问过库马尔这个问题。他的回答，本质上，是永远不要说永远。虽然 T-SQL/SQL Server 支持不在路线图上，但微软不会排除它。与此同时，微软对如何为 Cosmos DB 获得更多市场份额的理解是，首先支持一个流行的开源数据库，同时承认许多应用程序和服务都使用 Postgres，而这些显然是微软正在寻找的潜在客户。

这是一个合理的计算，但该公司也需要迎合其核心社区基础。当 Cosmos 被引入时，SQL Server 专业人员已经侧目看待它，这造成了某种隔阂。欢迎相同的社区和生态系统加入 Cosmos fold 是非常有意义的，并且可能有助于该平台。

当微软为 Power BI 提供 SQL Server Analysis Services(SSAS)一直拥有的全部功能时，这正是发生的事情。是的，Power BI 已经非常受欢迎，但是将 SSAS 社区及其技能集引入 Power BI 为平台增加了企业庄严感，扩大了帐篷，并重组了 Microsoft BI 社区。Cosmos DB 团队和更广泛的[微软智能数据平台](https://www.microsoft.com/microsoft-cloud/solutions/intelligent-data-platform)团队(具有强大的 BI 血统)可能想要考虑 Cosmos 和 SQL Server 的情况是否类似。

*披露:帖子作者 Andrew Brust 是微软数据平台 MVP 和微软独立影响者区域董事计划的成员。他的公司蓝徽洞察[[www.bluebadgeinsights.com](http://www.bluebadgeinsights.com/)]已经为微软做了工作，包括 Power BI 团队。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>