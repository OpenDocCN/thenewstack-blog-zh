# HashiCorp 深化了与 Kubernetes 和 CNCF 项目的整合

> 原文：<https://thenewstack.io/hashicorp-deepens-integrations-with-kubernetes-and-cncf-projects/>

[](https://www.linkedin.com/in/armon-dadgar/)

 [艾蒙·达德加尔

艾蒙是哈希公司的联合创始人兼首席技术官。他对安全性和分布式系统及其在现实世界问题中的应用充满热情。](https://www.linkedin.com/in/armon-dadgar/) [](https://www.linkedin.com/in/armon-dadgar/)

HashiCorp 已正式加入云计算原生计算基金会(CNCF)，以深化社区参与并为项目集成提供官方支持。

自 2012 年以来，HashiCorp 一直在开发开源工具，以实现云基础设施自动化。在那段时间里，我们发布了主要项目，如流浪者，包装，执政官，地形，金库和游牧。数百万 IT 从业者每天都在使用这些工具。我们还发布了 HashiCorp 的 [Tao，这是我们工具背后的设计理念，也是我们如何考虑构建新工具并随着时间的推移对其进行改进的指南。](https://www.hashicorp.com/tao-of-hashicorp)

我们在该文档中列出的两个最重要的原则是我们对工作流的关注，以及使技术生态系统可插拔和可组合。尤其是基础设施工具，我们生活在一个不断变化的丰富且不断增长的解决方案生态系统中。我们的方法使我们的用户能够快速采用新技术，而不必改变他们的工作流程。

过去几年中，一些最重要的基础设施技术已经成为 CNCF 的一部分，包括 Kubernetes、Prometheus、Envoy 和 Helm。随着这些工具被广泛采用，HashiCorp 的用户和客户渴望将它们与我们的工具组合一起使用。

在我们的产品组合中，我们整合了 CNCF 的项目。一些例子:

*   **Kubernetes 和 Helm 的原生地形提供商。** Terraform 的 [Kubernetes 提供者](https://registry.terraform.io/providers/hashicorp/kubernetes/)拥有数十种资源，从高级集群设置到使服务易于指定和部署。Terraform [Helm provider](https://registry.terraform.io/providers/hashicorp/helm/) 允许用户使用现有的 Helm 图表将服务部署到他们的 Kubernetes 集群，而不需要分割他们的工作流。

*   **服务网与领事。** Consul [与 Kubernetes](https://www.consul.io/docs/platform/k8s/index.html) 在多个层面进行整合，实现现代服务网络化。这包括传统负载平衡器、防火墙和 API 网关的网络自动化，以将传统基础设施连接到 Kubernetes。现代服务网格技术使服务到服务的通信高度动态和安全，而无需部署传统的中间件设备。

*   **土著使节与领事的融合**。领事也提供了与特使的本地集成。这既可以在 Kubernetes 环境中使用，也可以与传统的基础设施一起使用。Envoy 可以用作服务网格的[边车代理](https://www.consul.io/docs/connect/proxies/envoy.html)，传统的 API 网关或入口层，或[网格网关](https://www.consul.io/docs/connect/mesh_gateway.html)以支持多数据中心联网。

*   **用金库进行秘密管理。** Vault 提供了与 Kubernetes 的[平台集成，能够存储静态凭证、生成 API 密钥和证书等动态凭证，或者通过加密数据和卸载密钥管理和加密来保护应用数据。Vault 使用的基于身份的安全方法使 Kubernetes 应用程序具有高度的动态性，而不会受到具有静态规则和批准的传统安全团队的限制。](https://www.vaultproject.io/docs/platform/k8s/)

*   **舵图展开。**我们提供支持的掌舵图来部署 [Vault 服务器](https://www.vaultproject.io/docs/platform/k8s/helm/)和[consult 代理和服务器](https://www.consul.io/docs/platform/k8s/helm.html)。这使得用户更容易以 Kubernetes 本地的方式开始和管理我们的工具。

*   **普罗米修斯度量集成。**我们的许多项目，如[金库](https://www.vaultproject.io/docs/internals/telemetry/)、[领事](https://www.consul.io/docs/agent/telemetry.html)和[游牧](https://nomadproject.io/docs/telemetry/)都与 Prometheus 集成，以实现健康检查和指标信息的导出。

*   **容器原生联网。**CNI 项目允许丰富的网络供应商生态系统使用标准化接口进行集成。Nomad 与 CNI 整合，支持更广泛的集装箱网络生态系统。

我们在整个产品组合中完成了更多的集成，但这给人一种我们在各种 CNCF 项目中所做努力的感觉。

几年来，我们已经非正式地成为这些社区的一部分。我本人[在 KubeCon](https://www.hashicorp.com/resources/vault-secret-management-kubernetes) 演讲过，来自 HashiCorp 的多位[开发者拥护者也是如此。我们的工程和开发商宣传团队也参加了许多全球活动。](https://www.hashicorp.com/resources/modern-service-networking-consul-connect-envoy-k8s)

我们工具的主要用户和客户对我们与 CNCF 项目的集成有着至关重要的依赖，并要求我们就未来支持的意图提供明确的信息。我很兴奋地宣布 HashiCorp 已经正式加入 CNCF 来做这件事。虽然我们一直是许多工具的支持者并提供集成，但我们打算与社区密切合作来扩展这些集成。

这改变了什么？首先，希望看到哈希公司更多地出现在 CNCF 社区。我们计划在网上和世界各地参加更多的 KubeCon 活动，扩大参与范围。我们在活动中的展位经常被询问问题的用户淹没，我们将有更多的人准备好支持社区。

接下来，期待看到我们致力于更深更广的整合。我强调了我们所做的一些工作，但我们致力于确保 Kubernetes 在我们所有的产品上都是一流的体验。在 CNCF 的其他项目中，我们希望合作确保无缝集成，就像我们已经与 Envoy 和 Prometheus 合作一样。

最后，我们希望听取社区对我们可以做得更好的地方的意见。这是一个庞大的生态系统，我们希望了解我们可以改进的机会，包括我们可以打磨哪些锐利的边缘。我们鼓励人们在 GitHub、我们的[讨论论坛](https://discuss.hashicorp.com)或其他[社区活动](https://www.hashicorp.com/community/)上参与我们的团队。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>