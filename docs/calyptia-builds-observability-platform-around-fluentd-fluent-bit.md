# Calyptia 围绕 Fluentd、Fluent Bit 搭建观测平台

> 原文：<https://thenewstack.io/calyptia-builds-observability-platform-around-fluentd-fluent-bit/>

一年前，Anurag Gupta 和 [Eduardo Silva](https://www.linkedin.com/in/edsiper/) 推出了 [Calyptia](https://calyptia.com/) ，以支持围绕 Fluentd 和 [Fluent Bit](https://fluentbit.io/) 的快速增长的社区，Fluent d 和[Fluent Bit](https://fluentbit.io/)是两人帮助创建和维护的开源数据收集和可观测性工具，现在是[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)的一个项目。

通过 Calyptia，Gupta 和 Silva 看到了围绕 [Fluentd](https://thenewstack.io/fluentds-role-as-a-data-collector-in-todays-cloud-native-world/) 和 Fluent Bit 成立一家公司的机会，该公司可以帮助组织实现第一英里可观测性，即从多个来源(如应用程序、基础设施和网络设备)收集数据，然后对这些数据进行解析和转换，并最终发送到后端数据库和数据湖。

Gupta 告诉 New Stack，大多数企业在处理数据时都关注后端环境。

“你有几个从业者，他们在数据之上进行查询、操作和警报，”他说。“但是，如果我们能够将这种左移转移到数据收集的地方，我们就可以使它更有弹性、更快，并且可能更有洞察力，因为我们有数据在哪里、它在做什么以及它看起来像什么的完整上下文。这是我们公司更大的雄心，但我们真的相信第一英里是人们体验可观察性的第一步。”

## **埃及在行动**

该公司在 6 月份宣布了 Calyptia Fluentd v1.0 的初始版本，这是它自己发布的工具。它最近推出了 Calyptia Cloud，这是一个基于 Fluentd 和 Fluent Bit 的托管数据可观测性平台，提供了第一英里的数据收集功能，可以扩展到每天管理数千台服务器上的 Pb 级数据。

Calyptia 将于本周在 KubeCon+CloudNativeCon 谈论更多关于第一英里可观测性及其新的云平台。

Fluentd 是一个厂商中立的数据收集器，用于构建一个统一的日志记录层，而 Fluent Bit 是一个日志记录和度量处理器，用于收集各种来源的数据，自十年前在 [Treasure Data](https://www.treasuredata.com/) 开发以来，随着其基于 Ruby 的代码向开源社区发布，fluentd 越来越受欢迎。它们每天被下载数百万次，并被云提供商使用，如[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)、微软 Azure、数字海洋和[甲骨文](https://developer.oracle.com/?utm_content=inline-mention)。

它出现在云的采用快速增长的时候，像 [Kubernetes](https://thenewstack.io/category/kubernetes/) 和 [containers](https://thenewstack.io/category/containers/) 这样的云原生工具的使用正在激增，所有类型的公司都被迫采用软件功能。随着他们成为软件公司，他们需要能够看到他们使用的软件发生了什么，诊断问题并排除故障。

## **无供应商锁定**

古普塔说，企业可以选择 Elasticsearch 和 Datadog 等可观察性产品，但他们提供的代理基本上锁定了组织。这意味着企业只有一种方法来收集数据，他们要么必须收集所有数据，要么不收集数据，因为很难过滤掉这些数据，收集的数据越多，他们支付的费用就越多。

“我们看到这需要能够分离收集数据的方式和将数据发送到哪里的方式，”他说。“我们已经看到了巨大的势头，人们说他们希望拥有我们自己的战略，而不是被这些供应商所束缚。他们不想收集无用的数据或为无用的数据付费。这就是我们所说的第一英里可观测性。你旅程的第一部分，也就是第一英里，是收集数据并真正磨练它。”

[帽状云](https://www.globenewswire.com/news-release/2021/10/06/2309760/0/en/Fluent-Project-Creators-Announce-Calyptia-Cloud.html)是覆盖在 Fluentd 和 Fluent Bit 上面的。该平台托管在 Calyptia 自己的服务器上，并插入到使用开源工具的环境中，无论是在内部还是在私有或公共云上，并提供一个控制平面来管理和监控可观测性管道。用户可以收集、解析、过滤和路由第一英里数据，Calyptia Cloud 还通过实时指标为使用 Fluentd 和 Fluent 位数据的公司提供成本、速度和性能瓶颈。

古普塔说:“所有这些动作和对管道这一部分的解析，我们可以说这是你在整个过程中要做的所有动作和事情。”。“我们作为 Calyptia Cloud 所做的最后一部分只是提供实时指标，以便您可以了解这第一英里可观察性层的性能。是我发送数据太快还是太慢？我在缓冲数据吗？所有这些都是很多人在做第一英里时通常会忽略的事情，但随着成熟度的增长，它会一直出现在人们的脑海中。"

他补充道，“我们所带走的都是元数据。你没有给我们发送日志，你没有给我们发送什么样的客户信息可能会在系统中流动。只是关于系统如何运行的事情。”

## **对埃及云的兴趣很高**

虽然 Calyptia Cloud 刚刚宣布，但该公司已经有大约 1700 人注册，其中包括两家财富 10 强金融公司、硬件提供商和大型软件公司。他说，公司也对新兴的不可替代代币(NFT)和加密货币市场感兴趣，这些市场上的大量服务都是基于软件的。

目前，该公司专注于第一英里数据收集环节，与其他提供数据和分析服务的公司合作。

“我们对于将数据发送到哪里没有真正强烈的意见，”古普塔说。“如果你想把数据发送给(某个特定的供应商)，很好。如果你想把这些数据发送到 10 个不同的地方，太棒了。我们两个都支持。目前，我们在很大程度上是供应商中立的。我们确实希望为我们自己的平台带来更多的见解，但这更多的是一种共存和丰富的体验，而不是试图取代它。”

“第一英里是一种扩展趋势，它始于代理人，现在正在扩展到处理所有的信息，”席尔瓦告诉新的堆栈。

“许多在目的地完成的从数据中提取价值的功能正在转移到左边，”席尔瓦说。“现在，您可以尽快从数据中提取价值。这对你的生意更好。但是，如果您的基础架构正在增长，而您必须排队等待几分钟才能获得这一价值，那么您将错过许多机会。这里最重要的是企业从数据中提取价值的速度和可靠性，而我们的价值是我们提供所有这些工具来完成一个不受供应商限制的堆栈，以提取价值。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>