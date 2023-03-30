# Rancher Labs 的 Rio:Kubernetes 的应用部署引擎

> 原文：<https://thenewstack.io/rancher-labs-rio-an-application-deployment-engine-for-kubernetes/>

Portworx 赞助了 New Stack 在圣地亚哥的 KubeCon + CloudNativeCon 的报道。

正好赶上 KubeCon+CloudNativeCon 北美 2019，Rancher Labs 发布了两个新的包，用于为所有计算环境(从数据中心到云到边缘)创建端到端 Kubernetes 解决方案。

它已经推出了用于 DevOps 自动化的 [Rio 测试版](https://github.com/rancher/rio)，以及[K3s](https://thenewstack.io/k3os-a-kubernetes-os-distro-for-edge-computing/)的全面上市，K3s 是 Kubernetes 的一个小规模工作负载分布。

Rancher 的营销副总裁 Peter Smails 坐下来，实际上，与新的堆栈谈论这个新版本。

Rio 致力于使 Kubernetes 成为开发者可以在其上构建，但忘记它存在的东西。现已公开测试的 Rio 的主要功能包括:

*   一个轻量级的云原生平台，提供从运营到管道的完全集成的部署体验，而无需接管集群。
*   能够在任何地方的任何 Kubernetes 集群上运行，甚至在笔记本电脑上运行，处理 Istio、Knative 和 Prometheus 等公共服务的所有连线。
*   以安全为中心的配置，具有 Rancher 内置的安全功能，包括集群性能、多租户和加密。

Smails 说，到目前为止，Rancher 所做的很多工作都是面向 IT 运营，以管理他们所有的集群。对于开发人员来说，用户反复反馈对他们来说太复杂，对于为云和 edge 编写代码和在生产中运行来说仍然太难。

Smails 说，所有开发人员应该担心的是“编写代码，并在任何进程中跨任何 Kubernetes 集群构建、部署和管理代码。”

里约就是这么做的。

他将 Rio 描述为一个“自动化的应用程序部署引擎”,开发者可以自动构建、部署和管理任何应用程序，从而简化整个过程。

怎么会？

1.  **引入自动化构建:**开发人员构建源代码，他们通过与 Rio 的紧密集成提交给 Git，然后 Rio 将触发自动构建。在有人触发建筑之前。Rio 使用一个描述性的 GUI，然后集成了持续部署技术，如 Linux 基金会的 TechTon 或 Jenkins。
2.  **推动正确的集群:**当今最常见的边缘计算使用案例之一是在零售业。开发人员将运行必须在数百甚至数千家商店的销售点平板电脑上部署的软件。Smails 说，通过一个单一的说明性 GUI 向所有适当的集群推送具有很大的运营价值。
3.  **持续管理和监控:**在同一个环境中，使用 Rio，您可以管理通常复杂的 Kubernetes 部署和回滚，就像 canary 和 blue-green 部署一样。

”拓也有意固执己见。你为用户做出某些决定，使事情自动化和简单化。”

斯梅尔斯继续解释说，它遵循 80/20 法则。可能有 20%的组织希望自己做这件事，因为他们有复杂的集成等。他说，Rio 是为 80%的组织构建的，这些组织希望“为 CI/CD、服务网络和监控提供一种非常简单和自动化的方式。

Rancher 是在考虑 IT 和运营的情况下构建的，但 Rio 的目标是任何使用 Kubernetes 进行开发的开发人员，无论您是否使用 Rancher。

### K3S

Smails 表示，K3s 的这种普遍可用性非常重要，因为在他们的 beta 测试人员中，他们已经看到了重要的用例——大约 15%——用于必要的轻量级边缘计算。

“如果‘计算无处不在’是我们努力实现的目标，那么 Kubernetes 就是实现目标的途径，”他说，并将新产品描述为该公司三层软件“KubeCake”的重要补充，该软件现在包括:

*   **第 1 层:各地认证的 Kubernetes 发行版** — Rancher 支持任何认证的 Kubernetes 发行版，包括 Rancher Kubernetes 引擎、K3s 和云服务，如 Google Kubernetes 引擎、Amazon Elastic Kubernetes 服务和 Azure Kubernetes 服务。
*   **第 2 层:Kubernetes 管理** — Rancher 为所有集群提供简单的管理和安全性，并向用户提供工具和服务，包括网络、服务网格、报告和监控。
*   **第 3 层:DevOps 自动化** —让开发人员轻松构建、部署和管理容器化应用。

KubeCon+CloudNativeCon 2019 和 Linux 基金会是新堆栈的赞助商。

来自 Pixabay 的 congerdesign 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>