# 微服务:一切都与事件有关

> 原文：<https://thenewstack.io/microservices-its-all-about-the-events/>

微服务似乎是今年在纽约举行的[O ' Reilly Software Architecture](https://conferences.oreilly.com/software-architecture/)大会的主要讨论话题，与会的开发人员和系统设计人员对如何将他们的整体遗留系统转变为更加灵活的微服务驱动系统感到好奇。

在周二的开幕主题演讲中，许多演讲者解释了微服务驱动的架构与我们之前认为的 IT 系统架构有何不同。关键外卖？都是关于事件的。

最初的 Cloud Foundry 软件的创建者 [Chris Richardson](https://twitter.com/crichardson) 解释道:“事件在架构的每一个层面都扮演着重要的角色。”[软件架构主题的著名作者](http://chrisrichardson.net/learnmicroservices.html)。

[微服务](/category/microservices/)的想法是将大型的整体应用程序分解成更小的协调服务集，这样每个服务都可以被替换或扩展，而不需要改变整个整体。

他说，甚至当前的企业系统也是围绕事件驱动的。一家航空公司延误了航班，一家药店开了药方。已经安排了送货。有些事件是基于时间的:发票没有按时支付。事件允许独立的应用程序进行协作:事实上，一个应用程序中的任何状态变化都可以是一个事件，一个可以被另一个应用程序使用的事件。监控服务可以分析从另一个应用程序发出的事件流，检查以确保事件模式是正常的。

Richardson 解释说，事件驱动设计是一种不用修改应用程序就能扩展它们的方法。

可以通过某种消息传递软件将事件从一个应用程序传递到另一个应用程序。理查森说，对于内部沟通，像 Apache Kafka 这样的企业消息代理可以完成这项工作。对于外部通信，需要一种基于 HTTP 的传输形式，比如 [WebSockets](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API) 、 [Webhooks](https://thenewstack.io/wonderful-world-webhooks/) ，或者一种发布/订阅机制。

Pivotal 高级技术总监、即将出版的新书 [Cloud Native](https://www.manning.com/books/cloud-native) 的作者 Cornelia Davis 在她的主题演讲中指出，虽然最初，迁移到基于事件的架构听起来很容易，但它确实需要架构思维的某种转变。戴维斯说，微服务就其本质而言，是分布式计算的一种极端形式。

她指出，用于计算的传统服务器请求/响应模型来自命令式编程模型，尽管基于事件的模型实际上更像是函数式编程模型。“函数式编程模型对分布式系统非常非常有效，”她说。

传统的系统可能依赖于“重试”的概念，如果它最初没有从其他服务获得所有需要的材料。web 服务器可能不会返回所请求的网页，直到所有不同的元素都就位，最慢的服务会阻碍最终的交付。然而，在本质上不可靠的分布式系统环境中，[承诺](http://dist-prog-book.com/chapter/2/futures.html)的抽象可能比重试更合适。各种组件生成它们自己的事件，这些事件通过事件或更改的序列化流填充 Web 服务器的物化视图。“你可以把承诺想象成事件处理者，”戴维斯说。她说，事件处理程序将“在我需要时”完成一个步骤。

“分布式系统的一个关键是，你有一大堆独立的控制回路负责它们自己的处理，”她说。这个领域中最受欢迎的概念之一是[命令查询责任分离](https://martinfowler.com/bliki/CQRS.html) (CQRS)，它将向数据存储中插入数据的通道与查询该数据的通道分开，因此一个通道的性能不依赖于另一个通道。

“事件可以触发功能，这是实现功能即服务的一种非常自然的方式，”她说。

这个观点在会议的其他地方得到了响应。 [Duncan DeVore](https://twitter.com/ironfish) ， [Lightbend](https://twitter.com/Joab_Jackson/status/968608968179412992) ，[的软件工程师指出](https://twitter.com/Joab_Jackson/status/968608968179412992)有两种类型的系统交互:承诺和义务。“你想要承诺，而不是义务。义务转向不可预测的结果；承诺汇聚成明确的结果，”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>