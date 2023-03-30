# Streamlio Cloud 演示:简化流数据开发的消息平台

> 原文：<https://thenewstack.io/streamlio-cloud-demo-a-messaging-platform-to-ease-development-around-streaming-data/>

在本次演示中，我们将演练 Streamlio Cloud，这是一种托管的云原生消息传递、处理和事件存储服务，构建于开源的 [Apache Pulsar](https://pulsar.apache.org/) 分布式发布-订阅消息传递系统之上。我们的导游是 Streamlio 的营销副总裁[乔恩·博克](https://www.linkedin.com/in/jobock/)。

在这个模型示例中，一个假设的 Java 开发人员创建了一个程序，将来自一个 Twitter feed 的消息(“Tweets”)分成两个独立的 feed，一个是正面情绪，另一个是负面情绪(由一些导入的自然语言处理库确定)。过去，您可能会使用一些复杂的字符串处理路由来过滤和重定向消息。在这种方法中，使用 Streamlio 软件开发工具包(SDK)和他们喜欢的 IDE，程序员只需要识别输入和输出提要。生成的代码可以被编译成函数，签入版本控制系统，并开始构建以将其部署到消息传递环境中。

“编写这段代码相对来说比较简单。你不会看到任何与函数式编程、地图或平面地图或类似概念相关的东西。你在这里看到的基本上是专注于开发人员正在创建的逻辑的东西，”博克说。

该服务提供一个前端仪表板，提供应用程序的操作摘要，这些应用程序可以分组到不同的名称空间、租户或主题(单个流)中。由于使用了[普罗米修斯](https://prometheus.io/)，Streamlio 报告了一个函数被调用的频率，处理了多少数据，队列有多长。开发人员只能看到他们有权访问的主题，这使他们能够看到他们的应用程序在多租户环境中的表现。

Bock 展示了 Streamlio 如何让运营团队的工作变得简单。运营团队可以使用该软件为各个主题分配和限制资源。例如，该平台允许运营团队增加重复的主题，以增加可以处理的数据量。它还提供了在云中存储所有消息传递数据的能力，减轻了开发人员的详细存储管理任务。

“开发人员面临的一大挑战通常是，他们不得不处理大量的生产和运营工作。当然，运营团队也不会了解开发人员的内部情况，”博克说。“但我们真的希望将这两者分离，这样开发团队就不会因为运营问题而负担过重。”

[https://www.youtube.com/embed/e91oPZQo3m4?feature=oembed](https://www.youtube.com/embed/e91oPZQo3m4?feature=oembed)

视频

*TNS 执行主编 Joab Jackson 对此文有贡献。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>