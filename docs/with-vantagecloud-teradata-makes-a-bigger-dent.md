# 有了 VantageCloud，Teradata 取得了更大的进展

> 原文：<https://thenewstack.io/with-vantagecloud-teradata-makes-a-bigger-dent/>

在上周纽约证券交易所的一次引人注目的活动中， [Teradata](https://www.teradata.com/) 宣布了其新的 [VantageCloud](https://www.teradata.com/Press-Releases/2022/Teradata-Announces-VantageCloud-Lake) 服务，该服务使该公司的数据仓库平台能够容纳新的工作负载和新的用户。此外，Teradata 正在为其希望应用和实施的新用户和场景打造和重申其数据库内分析函数库。

## 核心新闻

为了应对来自 [Snowflake](https://www.snowflake.com/en/) 和 [Databricks](https://www.databricks.com/) 等公司的竞争，Teradata 正在推出其 VantageCloud Lake 平台，以云对象存储经济为探索性和临时分析需求提供服务，尽管它保留了 Teradata Vantage 平台的功能和企业级治理。对于更传统的数据仓库客户，VantageCloud Enterprise 似乎可以为全球 2000 强企业及其 IT 组织提供解决方案。VantageCloud Lake 希望瞄准更多的全球 5000 强企业，包括其 IT 和业务部门。两种 VantageCloud 服务都将利用云对象存储及其相关的成本模型。

VantageCloud Lake 是一个云原生 SaaS 产品，提供对 Teradata Vantage 平台的弹性、自动扩展版本的自助访问，基于使用量的单位定价，甚至可以在使用量降至零时自动休眠。尽管 VantageCloud Lake 的用户界面面向最终用户，但它还具有集中成本管理控制功能，以避免失控的云服务账单。

尽管有“湖”的名字，但该产品并不是要转换到[拼花地板](https://parquet.apache.org/)或[冰山](https://iceberg.apache.org/)作为桌子存储的原生格式。相反，重点在于 Lake 文件系统和本机对象存储，它们管理云存储中的专有 Teradata 表。与此同时，Teradata 的 [QueryGrid](https://www.teradata.com/Products/Ecosystem-Management/IntelliSphere/QueryGrid) 技术将继续为以更原始、开放的格式存储的数据提供连接，这些数据也可以存储在对象存储中。

## 数据库内分析和 ML

Teradata 推出了 [ClearScape Analytics](https://www.teradata.com/Press-Releases/2022/Teradata-Announces-ClearScape-Analytics) 作为其高级数据库内分析功能的品牌，该功能通过一个内嵌函数库扩展了 SQL，涵盖了高级计算、数据准备和一些重要的机器学习功能。除了品牌，Teradata 还在 50 多个新的数据库内函数中引入了新的时间序列功能。

ML 功能包括特征工程、模型评估和评分，以及引入定制 Python 或 R 代码、开源 ML 库甚至定制模型的能力。数据库中的模型也可以导出用于外部服务，Vantage ModelOps 扩展支持模型部署、数据漂移和性能监控，以及内置的功能存储。还有第三方人工智能平台的集成，包括[大台库](https://www.dataiku.com/)、 [H2O](https://h2o.ai/) 、微软 [Azure 机器学习](https://azure.microsoft.com/services/machine-learning/)、[亚马逊 SageMaker](https://aws.amazon.com/sagemaker/) 和亚马逊的几个现成的人工智能服务，如[预测](https://aws.amazon.com/forecast/)和[理解](https://aws.amazon.com/comprehend/)。

## 经典的数据仓库技术仍然适用

让我们稍微解释一下，回顾一下数据仓库、大数据和云分析的相关历史，看看它们是如何结合在一起的。Teradata 是数据仓库的先驱，实际上已经发明了这个类别、它的许多组成技术和它的早期商业模式。这听起来可能有些过时，但现实是大多数较新的数据云数据仓库竞争者现在都在使用这些技术，他们没有太多时间来磨练和完善这些技术，因此经验是一种资产，而不是负担——至少当你根据优点进行分析时是这样。

当今数据仓库技术的标准组合包括以下内容:

*   MPP(大规模并行处理),其中完成大型复杂查询的工作在一组工作节点之间分配，这些节点的集体输出然后被集成并返回给客户端。
*   列存储，其中数据值存储是围绕表中的列(而不是行)组织的，这简化了这些值的聚合。
*   向量处理，其中成批的值一起处理，而不是顺序处理。

所有这些技术都是由 Teradata 率先开发的，要么是它自己开发的，要么是早期数据仓库平台中的一员。因此，围绕这些功能的索引和查询优化试探法是 Teradata 几十年来一直能够构建、改进和完善的，从而带来卓越的性能。这就是为什么它在大型企业组织中使用了同样长的时间，并一直处于主导地位。同样，这些技术和优化的相关性并没有消失。

## 云经济和变革

但是由于云计算，数据仓库的经济模式发生了巨大的变化。内部数据仓库通常基于类似设备的硬件外形，即预配置了所有服务器、存储和网络的大机柜，并且随时可以即插即用。提供的抽象实际上非常像云，但它施加的限制却不是。那些大柜子对其中包含的所有资源造成了物理上有限的限制。

对于数据仓库设备，只能有一定数量的处理能力和存储。这两者都很重要，扩展这些资源需要大量的资本支出和大量的运营中断。成本和稀缺性的结合导致大多数 IT 组织以高度保守和防御的方式部署数据仓库，对新数据的访问、使用和引入设置了高门槛。这意味着数据仓库可以完成工作，但这些工作必须经过高度审查、可操作性和任务关键型。

## 作为数据仓库对比点的大数据

这种标准不利于自主的、探索性的、特别的分析。可以说，这正是导致大数据革命的原因，特别是因为它基于商用服务器和直连驱动器存储，这两者都很便宜，并且可以增量扩展和伸缩。此外，大数据范式基于处理原始形式的数据，这简化了向数据仓库添加新数据时必须进行的所有建模。因此，大数据集群非常适合更灵活、临时和探索性的使用情形，并且它们用进攻性部署来对抗企业数据仓库的防御性部署，这种进攻性部署鼓励对建立数据文化、数据素养和数据驱动型运营至关重要的分析的更多实验性使用。

有趣的是，Teradata 在过去十年的大数据时代收购的公司和技术是 VantageCloud 皇冠上的宝石。例如，QueryGrid 和许多 ClearScape 分析功能分别来自 Teradata 对 Aster Data Systems 及其 SQL-H 和 Aster 分析功能的收购。

## VantageCloud 使 Teradata 保持最新

即使 Teradata 推出了 Vantage 架构，允许除了使用内部部署之外的云部署，但旧的经济模式仍然存在，使用该平台的障碍也是如此。从 Vantage 到 VantageCloud 的迁移——尤其是 VantageCloud 湖——改变了这一切。原因如下:

*   VantageCloud 使用云对象存储，而不是工作节点中的高端板载磁盘。这意味着存储更便宜。这也意味着它可以无限扩展，并且独立于计算资源。
*   VantageCloud Lake 的计算具有弹性和自动伸缩性，因此将 Teradata 平台的性能属性与调整、配置、优化和管理数据仓库集群的需求相分离。
*   VantageCloud Lake 允许配置对相同数据进行操作的多个集群，从而实现更高的用户并发性和隔离，以确保自由分析工作不会影响生产工作负载的性能。

最终结果是，Teradata 进入了自助服务运营领域，更适合作为业务部门级别的探索性分析平台，对 it 的依赖性大大降低，表面上看，洞察和数据驱动型决策的速度更快。与此同时，Teradata 所熟知的工作负载管理、成本控制和数据治理在云数据仓库时代仍然适用。Teradata 认为这是两全其美的做法。

## 竞争格局

我们已经看到 [Databricks](https://thenewstack.io/databricks-hits-amazon-marketplace-on-paygo-basis/) 创建并推出了其 [Photon](https://www.databricks.com/product/photon) 引擎，专门为其平台带来数据仓库级的查询性能。这是该公司将其平台描述为数据湖库而不是数据湖的一个关键原因。随着对其平台的采用增加，我们还看到雪花增加了治理功能，并开始努力解决客户对成本的敏感问题。

Teradata 认为这验证了其核心技术方法和可信度，而 VantageCloud Lake 为其提供了自助服务和规模灵活性，使其能够在更加组织化的分散分析环境中竞争，数字化转型和数据网格等趋势已经普及并证明了这一点。

一些挑战仍然存在。Teradata 没有采用开源文件格式进行原生表处理，而 Snowflake 最近宣布它将完全采用这种格式(使用冰山格式), Databricks 原生地利用了像 Parquet 和 [Delta Lake](https://delta.io/) 这样的格式。因此，两家公司都可能要求更大的 lakehouse 绰号的权利。

## 入场费

除了技术之外，Teradata 的许多竞争对手提供入门级价格，允许好奇的开发人员以低成本或零成本获得他们的平台。Teradata 的目标是大型企业，没有类似的产品，它可能应该用于非生产用途。也就是说，Teradata 可能认为低成本或免费增值模式玷污了其企业声誉。是的，VantageCloud Lake 旨在适应现代功能、工作负载和使用模式。但它针对的是大型组织中的部门需求，而不是较小组织或个人的核心需求。

这是一个训练有素的销售战略决策。时间会证明现代数据行业是否能遵守它。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>