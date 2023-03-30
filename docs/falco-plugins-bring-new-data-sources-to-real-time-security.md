# Falco 插件为实时安全带来了新的数据源

> 原文：<https://thenewstack.io/falco-plugins-bring-new-data-sources-to-real-time-security/>

云安全公司 [Sysdig](https://sysdig.com/) 在今年的 [KubeCon+CloudNativeCon 北美](https://cncf.io/?utm_content=inline-mention)上宣布为 [Falco](https://falco.org/) 、[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)运行时安全项目添加插件。

Falco 插件，在早期访问活动中推出，将允许用户扩展 Falco 以包括新的数据源，Sysdig 正在推出新功能，以及一个用于亚马逊网络服务的插件[cloud trail](https://aws.amazon.com/cloudtrail/)，这是一个监测和记录整个 AWS 基础设施账户活动的 AWS 服务。

Sysdig 首席技术官和创始人[洛里斯·德吉奥安尼](https://www.linkedin.com/in/degio)说，Falco 的实时功能，在正常操作中使用[扩展的 Berkeley 数据包过滤器(eBPF)](https://en.wikipedia.org/wiki/Berkeley_Packet_Filter) 从 Linux 内核收集关于容器运行时的信息，为日志监控之类的东西带来了新元素。

“Falco 的美妙之处在于它可以实时操作，”Degioanni 说。“虽然许多解决方案都是基于检查配置、遵循 API、扫描图像等，但 Falco 就像一个安全摄像头，它不断地观察容器的行为。该策略引擎旨在实时进行检测，并在几秒钟甚至不到几秒钟的时间内向用户发出警报。

此外，Degioanni 说，该公司发现其策略引擎的属性是通用的、强大的，并且可能不仅仅适用于 Linux 内核中的容器。

“通过听取社区的意见，我们开始从根本上把这个引擎从底层数据收集中分离出来，”他说。“有了插件，你仍然可以使用这个引擎，它非常灵活，功能强大，本质上非常实时，你可以将这个引擎应用到任何你想要的东西上。”

[Falco Cloudtrail 插件](https://github.com/falcosecurity/plugins/tree/master/plugins/cloudtrail)使用 Falco 规则实时检测 AWS 云服务中的意外行为和配置更改、入侵和数据窃取。更具体地说，它读取 Cloudtrail 日志，并将其作为事件和新规则返回，以寻找可疑或值得注意的活动。虽然 Cloudtrail 插件提供了一些非常真实的功能，并将 Falco 带到了云中，而不仅仅是关注内核活动，但它也为社区尚未创建的其他插件提供了一个示例。

插件本身有两种类型——源插件和提取器插件。Source 插件允许将新的事件源和过滤器字段添加到 Falco，并使用规则和过滤表达式进行评估，而 extractor 插件定义了新的字段，可以从核心 Falco 事件或其他插件生成的事件中提取信息。该公司表示，这两种类型的插件将允许用户“为几乎任何类型的流媒体数据编写规则。”

“这是以完全开放的方式设计的，以在更广泛的意义上支持社区和行业。我们与法尔科 CNCF 社区的其他人一起设计了这些，”Degioanni 说。“我们已经开始看到用户通过这种插件机制对 Falco 的更多集成和更多数据源感兴趣。”

插件可以用任何支持暴露 C 函数接口的语言编写，这些接口可以从像 Falco 这样的 C/C++程序中调用，Sysdig 说它已经用 C、C++和 Go 编写了插件。该公司还提供了一个 Go [模块](https://pkg.go.dev/github.com/falcosecurity/plugin-sdk-go)，用于在 C 伪类型和 Go 类型之间进行翻译，并提供方便的方法，使得在 Go 中编写插件更加容易。

Degioanni 说，一些直接的扩展方向将包括其他主要的云提供商，他们有类似的日志监控插件。然而，除此之外，他说其他领域如 DNS 日志或负载平衡器日志都是新 Falco 插件的“好候选”。

随着 Falco 向云的扩展，Degioanni 表示，他看到了运行时检测和管理云基础设施之间的融合，Sysdig 最近进一步涉足这一领域，例如该公司最近收购了基础设施中的[作为代码空间](https://thenewstack.io/sysdig-aims-for-iac-auto-remediation-with-apolicy-acquisition/)。

“如果你在云中运行容器和 Kubernetes，非常重要的是能够有一个工具，能够保护基础设施端(与云资源、云中的活动和配置变化等有关的一切)和工作负载端(容器和 Kubernetes)，使用单一语言、单一融合的一组策略，以及一个中心位置，在这里你可以控制这些内容和通知，”Degioanni 说。

根据该公司的一篇博客文章，新的 Cloudtrail 插件-以及插件功能本身-仍处于“非常早期的访问”，但 Sysdig 预计两者都将在 2022 年初发布。目前，当 Falco 启用插件支持时，Falco 对监控系统调用的支持被禁用，一次只能加载一个源代码插件，但该公司表示，一旦我们解决了由单个 Falco 规则引擎处理多个事件流导致的并发性、公平性和资源利用问题，它将“允许一次运行多个源代码插件。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>