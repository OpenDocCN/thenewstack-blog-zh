# Gloo Federation 带来了跨多集群部署的统一控制平面、可拼接 API

> 原文：<https://thenewstack.io/gloo-federation-brings-unified-control-plane-stitchable-apis-across-multicluster-deployments/>

对于大规模运营并要求高可用性的企业来说，确保 Kubernetes 节点级别的故障转移是远远不够的。相反，许多公司都在多集群环境中运行，确保即使在集群级别出现故障，他们的应用程序仍能正常运行。

对于同时运行 [Solo.io](https://www.solo.io/) 的 Gloo [API 网关](https://www.solo.io/solutions/api-gateway/)和入口控制器的公司来说，这种多集群环境已经成为一个痛点，因为每个集群都需要自己的 Gloo 部署，这反过来意味着配置、管理和控制平面。作为回应，Solo.io 推出了 [Gloo Federation](https://www.solo.io/blog/gloo-federation-technical-deep-dive/) ，它汇集了部署在集群、云和区域的多个 Gloo 实例，允许通过统一的控制平面进行配置和流量管理。

“我们在我们的大客户身上看到的是，他们每个人都在很多地方有很多集群，他们在每个地方都放了 Gloo，这完全没问题，但唯一的问题是现在它非常分散。基本上，他们看不到任何地方发生了什么，或者管理它。Solo.io 首席执行官 [Idit Levine](https://www.linkedin.com/in/iditlevine/) 说:“他们亲自对每个集群进行配置，确保一切正常。

Levine 说，有了 federation，Gloo 不仅能够发现各种集群中的所有其他 Gloo 实例，并提供单点管理和配置，还能够从这些实例中收集所有数据，并提供单一位置进行故障排除。Gloo Federation 的集中控制平面允许管理员在部署范围或单个实例的基础上处理配置，并提供故障转移功能和基于位置的路由。关于这最后一点，Levine 指出，基于位置的路由可以在由于本地数据管理限制而无法访问最终用户数据的情况下提供对最终用户数据的访问。

[https://www.youtube.com/embed/Jx8vx2OtxTY?feature=oembed](https://www.youtube.com/embed/Jx8vx2OtxTY?feature=oembed)

视频

Levine 强调的另一个特性是 Gloo 对基于角色的访问控制(RBAC)的处理，它通过 Kubernetes 钩子的用户，抽象出了一些围绕权限的复杂性，并将其从 Kubernetes 的手中拿走。

“对于多集群，总是存在复杂性。RBAC 是谁能做什么。您想要更改路由的配置吗？你被允许吗？这很危险，因为你可以把网络上的所有东西都拆掉。现在，这种复杂性变成了我的。在此之前，是 Kubernetes 的复杂性，”莱文说。

除了联合 Gloo 本身和处理分发带来的复杂性的直接影响之外，Levine 还指出了另一个下游好处——将跨集群的 API 缝合到单一“API 产品”中的能力。在该公司最近推出的 Istio 开发者门户网站中，它将这些 API 产品作为面向终端用户的 API 进行了介绍，这些 API 是由多个内部 API 拼接而成的。Gloo 联盟现在将这种能力扩展到了集群之外。

“您可以从一个集群中取出一个微服务，从另一个集群中取出一个微服务，并将它们合并成一个 API 产品。Levine 说:“微服务可能位于不同的位置，甚至可能位于不同的大陆，但你仍然可以将它作为一个应用程序展示给用户。”他解释说，这也允许不同的团队共享微服务。“我认为它极其强大，但它并不存在。我们把世界带到了一起，这就是力量所在。”

Gloo Federation 面向 Gloo Enterprise 客户在[试用](https://lp.solo.io/lp-request-a-trial-general)，感兴趣的用户可以在即将举行的网络研讨会上了解更多信息。

图片由来自 Pixabay 的 Gerd Altmann 提供。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过[推特](https://twitter.com/thenewstack)或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>