# Lightbend 的 Cloudstate 构建于 Akka 之上，提供有状态的无服务器

> 原文：<https://thenewstack.io/lightbends-cloudstate-builds-on-akka-to-offer-stateful-serverless/>

无服务器计算得到了一个不太可能的来源的帮助:Java 社区。或者更具体地说，来自于 [Akka](https://akka.io/) 分布式消息传递工具包。

在许多方面，[无服务器](/category/serverless/)已经超越了最初运行小批量作业的用例。业界已经发现，在许多工作负载中，比如 Web 会话，必须维护某种状态，即使只是暂时的。为此，反应式微服务框架提供商 [Lightbend](https://www.lightbend.com/about-lightbend) 设计了一个名为 [Cloudstate](https://cloudstate.io/) 的架构，将分布式有状态数据保留带到无服务器功能(FaaS)和其他无服务器任务中。它建立在 Akka 集群的基础上，通过与附属于每个功能的代理/边车进行点对点通信，提供分布式弹性消息传递。

在本期[新堆栈环境](/podcasts/context)播客中，我们采访了 Akka 创始人兼 Lightbend 创始人/首席技术官 [Jonas Bonér](http://jonasboner.com/) ，探讨将 state 带入无服务器、反应式微服务框架和 Cloudstate 本身所面临的挑战。TNS 编辑和营销总监[利比·克拉克](/author/libby/)在 TNS 执行主编[约阿布·杰克逊](/author/joab/)的帮助下主持这一集。

[第 136 集:Lightbend 的 Cloudstate 构建于 Akka 之上，提供有状态无服务器](https://thenewstack.simplecast.com/episodes/episode-136-lightbends-cloudstate-builds-on-akka-to-offer-stateful-serverless)

粗略地说，“状态”是您获得应用程序或应用程序设置所需的所有操作数据，以保持其运行直到完成。保持状态的传统模型通常涉及数据库，这对于今天的工作负载来说[是一个弱答案](https://www.youtube.com/watch?v=D3bYGIo2kiQ),原因有二:与后端数据库的通信太慢，关系数据库不容易用于跟踪版本控制，或者数据如何更新。

[Cloudstate 方法](https://www.youtube.com/watch?v=DVTf5WQlgB8)是将数据和计算放在同一个节点上。这是通过附属于每项功能的边车来实现的。边车都是分布式集群的一部分，由 Akka 框架管理。对于开发人员来说，Cloudstate 就像一个服务(Bonér 建议，应该作为一个服务在 Kubernetes 集群上运行):它的状态输入/状态输出。Akka 基于 Java，但是没有冷启动延迟时间，这要感谢使用了 [GraalVM](https://www.graalvm.org/) ，它将代码预编译成二进制文件。

在我们与 Bonér 的对话之后，我们接着深入研究了本周其他一些著名的 TNS 帖子和播客，包括 [VMware 收购 SaltStack](/vmware-to-acquire-saltstack-for-advanced-multicloud-automation/) 和微软的一个新功能，该功能允许用户[停止和启动 Kubernetes 集群，如暂停视频](/microsoft-azure-stop-and-start-kubernetes-clusters-like-pausing-a-video/)。

本期标志着新的堆栈背景播客[的最后一集。10 月 12 日，TNS 将在](/podcasts/context) [The New Stack Makers](/podcasts/makers) 推出一个名为“攀登新高度”的新播客系列。我们的嘉宾主持人 [Christine Heckart](https://www.linkedin.com/in/christineheckart/) ，Scalyr 的首席执行官，与让现代生活成为可能的快速增长公司的工程经理交谈。聆听 Robinhood、Airbnb 和 Nextdoor 等公司的工程领导讲述他们的团队面临的大规模技术和人力挑战，以及他们是如何度过“绝望之谷”的。在 Itunes、SoundCloud 和 Spotify 上订阅的新 Stack Makers，或者在任何地方收听你喜欢的新 Stack 的播客。

Lightbend 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>