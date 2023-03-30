# ServiceNow 在其 Now 平台上加速数据库操作

> 原文：<https://thenewstack.io/servicenow-plans-to-hasten-database-ops-on-its-now-platform/>

企业数字工作流服务提供商 [ServiceNow](https://www.servicenow.com/) 正在努力加速其数据库操作，以扩展该公司旗舰 [Now 平台](https://www.servicenow.com/now-platform.html)的可扩展性。

该公司最近宣布有意收购总部位于柏林的数据库加速技术制造商 [Swarm64](https://swarm64.com/) ，试图为其客户提供越来越大、越来越智能的工作流。

Swarm64 开发了 Swarm64 DA，这是一个 [PostgreSQL](https://www.postgresql.org/) 数据库扩展，可以提高 SQL 查询性能并简化缩放，ServiceNow 平台工程高级副总裁[乔·戴维斯](https://www.linkedin.com/in/jdavissd/)在[博客文章](https://blogs.servicenow.com/2021/servicenow-to-acquire-swarm64.html)中说。该扩展显著提高了标准 Postgres 数据库的性能和可伸缩性。

Davis 说，ServiceNow 现在使用 PostgreSQL 作为其平台数据库之一，并打算在未来更广泛地使用它。

“Swarm64 在数据库性能和可扩展性方面的专业知识使我们能够通过帮助我们为客户提供越来越大、越来越智能的工作流来规划未来，”戴维斯告诉新堆栈 Swarm64 获得的功能对于 Now 平台的未来规模和性能非常重要，即利用内核数量大幅增长的 CPU 来提高性能。当前的平台功能已经并将继续支持我们客户的当前和即时需求。"

Swarm64 的技术专注于两个关键领域的改进:第一，通过支持混合分析和事务工作负载的列索引添加了[混合事务分析处理(HTAP)](https://www.gartner.com/en/information-technology/glossary/htap-enabling-memory-computing-technologies) 功能；第二，通过利用前面提到的用于[并行处理](https://searchdatacenter.techtarget.com/definition/parallel-processing)的大量内核来改进查询优化器和并行执行，从而实现极高的性能和规模，Davis 在采访中说道。

“Swarm64 基于开源的数据库技术非常适合大规模数据集；我们计划将 Swarm64 基于开源的数据库技术集成到我们的核心数据平台中，为我们的数据处理能力和 API 提供无缝补充，”他说。

虽然 ServiceNow 声称没有另一家公司完全像 Swarm64 那样做——即，为 HTAP 和并行执行改进提供 Postgres 扩展，以显著提高性能和规模，但“还有其他[公司](https://thenewstack.io/timescale-hyperfunctions-ease-postgresql-query-complexities/)提供 Postgres 扩展，拥有不同的架构，解决略有不同的问题，但它们处于不同的领域；我们不是在与这些公司竞争，而是将它作为一项技术添加到我们的核心平台，以支持我们行业领先的工作流程。”

另一家建立在 PostgreSQL 之上的公司是[时标](https://www.timescale.com/)，它提供了一个时序 SQL 数据库，通过自动化数据管理提供快速分析和可伸缩性。

“在 Postgres 之上有许多有趣的项目，”时标营销副总裁[普拉尚·斯里德哈兰](https://www.linkedin.com/in/prashantsridharan/)说。“显然，TimescaleDB 就是其中之一。微软前阵子又买了一个( [Citus Data](https://blogs.microsoft.com/blog/2019/01/24/microsoft-acquires-citus-data-re-affirming-its-commitment-to-open-source-and-accelerating-azure-postgresql-performance-and-scale/) )。这就是 Postgres 的魅力所在:它是一个平台，使人们能够在其上建立许多不同类型的专门数据库。我们正处于专用数据库的时代，选择基于 Postgres 的选项使您能够解决新问题，同时保持与其他业务数据的兼容性。”

数字化转型的组织需要一种混合数据库模型来利用事务和分析，以便交付智能工作流。

“由于我的 SQL Server 背景，我有偏见，但基本上，我将 my SQL 和 Postgres 视为具有广泛功能的商品数据库，但它们在性能方面不如商业 RDBMS 平台优化，”总部位于纽约的专门从事 BI、数据分析和数据库争论的 IT 咨询公司 [Blue Badge Insights](https://www.bluebadgeinsights.com/) 的首席执行官 [Andrew Brust](https://www.linkedin.com/in/andrewbrust/) 说。

因此，Brust 说，有各种独立的解决方案可以为他们创建企业发行版和/或加速他们的性能，“因为有很大的改进空间，”他指出。

此外，“如果像 ServiceNow 这样的公司已经在 Postgres 上实现了标准化，那么很明显，他们将从加速技术中受益，成为他们堆栈的一部分，”Brust 说。“收购一家公司可能是有意义的，而不是继续许可其产品，并担心它可能被其他人收购，这些人可能只是整合他们的平台，而不是继续作为一个独立的产品销售和支持它。”

随着 Swarm64 技术的加入，ServiceNow 将帮助客户管理许多不同用例的数据，以大规模执行复杂的高速数据分析。

用户期望并要求快速的用户体验，而管理大型数据集对此至关重要。

“借助 Swarm64，ServiceNow 客户可以比以往更快地查询更多数据源，”Davis 说。“我们将继续为企业带来消费者般的体验。Swarm64 结合了分析和事务数据库功能，不仅能够支持智能工作流，还能为我们的客户提供一流的性能和可扩展性。我们预计 Swarm64 的技术将更好地支持各行业的客户在 Now 平台上快速扩展大型工作流。"

例如，电信组织正在经历网络资产数量的爆炸式增长，包括交换机、路由器、设备以及处理电信网络和带宽分配的一切设备，这就需要存储和查询大量的整合数据。戴维斯说，有效利用这些数据是创造新的收入来源、为客户和员工创造高度个性化的体验以及释放整个企业生产力的基础。

此次收购预计将于今年第三季度完成。Davis 说，ServiceNow 将“本机重新平台化”Swarm64 技术，以便 ServiceNow 开发人员、客户和合作伙伴能够利用该技术，而不必重构他们的应用程序或对他们的工作流程进行任何更改。

“该平台将透明地动态利用这项技术来处理适当的工作负载，”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>