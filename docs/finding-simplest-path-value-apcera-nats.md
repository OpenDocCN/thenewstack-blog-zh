# Apcera NATS，信息传递和简单性

> 原文：<https://thenewstack.io/finding-simplest-path-value-apcera-nats/>

随着当今应用发送和接收的数据量不断增加，开发人员正转向可靠的技术来帮助他们解决不同应用之间或应用内不同微服务之间的消息代理问题。剥离大规模消息代理的复杂性是 Apcera 的目标，这是通过其基于 Go 的消息代理服务 T2 NATS T3 来实现的。

在这一集的[新堆栈分析师](https://thenewstack.io/podcasts/)中，我们探索 Apcera 如何希望 NATS 在消息代理生态系统中脱颖而出，为什么简单性是大规模消息代理的强大工具，以及开发者如何确保他们的服务长期保持成本效益。Apcera 产品经理 [Larry McQueary](https://www.linkedin.com/in/mcqueary) 和 Apcera 联盟和渠道副总裁 [Steve Dischinger](https://www.linkedin.com/in/stevedischinger) 采访了 New Stack 创始人 Alex Williams 和联合主持人 451 Research 分析师 [Donnie Berkholz](https://www.linkedin.com/in/dberkholz) 以了解更多关于 NATS 的信息。

[#106:用阿普塞拉 NATS](https://thenewstack.simplecast.com/episodes/106-finding-the-simplest-path-to-value-with-apcera-nats) 寻找最简单的价值路径

采访也可以在 YouTube 上听到。

McQueary 强调了开发人员在使用分布式应用程序(如 Kafka)时可能面临的一些挑战。“根据您使用的版本，它有一些活动的部分。我们只是试着把这一切留给应用程序和开发者。我们希望提供一个尽可能小的核心工具，占用空间最小，复杂性最低。因此，您可以构建最好的应用程序，而不必担心“我如何发送消息？”"

如果不密切关注，从 A 点到 B 点获取数据的相关成本会迅速增加。McQueary 强调，自从 Java 的远程方法调用(RMI)主导消息代理以来的 20 年里，协议可能已经发生了变化，但发布/订阅过程还没有变得模糊不清。“这些服务使用 HTTP 或[HTTP/2](https://thenewstack.io/take-advantage-http2-speed-web-sites-apps/)在进程之间建立点对点连接，它们首先必须通过外部服务如[consult](https://www.consul.io/)或 etcd 来查找，这样做的成本很高。一般比你想象的要贵。尤其是当您在控制平面中触发大量事件和事务时。”

随着对话的继续，McQueary 向那些寻求将他们的消息代理平台与他们现有的堆栈集成的人提出了一个问题，“我们认为用户应该考虑的事情是:在进行这些集成时，最简单的价值途径是什么？”

[![containercon_use](img/87828b392aaebc0d708c601f07dfcde2.png)](http://events.linuxfoundation.org/events/containercon)

Apcera 是新堆栈的赞助商。

在 [cc0](https://creativecommons.org/choose/mark/) 许可下，由 [Etienne Desclides](https://unsplash.com/@atn) 通过 [Unsplash](https://unsplash.com/photos/GYNxcQvBNzA) 拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>