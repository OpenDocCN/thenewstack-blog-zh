# 为什么 Google 不支持 Docker 的容器网络模型

> 原文：<https://thenewstack.io/google-wont-support-dockers-container-network-model/>

去年 7 月，随着 Kubernetes v1.0 的发布，Google 开始涉足容器管理领域。Kubernetes [koo-bur-net-eeze]是“一个[开源](https://en.wikipedia.org/wiki/Open_source) [容器](https://en.wikipedia.org/wiki/Container_(virtualization)) [集群管理器](https://en.wikipedia.org/wiki/Computer_cluster#Cluster_management)[它]旨在提供一个平台，用于跨主机集群自动部署、扩展和操作应用程序容器。”

随着 Kubernetes 的发布，谷歌宣布与 [Linux 基金会](https://en.wikipedia.org/wiki/Linux_Foundation)合作成立[云本地计算基金会](https://en.wikipedia.org/wiki/Linux_Foundation#Cloud_Native_Computing_Foundation) (CNCF)，并提供 Kubernetes 作为种子技术。

那么，为什么 Google 的 Kubernetes 会避开 Docker 的容器网络模型( [CNM](https://github.com/docker/libnetwork/blob/master/docs/design.md) )，Docker 的容器网络模型提供了对多种网络驱动程序的支持。

毕竟，”[谷歌软件工程师 Tim Hockin](http://blog.kubernetes.io/2016/01/why-Kubernetes-doesnt-use-libnetwork.html) 写道，“供应商几乎肯定会为 Docker 编写插件——我们使用相同的驱动程序会更好，对吗？"

好吧，谷歌会，但事实证明，Docker 的网络驱动程序在设计上有根本的差异，与 Kubernetes 不兼容。

霍金在最近的一篇博客文章中详细分析了多种原因。简而言之:就其核心而言，这两个系统在结构上是不同的，这使得它们之间的对话变得很复杂。哪个是容器易用性哲学的对立面？

“Kubernetes 支持多个容器运行时，Docker 只是其中之一，”Hockin 解释说，“配置网络是每个运行时的一个方面，所以当人们问“Kubernetes 会支持 CNM 吗？他们真正的意思是“Kubernetes 会用 Docker 运行时支持 CNM 驱动程序吗?”？"

谷歌工程师使用 Docker 使用的 libkv 接口，但是发现 libkv 与 Kubernetes 的结构不兼容。

[Hockin 讨论了解决这些问题的几种技术方案，](http://blog.kubernetes.io/2016/01/why-Kubernetes-doesnt-use-libnetwork.html)但没有一种方案能令人满意地解决这些问题。他们甚至尝试为 Docker 插件编写插件，以使平台能够协同工作，但 Kubrenetes 和 Docker 的底层结构之间有太多的哲学差异，使这一点不可行。归根结底，为什么要将一个多容器运行时解决方案硬塞进一个单一的运行时解决方案呢？

相反，谷歌的工程师们专注于 CoreOS 的容器网络接口([【CNI】](https://github.com/appc/cni/blob/master/SPEC.md))模型和部分应用容器( [appc](https://github.com/appc) )规范。

“这将会有一些不幸的副作用，”霍金承认特别是，由 Docker run 启动的容器可能无法与由 Kubernetes 启动的容器通信，如果网络集成商想要与 Kubernetes 完全集成，他们必须提供 CNI 驱动程序。

从好的方面来看，着眼于多容器运行时解决方案，Kubernetes 将使工程师们能够简化系统，使其更加灵活和易于使用。

你是否对谷歌不兼容 Docker 感到沮丧？谷歌工程师一直在寻找整合和简化 Kubernetes 的方法。

“如果你对我们如何做到这一点有想法，”霍金写道，“我们真的很想听听[你的想法]——在 [slack](http://slack.k8s.io/) 或我们的[网络签名邮件列表](https://groups.google.com/forum/#!forum/kubernetes-sig-network)上找到我们。”

该你了。

Docker 是新堆栈的赞助商。

瑞安·麦奎尔拍摄的专题图片，获得 CC0 许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>