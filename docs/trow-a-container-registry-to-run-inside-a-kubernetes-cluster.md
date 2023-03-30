# Trow，一个在 Kubernetes 集群中运行的容器注册中心

> 原文：<https://thenewstack.io/trow-a-container-registry-to-run-inside-a-kubernetes-cluster/>

今天，大多数容器注册中心独立于集群运行，集群运行从它们的映像构建的容器。但是在一个集群内运行一个注册中心本身可以提供许多优势，包括更快的启动时间，更好的审计，以及对名称空间更多的控制，[容器解决方案](https://www.container-solutions.com/)的首席科学家 [Adrian Mouat](https://twitter.com/adrianmouat) 指出。

为了测试这个想法，该公司正在建立一个符合 OCI 标准的图像注册和图像管理系统，该系统运行在名为 [Trow](https://trow.io/) 的 Kubernetes 集群中。Mouat 将在东部时间 4 月 14 日上午 11 点的网络研讨会上展示这项技术。

“目前，大多数注册管理机构被视为完全独立于它们向其提供图像的集群的实体。但在与集群的集成中，我们可能会提供更丰富的服务，”Mouat 在本月早些时候在线举行的 D2IQ[云原生虚拟峰会](https://cloudnativevirtualsummit2020.sched.com/event/bZSm/a-local-registry-for-kubernetes-clusters?iframe=no&utm_campaign=Trow%20Webinar&utm_source=hs_email&utm_medium=email&utm_content=86193086&_hsenc=p2ANqtz-8k6cw0nEShJU-8o8btHi-y7lR1KYILHSJfAJj9Jjt1OM-ial6WJBCGA1ZTaPwWU7IOStrIdUD_j9_K22IhAuUiqiJsUA&_hsmi=86193086)的一次会议上解释道。

传统上，大多数组织使用外部注册中心，这是有充分理由的。Docker Hub 为该行业提供了一项出色的服务，一个免费存储和共享容器图像的地方，以及一个全面的存档。对于软件项目，Docker Hub 是一个下载代码的好地方。它甚至为用户构建图像，尽管结果是来自这个 hub 的图像植根于 Docker 名称空间。“默认情况下，一切仍然有效地指向 Docker 中心，”Mouat 说。

其他注册服务也是基于类似的模式构建的。基于 Docker Hub 的[开放容器倡议](https://www.opencontainers.org/)规范，云提供商和 GitHub 等服务提供商提供自己的注册表，这些注册表提供归档、存储和推送图像的中央位置等功能。

但除了存档，注册中心的另一项重要工作是向节点分发图像，也就是说“专注于安全有效地向集群节点提供图像的工作集，”Mouat 在虚拟活动中说。也许这个功能可以在集群中更好地处理。

Trow 作为一个基本的注册表工作，能够像 Docker 客户端一样推送和拉取图像，完全兼容 OCI。

[![](img/c14b274d465577a5d62cfc115531ceae.png)](https://asciinema.org/a/48HK88yR4rJw0QuHt2VdkuVZn)

为了最小化它在集群中对性能的影响，项目开发人员在 Rust 中编写了 Trow。因此，“它可以快速启动和关闭。JVM 中没有需要等待的运行时。它是在不牺牲效率的情况下为安全而设计的，”他说。它还支持 OCI 目录 API，该 API 提供了一种从命令行列出可用的存储库和标记的方法。通过与 Kubernetes 的集成，它可以只允许加载某些图像，作为一种安全措施来阻止其他图像。

“事件日志注册表是确定群集中正在发生或已经发生的事情的重要资源。你可以看到下载了什么图片，谁下载了它们，下载的频率，它们是否过期等等，”Mouat 说。

Mouat 指出，诚然，像 Trow 这样的方法不适合图像的长期存档，尽管在 Kubernetes 集群中拥有注册表可以提供更多的控制和日志记录功能。其他计划的功能包括:

*   操作的完整审计日志
*   与现有身份验证和授权解决方案集成
*   用于快速部署映像更新的高级分发选项
*   支持不可变的标签和图像流
*   与漏洞扫描器集成

Trow 在 Apache 2.0 许可下[可用。](https://github.com/ContainerSolutions/trow/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>