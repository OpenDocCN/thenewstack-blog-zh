# CNCF 的 Falco 运行时安全工具从沙盒中毕业，进入孵化阶段

> 原文：<https://thenewstack.io/cncfs-falco-runtime-security-tool-graduates-from-the-sandbox-moves-into-incubation/>

[Falco](https://falco.org/) ，开源云原生运行时安全项目，是 2018 年 10 月第一个加入[云原生计算基金会(CNCF)](https://www.cncf.io/) 沙盒的运行时安全项目，现在可以宣称同样有加入孵化阶段的先例。Sysdig 和 Falco maintainer 的首席开源倡导者 Kris Nova 说，Falco 最初由 [Sysdig](https://sysdig.com/) 创建，在运行时检测并警告意外行为，采取了与当今 CNCF 其他安全项目不同的方法。

“我们来自一个传统的自省背景。现在我们处于云原生生态系统中，我们已经更进一步，我们现在使用内核作为一种方式，试图了解更多关于运行时系统中发生的事情，”Nova 告诉新的堆栈。Falco 可以作为一套制衡措施的一部分，与 CNCF 的开放策略代理和基于角色的访问控制(RBAC)或其他保护 IT 基础设施的预防技术一起使用。

Nova 解释说，CNCF 的其他安全项目目前可以抵御入侵，但 Falco 的不同之处在于，当出现入侵时，它会做出反应。“没有真正安全的软件，”Nova 说，“所以我们只是利用可观测性，在运行时尽可能多地获取信息，以防有东西通过我们应用于系统的预防技术。”

Falco 通过实现[扩展的 Berkeley Packet Filter (eBPF)](/linux-technology-for-the-new-year-ebpf/) 提供了运行时安全性，它允许工具在 Linux 内核级别捕获系统调用，而不会影响性能。Falco 从 eBPF 获取信息，并将其与来自 container runtimes 和 Kubernetes 的信息结合起来，创建一个 normal 的定义，并与之进行比较。Nova 说，目前，该项目使用 Sysdig 提供的 eBPF 实现来实现这一点，但是下一步的计划是提出一个开源的 eBPF 实现。

[https://www.youtube.com/embed/Z4POV5IXnHQ?feature=oembed](https://www.youtube.com/embed/Z4POV5IXnHQ?feature=oembed)

视频

“Falco 所基于的更深层次的技术来自 Sysdig technologies，我们正在考虑将其开放，并为内核跟踪重建 eBPF 解决方案。eBPF 是一种协议，所以它就像 HTTP 或 gRPC。这是任何人都可以使用或构建的东西，基本上是一个标准。我们正在考虑将我们今天如何使用 eBPF 的实现转移到 Falco 项目中，”Nova 说。“我们有许多工作要做。除了 eBPF 之外，我想强调的第一件事是，我们正在为 Falco 引入一个相互认证、TLS 加密的 gRPC API。这里的目的是使 Falco 更具可组合性和模块化，这样我们就可以开始与其他工具集成，如 OPA、Prometheus 和 Kubernetes RBAC。”

Nova 说，随着 gRPC API 的引入，该项目致力于保证向后兼容其他希望与 Falco 集成的项目，Falco 1.0 在不久的将来会有突破性的变化。作为达到孵化阶段的一部分，展示一个广泛的贡献者社区是这个过程的一部分，Falco 拥有 50 多个贡献者，提交量同比增长 100%。Nova 说，现在他们希望这个 API 能够与这个领域的其他安全工具进行更多的整合。

“我们希望其他人能够开始依赖 Falco，这样他们就可以与它集成，这样他们就可以开始通过 Falco 提供自己的安全信息。我们现在有一些生产用户已经开始这样做了，这是围绕它构建一个 API 的整个想法的灵感的一部分，”Nova 说。“你可以看到 Kubernetes、Envoy 和其他工具的成功，这些工具已经在 CNCF 取得了成功，他们采用了 API 优先的方法，这是我们对 Falco 的承诺。接受捐款。接受拉请求。

云计算原生计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>