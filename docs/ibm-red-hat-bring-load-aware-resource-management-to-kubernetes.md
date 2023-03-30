# IBM、Red Hat 为 Kubernetes 带来负载感知资源管理

> 原文：<https://thenewstack.io/ibm-red-hat-bring-load-aware-resource-management-to-kubernetes/>

IBM Research 和 T2 Red Hat open shift 的工程师最近联手解决了一个困扰 Kubernetes 领域的问题——如何在考虑现有负载和模式的情况下更有效地管理资源。虽然 Kubernetes 以其处理大量流量增长的能力而闻名，但它是通过水平扩展来实现的，即添加更多的单元和节点，而不是垂直扩展。此外， [Kubernetes 调度器](https://kubernetes.io/docs/concepts/scheduling-eviction/kube-scheduler/)放置应用程序容器时并不考虑节点的当前实际利用率。

[IBM t . j . Watson Research Center](https://www.linkedin.com/in/alaa-youssef-b0b75a13/)的容器云平台研究经理 Alaa Youssef 解释说，Kubernetes 实际上是“一个非常好的计数器”，但没有考虑到当前和历史的利用率，这些利用率可以使它更有效地运行。

“我们正试图在时间安排和规模上增加更多的智能，”他说。“我们必须从扩展 Kubernetes 框架开始。我们在 Kubernetes 的调度框架中实现的一件事是能够在调度决策中使用节点的实际利用率信息。信不信由你，这是库伯内特直到今天才有的东西。任何人现在都可以使用更智能的算法，在做出更好的调度决策时利用这些节点利用率信息。"

为了解决这个问题，团队决定在上游 Kubernetes 上构建解决方案，从两个不同的方向着手，这两个方向都是他们最近发布的开源项目。

首先，[三体负载感知调度器插件](https://github.com/kubernetes-sigs/scheduler-plugins/tree/master/pkg/trimaran)工作以“考虑工作节点上的实际使用——这是 Kubernetes 没有考虑的，”正如 [IBM](https://www.ibm.com/cloud?utm_content=inline-mention) 在[博客文章](https://www.research.ibm.com/blog/predictive-resource-management-openshift)中所写的。考虑到这种用法，Trimaran 将应用程序放置在最能提供高效集群利用率的节点上，避免使用负载波动较大的节点，以免影响应用程序的性能。

接下来，[Vertical Pod auto scaler(VPA)](https://docs.openshift.com/container-platform/4.8/nodes/pods/nodes-pods-vertical-autoscaler.html#nodes-pods-vertical-autoscaler)是一个开源控制器，现在可以在 Red Hat OpenShift 4.8 中使用，它允许开发人员自动调整容器的大小。VPA 通过审查 pod 中容器的历史和当前 CPU 和内存使用情况来管理规模，然后根据这些值更新资源限制和请求。

有了 VPA，优素福说，开发商可以不那么精确的他们目前和未来的需求，在必要的资源，一个容器。“你可以依靠垂直自动缩放器来检测你需要更多的资源，并开始要求 Kubernetes 在运行中给你更多的资源，”Youssef 解释说。

从本质上讲，这两种解决方案从相反的角度解决了同一个问题:三体船试图在根据当前和历史使用情况调度负载时预先优化性能，而 VPA 通过事后垂直扩展来实现这一点，根据应用程序观察到的资源使用情况将其容器的大小更改为正确的大小。

[IBM Research 云平台研究主管 Priya Nagpurkar](https://www.linkedin.com/in/priya-nagpurkar) 解释说，三体船和 VPA 只是第一步，尤其是三体船是未来创新的潜在基础。“Kubernetes 为您提供了许多调度和布局所需的旋钮，但在如何智能地驱动这些旋钮方面，仍有许多未开发的机会。这里的团队也参与了 Kubernetes 的设计，在某种程度上，正确的旋钮是存在的，”Nagpurkar 说。“Kubernetes 开始时有一些调度机制等等，但现在，有了我们的贡献，你可以用更多的智能和更多的算法来驱动它。”

PayPal 已经在生产中利用了三体船，为三体船建立了它的[负载观察器](https://github.com/paypal/load-watcher)，一个集群范围的指标聚合器。

对于三体船和 VPA，Nagpurkar 和 Youssef 都表示，他们看到了人工智能和人工智能可以用于提高效率和性能的未来。

Nagpurkar 说:“我们的目标是对云平台采取更少操作、更多以应用为中心的观点，并使其更具适应性和更自动化。“我认为在未来，这将只是在平台上透明地使用，用户不必做很多事情，但我认为这是更长期的愿景。智能平台将与这些工具和框架无缝集成。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>