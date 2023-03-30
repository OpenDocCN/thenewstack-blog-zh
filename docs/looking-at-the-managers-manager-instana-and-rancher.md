# 看经理的经理:Instana 和 Rancher

> 原文：<https://thenewstack.io/looking-at-the-managers-manager-instana-and-rancher/>

Portworx 赞助了 New Stack 对 KubeCon+CloudNativeCon 北美 2019 的报道。

当出现问题时，您不仅仅需要访问日志。你需要了解全局。

对应用结构的上下文和完全可见性的需求促使应用性能管理公司 Instana 与 [Rancher](https://rancher.com) 建立集成，这是他们在圣地亚哥的 KubeCon 上宣布的。

“他们几乎就像是 Kubernetes 的经理中的经理，”[Instana](https://www.linkedin.com/in/peteabrams/)的首席运营官皮特·艾布拉姆斯解释道。“这与 EKS 或 GKS 的作品略有不同。他们对待 Kubernetes 的方式与我们对待 APM 的方式几乎相同。

他的意思是，对于 Instana 和 Rancher 来说，有两个主要的、互补的用例——一个开发人员用例，它是关于获得快速反馈(在 Instana 的情况下)和快速建立 Kubernetes 环境(在 Rancher 的情况下)。然后是运营用例:确保稳定性、质量和安全性，以及在问题发生时为运营商提供快速解决问题所需的所有环境。

但是还有其他理由来支持牧场主。Instana 看到客户使用 Rancher 来部署 Kubernetes 环境，并使用 Rancher 来管理配置，但是当 Rancher 管理的配置出现问题时,[没有可见性](https://thenewstack.io/observability-a-3-year-retrospective/)来关注问题。

“牧场主是 Kubernetes 之上和周围的一层，”艾布拉姆斯说。Instana 已经有了对 Kubernetes 的支持，并且已经能够辨别，例如，正在使用的是什么口味的 Kubernetes，并跟踪特定于某个 Kubernetes 发行版的问题。然而，在 Rancher 支持之前，Instana 无法判断 Rancher 是否用于部署这些环境。

艾布拉姆斯说:“这都与环境有关。“牧场主被用来创造库伯内特环境的事实没有联系。”本质上，堆栈中有一部分是不可见的，这使得故障排除更加困难和耗时。

“假设我有一个性能问题，我发现这个性能问题是因为这个服务没有足够的处理能力，”Abrams 说。“嗯，等等。规定如何创建该环境的配置规则在哪里？”如果你能立即看到它不在 GKE，而是在 Rancher，这就缩短了解决问题的时间。

“这是一种环境意识，”艾布拉姆斯说。“当事情开始变得奇怪时，这正是人们所需要的。他们需要理解什么时候这个东西和那个东西联系在一起，并且依赖于那个东西。现在，这在我的指尖更容易。”

KubeCon+CloudNativeCon 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>