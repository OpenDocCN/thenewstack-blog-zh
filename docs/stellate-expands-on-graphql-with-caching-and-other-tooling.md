# Stellate 通过缓存和其他工具扩展了 GraphQL

> 原文：<https://thenewstack.io/stellate-expands-on-graphql-with-caching-and-other-tooling/>

自从 2015 年开源以来， [GraphQL](https://graphql.org/) 已经成为开发社区中的一个主要部分。多功能服务器端运行时技术被描述为“API 的查询语言”，其主要目的是检索数据。作为 REST 的一个有价值的替代品，GraphQL 最著名的特性是它的速度和为程序员提供 API 中数据的完整描述的能力。虽然毫无疑问很受欢迎，但那些大规模使用 GraphQL 的人发现它在某些领域有点欠缺。

[Stellate](https://stellate.co/) ，[原名 GraphCDN](https://stellate.co/blog/graphcdn-is-now-stellate) ，正试图用为 GraphQL 设计的解决方案来解决这些具体的痛点。Stellate 的 GraphQL 边缘缓存由联合创始人[马克斯·斯托伊伯](https://at.linkedin.com/in/mxstbr)和[蒂姆·苏查内克](https://www.linkedin.com/in/tim-suchanek-08219346)于 2021 年 3 月创建，旨在“通过缓存 GraphQL 查询来减少原始流量和提高性能”

“我联合创立的最后一家公司，”斯托伊伯在接受 New Stack 采访时说，“我们在使用 GraphQL 时遇到了这个问题，我们遇到了巨大的扩展问题。我们的服务器一天崩溃两次，我每天晚上都会收到传呼，不得不重置服务器。太可怕了。”他补充道，问题的根源在于拥有“一个相当糟糕的数据库”。

记住，GraphQL 既不是前端也不是后端技术。它更像是两者之间的传声筒，这意味着您必须实现自己的数据库，并编译一个最适合您的用例的堆栈。

“在我的上一家公司，我们有一个非常公开的用例——论坛，”斯托伊伯说。“想象一下，我现在位于奥地利的维也纳，而世界上大多数服务器都位于弗吉尼亚和阿什本，因为那里是 AWS 的一个数据中心。例如，每当我想从一个网站上获取数据时，我就必须从维也纳一路跑到阿什伯恩的服务器上，计算必须一路返回的数据。边缘缓存的功能是这样的:[如果我在]维也纳第一次加载数据时，我会经过我们在维也纳的位置，那里还没有数据。它将转到弗吉尼亚的原点，那里将计算它的东西，并计算出返回什么数据。它会将数据发送回我们在维也纳的位置，然后存储数据，再发送回给我。因此，下次有人请求这些数据时，它们会立即出现，并且可以被发送回来，而不必大老远跑到弗吉尼亚。”

斯托伊伯说，成长中的公司需要缓存来有效地扩展，否则他们将面临像他一样的服务器过载问题。“我们知道缓存可以解决我们所有的扩展问题，但是产品并不存在。还没有人建造它。”

## **为什么 GraphQL 需要补充？**

“脸书建造了它，(但)这是他们建筑的一层，”斯托伊伯继续说道。“他们需要 GraphQL，以确保他们的客户端开发人员可以从后端获得他们需要的准确数据。开源的 GraphQL 有点像他们构建的一个薄片，它实际上很好地解决了他们的问题，即数据访问。客户端可以通过 GraphQL 很好地访问数据，因为它有这个集中的契约。现在，问题是，他们没有开源他们拥有的任何其他工具，因为它与他们的基础设施紧密相连。事实是，所有采用 GraphQL 的大公司为了确保他们能构建优秀的 API，最终都不得不在内部重新构建所有的工具，因为脸书没有开源它。”

> “我们从边缘缓存开始，但基本目标是为每个人提供大公司拥有的工具。”

我问斯托伊伯，这是否意味着 GraphQL 在技术上有点像一个未完成的产品。他立即表示反对。“GraphQL 和 GraphQL 的技术完蛋了。这只是你需要的周边工具，(脸书)已经在内部保留了。”

“每个人都在一遍又一遍地重建同样的工具，”他继续说道。“我们正在做的是研究人们在生产中运行 GraphQL 时会遇到哪些问题，以及哪些问题可以为每个人解决。我们从边缘缓存开始，但基本目标是为每个人提供大公司拥有的工具。”

## **改进基础模型**

Stellate 除了其性能监控和错误跟踪工具之外，还提供 GraphQL 边缘缓存和 GraphQL 分析。Stellate 与任何 GraphQL 后端兼容，位于 GraphQL 的前面，代理所有流量。“我们只是在需要的时候 ping 你的图形 API，以获取我们需要的数据，”斯托伊伯说。

在分析方面，斯托伊伯说，“另一方面，分析帮助我们的客户更好地缓存，因为我们让人们了解他们的缓存表现如何。”

Stellate 的 GraphQL 性能和错误跟踪是另一个旨在简化开发人员体验的工具。

“我们的错误跟踪功能本质上只是查看并跟踪来自 GraphQL API 的所有错误，”斯托伊伯说，“然后我们在系统中建立了警报，我们可以在空闲或页面负载时向你发出警报，你可以看到哪里出错了，你可以调试它。”

## **全球范围内的 graph QL**

据斯托伊伯称，Stellate 刚刚开始扩展 GraphQL。“我们将建立我们所谓的[全球数据图](https://www.newsbreak.com/news/2627733399398/30-million-raise-to-build-the-global-data-graph)。我们意识到所有这些公司都在使用 GraphQL 将他们的数据转换成图表。然后，每家公司都有自己的孤岛图，在那里他们连接了所有的数据，但它没有连接到任何其他人。”

斯托伊伯说，每个人都错过了一个巨大的机会。“例如，想象一下，如果你在 Salesforce，你有一个客户。该客户与您在 Stripe 中刚刚支付了最新发票的客户是同一个人。此人也可能是与您共享 Slack 账户的 Slack 频道的同一个人。如果世界上的每家公司都有由 GraphQL APIs 公开的数据，也许有一种方法可以将它们连接在一起。如果我们把所有这些数据连接在一起，软件工程师的工作效率会提高多少？”

Stellate 的目标是创建一个跨越国家的互联数据地图。当然，为了让全球数据图真正有价值，世界上更多的数据必须通过图形 API 公开。与此同时，斯托伊伯说他很高兴“让 GraphQL 更容易为需要它的企业所用”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>