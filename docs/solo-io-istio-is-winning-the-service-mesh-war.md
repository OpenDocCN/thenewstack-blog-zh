# Solo.io: Istio 正在赢得网络服务之战

> 原文：<https://thenewstack.io/solo-io-istio-is-winning-the-service-mesh-war/>

solo.io 高管表示，开源 Istio 已经成为管理 Kubernetes 环境和微服务的“主导”服务网络。

[Gloo Edge 2.0](https://thenewstack.io/gloo-edge-2-0-a-fully-istio-integrated-api-gateway-for-multiple-clusters/) 将于年中发布测试版，Posta 表示，这是“第一个也是唯一一个”拥有所有 Istio 原生功能的 Istio 原生 API 网关。例如，入口控制器将集成 [Istio](https://istio.io/latest/docs/concepts/what-is-istio/) 以形成单个控制平面。

Solo.io 的声明也恰逢 solo.io 的 [Gloo Mesh](https://docs.solo.io/gloo-mesh/latest/) 和 [Gloo Edge](https://docs.solo.io/gloo-edge/latest/introduction/) 平台宣布了新的功能特性，其中包括 [Istio](https://istio.io/latest/docs/concepts/what-is-istio/) 与 Gloo Mesh 和 Gloo Edge 之间更紧密的集成。

Posta 声称 Istio 是微服务的“主导”服务网格，这在很大程度上是基于[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)的调查结果。

根据 2020 年 CNCF 云原生调查的 1000 多份回复，最近被 solo.io 聘为开源总监的 Istio 技术监督委员会成员孙林在周三的主题演讲中展示了在生产中使用服务网格的用户中有超过 40%是 Istio 用户。

更准确地说，[CNCF 2020 年的调查](https://www.cncf.io/wp-content/uploads/2020/11/CNCF_Survey_Report_2020.pdf)显示，在生产中使用服务网格的所有组织中，有 47%使用 Istio，其次是 Linkerd 和 Consul，两者的市场份额分别为 41%(一个组织可以使用多个网格)。

孙认为，Istio“显然处于领先地位”。

Sun 表示，Istio 在 2020 年的改进包括如何简化控制平面组件，以便在一个控制平面中有多个组件，称为“Istio”(Istio 守护程序)。“这确实大大简化了 Istio 的操作、安装和配置，”她说。

此外，需要搅拌机组件已被删除，以前需要运行 Istio，孙说。“我们中的许多人都担心性能问题，因为混频器的缘故，他们不得不禁用遥测技术。所以社区引入了“无混合器遥测技术”"

在周三的主题演讲中， [Zymergen](https://www.zymergen.com/) 的站点可靠性工程师 [Gigi Jackson，一位自称“生物制造商”的人，描述了她的组织如何使用 Gloo Mesh 和 Istio 的服务网格设计模式来“解决常见问题”，例如，与管理 sidecar 代理相关的问题。她说，Istio 允许应用程序网络层以“安全、可靠和可观察的方式”受益于跨多个集群的“服务到服务通信”，以便服务所有者可以专注于业务逻辑。](https://www.linkedin.com/in/gigijackson)

在他的 SoloCon 演讲“Istio 和 Gloo Mesh 安全模型”中，[的现场工程师 Lawrence Gadban](https://www.solo.io/blog/author/lawrence-gadban/) 讨论了 Isto 和 Gloo Mesh 提供的安全能力。他指出，例如，Istio 1.9 的发布引入了一个新的“自定义操作”概念。Gadban 说，这一功能为用户提供了定制的逻辑控制，而不是“要么允许，要么拒绝”的决定。

“这非常强大，将为 Istio 之上的一些更先进的工具打开大门，”Gadban 说。

访问和授权策略可应用于从源到目标工作负载的流量。Gadban 提到 Gloo Mesh 如何允许用户为集群拓扑创建复杂的访问规则，以及服务名称空间拓扑。

Gadban 说:“你可以看到这如何允许你制定非常复杂的规则来表达复杂的安全要求，因为你是在一个多集群的世界中操作的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>