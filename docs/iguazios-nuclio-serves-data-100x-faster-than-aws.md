# Iguazio 的 Nuclio 无服务器软件旨在超越 AWS

> 原文：<https://thenewstack.io/iguazios-nuclio-serves-data-100x-faster-than-aws/>

[Iguazio 的 nuclio 服务数据速度比 AWS](https://thenewstack.simplecast.com/episodes/iguazios-nuclio-serves-data-100x-faster-than-aws) 快 100 倍

[首席技术官兼](https://www.linkedin.com/in/yaronh/) [Iguazio](https://www.iguazio.com/) 的联合创始人 Yaron Haviv 加入我们本期[新堆栈制造商](https://thenewstack.io/podcasts/makers)播客。Haviv 在大数据、云、存储和网络领域的深厚技术经验使他领导团队创造了 Iguazio 的新产品 [nuclio](https://github.com/nuclio/nuclio) 。

这个开源项目于 2017 年 12 月[推出](https://www.iguazio.com/press-release/iguazio-debuts-serverless-platform/)，是一个速度极快的无服务器平台，具有实时处理引擎。速度极快，比 AWS Lambda 快 100 倍。“每个人都知道数据的价值会随着时间的推移而减少，”Haviv 说，“所以这意味着当数据开始流入系统时，你需要开始聚合上下文并在它流动时采取行动。”

问题是如何以极快的速度大规模地处理数据，从数据是可以存储和查询的东西的观念转变为将数据视为可以持续处理的东西。

在底层，它是一个构建在 Kubernetes 之上的抽象层，支持各种各样的本地事件源。它用于构建复杂、协调的微服务，这些服务可以在多云环境中透明地调用。或者，Haviv 说，“它确保你可以实时地将大量数据联系起来，并在这些数据的基础上做出决策。”

Nuclio 之所以开始，是因为团队希望简化将代码转移到产品中的过程。

“开发代码很容易，但操作代码要困难得多，”他说。为了操作代码，你需要调试点，放入观察点，考虑日志和自动缩放。接下来，在前端有负载平衡器，或者如果你是流，你需要考虑分片。然后是版本控制、滚动升级等。

“当我们编写代码时，我们希望按下一个按钮，获得滚动升级，集中记录和集中观察，这样我们就不必每次在平台上创建新功能时都重复这个过程，”他说。“然后我们的顾客问，‘为什么你们被宠坏了？’他们想要同样的功能。"

哈维尔说，该团队希望开源，让 nuclio 尽可能现代化。他们采用来自社区的代码，为其他开源项目做出贡献，找到最佳实践，并提出了他们自己的三个主要创新。

Haviv 解释说，使 Iguazio 如此快速的第一项创新是他们使用闪存设计数据，但让它像内存数据库一样运行。这使得它便宜 30 倍，密度高 30 倍。他说，它允许用户做更多有趣的事情。

第二个创新是创建一个数据库引擎，而不是拥有自己的 API。他们基本上采用了 API 的所有开源实现和 Amazon 实现，并将它们作为微服务堆在栈顶，从用户那里抽象出来。

这也允许用户通过一个 API 传输时间序列数据，并通过另一个 API 读取完全相同的数据。例如，这些客户可以将传感器数据传输到平台，同时对收集的所有传感器数据运行 SQL 查询。

第三项创新是基于 Kubernetes 作为一个平台，将所有这一切创建为 Haviv 所谓的“数据 PaaS”或数据平台即服务(PaaS ),一切都被容器化并设计为自动扩展。它具有非常灵活的可编程 API，并且是云原生的，具有所有的附加功能。

例如，对于 API 网关，他们并没有重新发明轮子，而是仅仅授权给他们的客户访问。因此，对于 Envoy、Istio 而言，该功能内置于其中，但客户不必进行设置。

那么，在如此高的速度下，客户在做什么呢？nuclio 允许亚洲的拼车公司查看所有用户的所有移动设备的所有信息，并可以实时围绕地图、数量、需求和定价建立聚合，以进行决策分析(想想激增定价)。

另一个例子是实时检测欺诈。基于来自应用程序本身的各种信息，股票价格，甚至可能是 Twitter feed 的决策，客户可以根据他们选择的参数立即检测他们系统中的任何欺诈行为。

Haviv 说:“你必须在一个向量的顶部网格化许多不同的数据点，在这个向量的顶部，你运行一个算法并做出决定。”

请收听，了解开源服务器如何比 AWS Lambda 更简单，nuclio 与开源的关系，以及该公司如何得名。

### 在这个版本中:

[1:37:](https://thenewstack.simplecast.com/episodes/iguazios-nuclio-serves-data-100x-faster-than-aws?t=1:37)nucl io 解决了哪些痛点或问题？
[4:02:](https://thenewstack.simplecast.com/episodes/iguazios-nuclio-serves-data-100x-faster-than-aws?t=4:02) 数据挖掘和数据湖的区别。
[7:08:](https://thenewstack.simplecast.com/episodes/iguazios-nuclio-serves-data-100x-faster-than-aws?t=7:08) 商家如何利用这个平台让自己的公司变得更好。
[10:26:](https://thenewstack.simplecast.com/episodes/iguazios-nuclio-serves-data-100x-faster-than-aws?t=10:26) 开发人员在决定无服务器是否适合他们时需要考虑的事情。
[14:50:](https://thenewstack.simplecast.com/episodes/iguazios-nuclio-serves-data-100x-faster-than-aws?t=14:50) 为了让 nuclio 工作，堆栈的哪些部分已经需要就位？
[16:41:](https://thenewstack.simplecast.com/episodes/iguazios-nuclio-serves-data-100x-faster-than-aws?t=16:41) 探索 Haviv 与云计算原生计算基金会在创建行业标准方面的工作

云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>