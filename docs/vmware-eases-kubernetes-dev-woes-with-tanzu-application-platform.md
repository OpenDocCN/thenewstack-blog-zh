# VMware 借助 Tanzu 应用平台缓解 Kubernetes 开发困境

> 原文：<https://thenewstack.io/vmware-eases-kubernetes-dev-woes-with-tanzu-application-platform/>

企业软件提供商 VMware 最近发布了 [Tanzu 应用平台(TAP)](https://tanzu.vmware.com?utm_content=inline-mention) 的测试版，旨在帮助开发人员在 Kubernetes 上提供更好的多云体验。

总的来说，TAP 的目标是通过提供一个自以为是的开发人员平台来简化开发人员通常复杂的 Kubernetes 体验，该平台消除了复杂性，并通过内置安全性、合规性和最佳实践的模板来提供护栏，以满足企业需求。

Enterprise Management Associates 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk/) 表示:“很高兴看到一系列由 VMware 支持的企业级 Kubernetes 服务能够自动将代码转化为容器化应用或微服务的过程。“开发人员讨厌必须找出如何以安全、高效和一致的方式最好地完成这项工作。他们现在所要做的就是提供一些基本的应用参数，TAP 会让所有东西在 TKG、阿拉斯加、GKE 或 EKS 运行。”

TAP 可以在任何 Kubernetes 发行版上运行，包括 [Azure Kubernetes 服务](https://azure.microsoft.com/en-us/services/kubernetes-service/)、[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)、[弹性 Kubernetes 服务](https://aws.amazon.com/eks/)、[谷歌 Kubernetes 引擎](https://cloud.google.com/kubernetes-engine)，以及像 [Tanzu Kubernetes 网格](https://tanzu.vmware.com/kubernetes-grid)这样的软件产品，VMware 现代应用平台产品营销高级经理[布拉德·博克](https://www.linkedin.com/in/bradley-m-bock/)和 VMware 产品营销人员[丽塔·芦田爱菜](https://www.linkedin.com/in/rita-manachi-8ab96a1/)写道

Bock 和 Minachi 写道，在上周的 [SpringOne](https://springone.io/) 会议上推出的这一新版本 TAP 还提供了自动化容器映像构建、服务和事件功能的运行时、API 发现和路由，以及对正在运行的应用程序进行快速故障排除的洞察。

VMware 希望开发人员能够快速开始构建和测试应用程序，而不管他们对 Kubernetes 的熟悉程度如何。

VMware 在一份描述 TAP 的声明中表示:“从模板开始，开发者将源代码转化为一个容器，并在几分钟内获得一个 URL 来测试他们的应用程序。”“一旦构建了容器，每次有新的代码提交或依赖补丁时，都会自动更新它。借助内部 API 管理门户，连接其他应用和数据变得前所未有的简单，无论它们是如何构建的，或者运行在何种基础设施上。”

VMware 产品副总裁 Graham Siener 告诉新的堆栈，TAP 旨在围绕 Kubernetes 构建严格的抽象和让开发人员自行其是之间取得平衡。

“我们不认为应用程序应该是平台敏感的，我们不认为开发人员应该知道 Kubernetes 才能成功，但与此同时，我们希望公开这些层，让他们深入到他们需要去的地方，”Siener 说。“在这方面，我认为我们确实与众不同，因为我们试图遵循这条路线，并帮助那些利用这一点的客户找到适合他们自己的组织成熟度和团队成熟度的平衡点。”

TAP 简化了 API 连接，也简化了从其他应用和基础设施消费事件的过程。TAP 的博文称，这是通过用于 VMware Tanzu 的[云原生运行时实现的，该运行时通过使用](https://tanzu.vmware.com/content/blog/cloud-native-runtimes-for-vmware-tanzu-advanced-ga)[trigger mesh](https://triggermesh.com/?utm_content=inline-mention)事件集成平台连接不同类型的事件源和消费者。TriggerMesh 通过运行在 Kubernetes 上的事件驱动架构从云原生应用中解锁外部事件源。

VMware Tanzu 应用平台是 Red Hat OpenShift 的直接竞争对手。

GlobalData 的分析师 Charlotte dun lap[表示，应用现代化的最新阶段是集成的可观察性和基础设施现代化，提高了开发人员理解微服务应用和底层系统之间发生的性能和集成问题的能力，并降低了获得这种见解的编码要求。](https://www.linkedin.com/in/charlotte-dunlap-6a32298/)

“由于 VMware 在 IT 基础设施方面的专业知识，该公司拥有一些优势，这使得 Tanzu 成为平台竞争对手的更大威胁，”她说。“然而，VMware 的主要竞争对手 Red Hat OpenShift 正在投资类似的 DevOps 模型，包括 Red Hat Insights，这是一种预测分析监控产品，可增强混合云到多云运营部署的可见性。”

与此同时，Constellation Research 的分析师[霍尔格·穆勒](https://www.linkedin.com/in/holgermueller/)说，由于 Kubernetes 的采用和成功，VMware 在老化的[云铸造](https://www.cloudfoundry.org/?utm_content=inline-mention)平台和虚拟化平台方面处于“双重困境”。

“幸运的是，它(VMware)已经在其 Tanzu 应用程序平台上工作了一段时间，所以现在有了 Cloud Foundry containers 的现代继任者，VMware 也参与了未来的工作负载，这对“拥有”本地工作负载的供应商来说至关重要，”他说。“对于开发人员来说，这是一个好消息，因为像 TAP 这样的托管 Kubernetes 产品使他们的生活更加轻松，消除了许多低级管道和相关的头痛问题，但允许他们在重要的事情上实现更高的开发速度，即自动化业务问题。”

然而，现在 Tanzu 创新正随着[Azure Spring Cloud Enterprise](https://thenewstack.io/microsoft-vmware-add-azure-spring-cloud-enterprise-tier/)来到 Azure，这使得 Spring 开发者更容易从 Tanzu 创新中受益，“为什么 VMware/微软没有将新的 Tanzu 应用平台带到 Azure 还有待观察，”Mueller 指出。

此外，VMware 决定放弃并行运行和管理 Cloud Foundry 应用程序和 Kubernetes 容器应用程序的“显然极其困难的工作”,这一决定得到了 Volk 的赞许。

“VMware 需要集中资源赢得与 OpenShift 的 Kubernetes 之战，”他说。重振摇摇欲坠的云计算平台将会分散注意力。"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>