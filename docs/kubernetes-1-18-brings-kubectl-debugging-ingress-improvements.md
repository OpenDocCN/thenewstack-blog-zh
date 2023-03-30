# Kubernetes 1.18 带来了 Kubectl 调试、入口改进

> 原文：<https://thenewstack.io/kubernetes-1-18-brings-kubectl-debugging-ingress-improvements/>

随着云计算原生计算基金会 Kubernetes 1.18 的发布，开源容器编排平台已经在新的实验性“alpha”功能、处于测试阶段的功能(“Beta”)和现已准备好用于生产发布的功能之间实现了最佳平衡，发布 K8s 负责人 [Jorge Alarcon](https://github.com/alejandrox1) 断言。

总的来说，这个版本有 38 个“增强”:15 个增强正在进入稳定版，11 个增强在 Beta 版，12 个增强在 alpha 版。Alarcon 说，alpha 功能是一个新提出的增强功能，可以在不实际破坏 Kubernetes 的情况下工作，而 Beta 功能则通过大量端到端测试来证明其兼容性，升级到稳定意味着它已经在多个版本中无缝工作，包括许多很少使用的边缘情况。

这个版本中的许多新特性展示了这个项目致力于改善[开发者体验](https://thenewstack.io/qa-intuits-developer-experience-with-kubernetes/)，这是软件的一个持续挑战。“现在库伯内特斯的状态非常好。人们使用它；它工作了。因此，我看到人们正在努力的下一个标志是如何让开发人员的体验更加舒适，”阿拉尔孔说。

也许最值得注意的是调试功能，在 alpha 中，用于 [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) 命令行界面。“ **kubectl debug** ”命令提供了一种进行交互式故障排除的方法，以及创建一个临时容器与被调查的 Pod 一起运行的能力。

数据中心解决方案的 Canonical 产品经理 Alex chalk IAS[在一封电子邮件中热情洋溢地表示，kubectl debug 命令“是故障排除方面的一大改进，比如将临时容器部署到正在运行的 pod，或者在主机名称空间中启动特权容器”。](https://www.linkedin.com/in/alexchalkias)

另一个需要增强的领域是 Kubernetes 的[入口](https://kubernetes.io/docs/concepts/services-networking/ingress/)，它提供负载平衡和流量路由。新的“路径类型”字段指定了路径应该如何匹配，并提供了支持“精确”和“前缀”路径类型的新选项。取代**kubernetes.io/ingress.class**，新的**Ingres class**资源可用于描述进入 Kubernetes 集群的流量类型。

其他新功能包括拓扑管理器(Beta)，它允许要求低延迟的工作负载享受 CPU 和设备的 [NUMA](https://www.kernel.org/doc/html/v4.18/vm/numa.html) 对齐。新版本的服务器端应用(Beta)可以跟踪和管理所有新 Kubernetes 对象的字段更改。

Canonical 的 Chalkias 还指出，对于 Canonical 的 [Charmed Kubernetes](https://ubuntu.com/kubernetes/features) 以多云为中心的发行版，对 Multus 和 CephFS 文件系统的支持得到了改善，这一点非常值得赞赏。Chalkias 写道:“Multus 使您能够在 pod 中定义多个网络接口，允许您分割网络流量(数据平面与管理平面)”。“CephFS 集成允许多个 pod 共享相同的读写文件系统进行存储。”

Kubernetes 的使用，尤其是在生产环境中，继续增长。CNCF[最近的年度调查](https://www.cncf.io/cncf-annual-report-2019/)发现，78%的受访者在生产中使用 Kubernetes，而去年为 58%。CNCF 将于 4 月 23 日举办一场网络研讨会，更详细地解释 Kubernetes 1.18 的主要新功能。

云计算原生计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>