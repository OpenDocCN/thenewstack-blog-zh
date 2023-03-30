# HTTP Alternative RSocket Gets a Home at The Linux Foundation

> 原文：<https://thenewstack.io/http-alternative-rsocket-gets-a-home-at-the-linux-foundation/>

The list of foundations hosted by the [Linux Foundation](https://www.linuxfoundation.org/) continues growing this week with the launch of the [Reactive Foundation,](https://reactive.foundation/) “a community of leaders established to accelerate technologies for building the next generation of networked applications,” according to a statement. Upon founding, those leaders will include Alibaba, Facebook, Netifi and Pivotal, with the open source [RSocket](https://github.com/rsocket) specification and programming language implementations also joining the new foundation’s “formal open governance model and neutral ecosystem.”

RSocket provides a basis for reactive programming at the protocol level and lays the groundwork for reactive programming in cloud native environments, [Ryland Degnan](https://www.linkedin.com/in/rjdegnan), co-founder and CTO at Netifi, said in an interview with The New Stack. It’s considered a replacement for HTTP in cloud native communications.

Lest you [confuse](https://samueleresca.net/2017/06/reactive-programming-damn-it-is-not-about-reactjs/) reactive programming with the [React UI Javascript framework](https://reactjs.org/) of a similar name, reactive programming is defined by its message-driven approach that aims to achieve resiliency and scalability independent of infrastructure, network issues or end-user device. More specifically, the [reactive manifesto](https://www.reactivemanifesto.org/) lists four characteristics of reactive systems: responsive, resilient, elastic and message-driven.

“With the whole cloud native movement, a lot more people are building software for the cloud that operates on a scale that’s an order of magnitude higher than anything we’ve seen before. It’s got a lot of moving parts and rationalizing how all those parts communicate is an incredibly important problem,” Degnan said. “The present problem that RSocket is seeking to solve is defining a standardized way for services to communicate that was built from the ground up and not using last year’s technology.”

“The de facto standard right now when people go out and build stuff is to use HTTP. That comes with loads of problems because it was really designed to be a request-response protocol,” Degnan said. “It has very little that was built for microservices. It was really built for this previous generation of requesting a resource from a monolithic server and returning a response. RSocket has been designed from the ground up for cloud native communication.”

## HTTP vs. RSocket

RSocket 最初由网飞创建，是针对[反应式流](http://www.reactive-streams.org/)的应用协议，提供网络上的应用流控制，以防止中断并提高弹性。与 HTTP 相反，RSocket 不等待来自客户端的响应或请求。德格南解释了 HTTP 和 RSocket 的核心区别。

“构建这些分布式系统所花费的大量努力最终都是为了解决 HTTP 的问题。断路器就是一个很好的例子。它解决了 HTTP 没有内置流量控制的问题，这意味着你必须猜测下游服务是否可用，以避免它接收太多的请求，”德格南说。“如果你认为它现在不可用，你需要切断它的流量，但这涉及到许多配置。RSocket 可以完全解决这个问题。”

相比之下，RSocket 采用了带有[非阻塞反压](https://www.reactivemanifesto.org/glossary#Back-Pressure)的异步流处理的思想，根据[反应宣言词汇表](https://www.reactivemanifesto.org/glossary)的说法，在这种思想中，故障组件将不会简单地丢弃流量，而是将其压力传递给上游组件，让它们减少负载，并允许系统“优雅地响应负载，而不是在负载下崩溃”。德格南进一步解释了这是如何应用于现代微服务领域的。

“反应流被设计成让信息的提供者和接收者相互分离。德格南说:“不是让接收者控制信息流，而是让发送者异步发送真正重要的数据。“例如，在微服务中，有许多需要通信的独立组件，经常发生的情况是，一些服务能够以比其他服务更高的速度运行，或者流量峰值淹没了部分系统。“反应流允许接收者说，‘好的，现在我准备好再接收五个请求’，然后在系统中询问该消息，并对信息流进行监管。”

虽然向 Reactive Foundation 捐赠 RSocket 奠定了基础，但该基金会的一位发言人解释说，它还将“努力扩展现有的语言实现/集成集，创建一个测试平台以确保不同协议实现之间的互操作性，托管一个关于一般反应系统/编程以及像 RSocket 这样的特定项目的文档库。”

Linux 基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>