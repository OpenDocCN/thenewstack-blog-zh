# 无服务器开启了云混搭的新世界

> 原文：<https://thenewstack.io/serverless-has-unlocked-a-new-world-of-cloud-mashups/>

无服务器是云计算的一个发展趋势，它正在引领我们如何在互联网上混合和匹配数据的一场静悄悄的革命。

这个名字本身是一个误称，因为物理服务器仍然存在(在堆栈的下方，位于内华达州和俄勒冈州等地的大型数据中心中)。但是在无服务器领域，开发人员不必担心这个问题。通过 AWS Lambda、Google Cloud Functions、Azure Functions 和 Knative(一个开源选项)等产品，服务器基本上已经被抽象掉了。

正如亚马逊网络服务[所说的](https://aws.amazon.com/serverless/)，“无服务器允许你构建和运行应用程序和服务，而不用考虑服务器。”它自己的无服务器产品 AWS Lambda 有一个按需付费的计算时间模型——你只需为你使用的计算时间付费，而不是为数据使用或服务器空间付费。

无服务器计算的货币是“事件”。每当有一个事件触发，你的代码运行，你支付你的便士，一个函数执行。

如果你的所有活动都在同一个云平台上，这是一个简单的过程，但由于另一个新兴趋势:多云，这变得越来越不常见。越来越多的开发人员需要创建与事件交互的应用程序，并在多个云环境中运行功能。

进入[触发画面](https://triggermesh.com/)。它将自己描述为“云原生集成平台”，这意味着它在不同的云、SaaS 服务和遗留系统之间提供了一座桥梁。 [Sebastien Goasguen](https://twitter.com/sebgoa) 和 [Mark Hinkle](https://www.linkedin.com/in/markrhinkle/) 在 2018 年创办了这家公司，目标是建立“我们认为会与行业发展方向相吻合的无服务器工具和基础设施”

Goasguen 和 Hinkle 预见到，随着云平台数量的增长以及与其他平台上的服务集成的商机相应扩大，应用程序将需要越来越具有可移植性。

TriggerMesh 构建在开源的 Knative 之上，Knative 本身构建在 Kubernetes 之上。Knative 专注于部署和管理现代无服务器工作负载，而 TriggerMesh 专注于应用层。或者正如 Goasguen 所说，当 TriggerMesh [在 2018 年 11 月](https://triggermesh.com/2018/11/launching-triggermesh/)推出时，“帮助人们部署功能并通过事件将它们链接起来，以构建新的云原生应用。”

Kubernetes 的专家有时会用乐高类比来尝试解释我们当前的时代。在最近的[新堆栈上下文播客](https://thenewstack.io/the-new-stack-context-serverless-application-flows-in-the-cloud/)中，Goasguen 这样说道:

*“Kelsey Hightower(谷歌的一名 Kubernetes 传播者)曾经提到，你和 Kubernetes 一起玩乐高。[……]我们正在玩的积木——大乐高——是我们正在使用的库，它们实际上是云服务。它是你的机器学习，它是你的分析平台，它是你的交易平台，你的对话工具——对吗？所以你有这些积木，你需要把它们组合起来。”*

Goasguen 指出，如果你“待在一朵云里”，那么从所有这些构建模块*中“组合”你的应用程序是非常简单的例如，如果你使用 AWS，你可以使用亚马逊的无服务器产品(EventBridge 和 Lambda)来构建你的应用。*

但是这越来越不是开发者生活的世界了。他们通常需要使用位于另一个云中(例如，谷歌基于云的机器学习服务之一)或本地(Goasguen 引用了内部运行的 Oracle 数据库的例子)的块。

“因此，当你需要跨越这些障碍时，”Goasguen 解释说，“[…]这就是你开始需要依赖事件的地方，你需要定义事件流。”他认为“云原生架构的未来[…]将是事件驱动的。”

在某种程度上，TriggerMesh 就像是经典 web 2.0 混搭服务的现代版本。事实上，在 1 月下旬的一篇关于新堆栈的文章中，联合创始人兼首席执行官马克·辛克尔(Mark Hinkle)将 TriggerMesh 比作雅虎管道(Yahoo Pipes)，这是雅虎的一项数据聚合服务，从 2007 年运行到 2015 年。

Yahoo Pipes 比 TriggerMesh 更容易概念化，因为它直接触及数据源。使用 Pipes，您可以通过 API 和 RSS 提要从 web 资源中获取信息。使用拖放式用户界面，您可以为该数据定义规则(例如，通过关键字进行过滤)。由于能够重用其他用户的“管道”,这个过程变得更加容易。正如我 2007 年 2 月在读写网[上写的那样，当雅虎 Pipes 推出时:](https://web.archive.org/web/20070209230149/http://www.readwriteweb.com/archives/yahoo_pipes_rss_remixer.php)

*“您可以使用漂亮的可视化工具从头开始创建一个新管道，或者浏览现有管道并选择一个您感兴趣的管道。您也可以“克隆”一个管道，并进行自己的调整。然后点击“运行此管道”查看结果。”*

当时，Yahoo Pipes 的构建模块是 API 和 RSS 提要——数据源(至少在当时)是丰富的信息来源。管道使得将这些数据“块”链接在一起变得很容易，然后您可以使用像“过滤”和“排序”这样的操作符来操纵它。

正如 Hinkle 在今年 1 月指出的，Yahoo Pipes 是“过滤所有数据以得到你想要的东西的一个很好的例子，这样你就可以触发你的功能。”

值得注意的是，雅虎 Pipes 是在一个更简单的时间推出的，远在 Kubernetes 和 containers [使应用成为抽象概念](https://thenewstack.io/why-apps-are-fundamentally-different-in-the-kubernetes-era/)之前。这也是一个更加乐观的时期，尤其是对互联网和网络而言。2007 年，人们认为数以千万计的 API 和 RSS 提要将可供人们(和应用程序)在他们认为合适的时候使用。当时人们认为，这些数据很容易获取，也很容易使用(和重复使用)。

嗯，结果并不完全是那样。很快，网络又回到了像脸书和推特这样有围墙的花园平台，那里的数据流受到严格控制。迄今为止，你还不能从脸书导出你朋友的全部数据。至于 RSS，脸书完全绕过了它——为用户创建了自己专有的、算法驱动的数据“新闻源”。

因此，开放混搭网络的愿景从未成为现实。在脸书时代挣扎了几年后，雅虎管道终于在 2015 年被关闭。

快进到当前的时代，互联网上有数十亿字节的有用数据——远远超过十年前的可用数据。它的大部分存在于云上；或者更准确地说，跨越多个云。

为了获取这些数据及其所有相关服务，你需要云原生工具，使你能够连接到它——并且*使用*它——无论一切都在哪里。这是 TriggerMesh 试图完成的一部分，同时管理和链接各种功能。

TriggerMesh 和其他现代工具的用户界面不像雅虎 Pipes 那样是简单的拖放。但是，多亏了无服务器技术，至少开发人员不必再为基础设施伤脑筋了，如果他们不想的话。

总之:虽然通过开放 API 和 RSS 提要使在线混搭变得容易的世界已经一去不复返了，但是一个全新的云混搭世界已经打开了。

TriggerMesh 和 Amazon Web Services 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>