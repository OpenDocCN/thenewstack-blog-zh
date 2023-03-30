# 利兹·赖斯:遵循 eBPF 的“超能力”承诺

> 原文：<https://thenewstack.io/liz-rice-following-the-superpower-promise-of-ebpf/>

[](https://www.linkedin.com/in/lizrice/)

 [利兹·赖斯

利兹·赖斯是等价网的首席开源官，也是云计算原生计算基金会](https://www.linkedin.com/in/lizrice/) [](https://www.linkedin.com/in/lizrice/)的技术监督委员会主席

对于许多从事软件工程的人来说，每时每刻都会出现一种真正激发想象力的技术。我确信许多新堆栈的读者会回想起他们第一次接触容器的经历，很可能是通过 Docker，并意识到这是一项可以改变一切的技术。容器化可以说是向云原生迁移的关键。

但是每前进一步都会产生新的挑战和新的边界。对我来说，eBPF 是另一项变革性技术，随着我加入 eBPF 先锋的领导团队，我很高兴能够更深入地参与其中。

eBPF 代表“扩展的 Berkeley 包过滤器”，但是对于描述这项技术的范围和潜力来说，这并不是一个非常有用的短语。它允许您在内核 中[运行定制代码](https://thenewstack.io/how-ebpf-turns-linux-into-a-programmable-kernel/) [*来响应几乎任何事件——网络数据包的到达、系统调用、用户空间或内核中的函数调用……这个列表实际上是无穷无尽的。来自网飞的 Brendan Greggs 创造了短语“Linux 的超能力”，这一点也不夸张。*](https://thenewstack.io/how-ebpf-turns-linux-into-a-programmable-kernel/)

作为[云原生计算基金会](https://cncf.io/?utm_content=inline-mention)技术监督委员会的主席，我有非常荣幸的机会听到许多关于云原生采用、技术和挑战的信息，涉及不同项目和不同级别的堆栈。如今，在生产中运行 Kubernetes 已经成为一种主流活动。

但是，随着用户扩展其环境并推出业务关键型云原生应用，他们开始意识到新的挑战。他们如何扩展连接性、解决问题并确保日益成为企业共享服务的安全性？

如今，许多应对这些挑战的解决方案都使用边斗模式来了解各个工作负载。这是一种可行的模式，但也有成本。用户空间网络堆栈会增加开销，每个 pod 中复制的可观察性和安全功能也会增加开销，我们已经看到，结果是高达 50%的 CPU 利用率最终被基础架构使用，而不是被业务应用程序使用！

此外，跨多个工作负载的安全事件无法从 sidecar 或防火墙内检测到，但对 Linux 内核是可见的。eBPF 通过直接利用 Linux 内核及其对主机上发生的一切的感知，为高性能网络、可观察性和安全解决方案开辟了潜力。您可以拥有面向业务应用的云原生独立微服务的技术和流程优势，同时使它们运行的基础架构能够感知工作负载和系统。

已经有一些出色的云原生项目利用了 eBPF。CNCF 的 Falco 项目支持基于 eBPF 的驱动程序来检测违反安全规则的行为。我以前在 Aqua 的团队正在开发 [Tracee](https://github.com/aquasecurity/tracee) ，它结合了 eBPF 事件检测引擎和开放策略代理的 rego 语言中定义的规则。但是在生产中部署最广泛的 eBPF 项目是基于 eBPF 的 Kubernetes 网络插件 [Cilium](http://cilium.io) 。

我记得第一次知道纤毛是在 2017 年的 DockerCon，通过等价的首席技术编辑[托马斯·格拉夫基于《星球大战》的演示](https://youtu.be/ilKlmTDdFgk)。当时，eBPF 是一个非常新的 Linux 内核特性——太新了，在许多企业部署中找不到，但是自从看到 Graf 的演讲后，我就对它的可能性产生了兴趣。

快进到 2021 年，Cilium 所依赖的内核特性现在已经广泛可用。这种可用性就是为什么 eBPF 在我的 KubeCon 主题演讲“TOC 的[预测](https://youtu.be/bESogtuHwX0)”中成为今年值得关注的热门技术之一，也是为什么这个领域的初创公司——包括 Isovalent——目前正受到投资者和收购公司的大量关注。

Graf 和 Isovalent CEO[Dan Wendlandt](https://www.linkedin.com/in/danwendlandt/)召集了许多世界顶级 eBPF 专家来研究 Cilium 项目，这无疑是该领域领先的网络解决方案。我已经看到一个又一个大客户采用 Cilium，在去年的 [eBPF 峰会](https://ebpf.io/summit-2020/)上，Datadog、Capital One、Adobe 和许多其他公司谈到该项目如何帮助他们克服在发展 Kubernetes 环境中遇到的诸多最大挑战。它提供的高性能网络，以及用于解决连接问题和检测安全事件的工具，只有通过使用 eBPF 才有可能实现，而使用 Cilium 让团队有信心在他们的 Kubernetes 平台上部署敏感的工作负载。我很兴奋也很高兴能够加入等价团队，帮助将纤毛的好处带到 Kubernetes 的每个部署中。

[https://www.youtube.com/embed/bESogtuHwX0?feature=oembed](https://www.youtube.com/embed/bESogtuHwX0?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>