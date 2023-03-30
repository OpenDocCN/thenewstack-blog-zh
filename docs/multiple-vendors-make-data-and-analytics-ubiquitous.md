# 多家供应商使得数据和分析无处不在

> 原文：<https://thenewstack.io/multiple-vendors-make-data-and-analytics-ubiquitous/>

过去几周，分析领域的许多新老巨头都发布了大量新闻。在 2023 年第一季度结束之际，他们共同指出了该行业的一些重要趋势。尽管分析领域可能非常复杂，但开始感觉到重要的想法和标准正在坚持自己的观点，并获得广泛的采用。

数据湖技术的日益关键和标准化，人工智能和[机器学习](https://thenewstack.io/machine-learning/)的持续重要性，在云中进行分析的额外动力，数据集成的持续相关性，以及将分析技术嵌入主流生产力和[开发工具](https://thenewstack.io/making-tools-for-developers-here-are-some-basic-pricing-tips/)，都在新闻中发挥了作用。因此，让我们来看看过去几周内八家不同供应商发布的产品，并分析一下它们对行业意味着什么。

## 冰山一角

为了说明这些趋势，让我们从数据湖和湖屋的世界开始，在那里，开源的 [Apache Parquet](https://parquet.apache.org/) 文件格式及其衍生物，如 [Apache Iceberg](https://iceberg.apache.org/) 和 [Delta Lake](https://delta.io/) ，继续获得动力。在 3 月 1 日的 [Subsurface](https://www.dremio.com/subsurface/live/winter2023/) 活动中，data lake/lake house player[dre mio](https://www.dremio.com/)宣布了对其冰山表格格式支持的多项增强。这些功能包括使用新支持的 SQL 命令 COPY INTO 将数据复制到 Iceberg 表中；支持将多个文件合并成一个文件，使用 [Dremio Sonar](https://www.dremio.com/platform/sonar/) 中的新优化命令(现在也可以跨更多数据源联合)；并添加了新的 ROLLBACK 命令来将表返回到以前的特定时间或快照 ID。所有这些功能似乎可以让 Iceberg 与竞争对手 Delta Lake 格式中的类似功能相提并论，Delta Lake 格式最初是由 Databricks 开发的，但现在是在 Linux 基金会的支持下管理的开源技术。

正如我提到的，Delta Lake 和 Iceberg 本质上都是拼花格式的衍生物(尽管 Iceberg 在技术上也可以将其功能引入其他格式),这只能证明拼花在数据湖世界中的重要性。但是看起来它在[图形数据库](https://thenewstack.io/graph-databases-why-are-they-suddenly-popular/)世界中也变得越来越重要。图形数据库竞争者 [TigerGraph](https://www.tigergraph.com/tigergraph-db/) 也在 3 月 1 日宣布，它将增加对 Parquet 的支持，并提供摄取该格式数据的能力。TigerGraph 还在共享的可视化图形仪表盘上添加了协作编辑和查看功能，该公司正在增强其 graph [数据科学](https://thenewstack.io/what-data-engineering-is-and-why-its-not-just-about-data-science/)包，通过[节点块](https://github.com/migalkin/NodePiece/blob/main/readme.md)提供更好的图形嵌入，并通过 [pyTigerGraph](https://docs.tigergraph.com/pytigergraph/current/intro/) 添加对其自己打包算法的支持。

巧合的是，TigerGraph 就在本周发布了一个基准测试,显然是在 [VLDB 基金会](https://www.vldb.org/)的赞助下，专注于图形分析的规模，以及图形结构数据的商业智能。在基准测试中，TigerGraph 在一个 [AWS EC2](https://thenewstack.io/testing-developer-velocity-aws-ec2-vs-lambda-vs-lambda-on-stackery/) 部署中承担了 108 TB 的工作负载，据该公司称，该部署在一个包含 2179 亿个顶点和 1.6 万亿条边的图上处理了 OLAP 风格的查询。TigerGraph 表示，基准测试的 108TB 数据量是“之前世界纪录的 3 倍。”尽管以健康的怀疑态度考虑所有基准测试总是明智的，但这里清楚的是，图形技术正在处理越来越大的数据量，并被用于分析和运营工作负载，所有这些都在云中。

## 哎，哦

这种与图形数据的交叉并不是本月人工智能在一般分析领域展示其实力的唯一地方。例如， [Databricks](https://thenewstack.io/databricks-hits-amazon-marketplace-on-paygo-basis/) 在 3 月 7 日宣布了新的机器学习模型服务能力。该产品专为在 Databricks Lakehouse 平台上执行的主流分析环境中集成 ML 模型创建、维护和服务而设计。它不仅负责模型部署和批量评分/推理，而且还设置了必要的 API 端点，以便轻松地进行实时交互式评分，包括流数据场景。Databricks ML 服务还集成了一段时间以来一直是 Databricks 平台一部分的技术: [Unity Catalog](https://www.databricks.com/product/unity-catalog) 和 [Feature Store](https://www.databricks.com/product/feature-store) (在推理时自动执行功能查找)，以及 [MLflow](https://mlflow.org/) 实验管理。

说到 Databricks，它是 SAP[于 3 月 8 日宣布将与其合作的四家重要公司之一，合作内容是其](https://www.sap.com/) [Datasphere](https://www.sap.com/products/technology-platform/datasphere.html) 服务，该服务是 SAP Data Warehouse Cloud 的改进版本。现有的 DWC 客户将自动看到新的数据层功能，无需迁移。

除了数据湖库方面的数据块，SAP 还与 [DataRobot](https://www.datarobot.com/) 合作实现人工智能优势， [Confluent](https://www.confluent.io/) 合作实现更多流数据 pizazz，以及 [Collibra](https://www.collibra.com/) 合作实现数据治理。用 SAP 自己的话来说，这些令人印象深刻的跨行业合作伙伴关系的目标是“丰富 SAP 数据环境，并允许组织创建一个统一的数据架构，安全地结合 SAP 和非 SAP 数据，无论数据存储在何处。”这种伙伴关系也是双向的。例如，借助 Databricks，客户将能够将 lakehouse 数据引入 Datasphere，并将 SAP 数据(包括来自 [ERP](https://www.sap.com/products/erp.html) 实施、 [Concur](https://www.concur.com/en-us/all-products-page) 和 [Ariba](https://www.sap.com/products/spend-management/ariba-network.html) 的数据)引入 Databricks 环境。这是相当企业化的东西；因此，SAP 还与许多全球系统集成商合作，包括埃森哲、德勤、凯捷、EY、IBM 和普华永道。

## 云中的数据集成:随用随付，提前合并

虽然“云”这个词可能来自 SAP 的产品名称，但云在分析领域的中心地位怎么强调都不为过。正如经验丰富的 SAP 在数据治理和管理领域与 Collibra 合作一样，另一家企业数据管理巨头 [Informatica](https://www.informatica.com/platform.html) 也宣布了自己的新云计划。2 月 28 日，该公司推出了其[云数据集成](https://www.informatica.com/free-data-integration.html) (CDI) Free 和 CDI Paygo。CDI Free 建立在去年推出的[数据加载器](https://marketplace.informatica.com/forms/data-loader.html)产品 [Informatica](https://thenewstack.io/informatica-launches-freemium-ai-powered-integrator/) 的基础上，增加了 SAP 经典堆栈的工业级数据集成能力。ELT(提取、加载和转换)每月可免费使用 2000 万行，ETL(提取、转换和加载)每月可免费使用 10 个处理小时，以先到者为准。之后，CDI Paygo(即“随用随付”)允许客户处理更多数据，并根据基于使用的定价模式进行计费。

过去几周，Informatica 并不是唯一一家制造新闻的云数据集成公司。在 Informatica 分享其新闻的同一天，该领域的另一家公司 [Talend](https://www.talend.com/products/data-fabric/) 宣布，它正在为云作业管理添加人工智能驱动的自动化，改善数据源连接，以及额外的数据可观察性功能，以监控数据质量。最近，姐妹公司 [Qlik](https://www.qlik.com/us/lp/sem/di/qlik-data-integration-tools-and-solutions?utm_team=DIG&utm_subtype=cpc_brand&ppc_id=AYwP1NKX&kw=qlik%20data%20integration&utm_content=sAYwP1NKX_pcrid_81020376322783_pmt_e_pkw_qlik%20data%20integration_pdv_c_mslid__pgrid_1296324632149185_ptaid_kwd-81020511942634:loc-190&utm_source=bing&utm_medium=cpc&utm_campaign=Qlik_USA_Bing_Brand_DI_Brand_EN&utm_term=qlik%20data%20integration&msclkid=b51abfe77d52136e3559dbe8f67adb18) 宣布将收购 Talend。由于两家公司都属于私募股权公司[托马斯·布拉沃](https://www.thomabravo.com/)，这笔交易似乎有可能会通过。与此同时，Qlik 的产品组合中已经有了重要的数据集成技术，所以我们必须等待，看看 Talend 新宣布的功能将如何发挥作用。

## 云数据和数据市场

新闻名单上的下一个是 [Rockset](https://rockset.com/) ，一个基于开源 [RocksDB](https://rocksdb.org/) 项目的实时分析数据库。Rockset 可以接收关系数据和流数据，将其保存在专有存储中，然后使用积极的索引策略来承担数据仓库和数据虚拟化工作负载的组合。3 月 1 日，该公司宣布了基于多集群架构的新工作负载隔离功能，该架构有助于将流数据接收与低延迟查询工作负载隔离，允许每个工作负载独立扩展，并且据该公司称，避免了对多个数据库副本的需要。Rockset 将自己描述为云原生的，将自己加入了越来越多地将云和分析永久融合在一起的供应商名单。

当然，为了丰富数据，云中的分析可以从基于云的外部数据源中受益匪浅。这就是为什么知名数据目录提供商 [Alation](https://www.alation.com/product/data-catalog/) 在 2 月 22 日宣布推出 Alation 数据市场。除了数据治理之外，Alation 对数据目录的态度一直是让数据可被发现、可访问，并且在某种意义上可以被同行审查(在企业内部)。同样的风气似乎导致了数据市场的引入，因此外部数据可以像公司数据一样被访问。

## 微软插件丰富

使数据更易访问的另一种方法是使其在核心数据目录和分析界面之外以及其他应用程序内部可用。这就是 Alation 另外宣布在 Alation Anywhere 中支持[微软团队](https://www.microsoft.com/microsoft-teams/)的原因，该公司现在可以在微软团队聊天中发现和查询数据集(加入先前存在的对 Slack 和 Tableau 的支持)。还有 [Alation Connected Sheets](https://www.alation.com/product/connected-sheets/) ，除了之前支持的 Google Sheets 之外，现在可以从 Microsoft Excel 访问目录中的数据。集成非常紧密，非常有价值——你可以在这里看到 Teams/Alation Anywhere 技术的演示。 Alation 还和我分享了一个 Google Sheets 上的连接工作表的演示，确实令人印象深刻。

最后，Teams 和 Excel 并不是唯一获得第三方分析集成的微软工具，Alation 也不是唯一这样做的公司。事实证明，Databricks 也加入了这场游戏。由于开发人员是 Databricks 的核心支持者，该公司决定将微软的 [Visual Studio 代码](https://code.visualstudio.com/)作为其集成的目标，为广受欢迎的多平台(免费)开发人员工具创建一个[插件](https://learn.microsoft.com/en-us/azure/databricks/dev-tools/vscode-ext)。本质上，该插件使 VS Code 成为 Databricks 的一级客户端，为开发人员提供了 Databricks 笔记本界面之外的选项，用于处理他们的 lakehouse 中的数据，以及他们已经构建或正在构建的 ML 模型。

## 这一切意味着什么？

开源表格格式越来越受欢迎和采用。在高性能场景中，图形数据越来越多地用于分析。在主流分析环境中，机器学习和流式数据越来越常见，并且集成得越来越紧密。像 SAP 这样的巨头正在更多的环境中共享更多的数据。数据整合变得越来越便宜和容易。丰富数据更容易获得，也更容易与公司数据融合。这一切都发生在云中，每个人都可以在他们喜欢的工具中进行分析，即使他们是 Slack 或 Teams 这样的协作平台，Excel 或 Google Sheets 这样的电子表格，或者是像 [VS Code](https://thenewstack.io/this-week-in-programming-all-hail-visual-studio-code/) 这样的开发工具。

分析变得越来越面向云，越来越无处不在，越来越嵌入到平台中，而不是仅仅专注于分析，甚至不是主要专注于分析。这意味着分析的采用和部署在增加，但它也在“消失”，因为它钻入了各种技术平台。这似乎是一个悖论，但实际上很符合逻辑:最有效的基础设施不引人注目地工作，以至于你甚至不知道它的存在，让你无需绕道或提前计划就可以使用它。这就是当今分析领域正在发生的事情，来自 Alation、Databricks、Dremio、Informatica、Rockset、SAP、Talend 和 TigerGraph 的所有消息都证明了这一点。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>