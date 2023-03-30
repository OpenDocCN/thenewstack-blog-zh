# 服务网状格局中的创新与变革 SoloCon 的邀请函

> 原文：<https://thenewstack.io/innovation-and-changes-in-the-service-mesh-landscape-an-invitation-to-solocon/>

[](https://www.linkedin.com/in/iditlevine/)

 [艾迪·莱文

Idit 是 Solo.io 的创始人兼首席执行官。她是 EMC 云管理部门的前首席技术官，也是其全球首席技术官办公室的成员，在那里她专注于整个堆栈、微服务、云原生应用和平台即服务的管理和协调(M&O)。Idit 被公认为各种云开源项目的主要贡献者，是集群管理(Kubernetes、Mesos 和 DockerSwam)方面的专家。](https://www.linkedin.com/in/iditlevine/) [](https://www.linkedin.com/in/iditlevine/)

在 [Solo.io](https://solo.io?utm_content=inline-mention) ，自 2018 年末我们推出 SuperGloo 以来，我们一直专注于大规模管理和编排服务网格，super Gloo 是一个固执己见的抽象层，也是 Gloo 网格的祖先。从那以后，我们理解了服务网格在微服务架构中的重要性，尤其是在 Kubernetes 中。

一晃两年多过去了，我们看到了服务网格领域的许多创新和变化。以下是对过去几年的一些观察和对不久的将来的预测。

**1。Istio 正在成为事实上的服务网，因为 Istio 和 Kubernetes 正在越走越近。**

很多年前，有一场关于哪个容器标准会成为事实上的标准的争论。今天，很明显，Kubernetes 是赢家。我也看到了这场关于服务网格的争论。有很多开源项目，但是根据我们与许多客户的讨论，我认为 Istio 正在成为事实上的标准。因此，我预计它将很快主导云原生环境。

Istio 和 Kubernetes 之间还有一种“共生关系”。Istio 一直在采用 [Kubernetes 服务 API](https://istio.io/latest/docs/tasks/traffic-management/ingress/service-apis/)来取代其现有的网络 API。Kubernetes 服务 API 旨在帮助用户从 Kubernetes 平稳过渡到任何实现它们的服务网格，因此我们预计 Istio 的举措将进一步提高其采用率。

**2。Istio 可以很容易地在边缘扩展企业级功能。**

我们的许多客户开始使用 Istio 的内置入口，但最终发现他们需要高级安全功能，如 WAF 和 DLP、请求和响应转换、高级外部身份验证、复杂的速率限制等。幸运的是，Istio 的架构提供了充分的机会来扩展所有这些特性，从而将其转变为企业级 API 网关。

**3。Web 程序集的可扩展性将会改变 Istio 的游戏规则。**

能够根据客户的具体需求定制 Istio 的重要性怎么强调都不为过。 [WebAssembly](https://webassembly.org/) (Wasm)是一种快速、高效、可移植的二进制指令格式，为平台扩展提供了一个可嵌入且安全的执行环境。使用 Wasm，用户可以编写(用任何语言)模块，以最适合他们需求的方式扩展他们的服务网格代理。我认为在不久的将来，Wasm 将成为动态扩展云原生应用的首选技术，Istio 将引领潮流。

**4。服务网格环境会很快变得复杂。**

迈出服务网格的第一步可能具有挑战性，因为它需要关注流量管理、策略、安全性和可观察性。一旦理解了这些基础知识，用户就可以在他们的多集群环境中部署服务网格了。然而，这带来了一系列新的挑战，包括服务网格的多个实例之间的协调。在这种情况下，拥有工具和策略来简化和统一集群间的配置、操作和可见性非常重要。

**5。所有正确的成分，但你能正确地组装它们吗？**

Istio 拥有许多强大的安全功能，可以保护您的应用程序免受网络内外恶意行为者的攻击。组织依靠 Istio 功能来满足旨在保护敏感数据环境的各种法规遵从性标准。这些包括加密、身份验证、授权、监控工具以及对进出流量的控制。不幸的是，启用和使用这些特性并不像点击复选框那么简单。正确配置这些策略(尤其是跨多个集群)需要更深入地了解默认行为、安装设置和 Istio CRDs，以及调试 Envoy 配置。未能正确配置会导致数据泄露或意外行为。

## **参加我们在 SoloCon 的更多服务网格讨论**

服务网格领域的新发展——尤其是 Istio 社区中的发展——提升了我对这个架构的热情和信心。这就是为什么我们 Solo.io 仍然是 Istio 社区的积极成员。我们致力于通过建议和支持以及我们的 Gloo Mesh 平台，帮助企业客户采用和运营他们的服务网格。

这也是即将到来的 SoloCon 的目标，在这里，我们、我们的客户和我们的开源社区将与 Istio 分享我们的经验。如果您想了解有关 Istio、塑造服务网格社区的趋势以及 Gloo Mesh 如何帮助您实现服务网格之旅的更多信息，我邀请您参加 3 月 23 日至 25 日在 SoloCon 举行的 **[大会。该会议旨在提供关于 Istio、服务网格、边缘网关以及其中许多主题的教育。](https://solocon.io/)**

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>