# Kubernetes 不仅仅是关于容器——它是关于 API 的

> 原文：<https://thenewstack.io/kubernetes-is-not-just-about-containers-its-about-the-api/>

[](https://www.linkedin.com/in/viktorfarcic/)

[Viktor far CIC](https://www.linkedin.com/in/viktorfarcic/)

[Viktor far CIC 是 Codefresh 的首席 DevOps 架构师，Google 开发者专家和 Docker Captains 组的成员，也是一名已发表的作者。](https://www.linkedin.com/in/viktorfarcic/)

[](https://www.linkedin.com/in/viktorfarcic/)[](https://www.linkedin.com/in/viktorfarcic/)

“Kubernetes 是一个可移植、可扩展的开源平台，用于管理容器化的工作负载和服务，有助于实现声明式配置和自动化。”

当项目开始时，这句话可能是一个很好的描述。今天，情况非常 diﬀerent，虽然不一定以一种明显的方式。Kubernetes 不仅用于管理 c *容器化的工作负载和服务*。我们可以使用 Kubernetes 来管理虚拟机，通过像 KubeVirt 这样的项目。我们可以使用 [ORKA](https://www.macstadium.com/orka) 来管理 macOS 机器和应用程序。Kubernetes 通过服务创建和管理外部负载平衡器已经有一段时间了。Kubernetes 管理的资源类型越来越多，因此我们不能说它是一个用于管理容器化工作负载和服务的*平台。*那么，如果那不是它，那是什么？或者更准确地说，Kubernetes 给我们的主要特征是什么？

> Kubernetes 完全是关于 API 及其接收事件的能力，并拥有监听这些事件的控制器。

API 本身被设计成可扩展的，并且正在变得通用。这就是 KubeVirt 和 ORKA 等项目选择 Kubernetes 来管理非容器事物的主要原因。他们这样做主要是因为 Kubernetes API 的功能，以及用户对可以管理(几乎)一切的通用 API 的普遍需求。

如果 Kubernetes API 正在成为事实上的标准，那么想想这对我们今天或在不久的将来意味着什么是很有趣的。一般来说，我们需要管理基础设施和运行在其上的应用程序。这是 Kubernetes API 可以覆盖的两个主要领域。

就应用而言，有两件事变得很明显。我们正在采用(或者已经采用)不变性，这意味着打包应用程序的流行方式是图像。我们需要将这些图像转换成容器、虚拟机或我们可能使用的任何其他运行时格式的过程；然后找出运行它们的最佳位置，并确保(几乎)始终保持所需的状态。故事的这一章已经结束了。尽管我们将继续看到这一领域的显著改进，但这可能是基于可用性而不是主要目标。

现在，更令人兴奋的方面是基础设施。

如果 Kubernetes API 正在成为通用和事实上的标准，那么我们不仅应该在应用程序中使用它，而且应该在基础设施中使用它。我认为这是下一个前沿领域。将基础设施管理引入 Kubernetes API 将把它转换成一个真正通用的事实上的标准。

有人可能会说，“使用 Kubernetes API 来管理我们的基础设施并不是放弃我们最喜欢的工具的足够好的理由。”然而，这将是短视的，因为同样的 API 是促成有史以来最大的生态系统的主要方面。今天，很大一部分创新是围绕 Kubernetes 进行的。大多数项目被转换到 Kubernetes 内部工作。过去几年中制作的大多数都是专门设计的，以利用我们在 Kubernetes 内部运行和利用其 API 所获得的优势。因此，设计用来利用 Kubernetes API 管理我们的基础设施的项目将允许我们对所有事情使用相同的 API；因此比其他人更好地利用我们在 Kubernetes 周围的生态系统。

我们有一个最接近的候选工具，可以作为基础设施即代码(IaC ),利用 Kubernetes API 背后的力量，这个工具就是 [Crossplane](https://crossplane.io/) 。我们可以通过我们最喜欢的工具来管理它，比如 Helm 或 Kustomize。如果我们想按照 GitOps 的原则使用它，我们可以将它与 Argo CD 或类似的工具结合使用。相反，如果我们想在更改 Git 中存储的定义时触发管道构建，我们可以使用 Kubernetes-native 解决方案之一，如 [Codefresh](https://codefresh.io/codefresh-signup/?utm_source=Blog&utm_medium=Post&utm_campaign=vfarcic-crossplane) 。或者，如果我们想监控它的行为，我们可以从[普罗米修斯](https://prometheus.io/)那里获取指标。

我们是否可以用那些不是为利用 Kubernetes API 而设计的基础设施即代码(IaC)工具来做所有这些和许多其他事情？我们当然可以。但是，在这些情况下，我们并没有获得 Kubernetes 提供的所有好处。Crossplane 是否会成为管理基础设施的下一个重要解决方案还有待观察。然而，一旦我们真的到了 Kubernetes API 被广泛用于管理应用程序和基础设施的地方，它将成为(几乎)一切的通用 API。这一天即将到来，因为我们都在采用 Kubernetes——不是因为它运行容器，而是因为它的 API。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>