# Calico Enterprise 3.9 带来实时数据包故障排除

> 原文：<https://thenewstack.io/calico-enterprise-3-9-brings-live-packet-troubleshooting/>

在大约六年前推出 Calico 开源软件 T1 后不久，我就一直推荐它用于容器网络和安全。但是，如果您想要更多的帮助和功能， [Calico Enterprise](https://www.tigera.io/tigera-products/calico-enterprise/) ，一个跨混合或多云配置(任何云、任何 Kubernetes 分发、虚拟机和裸机)的 Kubernetes 安全性和可观察性的自我管理平台，也需要您的关注。

有了 [Calico Enterprise 3.9](https://www.tigera.io/blog/whats-new-in-calico-enterprise-3-9-live-troubleshooting-and-resource-efficient-application-level-observability/) ，这一点比以往任何时候都更加真实，它使用需要访问底层数据的动态数据包捕获来提供更快、更简单的[实时故障排除](https://thenewstack.io/faster-troubleshooting-with-dynamic-packet-capture/)。

组织级数据包捕获存在许多问题。其中包括:

*   通过组织角色限制对数据包捕获的访问。
*   需要几个小时到几天来设置数据包捕获，而不是使其成为代码的一部分。一想到要用 Wireshark[做这件事，我就不寒而栗。](https://www.wireshark.org/news/20210827.html)
*   在不增加存储和计算成本的情况下捕获适量的数据极其困难。
*   花费数天甚至数周时间关联从不同 Kubernetes 组件(如名称空间、工作负载、pod 和微服务)收集的数据。

有了[动态数据包捕获](https://www.tigera.io/features/packet-capture/)，母公司 [Tigera](https://tigera.io/?utm_content=inline-mention) 宣称可以在你需要的时候收集到你需要的数据，不费吹灰之力。完成后，您可以基于协议和端口过滤数据，以微调其捕获，从而加快调试和后续分析，缩短解决问题的时间。它还使得跨不同的 Kubernetes 服务、名称空间、工作负载和 pods 关联数据变得更加容易。有了所有这些，再加上工作负载和 Kubernetes 的上下文，您可以快速查明问题，然后解决它们。我喜欢这个。我很喜欢这个。

动态数据包捕获功能还可以与 Kubernetes 基于角色的访问控制(RBAC)密切配合。这意味着您可以按角色分配访问权限，以降低安全性和合规性风险。再见无意的 HIPAA，PCI，SOC2 等。等。违反合规性。

最新的 Calico Enterprise 3.9 还将 [Envoy](https://www.envoyproxy.io/community.html) 作为 [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/) 与数据平面集成。这使得它对微服务舱的侵入性更小。这对于应用程序级的可观察性和控制是很方便的。

这比为相同的作业建立服务网格要容易得多，因为:

*   用户只需为每个节点管理和操作一个特使代理，而不是为每个单元管理和操作多个侧柜。这是一个小得多的潜在攻击面。
*   包括 Kubernetes 相关上下文和与其他组件的相关性的应用程序级信息使得故障排除更加容易。
*   在每个节点上使用 DaemonSet 而不是多个 sidecars 可以减少 CPU 和内存消耗。

最后，但绝非最不重要的是，在 3.9 版本中，你可以在微软 AKS 和[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)‘EKS】中获得点对点通信的传输中数据加密。

你觉得怎么样？已经知道并喜欢印花布？试试这个。这可能正是您对 Kubernetes 网络和安全性的需求。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>