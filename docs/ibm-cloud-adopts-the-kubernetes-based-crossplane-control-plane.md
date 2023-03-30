# IBM Cloud 采用了基于 Kubernetes 的交叉平面控制平面

> 原文：<https://thenewstack.io/ibm-cloud-adopts-the-kubernetes-based-crossplane-control-plane/>

Upbound 的 [Crossplane](https://crossplane.io/) ，这个开源项目旨在提供一个基于 Kubernetes 的[跨云和部署的通用控制平面](https://thenewstack.io/crossplane-a-kubernetes-control-plane-to-roll-your-own-paas/)，[在本月早些时候达到了 1.0 版本](https://blog.crossplane.io/announcing-crossplane-v1-0/)，标志着 API 的稳定性和为所有二进制文件增加了普罗米修斯指标，以及其他功能。与此同时，IBM 加入了这个项目，发布了针对 IBM Cloud 的交叉平面提供者[，增加了对超过 85 种 IBM 云服务的支持。](https://developer.ibm.com/blogs/ibm-joins-the-crossplane-community/)

Crossplane 自 2018 年以来一直处于开发中[，旨在解决混合多云 Kubernetes 部署带来的问题。虽然混合多云的概念近年来变得越来越普遍，但实际应用这一概念的技术却落后了。跨不同的云部署 Kubernetes 及其资源需要针对每个云进行独特的配置。Crossplane 通过以通用控制平面的形式提供另一个抽象层来解决这个问题，它提供了使用 Kubernetes 自定义资源定义(CRD)来管理基础设施和资源(包括云托管服务)的能力。](https://blog.crossplane.io/crossplane-turns-2-years-old-just-ahead-of-v1-release/)

“有了 Crossplane，您现在可以使用一致的资源模型来表示那些在群集之外的资源。例如，如果我需要 AWS 或 GCP 或 IBM cloud 上的数据库，我可以使用相同的模型，基本上利用我现有的用于 Kubernetes 的 GitOps 方法，我现有的 GitOps 管道，还可以利用我围绕我的资源制定的所有策略，”IBM Research 的高级技术人员 Paolo Dettori 说。“这是 Crossplane 带来的核心价值之一。它提供了一种一致的方法来为不同的云和 Kubernetes 集群之外的不同服务构建提供商。”

Crossplane 使用一种叫做“组合”的东西来实现这一点，这种东西在 CRDs 之上添加了一个额外的抽象层，带有`CompositeResourceDefinitions` (XRDs)。[IBM 混合云可观测性首席架构师克里斯·贝利](https://www.linkedin.com/in/chrisbaileyibm/)解释说，XRDs 让你表达你想要的意图，然后依靠 Kubernetes 来实现它们，这取决于它们在哪里实现。这也是提供商介入的地方，IBM 刚刚发布了自己的 IBM Cloud 实验版本，该版本提供了一组 CRD 和控制器来从交叉平面控制平面提供和管理 IBM Cloud 基础设施和服务。

“Kubernetes 非常擅长控制配置，然后将配置变为现实。它的控制面板是它的巨大优势之一，”贝利说。“Crossplane 中的提供商允许您使用 Kubernetes 中的配置协调来管理其他事情，无论是部署在 IBM Cloud、AWS、GCP 等中的资源。现在，这些云中的每一个都在 Crossplane 中有一个提供者，所以您可以说，‘我想要一个 Postgres’并获得一个实际上在 IBM Cloud 中提供的，而不是在集群中提供的。”

除了允许用户简单地声明他们想要一个数据库实例，然后让 Kubernetes 在任何需要的地方创建它，组合还提供了嵌入一些预置的能力。

“您现在可以限制开发团队可以访问的配置，”Bailey 解释道。“如果必须有现成的安全级别或高可用性，所有这些类型的策略都可以包含在组合中。您可以选择真正限制开发运维团队的配置级别。”

Bailey 认为，最终，Crossplane 真正朝着混合多云和应用可移植性的承诺迈进了一步。

“现实是，可移植性是不完整的。因此，一般来说，应用程序一旦部署，无论在什么环境中，都不会被移动，”Bailey 说。“Crossplane 增强了应用程序可移植性的承诺，并使其更接近真正的现实，因此我可以定义一个今天在本地运行，明天就可以迁移到 AWS 的应用程序。如果我真的想将它分布到云中以提高可用性，我可以这样做，而且在两者中运行的配置完全相同。”

贝利说，展望未来，Crossplane 将努力实现 100%的覆盖，不仅是对 IBM，而是对它支持的所有云提供商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>