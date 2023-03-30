# Kubernetes 核心组件的 CNCF 开源安全审计

> 原文：<https://thenewstack.io/cncf-open-sources-security-audit-of-core-kubernetes-components/>

本周，云计算原生计算基金会(CNCF)发布了第三方对 Kubernetes 的八个核心组件进行的为期两个月的安全审计的最终结果，发现了各种漏洞。

根据 CNCF 的说法，已经为漏洞创建了 CVE，这些漏洞已经得到了解决。此外，分析还发现了许多 Kubernetes 部署中存在的问题，包括:

*   策略可能无法应用，导致错误的安全感。
*   默认情况下使用不安全的 TLS。
*   大多数组件接受入站 HTTP。
*   大多数组件不强制出站 HTTPS。
*   凭据在环境变量和命令行参数中公开。
*   秘密的名字在日志中被泄露。
*   没有证书吊销。
*   默认情况下，seccomp 不启用。

该过程始于去年对 [CoreDNS](https://coredns.io/2018/03/15/cure53-security-assessment/) 服务发现软件、特使代理和 [Prometheus](https://cure53.de/pentest-report_prometheus.pdf) 监控工具的审计，之后基金会将注意力转向 Kubernetes 本身，成立了安全审计工作组来领导该过程。在收到来自六家独立供应商的提议后，两家公司合作执行安全审计并创建最终报告，该报告将在工作组的 GitHub 存储库中完全可用，以及迄今为止该过程的全部细节——云本地计算基金会首席技术官兼首席运营官 Chris Aniszczyk 指出这是与众不同的一点。

“我不认为有很多安全审计是以开放社区的方式进行的。这是一个开放的 RFP，背后有一个 Kubernetes 治理结构和一个工作组。Aniszczyk 说:“我们公开了所有的结果和论文，这通常不会发生在安全审计中。“为开源项目进行这些审计的好处在于，你可以对安全披露流程的工作方式进行基准测试，而且效果相当好。CVE 是针对 Kubernetes 中发现的许多严重问题而创建的。”

事实上，整个流程在安全审计工作组存储库中都是可见的，包括 RFP、RFP 决策流程，以及来自被选择来执行审计的 [Atredis](https://www.atredis.com/) 和[Bits](https://www.trailofbits.com/)的已接受提案。根据 CNCF 的一篇博客文章，在这个过程中审计的组件包括 kube-apiserver、etcd、kube-scheduler、kube-controller-manager、cloud-controller-manager、kubelet、kube-proxy 和容器运行时。这些组件被选为 Kubernetes 控制平面的核心，涵盖六个方面——网络、加密、认证、授权、机密管理和多租户。

除了发现许多漏洞之外，安全审计还为 Kubernetes 开发人员和集群管理员提供了许多建议。Aniszczyk 将一些建议与您可能期望的从零开始编译 Linux 的建议进行了比较，并与使用供应商提供的强化版本进行了比较。例如，建议 Kubernetes 开发人员检查文件权限并避免硬编码依赖性，而集群管理员应该注意基于角色的访问控制(RBAC)最佳实践以及节点主机配置和权限等问题。

根据 CNCF 的博客帖子，这些安全审计部分受到了[核心基础设施倡议(CII)最佳实践徽章计划](https://bestpractices.coreinfrastructure.org/en)的启发，该计划要求所有 CNCF 成员参加，旨在表明项目遵循最佳安全实践。展望未来，CNCF 将为其其他项目提供安全审计，优先考虑毕业项目，尽管 Aniszczyk 说没有规定的过程。

“在 CNCF，审计流程的运作方式是，项目在需要的时候提出要求。我们没有规定他们必须每年接受审计。我们规定的是，任何成为 CNCF 毕业项目的项目都必须通过独立的安全审计，并公开结果，”Aniszczyk 说。“我设想这样的事情可能每隔几年就会发生一次，但这确实需要安全审计工作组做出决定，因为他们是专家。”

云计算原生计算基金会是新堆栈的赞助商。

来自 Pixabay 的 David Mark 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>