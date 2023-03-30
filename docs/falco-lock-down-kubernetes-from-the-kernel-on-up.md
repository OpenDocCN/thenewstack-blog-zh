# Falco:从内核开始锁定 Kubernetes

> 原文：<https://thenewstack.io/falco-lock-down-kubernetes-from-the-kernel-on-up/>

想度过糟糕的一天吗？犯一个全世界都能看到的安全错误——是的，[我们正看着你网络安全管理软件产品](https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/)。没有人希望这样。这就是为什么即使 [Kubernetes 不是最容易安全锁定的系统](https://thenewstack.io/kubernetes-security-best-practices-to-keep-you-out-of-the-news/)，你也必须这么做。幸运的是，像[法尔科](https://falco.org/)这样的项目可以有所帮助。

2020 年[北美 KubeCon+CloudNativeCon](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/) 特别推出了几场关于 Falco 的讲座。以下是您需要了解的关于这个有用的 Kubernetes 安全程序的基本知识。

首先，它可能对你来说是新的，但 Falco 实际上可以追溯到 2016 年。它是由安全开发公司 [Sysdig](https://sysdig.com/) 创建的。Falco 最初是一个开源行为活动监控代理。被描述为混合了 [snort](https://talosintelligence.com/snort) 、 [ossec](https://github.com/ossec/ossec-hids) 和 [strace](https://strace.io/) ，而不是使用基于签名的安全监控方法来寻找特定的漏洞和弱点， [Falco 寻找可疑的系统活动](https://sysdig.com/blog/sysdig-falco/)，这表明攻击者可能正在工作。

它是在 Linux 内核级完成的。具体来说，Falco 的工作方式是在运行时获取 Linux 系统调用信息，并在内存中重建内核状态。

有了这些数据，它使用一种简单的过滤语言来创建规则，可以在行为中捕捉不良行为。一旦检测到 Falco 发出适当的错误信息。例如，如果 mysqld 在启动后产生了一个新进程，您会得到一个报告，说有一个 SQL 注入攻击正在进行。

想要快速掌握这些规则吗？Sysdig 的[云本地安全中心](https://securityhub.dev/)为许多流行程序提供最佳实践规则，如 [etcd](https://etcd.io/) 、Kubernetes clusters 和 [Nginx](https://nginx.org/en/) 。

就是这样。Falco 不做收集、警报、报告或补救工作。遵循“做好一件事”的 Unix 哲学，Falco 是一个边缘代理。它意味着与您已经用于报告和监控的任何系统密切配合。

为了使这更容易，Falco 正在过渡到“API 优先”的架构。有了这个，你就可以更容易地将 Falco 与其他程序一起使用，如[普罗米修斯](https://prometheus.io/)监控系统和[特使](https://www.envoyproxy.io/)代理服务。

这种技术保持不变，但是它的实现方式随着时间的推移已经发生了变化。当它开始时，Falco 引擎依赖 Falco 内核模块驱动程序来处理内核的系统调用信息的原始流。

从那时起，Falco [扩展的 Berkeley 数据包过滤器(eBPF)](https://lwn.net/Articles/740157/) 探测器被引入环境，如 [Google Kubernetes 引擎(GKE)](https://cloud.google.com/kubernetes-engine) 内核模块不被信任或允许，但 eBPF 程序被信任或允许。最新的探测器 [pdig](https://github.com/falcosecurity/pdig) 运行在用户空间中，构建在 Linux 的[进程跟踪(ptrace)](https://man7.org/linux/man-pages/man2/ptrace.2.html) 之上。正如你可能想象的那样，因为它运行在用户空间中，所以速度很慢，但是如果不允许使用内核模块或 eBPF，总比没有好。

无论调查如何，Falco 都是抵御新的、未打补丁的漏洞、不安全的配置、泄露或薄弱的凭据以及内部攻击的最后一道防线。结合开源的 Clair(一个使用静态分析找出应用程序容器漏洞的容器扫描器)，这两个人组成了一个强大的团队。

组织上，法尔科也变了。2018 年 10 月，Falco 成为首个[云原生计算基金会(CNCF)](https://www.cncf.io/) 安全沙盒项目。2020 年 1 月，它成为第一个 CNCF 孵化级托管项目。

通过向社区开放 Falco，Falco 在开发界变得非常受欢迎。它的提交量同比增长了 100%,现在有超过 55 个贡献者，包括许多来自 Sysdig 外部的工程师。

用户也喜欢。自从成为 CNCF 项目以来，Falco 已经被下载了超过 2000 万次。它也在其他公司的安全包中得到了应用，比如 AWS Firelens 的弹性容器服务(ECS)日志路由器； [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-getting-started.html) 测井仪；以及[谷歌 Anthos](https://cloud.google.com/anthos) ，一个 Kubernetes 云框架。Sysdig 自己的商用 Falco 监控系统 [Enterprise Falco](https://sysdig.com/opensource/falco/) ，可以在几乎任何支持 Kubernetes 的平台上部署 Falco。

Sysdig 认为开源安全工具如 Falco 是 Kubernetes 安全的前进方向。看起来他们是对的。如果您还没有在您的 Kubernetes 集群上使用 Falco，那么是时候对它进行深入的研究了。我想你会喜欢你所看到的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>