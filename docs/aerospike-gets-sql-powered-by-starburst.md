# Aerospike 获得 SQL，由 Starburst 提供支持

> 原文：<https://thenewstack.io/aerospike-gets-sql-powered-by-starburst/>

由实时数据平台供应商 [Aerospike](https://aerospike.com/) 最新发布的 Starburst 提供支持的 Aerospike SQL 的两重性非常重要。该解决方案象征着 Aerospike 和分析引擎专家 [Starburst](https://www.starburst.io/) 之间的合作伙伴关系，使组织能够在 Aerospike 的 NoSQL 数据库上运行 Starburst SQL 查询。

这些质疑来自 Aerospike 首席产品官 [Lenley Hensarling](https://www.linkedin.com/in/lenleyhensarling) 所谓的“Presto Trino”。除了允许 SQL 访问 Aerospike 的 NoSQL 数据之外，该产品还有效地将 Aerospike 引入了 Starburst 支持的现代分布式数据架构。

亨萨林说，该解决方案的好处通过“一个双赢的设置延伸到最终用户和各个供应商，有时我们出售这个，这导致人们说‘我可以将这个用于其他数据源’，这为[Starburst]带来了业务”。“当他们进入时，有时人们会说，‘这会对 Aerospike 起作用吗，因为我一直在考虑使用它，但我的合规人员无法访问数据。’"

由 Starburst 支持的 Aerospike SQL 使数据访问民主化，因此从合规团队到分析师，任何熟悉 SQL 的人都可以使用 Aerospike 的实时 NoSQL 数据。该产品为 Aerospike 的低延迟数据库带来了全新的用户群，大大拓宽了其在整个企业中的价值。

## **SQL 访问的威力**

Aerospike 的实时 NoSQL 数据库主要限于需要金融交易、经纪公司、广告技术或边缘部署的低延迟应用程序的开发人员或数据科学家。新版本(包括 Aerospike 与基于 SQL 的联邦查询引擎 Trino 的连接器，通过仅限于 Aerospike 数据的许可)将数据扩展到整个企业。第一个优势是，任何不熟悉 Aerospike 编程的业务角色现在都可以使用“他们最喜欢的工具，如 Tableau 或 [DBeaver](https://dbeaver.io/) ”来访问这些数据。

因此，这种以前难以访问的数据现在变得对业务报告、分析、审计或组织可能对其有任何其他用途非常有用。其次，这个更广泛的用户群可以利用 SQL 访问 NoSQL 数据，如键值对、图模型、文档结构(JSON)等等。“当你使用 Presto Trino 时，我们会检查数据库中的数据结构，并将其放入看起来像 SQL 模式的内容中，”Hensarling 评论道。"这是《星爆》魅力的一部分."随后，SQL 成为半结构化和非结构化数据的网关，而不仅仅是结构化数据。

## **分布式数据架构**

Aerospike 通过支持其 Aerospike 数据库 6 中的二级索引来协助上述过程，这与 Trino 的下推相结合，提高了其性能。“在索引可用的地方，Starburst 使用它们，所以我们对这些类似 SQL 的查询更敏感，”Hensarling 说。此外，由 Starburst 支持的 Aerospike SQL 将 Aerospike 的实时适用性转移到分布式数据架构 Starburst champions 中。后者的数据虚拟化、查询联合和数据具体化功能支撑了数据结构和数据网格部署的一些基本发展。

然后，用户可以随意与 Aerospike 与 SQL——以及“Oracle、PostgreSQL、MySQL 和 Cassandra 等其他数据源联合，同时允许我们成为现代数据网格的一部分，”亨萨林解释道。将 Aerospike 的实时数据与这些额外的来源结合起来，增强了所有企业数据的价值，因此用户可以跨这些数据进行查询。“大型企业目前的情况是，他们拥有本地所有权，但他们希望拥有全球视野。也许对于给定的应用程序，他们有数据。但是《星爆》允许你把它提供给其他人。即使你在 Aerospike 上有多个应用程序，每个应用程序都有自己的集群，Starburst 也可以让你一起查看这些数据。”

## **关键要点**

尽管基于 SQL 访问 NoSQL 数据源、格式和结构并不新鲜，但它对企业具有持久的价值。在这种情况下，通过使更多不同的用户能够访问填充 Aerospike 数据的实时数据，就好像它是结构化的一样，这种能力可能会增加 Aerospike 平台的吸引力。

此外，即使是对数据结构和数据网格的长期效用持最大怀疑态度的人也必须承认跨数据源提供统一访问的优点。数据环境继续变得更加分散的事实进一步强化了这种需求。“这是 Aerospike 积累的数据价值的一大进步，”Hensarling 总结道。“它允许我们用 SQL 访问我们的数据。但它也将我们带入了星爆的生态系统，这样我们就可以联合起来。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>