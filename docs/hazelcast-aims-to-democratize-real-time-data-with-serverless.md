# Hazelcast 的目标是通过无服务器实现实时数据的民主化

> 原文：<https://thenewstack.io/hazelcast-aims-to-democratize-real-time-data-with-serverless/>

Hazelcast 的愿景是实现实时数据处理和管理的民主化，而这一战略的关键是该公司的 Viridian 无服务器产品。

Hazelcast 首席产品官[马尼什·德弗根](https://www.linkedin.com/in/manishdevgan/)说，7 月底推出的测试版 Viridian Serverless 是一个自助式供应过程，其中集群会根据工作负载自动增长和收缩。该服务为用户提供了对水平可扩展实时数据平台的快速访问，该平台包括高速数据存储和[流处理](https://hazelcast.com/glossary/stream-processing/)功能。

## 非常适合黑兹尔卡斯特

因此，用户可以加快应用程序开发，简化供应，并使实时数据能够灵活地集成到应用程序中，Devgan 说。该服务处理所有底层硬件配置和任何操作复杂性，用户可以在几秒钟内部署一个功能集群。此外，该服务有助于组织避免过度配置和配置不足，并且用户可以立即开始使用终身免费层。在发布时，Hazelcast 表示，它将免费为用户提供高达 2 千兆字节(GiB)的数据存储。这个提议仍然有效。

弗雷斯特研究公司(Forrester Research)的分析师 Mike Gualtieri 告诉新堆栈:“无服务器非常适合 Hazelcast，因为它们支持极低延迟的工作负载，这些工作负载通常会从涓涓细流到雷鸣般的事件数据大幅波动。”。

他指出，如果没有无服务器，唯一可能的方法是构建一个具有足够扩展空间的集群来处理最大的预期负载，或者手动重新配置集群，这是一项劳动密集型工作。

Gualtieri 说:“无服务器方法能够始终提供适当规模的计算、存储和网络资源，而不会浪费电力、冷却和成本。“无服务器并不新颖，但由于延迟和吞吐量工作负载的可变性，它对于 Hazelcast Viridian 来说是一个特别好的体系结构。”

而拥有大量开发人员的大型企业，DevOps 团队和 [SREs](https://thenewstack.io/devops-institute-checks-the-pulse-of-sre/) 都有能力在公共云或自己的数据中心建立自己的平台。“但不是每个人都能做到，”德弗根说。“不是每个人都有 20 名开发人员在开发一个实时应用程序，并且必须管理所有这些。因此，对于这些客户，我们基本上是以服务产品为目标的。我们基本上想让经济的这一实时方面民主化。”

## 变得不可预测

但是，Hazelcast Viridian Dedicated 是一个托管的单租户集群，专为拥有清晰、可预测的使用模式并希望精确控制自己的集群的组织而设计。同时，用户可以选择用于开发和不可预测的生产工作负载的无服务器模式，尽管需要用于生产和可预测工作负载的企业级解决方案的客户可能会选择专门满足其公司需求的 Viridian。

“如果你的工作负载是不可预测的，那就是你应该使用 Viridian 的时候，”Devgan 告诉新的堆栈。“您希望尽快构建您的应用程序。您不必预先决定一个群集中需要多少节点，您只需回答几个问题，我们将为您进行幕后的规模估算。”

现收现付模式也有利于那些希望快速入门并使用所需资源的用户。

“当无服务器方法在几年前开始时，它主要局限于无状态应用程序。然而，我们现在看到越来越多的数据管理工具采用这种模式，[sanj emo](https://www.sanjmo.com/)的负责人和创始人 Sanjeev Mohan 说。“有许多好处，例如优化的资源使用、降低的配置复杂性、按使用付费的价格以及可扩展性。随着越来越多的数据库宣布它们的无服务器功能，我们看到这种趋势将继续下去。”

## 里面是什么

功能包括:

*   自助注册一个永久免费层，其中包括 2gb 内存存储的限时优惠
*   熟悉的声明式 API，用于构建利用实时流数据的应用程序
*   支持流式 SQL，使大量开发人员能够对实时数据进行查询
*   到多个云数据源的现成连接器，以及用于构建到任何其他数据源的自定义连接器的 API
*   与流行数据技术(如 Apache Kafka)的云部署集成
*   WAN 复制功能，支持跨云部署的数据集成，以支持地理分布式系统和灾难恢复策略
*   [改变数据捕获(CDC)](https://hazelcast.com/glossary/change-data-capture/) 技术，实现对数据更新的实时响应

## 黑兹尔卡斯特平台

“实时应用很难在传统数据平台上构建，迫使企业在战略目标上妥协，”Devgan 在一份声明中说。“Hazelcast Viridian Serverless 是提供真正实时云的下一步，同时使开发、配置和部署创新应用更加容易。”

Hazelcast 与像 [Redis](https://thenewstack.io/redis-puts-almost-everything-under-a-single-module/) 和 [Aerospike](https://thenewstack.io/aerospike-gets-sql-powered-by-starburst/) 这样的数据平台竞争，这些平台提供非常相似的低延迟数据访问。但是他们不做流媒体。

该公司表示，Hazelcast Viridian 产品由 [Hazelcast 平台](https://thenewstack.io/hazelcast-boosts-stream-processing-with-in-memory-computing/)提供支持，这是一个实时数据平台和集成的运行时，结合了分布式流处理和实时数据管理，可以自动对发现的模式、趋势和异常采取行动。这消除了在其他体系结构中产生瓶颈的功能，包括数据库写入、批处理和对人工干预的需求。

“夜间批量作业的日子屈指可数，”莫汉告诉新堆栈。“市场的一个巨大需求是根据最新数据做出决策。为了实现实时分析，我们不仅需要正确的数据平台，还需要无服务器的数据基础架构。因此，Hazelcast 的无服务器选项将帮助其客户提高开发灵活性，并部署他们的实时应用程序。”

此外，Hazelcast 有两个流行的开源项目。一个是数据管理领域——该公司同名的内存数据网格。另一个大项目是 [Jet 项目](https://jet-start.sh/)，这是一个流分析引擎。

“想象一下，你正在编写一个实时应用程序，你能够连接静态数据和动态数据，”Devgan 说。“有很多这样的使用案例—能够在数据流入时进行实时分析，同时还能提取实时发生的事件的上下文信息。”

## 用例，可用性

Devgan 说，Viridian Serverless 的一个典型用例是，当客户在银行存款或检测到欺诈事件时，银行延长优惠或优惠券。

事实上，从银行业到零售业以及越来越多的其他行业，无服务器架构的采用都在持续增长。事实上，根据思科的“ [2022 全球混合云趋势报告](https://www.cisco.com/c/en/us/solutions/hybrid-cloud/2022-trends.html?ccid=cc002960&oid=rptdnc029203)”，40%使用云原生技术的企业也在使用无服务器

根据 [Hazelcast](https://hazelcast.com/?utm_content=inline-mention) 的说法，Viridian 无服务器产品适用于[数字集成中心](https://www.gartner.com/en/documents/3880263)模式架构，使公司能够从众多来源捕获数据并立即关联数据，从而为最终用户创建增强的上下文。该公司表示，通过这种架构，公司可以获得 360 度的客户视图，实时跟踪资产，防止欺诈性交易，提供个性化推荐，创建实时促销优惠等。

此外，Hazelcast 无服务器服务适用于流处理环境，这些环境是支付处理、物联网分析和微服务消息传递的基础。

该服务在 [AWS](https://aws.amazon.com/?utm_content=inline-mention) 上可用，在谷歌计算平台(GCP)上的可用性即将到来。Devgan 说，微软 Azure 上有 Hazelcast Viridian Dedicated，但无服务器版本尚未推出。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>