# 融合通过单一 API 将云本地和本地数据流结合起来

> 原文：<https://thenewstack.io/confluent-combines-cloud-native-and-on-premises-data-streaming-through-single-api/>

Kubernetes 的 [Confluent 的发布将 Confluent APIs 放入 Kubernetes API，用于与](https://docs.confluent.io/operator/current/co-prepare.html) [Apache Kafka](https://kafka.apache.org/) 进行数据流传输，使客户能够跨多云和本地环境管理所有 Confluent 平台组件。通过这样做，该平台弥合了 Kubernetes 环境中内部和云基础架构之间数据访问的迫切需要的差距。

创建融合平台 6.0 是为了解决运营团队在使用 Kafka 管理集群时面临的几个问题，包括必须手动将集群链接在一起。对于使用 Kafka 的运营团队来说，修复单个集群故障以及将它们连接在一起是一项更加耗时且耗费资源的任务。新的集群链接功能通过自动将不同的集群汇集到一个“卡夫卡的全球网络”来实现这一点， [Confluent](https://www.confluent.io/?utm_content=inline-mention) 说。

Apache Kafka 数据流平台的广泛采用可以反映出对数据管理平台的需求激增，这种平台可以支持数据操作并满足许多来源的需求，通常是在全球范围内。例如，根据 Gartner 最近的报告[“了解云数据管理架构:混合云、多云和互云](https://www.gartner.com/en/documents/3985689/understanding-cloud-data-management-architectures-hybrid)”,几乎一半拥有数据管理运营的组织在内部和云环境(通常为多云)中管理数据。而 Gartner 表示，这些组织中有 80%以上依赖于多云环境。

此前，在为 Kubernetes 发布 Confluent[之前，Confluent 的一位产品经理 Rohit Bakhshi](https://www.linkedin.com/in/rohitbakhshi) 描述了客户可能如何单独使用 Confluent Operator 这是为了管理 Apache Kafka 和 Kubernetes 上的 Confluent 平台而创建的。

Bakhshi 说:“对于 Kubernetes 来说，我们利用我们在融合云中管理数千个 Kafka 集群的经验，为管理数据流创造了云原生体验，即使是对私有基础设施上的客户来说也是如此。”

这样，Kubernetes 的汇合通过[customresourcediations](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/)扩展了 Kubernetes API，以提供管理所有汇合平台组件的资源。它还引入了`CustomResourceDefinitions`来管理主题和基于角色的访问控制(RBAC)策略。Bakhshi 说，这使 DevOps 团队能够依赖 CI/CD 进行云原生部署，以及 GitOps，以代码形式管理其完整的流基础设施和流应用。

“Confluent for Kubernetes 将最佳实践打包，以在默认情况下自动执行安全、生产就绪的融合部署。现在，客户可以获得完全安全的部署——具有强授权、RBAC 授权和完整的网络加密——只需一个部署规范即可部署。“以前这是一个多步骤的手动过程。”

Bakhshi 描述的 Kubernetes 的其他功能包括:

Bakhshi 说，这是一个基于`CustomResourceDefinitions`的 API，用于“安全性、可靠性和开发自动化”。DevOps 团队现在可以利用 Kubernetes 的污点和容忍度，在他们共享的 Kubernetes 私有云基础架构上安排融合以及其他工作负载。安全选项包括 [Kubernetes Secrets](https://kubernetes.io/fr/docs/concepts/configuration/secret/) 和 [Hashicorp Vault](https://www.vaultproject.io/) 用于融合部署的秘密管理。

一个用于管理和排除 Kubernetes 汇合故障的 ku bectl CLI 插件。Bakhshi 说，通过这个 CLI 插件，DevOps 团队可以查看他们的部署状态，“快速获得故障排除信息”，并为他们的融合部署启动 GUI 控制中心界面。

对于缓存内存，为了确保公共数据池访问的超低延迟，Kubernetes 声明式 API 的 Confluent 允许使用 [ksqlDB](https://ksqldb.io/) 管理集群，ksqlDB 是用于应用程序流的数据库。KsqlDB 可以通过其连接器支持导入外部数据集，包括非流式和流式数据集，”[融合产品经理 Michael Drogalis](https://www.linkedin.com/in/michael-drogalis-01029924) 说。导入后，数据集将作为数据表进行处理。例如，ksqlDB 可以从 AWS S3 和 Kinesis、MySQL、Postgres、Salesforce 和通用文件系统导入数据。

“对于流分析，数据作为流被连续导入，以便外部数据集的未来变化以秒为单位的最小延迟反映在 ksqlDB 中，”Drogalis 说。“因此，流查询总是对最近的数据进行操作——有效地充当了低延迟访问的内存缓存，”Drogalis 描述道。“客户需要它来进行分析，以及在使用 ksqlDB 处理财务交易等事务时，例如大型机卸载用例。”

## 数据流棘手问题

组织通常需要跨共享数据池、跨多云和内部基础架构的实时数据访问。Kafka 数据流可以确保不同分布式应用程序和基础设施之间的数据流所需的低延迟。

“企业需要实时利用不断在其组织中流动的数据。但要做到这一点，他们需要一个中央神经系统来管理传统业务线(lob)、环境和应用程序中的所有数据，”Bakhshi 说。“他们需要提供一致的体验和标准化的最佳实践，以便向整个企业的全球团队推出这种动态数据平台，无论是在云中还是在内部。”

Bakhshi 说，例如，一家财富 500 强企业客户的任务是将业务分析应用程序从支持其数据中心关键 IT 基础设施的遗留系统转移到公共云。“为了在这种混合基础设施之间架起桥梁，他们正在数据中心和公共云之间使用 Kafka，”Bakhshi 说。“借助面向 Kubernetes 的融合，他们可以在其私有数据中心无缝部署和运行融合平台，并将云环境中的数据连接到融合云。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>