# Kubernetes 团队用 1.13 版本推动更短的发布周期

> 原文：<https://thenewstack.io/kubernetes-team-pushes-toward-shorter-release-cycles-with-1-13-release/>

Kubernetes 的 1.13 版本已经发布，在漫长的等待之后，它推出了三个功能，同时还有许多其他值得注意的功能进入了稳定版和测试版。展望未来，该项目承诺更快的发布周期和更大的分支独立性。

据领导 1.13 版本[发布团队](https://github.com/kubernetes/sig-release/blob/master/releases/release-1.13/release_team.md)的谷歌软件工程师 [Aishwarya Sundar](https://www.linkedin.com/in/aishwarya-sundar-1083768) 称，这一最新版本背后最引人注目的消息不仅仅是功能本身，而是 Kubernetes 项目及其开发周期的日益成熟。

“这些版本确实有所改进。Sundar 说:“几个周期前，在发布周期的大部分时间里，我们有作业中断或失败，主服务器将被锁定三周，以稳定发布。“在过去的几个版本中，我们已经在游戏中提前转移了焦点，并真正减少了代码冻结时间。最后一个发布周期是十周的开发，我们只能冻结一周半。这表明该项目已经发展到了什么程度。”

与此同时，1.13 核心的三个突出特性包括 [kubeadm](https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/) 和[容器存储接口(CSI)](https://github.com/container-storage-interface/spec) 特性的全面可用(GA)，以及将 [CoreDNS](https://coredns.io/) 作为 Kubernetes 的默认 DNS 服务器。

首先，kubeadm 是一个工具，它通过执行必要的操作来帮助用户快速跟踪 Kubernetes 集群的创建和维护，以获得一个最小可行的集群，经过近一年的开发，该工具现在已经正式推出。根据发布声明，最值得注意的是“现在升级的高级功能，特别是围绕可插拔性和可配置性。”

接下来，CSI 也在近一年后升级到了全面可用[，现在“为第三方存储提供商提供了一个机会，可以编写与 Kubernetes 互操作的插件，而无需接触核心代码。”](https://kubernetes.io/blog/2018/04/10/container-storage-interface-beta/)

Sundar 肯定会指出，CSI 是一个很好的例子，说明这个项目试图更快、更好地为外部开发人员提供构建工具的能力，而不需要作为主分支的一部分。

“有许多第三方供应商构建和集成功能。一个共同的主题是让他们能够在核心的 Kubernetes 之外进行构建，并轻松地插入和集成。这是我们一直在努力的事情，CSI 就是一个很好的例子，”Sundar 说。“有了这一特殊功能，我们积极推动存储提供商以更加无缝的方式，在他们的驱动程序准备就绪时插入。它有助于开发者不被束缚在 Kubernetes 的主要开发周期中。

最后， [CoreDNS 现在正在取代 kube-dns 成为默认 DNS 服务器](https://github.com/kubernetes/features/issues/566)，Sundar 将这一举动解释为“以身作则”的一个例子，并指出“CoreDNS 有很多功能优势，在内存和 CPU 消耗方面更具性能。”

对于对更多细节感兴趣的人，发布说明是可用的，发布团队将在 1 月 10 日上午 9 点(太平洋标准时间)举办一次网络研讨会。这个版本是 2018 年的第四个也是最后一个版本，Sundar 预计团队将从 2019 年 1 月开始忙于 1.14。

管理 Kubernetes 的云本地计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>