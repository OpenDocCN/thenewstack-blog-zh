# Akka Java 中间件:容器中的内容很重要

> 原文：<https://thenewstack.io/akka-java-middleware-what-goes-inside-the-containers-counts/>

当 Jonas Bonér 根据他在分布式系统方面的工作形成了[反应宣言](http://www.reactivemanifesto.org/)背后的想法时，向云的迁移还处于起步阶段，容器和 Kubernetes 还没有到来。然而，他正在寻找 [Akka](https://akka.io/) ，他创建的中间件增加了组件之间的抽象层，在 Docker 和 Kubernetes 世界中具有新的相关性。

“Kubernetes 和 Docker 的历史问题是，人们把旧的东西、传统的东西、JEE 风格的东西放进容器里。然后，他们把所有旧习惯、旧通信方法、同步协议、管理状态的坏东西都放进了容器。那你只能走一半。你有一个很好的编排容器的模型，但是在容器中运行的东西确实不是最佳的。它们并不适合这个新的云世界，”Bonér 在接受采访时说。

五年前[公开发布的](http://globenewswire.com/news-release/2018/07/24/1541116/0/en/Five-Years-of-Innovation-Reactive-Manifesto-Reaches-Key-Milestone.html)反应宣言呼吁系统要有反应能力、弹性、弹性和信息驱动。

Kubernetes 和 Docker 试图从基础设施层面解决故障等问题，而 Akka 则从编程模型的角度解决这些问题——如何构建业务逻辑，如何构建工作流。LinkedIn、威瑞森、Capital One 和 Credit Karma 都使用 Akka。

“应用程序的本质是事物如何交流，事物如何相互联系，信息如何在不同部分之间流动，”Bonér 说。“通过 Akka，我们试图为云构建最佳编程模型。这是真正意义上的云原生。在“云原生”这个术语被创造出来之前，它就是为在云中原生运行而构建的。”

Akka 是一个基于 Scala 的框架，运行在标准 JVM 上。它是一组开源库，用于设计跨处理器内核和网络的可伸缩、弹性系统。这是最著名的[角色模型](https://www.brianstorti.com/the-actor-model/)的实现，它使用轻量级的、隔离的“角色”通过异步消息传递进行通信。它专注于实现业务逻辑，而不是编写低级代码来提供可靠的行为、容错和高性能。

它由 Bonér 的公司 [Lightbend](https://www.lightbend.com/) 支持，该公司是 Scala 语言和 *Lagom* 微服务和 Play web 应用框架的母公司。Akka 也在 Java 上工作。它在 GitHub 上有超过 250 个项目，以及一个到. NET 的端口。然而，根据 RedMonk 分析师 James Governor 的说法，它伴随着 Scala 的陡峭学习曲线。在最近的编程语言排名中，他注意到 Scala 在经历了前三个季度的下滑后，出现了[的上升。](https://redmonk.com/sogrady/2018/08/10/language-rankings-6-18/)

Akka 一直在慢慢成长。然而，Bonér 说，今天它每月有大约 500 万次下载，而两年前每月有 50 万次下载。

Bonér 说:“Akka 在如何建立业务逻辑，如何在更精细的层面上协调工作流程方面做得非常好。“这是你放在码头集装箱里的东西。它是驱动应用程序逻辑和通信模式的东西。这是你放在盒子里的东西，是你和 Kubernetes 一起编排的。所以我认为这两种不同的看待世界的方式是相辅相成的。”

Bonér 之前与新堆栈讨论过[反应式编程如何解决横向扩展](https://thenewstack.io/typesafes-jonas-boner-how-reactive-programming-addresses-the-scale-out-problem/)问题。

他指出，现在很多注意力都集中在微服务上，有很多框架可以让创建单个微服务变得非常容易，但一个微服务并没有那么有用。

“微服务只有在能够协作的时候才有用。…一旦他们开始协作，我们就需要在整个分布式系统中进行协调。这就是所有困难的地方——管理沟通，管理状态。…然后你必须自己把所有的东西缝合在一起，而 AKKA 从一开始就是为此而生的，从一开始就为分布式系统构建一个结构。”

Akka 信奉“让它失败”的态度——失去一个演员不应该有关系，因为另一个人会接手工作——那个演员甚至可能在另一台机器上。Bonér 解释了这在集装箱化的世界中是如何工作的:

Akka 模型的一个关键方面是位置透明的概念。每个组件都有一个虚拟地址。

“你所需要做的就是与这个代理，这个虚拟地址进行通信。然后，所有的通信都被转发到那个演员所在的地方。它可能在同一台机器上，但是出于可伸缩性的原因，它可能被移动到另一台机器上。作为用户，你可能永远也不会知道。

“那个演员碰巧在哪里对你来说并不重要。这意味着系统可以根据需求或应用程序的负载自由地扩展或缩小系统。在复制或冗余方面，您也可以利用这一点，但它可能会产生三、四个实例。如果其中一个失败了，它会指向一个复制品——这一切你甚至都不知道。

他说，作为 Kubernetes 之上的一层，所有这些都可以在没有管理员干预的情况下由运行时本身完成。但是，如果整个节点都瘫痪了，您需要采用一种更粗粒度的方法来进行故障管理。

“这可能是一个更密集的过程。最好让分布结构来管理它—在这种情况下是 Akka。让运行时为您管理失败。我认为这种对失败的细粒度管理和 Kubernetes 中对失败的粗粒度管理是相辅相成的。”

在 6 月于西班牙召开的会议上，软件架构师 T2 赞扬了 Akka 和 Kubernetes 联合提供的弹性。

[https://www.youtube.com/embed/OOXRgd5yUQo?feature=oembed](https://www.youtube.com/embed/OOXRgd5yUQo?feature=oembed)

视频

[Genuine.com](https://www.linkedin.com/in/leocheung1/)的负责人 Leo Cheung 坚持认为，Akka 和 [actor 模型是物联网应用的理想选择](https://www.infoworld.com/article/3209728/internet-of-things/why-akka-and-the-actor-model-shine-for-iot-applications.html)，并指出:“‘最低限度’的要求与 actor 模型非常吻合，在 actor 模型中，将业务逻辑分解为单个 actor 处理的最小任务是该模型基本原则的一部分。”

特征图片:[康纳无法无天](https://www.flickr.com/photos/conchur/)的《DSC_2915_PinkSeeds2》，授权于 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>