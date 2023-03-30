# 新的 Alcide 版本增强了 Kubernetes、Istio 的安全性

> 原文：<https://thenewstack.io/new-alcide-release-enhances-kubernetes-istio-security/>

微服务安全厂商 [Alcide](https://www.alcide.io/) 的最新版本专注于保护复杂的多集群 Kubernetes 和 Istio 部署。

根据 451 Research 的一份报告，Alcide 因其专注于安全的 DevOps 而与众不同。它支持云原生应用程序开发人员将安全策略作为代码嵌入到 CI/CD 管道中。同时，Ops 和 Sec 团队可以使用机器学习持续监控和保护不同集群的异常行为，并在单个事件流中查看整个环境。

> Alcide 支持云原生应用开发人员将安全策略作为代码嵌入到 CI/CD 管道中。

这家总部位于特拉维夫的初创公司在 2018 年 4 月推出了云原生安全平台，然后在次年 7 月更新了该平台，支持无服务器。

新的增强功能包括:

*   **扩展的攻击检测覆盖范围，**包括基于算法的恶意软件检测，以及使用机器学习的对等容器分析，以基于历史上下文和对等体的上下文来确定正常行为。
*   **智能** **威胁管理器警报，**提供将警报发送给适当人员并将威胁警报导出到所选管理平台的能力。
*   **端点** **嵌入式策略**，能够将安全策略直接嵌入到工作负载中，从而在部署工作负载的任何地方实现有效的运行时微分段。
*   **除了 AWS 和 Azure 之外，在谷歌的云平台市场**上的可用性。

Alcide 与越来越多的微服务和容器安全供应商竞争，包括 [NeuVector](https://thenewstack.io/neuvector-adds-enhanced-security-to-service-meshes/) 、 [Capsule8](https://thenewstack.io/capsule8s-stopping-attacks/) 、 [Aqua Security](/aqua-securitys-kubernetes-benchmarks-get-cis-approval/) 、 [Twistlock](/twistlock-enhances-visibility-into-multicloud-istio-kubernetes/) 和 [Anchore](/anchore-container-security-starts-with-the-images/) 。

Alcide 自称是微服务防火墙。

传统防火墙应用在边缘，微服务环境没有清晰的边缘。Alcide 微服务防火墙作为运行微服务的基于主机的代理运行。在 Kubernetes 上，它被部署为 DaemonSet 在无服务器上，它被部署为功能代理。

Alcide 的联合创始人兼首席技术官 [Gadi Naor](https://www.linkedin.com/in/gadinaor/?originalSubdomain=il) 表示，它可以实现针对微服务如何相互交互的细粒度细分和细粒度策略，并提供异常检测。

他指出，云原生技术和 Kubernetes 的采用是由 DevOps 推动的，而不是 IT，并补充说，传统的安全解决方案不是为分布式环境设计的，在分布式环境中，有多个团队开发整个应用程序的小部分。

他说:“当你将两者结合起来时，你最终会需要一些全新的和不同的东西，将安全融入到开发过程中，并将安全融入到生产中。”“[它]允许开发人员和开发人员在代码中捕获安全策略…从代码到产品有许多阶段，我们的产品在这些阶段进行部署。”

这些增强功能使用户能够在测试阶段尽早发现是否有行为不当的元素。他说，改进的微服务异常检测，特别是围绕利用 VNS 基础设施的攻击，没有效率较低的传统产品的开销。

Alcide 使用户能够实时搜索、控制和执行策略，包括将应用程序与互联网、负载平衡器以及内部出口和第三方服务隔离的能力。

事件可以流式传输到其仪表板以及 Slack 和 Splunk 等其他工具。

根据 451 Research 的说法，它执行统计分析和基于规则的检测，但主要关注微服务抽象级别，而不是底层基础设施。它组织了可视元素，以便对外部和内部组件以及外部服务的标注有一个清晰的理解。特定于应用程序和特定于服务的视图也是可用的。

它称赞了该公司的直观可视化以及与 ChatOps 的集成。它提到的弱点是应用程序可见性的协议数量有限(DNS 和 HTTP)，并表示其基于代理的方法可能会限制某些托管环境中的部署选项。

*您可以在此查看 Alcide 关于 Kubernetes 和 Istio security 的网络研讨会。*

Twistlock 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>