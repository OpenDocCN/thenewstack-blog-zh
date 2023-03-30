# Lightbend 的 Akka 无服务器平台即服务可大规模管理分布式状态

> 原文：<https://thenewstack.io/lightbends-akka-serverless-paas-to-manage-distributed-state-at-scale/>

开源应用框架提供商 [Lightbend](https://www.lightbend.com/?utm_content=inline-mention) 为其新的 Akka 无服务器平台推出了一个公开测试版，该公司声称这是第一个消除阻碍开发者使用[无服务器](https://thenewstack.io/category/serverless/)构建业务关键型应用的障碍。

Akka Serverless 建立在 [Lightbend 的 Akka 平台](https://searchapparchitecture.techtarget.com/news/252496868/Lightbend-launches-new-Akka-Cloud-Service-on-AWS)之上，这是一个用于构建大规模分布式应用的框架。总部位于旧金山的 Lightbend 战略执行副总裁 Brad Murdoch 表示，Akka 平台每年吸引超过 2000 万次下载，是在 Kubernetes 的容器上构建云原生应用程序的最受欢迎的编程模型之一。

“你今天可能用了 Akka，甚至都没有意识到。因为它能为 Siri、iTunes 和苹果地图提供动力，默多克说。它在数字飞轮中处理每一笔星巴克交易——移动奖励、移动订购、移动支付，个性化是通过人工智能平台完成的。如果你看 Disney+，那么整个流媒体平台和所有相关的分析都建立在基于 Akka 的平台上。因此，我们知道构建大规模高性能系统需要什么。"

然而，Akka 无服务器 PaaS 为无服务器带来了一种有状态的方法，使开发人员能够创建高性能的后端服务和 API。

[有状态](https://whatis.techtarget.com/definition/stateless)意味着计算机或程序跟踪交互的状态，通常是通过在为此目的指定的存储字段中设置值。如果一个[有状态事务](https://www.redhat.com/en/topics/cloud-native-apps/stateful-vs-stateless)被中断，上下文和历史已经被存储，所以您可以或多或少地从您离开的地方开始。

“所以，我们在过去两年中一直关注的是，我们如何才能获得 Akka 的所有优点，并将其隐藏起来，让任何开发者都可以使用，这样他们所需要做的就是基本上为他们的程序编写业务逻辑”，默多克说。

此外，“我们研究出的是如何最好地获取持久存储在某个地方的数据，”他说。“它实际上在数据库中。但是它可以在一切都是异步的情况下运行，并且在运行时一切都在内存中。因此，我们找到了能够将其转化为功能即服务模式的方法。这真的是我们能够做到的重大创新。”

凭借其新的分布式状态架构，Akka Serverless 消除了云原生应用程序对数据库的需求。因此，该产品使组织不必为数据库管理、维护甚至 API 而烦恼。

Lightbend 已经在 Akka Serverless 上工作了近三年，并且在过去的三个月里已经有了这项技术的私人测试版。

总部位于伦敦的 [Judopay](https://www.judopay.com/) 的首席技术官罗伯特·霍维斯参加了私人测试，并表示他看到了 Akka Serverless 增加 Judopay“创新镜头”的潜力，这意味着它已经扩展了他对该公司可以提供的新服务的愿景。

“这创造了一个有趣的创新机会，因为我们已经拥有了我们的核心支付产品，这通常会获得我们带宽、资源和注意力的最大份额，”霍维斯说。但他说，他看到了更广泛的支付方式，适用于更广泛的商家、零售商和商业领域。

“有许多重要的使用案例，比如对账报告、自动化自助服务、自动化入职，还有一些事务优化。”

默多克说，到目前为止，无服务器技术还不能支持企业今天正在构建的有状态、高性能、可扩展的应用程序。此类应用的示例包括消费和工业物联网、工厂自动化、现代电子商务、实时金融服务、流媒体、基于互联网的游戏和 SaaS 应用。

451 Research 的 cloud native 研究总监 William Fellows 表示:“无服务器应用程序设计的有状态方法将需要支持目前无法利用它的各种企业应用程序，如电子商务、工作流和任何需要人工操作的应用程序。"无服务器函数是短命的，在执行时会丢失任何“状态”或上下文信息."

Lightbend 通过 Akka 无服务器解决了大规模管理分布式状态的挑战。

“我们从测试版中获得的最重要的反馈是，我们必须要做的一件关键事情是建立这个平台，找到一种方法，能够在运行时自动在内存中提供数据，而开发人员不必做任何事情，”默多克说，

这转化成了持久层的抽象，开发者根本不需要了解任何关于数据库的知识。

“因此，就如何存储或管理数据而言，它完全消除了开发人员对数据库的考虑，这对开发人员的生产力来说是一个巨大的进步，”默多克说。

默多克说，尽管 Akka 平台以前仅限于更常见的 Java 虚拟机(JVM)语言，如 Java 和 Scala，但 Akka Serverless 是一个支持任何编程语言的多语言平台。他说，在私人测试期间，有 C#开发人员、[TypeScript](https://searchapparchitecture.techtarget.com/news/252488217/TypeScripts-co-creator-speaks-out-on-TypeScript-40)开发人员，以及 JavaScript 和 Node.js 开发人员在开发应用程序。

“该平台被设计为可以在多种云上运行，它确实可以在 Kubernetes 上运行。所以，它使用的是 T2 GKE T3 谷歌 Kubernetes 引擎。

他说，该平台目前仅限于[谷歌云平台](https://thenewstack.io/3-tips-for-benchmarking-and-provisioning-google-cloud/)，但还会有其他云出现。

“我们也有可能将它变成一种混合产品，这是我们尚未承诺的。默多克说。目前，我们专注于提供这种服务。但是有可能我们可以使用 Kubernetes 和 cloud native，能够使用 OpenShift 或 [Tanzu](https://thenewstack.io/vmwares-tanzu-extends-across-all-security-layers-on-kubernetes/) 或 Rancher 或类似的东西作为混合产品。"

Akka 无服务器目前正处于[公开测试阶段](https://console.akkaserverless.com/p/register)，预计将于今年第四季度全面上市。Lightbend 将在 2021 年 6 月 16 日星期三举行的[发布网络研讨会](https://info.lightbend.com/akka-serverless-open-beta-stateful-services-made-simple-register.html)上提供更多关于 Akka Serverless 的信息。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>