# SAP 依赖于 Cloud Foundry，Kubernetes，因此用户可以随意启动数据库

> 原文：<https://thenewstack.io/sap-relies-on-cloud-foundry-kubernetes-so-users-can-fire-up-databases-at-will/>

全球最大的软件提供商之一 SAP 扩大了对云原生平台和 Kubernetes 的依赖，这为软件行业对 Kubernetes 的广泛采用可能会兑现其早期承诺(或如一些人所说)的说法提供了证据。

SAP 最新的 Kubernetes 举措包括本周在巴塞罗纳[举行的 SAP TechEd 2019](https://events.sap.com/teched/en/session/48841) 大会上发布的 HANA Cloud 数据库功能的[新增内容](https://news.sap.com/2019/10/sap-teched-barcelona-new-data-driven-cloud-services/)。SAP 高管在会议期间表示，该软件将于年底开始运行在云铸造服务和微服务以及 Kubernetes 集群上。

SAP 首席技术官兼执行董事会成员 [Juergen Mueller](https://twitter.com/JuerMueller) 在会议的主题演讲中描述了 HANA 云增强的重要性，但没有具体提到 Kubernetes，就目前大多数 SAP 应用程序如何在 HANA 上运行而言, [HANA](/evolution-sap-hana-express/) 的重要性。“这就是我们致力于在更多 SAP 解决方案中嵌入更多 SAP 分析云[选项]的原因，”Mueller 说。

HANA 的宣布主要是关于“利用 Kubernetes、云原生和微服务”，[副总裁兼开发者关系和 SAP 社区负责人 Thomas Grassl](https://de.linkedin.com/in/grassl) 说。

SAP 还计划继续支持 Cloud Foundry 并为其做出贡献，以帮助改善其底层云原生基础设施，支持其在云上的 Kubernetes 上运行的软件，从而间接帮助改善用户使用 HANA 云的体验。

“我们需要帮助改善云铸造，”格拉斯尔说。“这就是我们将继续为该项目捐款和提供支持的原因。”

基础微服务将在 HANA 云下运行，而开发人员将无法直接访问 HANA 的 Kubernetes 集群或微服务的 API。但是开发人员和运营团队将能够直接受益于 Kubernetes 集群和微服务，因为该结构支持微服务。Grassl 说，例如，DANA 的云数据库将能够根据需要更动态地“扩大规模，然后缩小规模”，这在很大程度上归功于集群的无状态性。

“在过去，这就像是，‘好吧，你有一个安装了 HANA 的实例。’”格拉斯尔说。现在，如果您有更多的需求，需要一个更大的实例，您可以转到配置，直接对其进行扩展或缩减。这是一个重大的声明。"

对于 DevOps 团队来说，SAP 希望通过 Kubernetes 和微服务底层，使 HANA 云更易于管理、更加灵活。为了简单起见，SAP 表示，它试图通过在一个组织的整个数据库中提供一个所谓的“虚拟交互访问层”(取决于用户的安全层访问),以单个查询引擎来减轻数据库编程、管理和存储的负担。

Grassl 说，对开发人员来说，其中一个优势是 HANA Cloud 可以作为一个“内存”数据库和数据管理平台。Grassl 说，HANA Cloud 因此为开发人员承担了“许多数据管理方面”。这些包括不必配置数据库索引或“复杂的查询，例如，由数百万个数据点组成，搜索查询结果在几毫秒内生成，”Grassl 说。

最终，云产品在很大程度上旨在提高 DevOps 的数据访问时间，无论是访问一年还是五年前的数据，都无需更改底层搜索查询代码或执行其他数据库配置或管理任务。“HANA 云对开发者来说越来越透明，因为它可以在云上配置，”Grassl 说。换句话说，作为云原生平台可以提供的另一个例子，DevOps 可以通过单个 API 直接访问和更改搜索查询和数据库访问，而这种项目由在数据中心内部重新安装或配置数据库服务器的漫长而繁琐的任务组成的日子已经一去不复返了。

“现在有了更多的灵活性，”格拉斯尔说。

Cloud Foundry Foundation 和 Cloud Native Computing Foundation(CNCF)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>