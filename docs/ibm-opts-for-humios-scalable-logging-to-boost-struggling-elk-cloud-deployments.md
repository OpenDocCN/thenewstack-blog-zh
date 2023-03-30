# IBM 选择 Humio 的可扩展日志来推动苦苦挣扎的 ELK 云部署

> 原文：<https://thenewstack.io/ibm-opts-for-humios-scalable-logging-to-boost-struggling-elk-cloud-deployments/>

当谈到日志记录时，在节省空间的同时获得您需要的东西和因为您试图节省存储而错过一些重要的东西之间有一条微妙的界限。传统的日志工具可能是数据猪，而大规模的现代分布式应用只会加剧这个问题。然而，Humio 提供无索引日志记录，该公司称这允许它“记录一切，不遗漏任何东西”，我们最近在圣地亚哥的 [KubeCon + Cloud NativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 采访了他们，谈论其最近与[IBM](https://www.humio.com/whats-new/blog/humio-adds-streaming-log-management-capabilities-at-scale-to-ibm-cloud-pak-for-multicloud-management)[的合作](https://www.ibm.com/us-en/)。

[IBM 产品经理 Mike Mallo](https://www.linkedin.com/in/mmallo/) 表示，IBM 之所以选择 Humio，是因为客户在使用该公司的[elastic search Logstash Kibana](https://www.elastic.co/what-is/elk-stack)(ELK)堆栈时遇到了规模问题。

Mallo 说:“我们邀请 Humio 作为合作伙伴，为我们的 Cloud Pak 多云管理解决方案捕获日志，因为我们的客户正在使用我们今天在解决方案中提供的 ELK，从规模角度来看，它已经远远超出了我们的需求。“从 ELK stack 的角度来看，仅仅运行 ELK 高可用性就是一项支出，因为您基本上必须承担所有这些运营成本。普罗米修斯也是这样。它只能运行大约 24 小时的数据和规模，直到您必须开始用另一个系统进行备份。”

IBM 和 Humio 之间的合作伙伴关系包括通过集成 Humio 的实时和可扩展日志管理平台来提高 IBM 用于多云管理的 [Cloud Pak 的可观察性，Humio 执行副总裁](https://www.ibm.com/cloud/cloud-pak-for-management) [Morton Gram](https://www.linkedin.com/in/mortengramdk/?originalSubdomain=ch) 称该平台“旨在解决与高度分布式系统和现代应用程序相关的任何痛点。”对于 Gram 来说，让用户摆脱存储和规模与全面日志记录之间的紧张平衡带来了新的可能性。

Humio 提供了一种服务，可以存储无限量的非结构化日志信息，因此可以很容易地进行搜索。据该公司称，Humio 引擎可以无延迟地处理高达万亿字节的日志数据。除了能够在不考虑存储的情况下进行日志记录之外，Humio 还提供了实时可观察性，Mallo 认为这是了解短暂的云原生部署的唯一方式。

“一旦你开始消除限制，无论是复杂性、硬件成本还是许可证成本，客户就可以开始接受，而不必考虑这些参数，他们的行为就会完全改变。突然间，他们不再花时间过滤日志，而是开始记录一切。当他们开始这样做时，他们对自己的环境有了不同的认识，”Gram 说。“最大的挑战实际上是你的事故。它们从来不会发生在你看着的地方，而是发生在你看不到的地方。您的恢复时间取决于您所拥有的数据。如果没有可用的数据，您的恢复时间将会非常长。”

Mallo 说:“当你在云原生环境中时，日志确实是你在生产中看到它的唯一方式，因为容器可能只持续一分钟，然后因为出现问题而被终止，它丢弃了一些重要的日志。“如果你不能随着时间的推移回头去看那些，你就不会真正看到发生了什么。容器的短暂性意味着日志实际上是你的可观察性方面，你的度量和一切可能在那一点上消失了。”

然而，对于 Gram 来说，实时日志提供了实时警报的能力，以及提取以前被锁定在商业智能(BI)工具中的价值的能力。

“如果您查看一下您的应用程序日志，就会发现您的应用程序日志中包含了如此多的业务价值。如果你真的想做实时分析，以改变你在企业中运行流程的方式，最好的方法是通过你的日志，”格拉姆说。“如果你看看你在 Humio 这样的平台上问任何问题的灵活性，它实际上是一种让企业获得实时发生的事情的真正好的仪表板的简单方法。有多少次，首席执行官问了一个问题，但你无法从他的商业智能工具中得到答案，因为它不是预定义的？”

作为合作伙伴关系的一部分，Humio 可在 IBM Cloud Pak 中作为服务或内部部署用于多云管理，在 Red Hat OpenShift 上的客户端防火墙后安全运行，并根据单一合同运行。

除了 IBM，Humio 服务也被 SpareBank 和 Netlify 使用:

[https://www.youtube.com/embed/xBA9Qe2w1cs?feature=oembed](https://www.youtube.com/embed/xBA9Qe2w1cs?feature=oembed)

视频

*TNS 编辑和营销总监 Libby Clark 对此文有贡献。*

Humio 和 OpenShift 是新堆栈的赞助商。

来自 Pixabay 的 David Mark 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>