# 开放策略代理保护云安全的使命

> 原文：<https://thenewstack.io/open-policy-agents-mission-to-secure-the-cloud/>

[](https://www.manifold.co)

 [杰冯·麦克唐纳

过去十年，杰冯·麦克唐纳一直致力于打造高科技企业。他是云原生市场公司 Manifold 的联合创始人兼首席执行官。在 Manifold 之前，他是 GoInstant 的联合创始人兼首席执行官，该公司于 2012 年被 Salesforce 以 1 亿美元收购。收购后，他在 Salesforce 担任服务云移动总经理。在此之前，他曾在达奇斯集团、Firestoker.com 和 silverorange.com 工作。](https://www.manifold.co) [](https://www.manifold.co)

如果云计算和软件开发要继续繁荣，就需要更多的合作来确保我们共享系统的安全。

为此，我们需要同意在关键领域实施行业标准。[开放政策代理](https://www.openpolicyagent.org/) (OPA)是朝着这个方向迈出的重要一步，它还没有得到应有的关注。

OPA 是一个开源工具，支持跨域和堆栈中的所有层实施广泛的策略。该策略引擎为用户提供了对其环境的更大控制，同时消除了为每个产品和服务编写不同策略语言、API 或模型的需要。

想想我们许多人投入政策管理的时间和精力。我们必须经常实施旨在根除网络漏洞的工具，部分原因是我们缺乏实用的方法来测试一项政策是否在所有地方都行得通。太多的资源专门用于身份认证和合规性，而不是我们的核心产品。

OPA 有助于消除这些问题以及许多其他问题。

这项技术在 2018 年成为新闻，当时[云原生计算基金会](https://www.cncf.io/) (CNCF)宣布它已经[同意主持](https://www.cncf.io/blog/2018/03/29/cncf-to-host-open-policy-agent-opa/)并“沙盒”OPA 项目。CNCF 是许多最重要的开源项目的供应商中立之家，包括 Prometheus 和 Kubernetes。

在去年 11 月的 KubeCon+CloudNativeCon San Diego 大会上，在 Pinterest、Yelp、微软、谷歌和 Trip Advisor 等公司分享了用例并提供了证明之后，OPA 引发了更多的讨论。

## 证据

到目前为止，我们对 OPA 的了解是，它是一个灵活方便的工具，支持跨容器、服务器、微服务 API 和公共云基础设施的策略控制。这种通用策略引擎的最佳特性之一是，它不要求用户强制执行一组特定的规则。

OPA 的策略语言减压阀使用户能够轻松定义规则。服务运营商编写规则，规定谁在哪里获得什么访问权限。OPA 查询 API 请求，并根据操作者提供的规则决定是否同意该请求。OPA 将策略从服务代码中分离出来，并在不牺牲可用性的情况下支持审查和测试。

CNCF 执行董事 Dan Kohn 在最近的 KubeCon 大会上解释说，大量有安全意识且受到严格监管的企业公司曾经花费大量时间审核软件发布。除了耗费大量时间之外，审计并不总是可靠的。Kohn 说，随着越来越多的企业转向微服务架构，而不是一个大的整体，他们现在可能有数百个微服务应用程序要拆分。

随着企业从按季度或按月安装软件发展到每天多达 50 次部署，旧的手动审查系统变得难以为继。

科恩说:“对 OPA 来说，最简单的办法就是说，‘我们把过去由人工审计员和审查员完成的所有功能都放进了软件。我们将监控软件在执行规则方面是否做了它应该做的事情。"

请记住，OPA 是一项正在进行的工作，其实现并非没有挑战。一些在 KubeCon 分享用例的经理提醒观众注意 OPA 的一些复杂性。

“避免我们的错误，”[Pinterest 软件工程师 William Fu](https://www.linkedin.com/in/william-fu-7305a2a8/) 开玩笑地告诉 KubeCon 与会者。Fu 建议使用 OPA 提供的包可以节省时间。

在授权访问时，傅说，创建一个通断开关对于处理紧急情况非常重要。他补充说，Pinterest 希望看到类似滑动控制条的东西，让运营商能够授权不同的流量百分比。

傅还建议让工程师们自己制定政策。

[https://www.youtube.com/embed/LhgxFICWsA8?feature=oembed](https://www.youtube.com/embed/LhgxFICWsA8?feature=oembed)

视频

来自猫途鹰的 Luke Massa 谈到了在部署 OPA 时编写测试的重要性。

“边走边写测试有助于整理你对 OPA 的理解，”Massa 告诉大家。他补充说，早期测试不仅有助于运营商在减压阀获得舒适的写作，而且还使添加新策略更容易，压力更小。

虽然今天实施 OPA 的成本有点高，但这项技术通过提供更多的控制和帮助保护系统而获得了回报。随着 OPA 的不断完善，我们可以预计实施成本将会下降，从而使 OPA 的投资更具合理性。

云基础设施庞大而复杂，需要比我们现在拥有的更复杂的保护——特别是当我们看到越来越多的大公司采用 Kubernetes 时。

[https://www.youtube.com/embed/X09c1eXvCFM?start=1106&feature=oembed](https://www.youtube.com/embed/X09c1eXvCFM?start=1106&feature=oembed)

视频

[Torin Sandall](https://www.linkedin.com/in/torin-sandall-1967387/) ，一位来自 [Styra](https://www.styra.com/) 公司的工程师，创立了 OPA，他去年说这个项目的发展见证了越来越多的贡献者。他还明确了 OPA 的最终目标。

“我们看到越来越多的安全厂商对 OPA 感兴趣，”Sandall 说。“你知道，从长远来看，这将有助于实现跨多个不同系统统一策略控制的目标。永远不会有一个供应商主宰一切，总会有不同技术的融合。”

他说:“我认为，我们能做的最好的事情就是提供这种可以嵌入到任何地方的构件。”

OPA 有潜力成为重要的行业标准。采用厂商中立的标准通常能够使蓬勃发展的技术生态系统围绕它们成长。如果没有以太网、TCP/IP 和 HTML，我们会怎样？

显而易见的是，为开发像 OPA 这样的技术做出贡献的人越多，我们受益就越多。

KubeKon+CloudNativeCon 和 CNCF 是新堆栈的赞助商。

特征图像:[开放策略代理](https://www.openpolicyagent.org/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>