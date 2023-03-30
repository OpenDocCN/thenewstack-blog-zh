# 共价谈纤毛，以及它如何把 BPF 带到库伯内特

> 原文：<https://thenewstack.io/covalent-talks-cilium-and-how-it-brings-bpf-to-kubernetes/>

[共价会谈纤毛，以及它如何把 BPF 带到库伯内特](https://thenewstack.simplecast.com/episodes/covalent-talks-cilium-and-how-it-brings-bpf-to-kubernetes)

伯克利数据包过滤器(BPF)是 1992 年在劳伦斯伯克利实验室创建的，目的是更好地过滤和分类网络数据包。在 21 世纪初，它是旷日持久的 SCO 对 Linux 诉讼的核心。今天，它只是包含在 Linux 中的另一个原始接口。然而，最近 BPF 已经成为一个有趣的话题，因为它已经成为 IPTables 的热门替代品。

[Thomas Graf](https://www.linkedin.com/in/thomas-graf-73104547/) ，共价科技的首席技术官和联合创始人。也是[纤毛项目](https://cilium.io/)的负责人。Cilium 为基于 BPF 的 Kubernetes 用户提供支持 API 的网络和安全性。Graf 说，在 Kubernetes，BPF 的力量可能很难利用，因此纤毛项目旨在使其变得更容易。

“它允许您翻译声明性的高级意图，如策略、网络、负载平衡，所有这些高级意图都是用 Kubernetes 服务描述的。 [Cilium](https://github.com/cilium/cilium) 通过 BPF 以最有效和安全的方式实现这些高级结构。它以一种易于消费的方式带来了 BPF 的力量，并实现了已知的 Kubernetes 接口，”Graf 说。

他说，该项目允许对 Kubernetes pods 周围的网络访问进行更大的控制。“Cilium 为 Kubernetes 提供网络、负载平衡和安全性。你可以运行 Cilium，它将连接你的 [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) ，它将以一种可扩展的方式提供负载平衡，例如，比标准的 [Kube-Proxy](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-proxy/) 实现要高效许多倍。它还实现了分段和安全性。它可以强制规定只有特定的 pod 可以与特定的外部服务对话。例如，它只能访问数据 API 的 IP。或者你可以定义某个 pod 只能在某个端口上通话，”格拉夫说。

然而，格拉夫说，这只是纤毛力量的开始。该项目对 Kubernetes pods 之间的通信方式增加了更精细的控制。旧世界的模型只是简单地用防火墙打开或关闭一个端口，而 BPF 和纤毛可以影响豆荚上的特定控制来限制它们的流量。

“它也进入了 API 调用级别。这就是我们看到的最基本、最重要的功能，因为如果我们应用传统的网络安全，基本上就是说:两个服务可以在特定端口上相互通信，比如说端口 80…在传统的防火墙世界中，这意味着要么开放整个 API 表面，让两个服务执行所有 API 调用，要么不执行。格拉夫说:“我们允许你做的是说‘这两个 pod 不仅可以相互对话，而且它们只能发出某个 API 调用。

### 在这个版本中:

[4:25:](https://thenewstack.simplecast.com/episodes/covalent-talks-cilium-and-how-it-brings-bpf-to-kubernetes?t=4:25)BPF
[6:42:](https://thenewstack.simplecast.com/episodes/covalent-talks-cilium-and-how-it-brings-bpf-to-kubernetes?t=6:42)的纤毛实现是怎样的，你们是如何考虑到这种控制粒度的？
[10:16:](https://thenewstack.simplecast.com/episodes/covalent-talks-cilium-and-how-it-brings-bpf-to-kubernetes?t=10:16) 纤毛项目如何演进，走向何方？
[15:04:](https://thenewstack.simplecast.com/episodes/covalent-talks-cilium-and-how-it-brings-bpf-to-kubernetes?t=15:04) 纤毛如何处理状态？
[17:07:](https://thenewstack.simplecast.com/episodes/covalent-talks-cilium-and-how-it-brings-bpf-to-kubernetes?t=17:07) 你在这个社区的同行有哪些？

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>