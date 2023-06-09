# Kubernetes 应用保护和移动性策略

> 原文：<https://thenewstack.io/kubernetes-application-protection-and-mobility-strategies/>

[](https://www.linkedin.com/in/sayandebsaha/)

[Sayan Saha](https://www.linkedin.com/in/sayandebsaha/)

[Sayan Saha 是一位经验丰富的产品执行官，拥有超过 12 年的开源软件产品管理经验，涉及基于 Linux 的平台软件、容器、Kubernetes、高可用性/集群软件和软件定义的存储。在 NetApp，他是 Astra 和 Trident 的产品管理高级总监，Astra 是一种针对 Kubernetes 应用程序的完全托管(SaaS)多混合云数据管理服务，Trident 是一种针对容器化工作负载使用持久存储的开源解决方案。](https://www.linkedin.com/in/sayandebsaha/)

[](https://www.linkedin.com/in/sayandebsaha/)[](https://www.linkedin.com/in/sayandebsaha/)

随着 Kubernetes (K8s)和容器成为开发、部署、运行和扩展云原生和下一代 IT 应用的事实上的选择，企业正在 K8s 集群上运行越来越多的业务关键型应用。业务关键型应用程序通常是有状态的。有状态应用程序具有相关的状态、数据和配置信息，并依赖于以前的数据事务来执行其业务逻辑。

Kubernetes[上提供服务的业务关键型应用程序通常像传统应用程序一样具有可用性和业务连续性要求，这意味着服务中断(违反 SLA)会严重影响提供商的收入和声誉。企业通常意识到，在发生影响服务的灾难后，或者当他们面临将应用程序迁移到新的集群或环境的艰巨任务时，他们需要使用数据管理工具使他们的 Kubernetes 部署能够适应服务故障。](https://thenewstack.io/category/kubernetes/)

其他企业认识到了这种需求，但是使用内部开发的定制工具，这些工具非常熟悉应用程序，很难在整个企业和应用程序团队中进行扩展、应用和标准化。换句话说，这种工具是特定于应用程序的，需要为每个应用程序定制开发。因此，企业努力为他们的 Kubernetes 资产制定一致和内聚的持久性和数据管理策略。

## K8s 应用程序数据持久性和管理的当前状态

更大的 Kubernetes 社区和生态系统在定义容器存储接口(CSI)方面做得非常出色，它解决了用户在有状态 Kubernetes 应用程序的持久存储供应和消费方面的首要问题。CSI 接口还定义了数据管理原语，如支持永久卷(PV)快照和克隆。这些接口为存储和数据管理供应商构建全面的应用程序数据保护和移动解决方案奠定了基础。

## Kubernetes 数据管理——应用感知是关键——它并不总是与集群中的内容有关

如今，Kubernetes 应用程序的构成还没有具体的定义。然而，对于大多数 Kubernetes 从业者和用户来说，K8s 应用程序是通过包含有关应用程序的数据和元数据而形成的，该应用程序跨名称空间(在某些情况下，跨集群)组合了标准 K8s 对象和资源(如 ConfigMap、Secrets、Deployment、ReplicaSet)、持久性卷(PVs)和定制资源(CRDs 和 CRs)。因此，任何与应用程序无关的 Kubernetes 数据管理工具都需要考虑组成应用程序的所有这些组件。

如果不这样做，并且复制和/或备份与 K8s 应用程序相关的永久卷，在灾难发生后恢复应用程序时，可能会导致一些严重的故障。将应用程序视为保护和迁移的整体单元是实现 Kubernetes 应用程序数据管理的关键。

使这种情况更加复杂的是主要在公共云中使用的云原生 K8s 应用程序设计模式，其中应用程序团队利用使用完全托管的云服务(如数据库、消息队列和对象存储)的便利性、稳定性和性能。在这种情况下，根据定义，K8s 应用程序不再局限于一个集群，而是跨越集群之外的完全托管的服务。从 Kubernetes 集群中运行的应用程序中使用外部完全管理或自我管理的数据库是非常常见的。

基于这种云原生开发的设计模式，像 AWS 和 Azure 这样的公共云使得使用 Kubernetes 原生 API 从 Kubernetes 集群消费完全托管的服务变得更加容易。Kubernetes 的 AWS 控制器( [ACK](https://aws-controllers-k8s.github.io/community/docs/community/overview/) )和 [Azure 服务运营商](https://github.com/Azure/azure-service-operator)(用于 Kubernetes)就是这类举措的例子。

## Kubernetes 的替代品——本地持久性——常见的设计模式及其原因

如上所述，构建基于现代 Kubernetes 的服务的应用程序团队除了使用其他本地云服务(不限于在 K8s 集群中使用持久性卷)之外，通常还会使用多种持久性技术。这种模式的出现有许多原因，包括但不限于:

*   一个根深蒂固的信念是 Kubernetes 是一个优秀的平台，只运行无状态的应用程序。
*   在 K8s 集群上运行数据库的早期经验，或者了解尝试这样做的失败项目。
*   采用云原生和微服务方法，使用原生公共云 DBaaS(例如，AWS RDS、Google Cloud SQL、Azure Cosmos DB)、第三方供应商管理的数据存储(作为 SaaS 交付)或自我管理的外部数据库集群来构建 Kubernetes 应用程序，感觉很正常。这种设计范式自然符合云原生设计方法，这种方法通过在微服务之间使用基于 API 的契约，利用这些数据服务的可伸缩性、弹性、伸缩性和灵活性。
*   将对象存储用于 K8s 持久化需求，因为它在公共云中无处不在，并且普遍用于持久化现代应用程序。

像其他事情一样，这些持久性选择也有一些缺点。使用完全托管的原生公共云数据库和 NoSQL 数据存储可能成本高昂，并会导致隐式锁定到一个公共云。但是，对于选择单一或主要云提供商来满足其 IT 需求的企业来说，这可能是一个不错的设计选择。为了避免被云提供商锁定，采用多云策略的企业通常使用第三方 ISV 提供的云无关 DBaaS 产品。

在其他情况下，他们在云提供商的预留实例上运行外部数据库集群(利用预留实例的折扣价格)以节省成本。这样，他们最终会自行管理数据库集群，这可能会很繁琐。

使用对象存储实现 Kubernetes 持久性非常流行。然而，使用对象存储也可能使应用固有地不太容易移植，因为用于访问公共云中的本地对象存储服务的 API 不兼容，因为它们本身不支持相同的 API。K8s 社区正在开发一个新的标准[容器对象存储接口](https://container-object-storage-interface.github.io/) (COSI)来提供一个通用的抽象层，用于从 K8s 应用程序中消费对象存储，这将使使用对象存储的 K8s 应用程序的可移植性更容易。此外，对象存储不适合许多现有的应用程序，即使它们正在被重构。

## 这对企业意味着什么？

显而易见，Kubernetes 应用程序的定义及其持久性需求并不总是与集群中的 Kubernetes 资源和集群中运行的 pods 上的持久性卷相对应。K8s 数据持久性的选择非常丰富，每种选择都有其优点和缺点。这意味着常见的 K8s 应用程序数据管理功能，如备份、恢复、迁移和法规遵从性，必须包括 K8s 群集内部的内容，以及可能驻留在群集外部并且是应用程序不可或缺的一部分的对象和资源。

例如，对 K8s 应用程序进行一致备份还意味着触发对完全托管的公共云数据库的备份，除了 K8s 资源、元数据和 Kubernetes 集群中存在的对象之外，该数据库还为该应用程序提供数据服务。除了集群内 K8s 资源之外，后续恢复过程还必须恢复外部数据库。

因此，企业必须仔细审查他们的 K8s 应用程序保护、移动性和合规性策略，并为他们的 K8s 存储和数据管理解决方案使用选择标准，以适应他们自己的应用程序团队和开发人员采用的最常见的云原生持久性设计模式。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>