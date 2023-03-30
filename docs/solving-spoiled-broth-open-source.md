# OSCON 2016:可扩展的 Kubernetes 和 OpenShift 实现优雅进化

> 原文：<https://thenewstack.io/solving-spoiled-broth-open-source/>

如果你在开源世界呆了很长时间，那么你可能会对这句老话很熟悉:“厨子多了烧坏了汤。”当然，虽然版本控制系统很久以前就消除了处理代码库的多个贡献者的许多痛苦，但开源系统在处理改变核心 API 的新贡献时会面临问题。

在本期 [The New Stack Analysts](/tag/the-new-stack-analysts/) 播客中，New Stack 创始人 Alex Williams 与 [Ryan Jarvinen](https://twitter.com/ryanj) 对话，他是 Red Hat 的开发者倡导者和开源倡导者，他谈到了[上周的 OpenShift 3.2 版本](https://blog.openshift.com/openshift-3-2-whats-new/)和下个月的 [Kubernetes](/category/kubernetes/) 1.3 版本，这两个版本都解决了通过使用扩展破坏 API 的问题(OpenShift 基于 Kubernetes)。采访是在本周于奥斯丁举行的 OSCON 开源会议上进行的。请点击这里收听 SoundCloud 的采访:

[OSCON 2016:Ryan Jarvinen，红帽开发者倡导者](https://thenewstack.simplecast.com/episodes/oscon-2016-ryan-jarvinen-red-hat-developer-advocate)

Jarvenin 解释说，该公司已经看到了这种使用扩展来安全地添加到 Kubernetes 的方法，而不是直接改变核心 API 或代码。

Jarvenin 解释说:“当我们查看 OpenShift 代码库时，我们通常会在代码库的早期提供一些实验性的功能。“一旦它们被更广泛的社区更普遍地接受，我们就将它们上游到主线 Kubernetes 代码中。这是一种模式，我认为我们将看到越来越多的 Kubernetes 贡献者采用这种模式——开发扩展，并允许人们将它们插入现有的堆栈，然后评估它们，而不是试图改变基本的 API。”

除了通过扩展做出贡献之外，Jarvenin 还探索了即将发布的新特性，以提高性能，增加对更多样化的应用程序工作负载的支持，并提供更全面的集群管理。

例如，ProtoBuf 是 Google 开发的一种协议，它通过序列化数据并将其作为语言和平台中立的二进制文件而不是 JSON 流发送来减少网络数据开销，从而提高性能并使可伸缩性更容易实现。

在集群管理方面，“ [Ubernetes](https://github.com/kubernetes/kubernetes/blob/8813c955182e3c9daae68a8257365e02cd871c65/release-0.19.0/docs/proposals/federation.md) ”项目旨在允许多个 Kubernetes 集群相互识别，同时提供跨集群管理。在解释中，Jarvenin 问道，例如，让 1000 个节点都运行相同的管理命令行工具是否真的是一个好主意，其中一个错误的命令可能意味着灾难。Ubernetes 解决了这个显而易见的问题，允许分段和全面控制。

以下是对话视频:

[https://www.youtube.com/embed/90QGXjXJafA?feature=oembed](https://www.youtube.com/embed/90QGXjXJafA?feature=oembed)

视频

红帽是新堆栈的赞助商。

特征图片: Ryan Jarvinen，Red Hat 开发者倡导者和开源倡导者(左)，和新的 Stack 主编 Alex Williams。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>