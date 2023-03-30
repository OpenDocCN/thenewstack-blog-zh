# Apcera NATS 之旅:简单、高性能的信息系统

> 原文：<https://thenewstack.io/demonstrating-nats-apceras-simple-high-performance-messaging-system/>

为服务通信建立复杂的消息传递系统可能是一项挑战。Apcera 的 [NATS](https://thenewstack.io/nats-rest-alternative-provides-messaging-distributed-systems/) 开源信息平台就是为了解决这种复杂性而设计的。“这背后的核心原则是简单性和性能。NATS 非常简单。它使用一个随时可用的纯文本协议。无论规模大小，你的系统都可以相互通信，”Apcera 的社区和生态系统经理 [Brian Flannery](https://twitter.com/brianflannery) 说。

在下面嵌入的[简短演示](https://thenewstack.io/podcasts/tutorials/)中，Apcera 高级软件开发人员 [Waldemar Quevedo Salinas](https://github.com/wallyqs) 与 Flannery 一起，作为新 Stack 创始人 [Alex Williams](https://twitter.com/alexwilliams) 与两人一起在 DockerCon 2016 活动大厅进行 NATS 现场演示。萨利纳斯提供了一个循序渐进的指南，介绍了 NATS 最强大的一些功能，包括 NATS 对传统发布/订阅模式的独特做法。

[https://www.youtube.com/embed/EU4au3PJr5o?feature=oembed](https://www.youtube.com/embed/EU4au3PJr5o?feature=oembed)

视频

当 Salinas 开发一些基本客户时，他解释说 NATS 为它的消息系统使用一个纯文本的、基本的发布和订阅模型。Salinas 指出，NATS 内部架构简化了许多传统上开发人员在建立消息传递系统时需要的粘合工作。

“通过使用基于 NATS 的架构，您可以扫描以至少建立连接，这意味着您不必担心创建开放套接字、估计到服务器的连接或发送有效负载。你也不必担心如何包装所有的东西，或垃圾收集。对于 NATS，你只需要专注于发送和响应，就是这样，”他说。

萨利纳斯继续利用 docker-compose 构建一个简单的架构，创建他能够实时查看流量的任务。工作人员能够接收来自终端服务器的请求，并被配置为期待相同的响应。在安排了一个任务之后，Salinas 向服务器请求跟踪日志——在 8 毫秒内返回。

在构建了一个包含监控工具的新 Docker 容器后，Salinas 轮询服务器以获得当前运行的客户端的视图。通过再次利用 docker-compose 工具，Salinas 能够快速扩展客户端。正是这种灵活性，不假设一个人的架构是什么样子，也不假设一个系统应该如何通信，Apcera 将这种灵活性带到了 NATS 的桌面上。

其他消息传递协议假设您的系统架构应该是什么样子。NATS 在那里处理酒吧/订阅，并始终可用。这是一个很大的区别，是灵活性，”弗兰纳里完成。

Apcera 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>