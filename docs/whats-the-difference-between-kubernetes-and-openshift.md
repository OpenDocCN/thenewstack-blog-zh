# Kubernetes 和 OpenShift 有什么区别？

> 原文：<https://thenewstack.io/kubernetes/whats-the-difference-between-kubernetes-and-openshift/>

[Kubernetes](https://thenewstack.io/category/kubernetes/) 在[云原生应用开发](https://thenewstack.io/category/cloud-native/)中的重要性日益增加，这意味着您现在有很多选择来部署您的编排平台。你可以从一个标准的 Kubernetes 环境开始，或者选择一个云托管的托管实例，由[谷歌、亚马逊和微软](https://thenewstack.io/comparison-amazon-azure-and-googles-managed-kubernetes-services/)提供。或者，你可以从越来越多的托管 Kubernetes 平台中选择一个。

Red Hat 的 [OpenShift](https://www.openshift.com/try?utm_content=inline-mention) 可能是这些平台中最著名的，它提供了一系列服务，从边缘部署到在公共云上运行的虚拟基础设施中工作。通过简化 Kubernetes 体验，它最有可能作为混合云战略的一部分部署在您自己的数据中心。主要云供应商支持 OpenShift，与虚拟基础架构工具(如 vSphere、Red Hat 的 OpenStack 工具)进行内部集成，或者直接在裸机上集成。

作为题外话，不要混淆红帽 OpenShift 和红帽 OpenStack。第一个是其管理的 Kubernetes 第二个是它的私有云平台，经常用来托管 OpenShift。

像所有托管的 Kubernetes 服务一样，很难确定红帽通过 OpenShift 带来了什么。毕竟，如果您运行的是经过认证的 Kubernetes，那么无论您从哪里获得，您的容器和编排都应该能够运行。这种潜在的中立性是 Kubernetes 成功的关键，因此任何受管理的 Kubernetes 发行版需要提供的不仅仅是滚动自己的 Kubernetes 环境。

有超过 70 种经过认证的 Kubernetes 发行版，很难找到它们之间的区别点。它们都支持同一套 APIs 它们都使用相同的容器标准。也许最重要的是，特别是对于像 OpenShift 这样的托管 Kubernetes 环境，是发行版背后的哲学，因为它影响到您如何以及在哪里使用它。有些是为边缘设计的，有些是为云设计的，有些是为混合环境设计的。

## 为平台运营管理 Kubernetes

所有 Kubernetes 发行版都利用的一个关键特性是它如何为分布式应用程序开发和操作添加一个新的抽象层。像 Kubernetes 这样的工具允许我们将 DevOps 实践分成三个部分。基础设施运营部负责管理服务器和网络，即托管虚拟环境的物理系统。应用运营团队管理我们在需要的地方部署的容器和代码:云中、内部和边缘。两者之间是平台运营，管理虚拟基础设施和容器编排。

OpenShift 最好被认为是一个平台操作工具，它将管理工具包装在一个经过认证的 Kubernetes 实例周围。不再需要使用多个界面来配置多个工具，而是将它们都集中到一个地方。所以，你不需要，比方说，使用 Calico 来添加网络安全 sidecars 到你的 Kubernetes 基础设施中，使用他们自己的管理工具；相反，您将通过与其余应用程序相同的门户来配置 OpenShift 的安全提供者。

红帽称其为“分布式应用平台”，使用 Kubernetes 作为内核。这是一种哲学方法，可以追溯到 Kubernetes 的早期，当时它不是主导平台，像 Mesos 这样的竞争对手将自己描述为“数据中心操作系统”。以这种方式思考 Kubernetes 肯定有价值，因为它有助于从平台运营的角度理解它，将其视为简化支撑大规模分布式应用环境的概念的一种方式。

该模型非常适合 Kubernetes APIs 的一些主流开发，它被视为管理打包容器和 WebAssembly 应用程序部署的一种方式。提供一个托管的 Kubernetes 环境，就像它是一个本地托管的平台即服务环境一样运行，消除了许多 Kubernetes 管理开销，同时仍然支持 Kubernetes APIs。

## 简化管理

通过提供自己的管理控制台，OpenShift 设法避开了 Kubernetes 的一个更烦人的方面，配置基于 web 的工具来与平台一起工作，然后处理对服务的访问。拥有单一用户界面可以更轻松地培训运营和应用程序开发团队，使用相同的用户界面管理整个网络(从边缘到云)中的节点。

简化有其自身的缺点；虽然 OpenShift 支持大多数核心 Kubernetes 特性，但它不支持最新的服务或关键的打包和部署工具。您将需要考虑如何将纯 Kubernetes 操作转换为 OpenShift，尽管对 Ansible 等工具的支持以及与 CI/CD 平台的直接集成可以大大减少摩擦。

虽然 Kubernetes 总是支持最新的技术，但是能够依靠 CI/CD 可以让您快速地将 OpenShift 集成到构建管道中。通过这种方式，您可以快速实现云原生最佳实践，在从私有容器存储库部署到 OpenShift 之前，使用 Jenkins 或 Tekton 等工具构建和测试容器。

Red Hat 现在通过 CRI-O 以及 Docker 支持公共运行时接口和 OCI 容器，为您提供了构建容器的灵活性。这允许开发人员在工作站上进行基本的 Kubernetes 安装，同时部署到 OpenShift 环境。由于 OpenShift 是经过认证的 Kubernetes 环境，所以您可以在开发人员工具链中安装相同的基础版本，并将许可成本保持在最低水平。

## 单一堆栈

OpenShift 还有另一个经常被遗忘的方面:它是从主机操作系统到应用程序的单一堆栈，构建于 Red Hat 的 Linux 和 DevOps 工具之上。这种方法可能不像推出自己的平台、从各种选项中挑选和混合那样灵活，但它确实为整个堆栈提供了单一支持联系人。支持仍然是更多企业部署的关键需求，Red Hat 在支持开源和自由软件方面的经验可以帮助将 OpenShift 的堆栈与您的基础设施的其余部分集成。

这是一种让您受益于内置安全工具的方法。保护 Kubernetes 需要使用多种技术，从服务网格到通过 kubectl 管理访问控制，OpenShift 使用 Red Hat 自己的安全工具来管理 Kubernetes 的关键功能，并提供额外的实时扫描来添加动态威胁检测。该功能还增加了漏洞管理，并帮助您了解与应用程序相关的风险。

Red Hat 为大多数常见的公共云和私有云提供自动安装和升级，允许您按照自己的计划进行更新，而不会中断运营。这个过程可能是 OpenShift 和标准 Kubernetes 环境之间的最大区别之一，因为它提供了一个更新操作手册，并使用它来避免中断。如果您运行的是 OpenShift 服务器集群，您将能够在应用程序继续运行的同时进行升级，OpenShift 的编排工具会根据需要移动节点和容器。

当谈到托管内部 Kubernetes OpenShift 时，它可能是与微软的 Azure Arc 工具相比最好的工具，该工具将 Azure 的托管 Kubernetes 带到内部，使用 Azure 门户作为管理工具，或 VMware 的 Tanzu。它们都基于经过认证的 Kubernetes，添加了自己的管理工具和访问控制。

OpenShift 更多的是 Kubernetes 对于企业应用开发的重要性的一个标志。大多数组织都有一个相对受限的运营环境，并且通常没有必要的资源来建立一个完整的 Kubernetes 管理团队。Kubernetes 的所有操作都采用单一平台，这降低了风险，利用了自动化并减少了培训需求。

如果您想使用 [Kubernetes](https://thenewstack.io/kubernetes-in-the-house-enterprise-options-for-k8s-on-prem/) 将云原生开发引入您的数据中心，像 Red Hat OpenShift 这样的托管 Kubernetes 是显而易见的选择。如果你在 VMware 生态系统中，那么你很可能会在微软的 Azure Stack 和 Azure Arc 中使用 Tanzu，而 OpenShift 将对 Linux 和 IBM 用户有吸引力。事实上，它们都建立在经过认证的 Kubernetes 之上，这使得它更容易被采用，因为你知道你应该能够在云平台上使用它，并且使用相同的容器和配置。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>