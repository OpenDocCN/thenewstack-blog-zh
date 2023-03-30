# Linkerd 1.0，一个面向云原生应用的通信服务网格

> 原文：<https://thenewstack.io/linkerd-reaches-1-0-provides-communications-service-mesh-cloud-native-ops/>

随着云原生应用的日益流行，可靠性和性能变得更加复杂。为了解决这些问题，开源[Linkerd](https://github.com/linkerd/linkerd)项目背后的开发人员提倡一个独立的通信层来透明地处理服务发现、负载平衡、故障处理、工具和服务路由等方面。

它完全将这个通信层从应用程序代码中分离出来。这意味着开发人员可以专注于编写应用程序逻辑，而不是网络代码。据赞助商公司[buppy](https://buoyant.io/)的首席执行官[威廉·摩根](https://github.com/wmorgan)称，开发商甚至不必关心这些运营方面的问题。

[![](img/1946ade56094f684dd747b20bf20bf3c.png)](https://github.com/linkerd/linkerd)

2015 年，工程师摩根和奥利弗·古尔德在 Twitter 工作了大约五年，致力于战胜臭名昭著的“失败鲸”，并成立了浮力公司。他们发现许多问题源于服务对服务的交流，这最终会导致整个网站瘫痪。

他们试图引入工具来确保可靠性，这源于 Twitter 从一个单一的 Ruby on Rails 迁移到一个新的基础设施——“我们甚至不知道该叫它什么，”Morgan 说。

摩根说，Linkerd(发音为“linker-DEE”)从 2016 年 2 月的“冷启动”开始——没有用户，没有采纳者，没有贡献者。一年多后，它被 Credit Karma、PayPal 和 Ticketmaster 等公司使用，并成为[云本地计算基金会](https://www.cncf.io/)的一个项目。

这家总部位于旧金山的公司宣称，在过去一年专注于性能、可靠性和可扩展性之后，它已经达到了 1.0。

1.0 版本的主要特性包括一个服务网格 API 端到端的可靠性特征，例如负载平衡、电路中断、请求路由、截止期传播和重试管理；安全和加密功能，如透明传输层安全(TLS)；分布式跟踪和细粒度检测；以及与云原生生态系统的集成，包括 [Kubernetes](/category/kubernetes/) 容器编排软件、Prometheus 监控工具和 [gRPC](http://www.grpc.io/) 。

“这是公司在迁移到云原生堆栈时可以使用的东西。摩根说:“如果你有一个庞大的、单一的应用程序，它就没那么有用了——只有当你转向 Docker 和 Kubernetes 之类的应用程序时，它才真正有用。”。

## 寻求一致性、可靠性

Linkerd 源于 Twitter 的 [Finagle](https://twitter.github.io/finagle/) 项目*，*一个为 JVM 设计的可扩展远程过程调用(RPC)系统，它为各种协议实现了统一的客户端和服务器 API，具有高性能和并发性。Linkerd 建立在 [Netty](https://netty.io/) 之上，这是一个非阻塞 I/O (NIO)客户端-服务器框架*、*和 Finagle，它允许微服务从位于另一个网络上的程序请求服务，而不必输入其网络细节。

[https://www.youtube.com/embed/0xYSy6OmjUM?feature=oembed](https://www.youtube.com/embed/0xYSy6OmjUM?feature=oembed)

视频

然而，摩根和古尔德希望它能跨任何语言和任何基础设施运行，而不仅仅是 Java。

“人们已经将这种逻辑写入了他们的应用程序。十年前，人们编写三层应用程序— web 服务器、应用程序逻辑、数据库。只有 web 服务器和数据库相互通信。你可以为重试、超时编写非常复杂的逻辑——它特定于两跳，”摩根解释道。

当像脸书和 Twitter 这样的公司必须扩展它时，他们会将它作为库的一部分来编写，如 Finagle 或 Google 的 Stubby (Google 的内部远程 RPC，它形成了 gRPC 的基础)。服务网格本质上是它的延伸。

“我们是说它应该是一个单独的层；它应该是你和它一起运行的代理。它与应用程序本身完全分离。这在云原生世界中尤其重要，因为像 Docker 这样的东西，人们正在编写这些多语言应用程序，它们有数百种不同的语言、框架，开发人员可以挑选他们想要的。对于一个库来说，保持一致性变得非常困难。”

他说，最大的障碍是让公司接受增加另一个抽象层次背后的理由。在一篇博客文章中，他为 Linkerd 的[服务网格](https://blog.buoyant.io/2017/04/25/whats-a-service-mesh-and-why-do-i-need-one/)的概念提供了理由，所有的服务请求都通过这个服务网格发生。

在某些方面，服务网格类似于 TCP/IP。正如 TCP 栈抽象了在网络端点之间可靠地传递字节的机制一样，服务网格抽象了在服务之间可靠地传递请求的机制。像 TCP 一样，服务网格并不关心实际的负载或者它是如何编码的。他写道:“应用程序有一个高层次的目标(“从 A 向 B 发送一些东西”)，服务网格的工作，就像 TCP 的工作一样，就是完成这个目标，同时处理过程中的任何故障。”。

然而，服务网格进一步提供了以前不存在的可见性和控制级别，以帮助运营商了解问题所在。

它可以通过应用动态路由规则来处理复杂性，选择最有可能返回快速响应的实例，对另一个实例执行重试，如果不起作用，则使请求失败，而不是通过进一步重试来增加负载。

“大规模的分布式系统，不管它们是如何构建的，都有一个决定性的特征:它们为小的、局部的故障升级为系统范围的灾难性故障提供了许多机会。他写道:“服务网络的设计必须能够在底层系统接近极限时，通过减少负载和快速故障来防范这些升级。

但它还可以更进一步，执行协议升级，动态转移流量，在数据中心之间进行故障转移等等。

## 未来的工作

Linkerd 通常使用主机服务器上大约 100MB 的内存。摩根说，未来的目标是让 Linkerd 更小、更快、更轻。为此，它在 3 月底发布了 Linkerd-tcp，这是一个轻量级的 tcp 负载均衡器，适用于只需简单地代理 TCP 的场合。

目前， [Linkerd 只支持 HTTP(和 HTTPS)请求](https://lwn.net/Articles/719282/)，充当 web 代理。对更多协议和原始 TCP 的支持也在进行中。

一位观察者在[黑客新闻关于 Linkerd](https://news.ycombinator.com/item?id=14195956) 的讨论中写道:“很多人都不明白为什么这样做是必要的，在我看来，这实际上可以归结为一件事:有时你想与之交谈的东西会四处移动。”。

Morgan 说，展望未来，service mesh 将成为向无服务器架构发展的一部分。

“这仍然是一个模糊的空间，”他说。“云网格为迁移到无服务器方法铺平了道路——不仅与硬件外观完全分离，而且与单个长期运行的服务也完全分离。在无服务器的世界里，我们有这些功能，它们做一些事情，然后就消失了。Service mesh 使您能够管理功能之间的通信，就像管理服务器之间的通信一样。这在很大程度上是我们未来的工作。”

[云本地计算基金会](https://www.cncf.io/)是新堆栈的赞助商。

特征图片:[卡里斯·卡德吉斯](https://www.flickr.com/photos/ravh/)的[在等一个电话](https://www.flickr.com/photos/ravh/5099979093/in/photolist-8LEJ72-6gCsv7-qYsLp6-nSgEhz-adyei4-5vZHDc-4Kr7fZ-8s8Yrg-6aLBeX-3df3Gu-aYpvF6-9DfCen-8usxLq-5LSH4e-3df3PJ-9UiPL8-Af8wV4-C8vDp-dazDNF-5BK8Ck-5w54Fj-5w54gL-cQ4euh-eaQoZE-8qc54F-8j8VJA-bsdAnH-4byzHC-asW2pF-7tKmWB-v5MfJ-8CFyZv-3k1D6J-TM6NkH-8pWarp-kEoAU-FVJrXw-68FbEa-nVo37F-coAadh-pxSoGA-SMmLQM-hjHm4x-7KNfx7-4NxqZf-rzeDTR-fc8Q6q-B9mU8x-8BB4bY-qyreWM)，授权 **[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>