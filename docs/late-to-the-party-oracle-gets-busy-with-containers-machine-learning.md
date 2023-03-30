# 派对结束后，甲骨文开始忙于容器和机器学习

> 原文：<https://thenewstack.io/late-to-the-party-oracle-gets-busy-with-containers-machine-learning/>

数据库巨头[甲骨文](https://developer.oracle.com/?utm_content=inline-mention)最近一直很忙，推出了一个新的容器部署和管理平台 [Verrazzano](https://www.oracle.com/java/verrazzano/) ，并为其 [MySQL HeatWave](https://www.oracle.com/mysql/heatwave/) 数据库服务添加了新的机器学习功能，但该公司继续受到打击，在某些方面迟到了，在其他方面只迎合了现有的客户群。

Verrazzano 于本月早些时候正式推出，旨在帮助开发人员在 Kubernetes 中部署、管理和保护基于容器的应用程序。该技术的高级首席产品经理 Dave Cabelus 在一篇博客文章中说:[它还有助于统一跨微服务和传统](https://www.linkedin.com/in/davidcabelus/) [WebLogic Server](https://www.oracle.com/java/weblogic/) 应用的应用生命周期管理，并标准化跨内部、Oracle 云基础设施和其他公共云上的 Kubernetes 集群的管理。

## 去市场晚了？

以数字化转型为目标，许多组织转向基于容器的开发和多云环境，以获得其允许的开发灵活性和速度。然而，甲骨文的竞争对手，如 IBM、微软、亚马逊网络服务、谷歌和其他公司凭借基于 Kubernetes 的容器管理平台击败了甲骨文。

在一次采访中，Cabelus 承认，Oracle 可能不是第一个将平台推向市场的公司，但还不算太晚，因为根据分析师的说法，企业客户向容器化和多云环境的转变只完成了约 5%。

“我们的战略是提供一个真正现代的应用开发平台，并以 DevOps 为中心，使客户能够保留他们在现有应用上的投资，”他说。

一位行业观察人士表示，甲骨文正在推进客户至上的战略。

“这是 Kubernetes 的时代，争夺超级控制游戏的战斗已经开始。Constellation Research 的分析师 Holger Mueller 说:“随着基于开源的 Verrazzano 的推出，后来者甲骨文试图让客户控制他们在任何容器集群中运行的所有工作负载。“这是一个明智之举，因为它让 Oracle 客户能够更清楚地了解以前的云投资，并尝试更多的工作负载。众所周知:无论谁管理工作负载，都可以就在哪里运行它们提出建议。”

Cabelus 说，对于 Verrazzano，“在哪里运行它们”包括在[甲骨文云基础设施(OCI)](https://www.oracle.com/cloud/) ，内部或任何其他主要云上。然而，[甲骨文正在竭尽全力让企业在 OCI 上运行工作负载。](https://thenewstack.io/oracle-lures-developers-with-more-always-free-cloud-services/)

Omdia 分析师 Brad shimmen 说:“我不认为甲骨文[介绍]表明他们上市晚了。”。“Verrazzano 的推出与其说是为了创建一个与云无关的应用平台，不如说是为了为 OCI 构建一个一致的平台架构，超越 Oracle 云本身的界限。顾名思义，Verrazzano 是希望通过采用云原生架构实现现有应用现代化的客户的桥梁。”

然而，英特尔公司的分析师杰森·彭博却不敢苟同。

“乍一看，Verrazzano 似乎是一个开源产品的集合，支持混合 IT 环境中的容器管理，”彭博说。“就这一点而言，它与市场上的许多其他产品相似，而甲骨文在这一领域的起步有点晚。Verrazzano 最重要的与众不同之处在于它是如何被调整以支持 Oracle 产品的——肯定对 Oracle 客户有用，但对其他任何人都没有特别的兴趣。”

## 关注现有客户

现有应用将由 Oracle 的 WebLogic Server、Coherence 内存数据网格以及 Helidon Java 微服务框架客户的应用组成。这些产品以及大量其他组件被捆绑到 Verrazzano 平台中。

“ [Helidon](https://helidon.io/#/) 项目肯定有一些吸引力，Coherence 和 Helidon 的组合得到了相当好的采用，通常是 Kubernetes，所以看到这种部署风格的预建自动化和捆绑是一个好的举措，[卡梅隆·波弟](https://www.linkedin.com/in/cameronpurdy/)说，他是 [xqiz.it](http://xqiz.it/) 的首席执行官和创始人，[隐身开发工具初创公司](https://www.theserverside.com/news/252471233/Ecstasy-programming-language-targets-cloud-native-computing)。波弟是 Coherence 的创始人之一，曾在甲骨文担任高级开发副总裁数年。

“我们专注于现有客户，”卡贝鲁斯说。"我们确实有一个非常大的 WebLogic 客户群，甚至更多."

事实上，“Oracle Verrazzano 建立在 Oracle WebLogic Kubernetes 工具包的基础上，使您能够轻松地将应用程序移动到容器和 Kubernetes，并自动部署 [WebLogic Kubernetes 操作符](https://github.com/oracle/weblogic-kubernetes-operator)，提供 WebLogic 域，配置对应用程序的访问，以及收集域和应用程序的指标和日志记录，”他在帖子中说。

## 维拉扎诺做什么

此外，根据该博客，当您在 Verrazzano 中部署应用程序时，系统会自动采取以下操作:

*   将应用程序的 Kubernetes 定制资源分发到将要部署应用程序的集群中。
*   为应用程序创建命名空间。
*   将机密复制到命名空间。
*   对于 Oracle WebLogic Server 域和 Oracle Coherence 集群，部署所需的操作员并将自定义资源传递给操作员。对于其他应用程序，系统创建一个 Kubernetes 部署和一个 Kubernetes 服务。
*   在 Istio 服务网格中创建网络策略。
*   创建进入服务网格的入口。
*   将度量和日志记录传输到 Verrazzano 可观察性堆栈。

“复杂的运营需求一直是业务转型的主要障碍。[环球数据](https://www.globaldata.com/)分析师[夏洛特·邓拉普](https://www.linkedin.com/in/charlotte-dunlap-6a32298/)表示:“IT 购买者面临的挑战是，组装出既能组合又能协调商业软件以及软件运行基础设施的解决方案。“因此，集成和平台提供商(如 Oracle)非常关注 Kubernetes 集群管理和新兴的可观察性工具。然而，还没有一个供应商能够管理这种合并的整个生命周期。Oracle 面临着一个竞争激烈的市场空间，比如 Red Hat 凭借其广受欢迎的高级集群管理(针对 Kubernetes)和 Insights/Ansible 可观测性解决方案。”

## 自动化 MySQL 热浪

与此同时，甲骨文还推出了 MySQL 自动驾驶仪，这是其 MySQL 热浪数据库服务的一个新组件。热浪是 OCI[MySQL 数据库服务](https://www.oracle.com/mysql/)的内存查询加速引擎。Oracle 数据库和自主服务副总裁史蒂夫·齐瓦尼克(Steve Zivanic)说，MySQL 自动驾驶采用机器学习来实现 HeatWave 的自动化，并提高性能和可扩展性。

MySQL automatic 可自动执行诸如资源调配、数据加载、查询执行和故障处理等任务。它还可以自动采样数据、收集数据和查询的统计数据，并使用 Oracle AutoML 构建机器学习模型，以对内存使用、网络负载和执行时间进行建模。

此外，MySQL 自动驾驶仪不断提高 HeatWave 查询优化器的效率，因为它在每次使用时都会学习。

“随着用户运行更多的查询和工作负载，他们使用系统的次数越来越多，系统会不断学习并变得更好，”Oracle 研究与高级开发副总裁 [Nipun Agarwal](https://www.linkedin.com/in/nipun-agarwal-42603a1/) 表示。

MySQL 自动驾驶仪中九种新的机器学习支持的自动化功能包括自动配置、自动并行加载、自动编码、自动查询计划改进、自动数据放置、自动查询时间估计、自动更改传播、自动调度和自动错误恢复。

## 基于机器学习与基于规则的比较

Agarwal 声称，HeatWave with Autopilot 是唯一一个提供基于机器学习的自动化的 SQL 服务，特别是与其他竞争分析服务相比，如[雪花](https://www.snowflake.com/?utm_content=inline-mention)、[亚马逊红移](https://aws.amazon.com/redshift)、微软 [Azure Synapse](https://azure.microsoft.com/en-us/services/synapse-analytics/) 等。

“我们采取的自动化方法是基于机器学习的自动化，而不是基于规则的机制，”Agarwal 说。“使用基于机器学习的自动化的优势在于，它为数据库的每个实例提供了定制的适应性。这不是一刀切的情况，你需要一个规则，并将其刻录到你的软件中。”

Constellation Research 的穆勒说，自动驾驶概念标志着甲骨文在将机器学习引入数据库方面的实力。

“我们正处于机器学习的时代，机器接管简单和日益复杂的任务，”他说。“Oracle 的 MySQL HeatWave 产品通过其 AutoDB 功能展示了这一点，其中关键的数据库安装、维护和操作流程由软件自动完成。这对于那些可以专注于在 HeatWave 上运行的下一代应用程序而不是处理管道问题的客户来说非常好。此外，它还降低了运行 HeatWave 的成本。”

MySQL HeatWave 客户可免费使用自动驾驶功能。

## 横向扩展数据管理

此外，甲骨文还推出了 MySQL 横向扩展数据管理(MySQL 横向扩展数据管理)( MySQL 横向扩展数据管理)( MySQL 横向扩展数据管理)( MySQL 横向扩展数据管理)( MySQL 横向扩展数据管理)( MySQL 横向扩展数据管理)( MySQL 横向扩展数据管理)( MySQL 横向扩展数据管理)( MySQL 横向扩展数据管理)( MySQL 横向扩展数据管理)( MySQL 横向扩展数据管理)( MySQL 横向扩展数据管理)可以将数据加载到 HeatWave 的性能提高 100 倍。他指出，HeatWave 现在支持 64 个节点的集群规模，而不是 24 个节点，并且能够处理高达 32TB 的数据，而不是 12TB。

“一些云数据库提供商继续为特定的工作负载提供专门的数据库，并假设，特别是在开源领域，开发人员喜欢手动修改参数以优化性能，”IDC 的分析师 Carl Olofson 在一份声明中说。“Oracle 正走在一条不同的道路上，希望将数据库功能整合到一个系统中。它在开源云数据库服务 MySQL HeatWave 中提供数据库融合和自动化。”

Olofson 进一步指出，“甲骨文在 2020 年底推出了 MySQL HeatWave，带来了全面的原生云支持，并将 [OLTP](https://www.oracle.com/database/what-is-oltp/) 和 [OLAP](https://www.ibm.com/cloud/learn/olap) 统一在一个数据库中，这消除了对 [ETL](https://www.ibm.com/cloud/learn/etl) 的需求。在这个新发布的版本中，Oracle 增加了基于机器学习的自动化，消除了配置、数据加载、查询执行和故障处理中的猜测和人工劳动。”

[https://www.youtube.com/embed/iGMFQLrZGTc?feature=oembed](https://www.youtube.com/embed/iGMFQLrZGTc?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>