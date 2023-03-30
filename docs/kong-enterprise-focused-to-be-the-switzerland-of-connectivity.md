# 孔企业致力于成为“连接的瑞士”

> 原文：<https://thenewstack.io/kong-enterprise-focused-to-be-the-switzerland-of-connectivity/>

服务连接软件提供商 [Kong](http://konghq.com) 发布了 [Kong Enterprise 2.1](https://konghq.com/products/kong-enterprise/) ，提供了各种新功能，但首席技术官和联合创始人 [Marco Palladino](https://www.linkedin.com/in/marcopalladino/) 解释说，这些功能的核心是自公司成立以来一直推动公司发展的同一个主题:连接。当 API marketplace Mashape 从整体服务过渡到微服务时，Kong 作为一个开源项目而诞生，它需要一个网关，可以在新的容器化基础设施上以去耦和分布式的方式运行。这一最新版本的核心扩展了 Kong 在多种环境中工作以及在各种类型的工作负载之间进行通信的能力。

Palladino 说:“如果不考虑连接性，您的组织将无法成功过渡到现代应用，更不用说微服务了。“我喜欢把香港比作互联互通的瑞士。我们保持中立，并与所有其他云供应商友好合作，以便能够提供这种基本上没有边界的连接。”

这种中立性是 Kong Enterprise 2.1 的关键，它引入了混合模式，使 Kong 用户不仅可以跨数据中心、云和地理位置运行 Kong 数据平面，而无需进行集中的 Cassandra 部署，还可以为运行在这些不同位置和服务上的虚拟机(VM)和容器提供集中的控制平面。

“当我们看基础架构架构师的角色时，这些人必须调配和支持在组织内执行任何工作的所有应用程序团队。其中一些在一个云上运行，一些将在 Kubernetes 上运行，一些将在传统虚拟机上运行。那么，不管底层基础设施如何，我们如何支持它们呢？Palladino 解释说:“通过支持在这些不同的架构、云或地理位置中运行的数据平面，我们可以更轻松地支持所有这些环境。“如果没有此功能，组织一直在使用不同的技术来管理不同孤岛中的连接。通过提供混合模式，我们可以减少碎片，从而提高连接管理的可靠性。”

> 就像我们如何使用 Kubernetes 来抽象数据中心运营一样，我们的客户正在使用 Kong enterprise 来抽象他们所有环境的连接。—马可·帕拉迪诺，孔

帕拉迪诺还指出，作为一项关键发展，Kong Enterprise 可以用作服务网格入口和出口，并与 [Kong Mesh](https://konghq.com/products/kong-enterprise/kong-mesh/) 集成，后者构建在今年早些时候加入云计算原生计算基金会(CNCF)的基于[特使](https://www.envoyproxy.io/)的[库马](https://kuma.io/)服务网格之上。虽然 Kong 最初打算在另一个基于 Envoy 的服务网格 [Istio](https://istio.io/) 的基础上构建这一功能，但 Palladino 表示，这最终太难了，Istio 太难扩展和使用，而且不支持多个网格，并将虚拟机视为二等公民。相比之下，Kong Enterprise 2.1 为库马提供了开箱即用的企业级支持，将虚拟机视为一等公民，是 Kubernetes 本地的，并将直接与 Kong API 网关集成。

Palladino 强调的最后一个变化与用 Kong 插件扩展 Kong 的能力有关。以前，这些插件必须用 Lua 或 C 编写，但 Kong 发布了一个 SDK，现在增加了对 Go 编程语言的支持。

展望未来，帕拉迪诺说，孔希望扩大其功能，以帮助正常运行时间，并扩大其作为控制平面的作用。

“我们有一套机器学习产品，现在可以进行异常检测和自动记录。我们真的希望我们的连接平台成为服务连接的 Waze，因为我们确实有数据平面作为边车运行在边缘，我们有数据平面运行在您组织中的每个服务旁边，”Palladino 说。“我们还可以自我修复，保持整个架构基础设施的正常运行时间，无需任何人工干预。我们将越来越多地致力于确保人类不会成为保持整个企业正常运行时间的依赖。”

云计算原生计算基金会是新堆栈的赞助商。

Pixabay 的 skeeze 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>