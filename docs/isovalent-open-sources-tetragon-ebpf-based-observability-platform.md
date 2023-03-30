# 等价开源 Tetragon，基于 eBPF 的可观测性平台

> 原文：<https://thenewstack.io/isovalent-open-sources-tetragon-ebpf-based-observability-platform/>

你想观察你的系统有多深？您想深入了解 Linux 内核吗？如果这对你来说听起来不错，你会很高兴地知道[等价](https://isovalent.com/)，一家将网络、安全、Kubernetes 和 [eBPF](https://ebpf.io/) 融入其程序的公司，最近开源了 [Tetragon](https://github.com/cilium/tetragon) 。这是一个非常有用的基于 eBPF 的安全可观察性和运行时实施平台。

你可能不知道它的名字，但 Tetragon 并不是一个新程序。Isovalent 已经在它的[等价纤毛企业](https://isovalent.com/product)项目中使用了多年。 [Cilium](https://cilium.io/) 通过 Kubernetes 身份监控网络和运行时行为，为云原生取证、审计和合规性监控提供单一数据源。总之效果很好。

就其本身而言，Tetragon 是一个运行时安全实施和可观察性工具。它在内核中直接在 eBPF 中实施策略和过滤。它直接在内核中过滤、阻止和响应事件，而不是将事件发送到用户空间代理。这意味着它在很低的水平上节省了时间和资源。

或者，正如 Isovalent 的联合创始人兼首席技术官托马斯·格拉夫(Thomas Graf)所说，“Tetragon 是一个巨大的飞跃，它将它一直扩展到底层内核可见性，带来了跟踪函数调用、进程执行等的能力。一直到内核子系统，并为平台和安全团队提供了大量高级观察功能。Tetragon 的运行基本上为可观察性‘超级用户’场景创造了无限的机会。”

例如，用 Tetragon 你可以看到内核子系统。这意味着您可以查看名称空间转义、功能和权限提升、文件系统和数据访问、协议(如 HTTP、DNS、TLS 和 TCP)的网络活动，甚至可以查看系统调用层以审核系统调用并跟踪流程执行。

## 不仅仅是可观察性

但是，Tetragon 不仅仅让你看到深层次的情况。你也可以影响它。因为 Tetragon 通过 eBPF 可以访问 Linux 内核状态，所以它可以将这个内核状态与 Kubernetes 感知或用户策略结合起来，以创建由内核实时执行的规则。这允许注释和执行进程名称空间和功能、进程套接字、文件名的进程文件描述符等等。

有了这些数据，Tetragon 可以通过在几个层上允许访问控制列表来在整个操作系统中实施安全策略。安全策略可以通过 Kubernetes (CRDs)、JSON API 或开放策略代理(OPA)等系统注入。

不算太寒酸，嗯？

Tetragon 还附带了一个代理，可以与现代可观察性和策略标准进行本机集成，如 Kubernetes、Prometheus、fluentd、OpenTelemetry、开放策略代理以及传统的安全信息和事件管理(SIEM)平台。

当然，如果你购买了 Isovalent Cilium Enterprise，Isovalent 会很高兴，但老实说，通过在 Apache 2 许可下开源 Tetragon，它为精通 Linux 的开发人员和管理员提供了所有他们需要的工具，来完成他们的云原生系统的出色工作。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>