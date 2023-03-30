# Instaclustr 在其平台上增加了管理型 Cadence

> 原文：<https://thenewstack.io/instaclustr-adds-managed-cadence-to-its-platform/>

Instaclustr 是一家管理开源数据库、管道和工作流应用的平台提供商，作为一种服务交付，本周在 [Instaclustr 平台](https://www.instaclustr.com/platform/)上推出了 [Instaclustr 管理的 Cadence](https://www.instaclustr.com/platform/managed-cadence/) 。

instaclustr,[NetApp 刚刚宣布了收购意向](https://www.netapp.com/newsroom/press-releases/news-rel-20220407-656381/),通过管理开源数据基础设施，帮助组织大规模交付应用程序。

## 什么是 Cadence？

[Cadence](https://cadenceworkflow.io/) 由优步开发并开源，是一个工作流引擎，它简化了大规模复杂的长期运行的自动化业务流程的开发。Instaclustr 说，它特别适合在基于微服务的架构中使用，在这种架构中，必须随着时间的推移协调多个服务调用才能实现业务成果。

优步创建了 Cadence，因为它使用的基于 Kafka 的架构变得过于复杂，用 Cadence 代替它意味着集成逻辑可以直接用易读的代码表达。

## Cadence 和 Instaclustr 平台

[Instaclustr 首席产品官 Ben Slater](https://www.linkedin.com/in/ben-slater-2720562/?originalSubdomain=au) 表示，由于依赖 Apache Cassandra、Apache Kafka 和 OpenSearch 这三种技术，insta clustr 在以最高水平的可用性和性能运营方面拥有丰富的专业知识和经验，因此该公司在提供完全托管的 Cadence 方面具有独特的优势。

Slater 说，Instaclustr 平台是一个可扩展开源技术的托管平台。特别是 Instaclustr 提供了 Apache Cassandra、Apache Kafka、OpenSearch、 [Redis](https://redis.com/?utm_content=inline-mention) 、Postgres、Apache Zookeeper 以及现在的 Cadence。该平台提供自动化供应、监控和操作。

## 节奏和工作流程

“Cadence 在技术领域非常罕见。在我看来，它提供了一种明确的更好的方法来实现一个非常常见的用例类别:工作流或服务编排类型的问题，”Slater 告诉 New Stack。他说，“在这个领域，Cadence 优于替代或遗留解决方案”，原因有几个，包括它让开发人员可以直接用他们熟悉的编码语言工作。

此外，由于 Cadence 工作流是用标准代码实现的，它们可以利用任何现有的服务，而不需要任何特殊的集成工作。Slater 说，这些代码可以用非常简单的方式编写，这使得开发人员可以很容易地理解他们工作流程的逻辑。

此外，“Cadence 的内置功能，以及它强加在代码上的逻辑结构，已经被证明在许多用例中极大地提高了开发人员的生产力，”他说。

Slater 说，Instaclustr 的开发人员已经使用 Cadence 大约九个月了，并且全心全意地采用了它。

“Cadence 为拥有基于微服务的架构的组织提供了一个非常有吸引力的解决方案，这些组织需要协调业务流，这些业务流需要跨微服务的最终一致性和活性保证，”优步的高级软件工程师艾姆拉·谢克尔在一份声明中说。“作为一个容错的有状态代码平台，Cadence 梳理了这些分布式系统中具有挑战性的细微差别，同时允许应用程序开发人员专注于轻松地将复杂的业务逻辑表达为代码。”

## 负责两件事

Slater 说，Cadence 基本上为用户做了两件事，而没有给他们的代码增加任何复杂性——处理潜在的故障和扩展的基础设施。

例如，在 Cadence 术语中，Workers 是实现您的业务逻辑的客户端应用程序。斯莱特解释说，他们类似于阿帕奇卡夫卡世界中的生产者和消费者。

“工人实现两种类型的业务逻辑:工作流和活动，”他说。“活动是您逻辑中的‘做’步骤—调用外部服务、将文件写入磁盘、任何不确定的或有可能失败的事情。工作流具有决定以何种顺序执行哪些活动的逻辑。对于一组给定的输入和活动结果，工作流逻辑必须是完全确定的。”

然而，使用 Cadence，您可以获得工作流和活动代码的代理/存根，这允许 Cadence 在执行这些事情时透明地注入自身，Slater 解释道。然后，Cadence 使用事件源模式保存每个活动执行的输出，并通过确定性工作流代码重放该输出，以便在需要通过中断进行恢复时重新创建状态。

“Cadence 还负责在多个工作人员之间分配工作的实际执行，”Slater 指出。“由于工作人员使用优化的轮询方法来获得新工作，新工作人员的启动是一个非常简单的过程，不需要从 Cadence 服务到工作人员流程的网络连接。”

## 管理节奏的主要特点

与此同时，Instaclustr 的托管 Cadence 的主要功能为 Cadence 运营提供 99.95%的可用性 SLA，自动配置 Cadence，包括 Instaclustr 平台上所需的 Apache Cassandra(或 PostgreSQL)、Apache Kafka 和 OpenSearch 集群，以及 Apache Cassandra、Apache Kafka 和 OpenSearch 集群的折扣价。

此外，Instaclustr 管理的 Cadence 用户还可以获得:

*   通过 Instaclustr 的控制台、API 或 Terraform 提供程序进行垂直和水平扩展
*   在 GCP Azure 的 [AWS](https://aws.amazon.com/?utm_content=inline-mention) 上可用，或者在私有基础设施中运行(包括本地)
*   24/7/365 监测和专家支持
*   SOC 2 认证安全性

## 在新的管理下

“Cadence 是一个非常强大的系统，但为了能够以其目标的规模和可靠性运营，它需要建立在现有系统的基础上，”Slater 说。“特别是，你需要一个数据库。支持 Apache Cassandra、PostgreSQL 等，如果你在使用 Cadence 的所有功能，还需要 Apache Kafka 和 OpenSearch 或 Elasticsearch 供 Cadence 使用。”

为所有这些东西建立一个生产就绪的架构本身就是一个大项目，Instaclustr 托管平台会处理好这个问题。

“借助托管平台，您可以在不到半小时的时间内建立并运行完整的生产就绪型架构，”Slater 说。

Instaclustr Managed Cadence 可在 AWS、GCP 和 Azure 上用于生产，或供客户在自己的云或内部基础设施上运行。组织可以通过 [Instaclustr 控制台](https://console2.instaclustr.com/signup)注册，尝试 Instaclustr 管理的 Cadence。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>