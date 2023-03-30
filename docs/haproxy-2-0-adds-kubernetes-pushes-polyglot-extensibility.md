# HAProxy 2.0 增加了 Kubernetes，推动了“多语言可扩展性”

> 原文：<https://thenewstack.io/haproxy-2-0-adds-kubernetes-pushes-polyglot-extensibility/>

早在 Kubernetes 在谷歌眼中闪闪发光之前，HAProxy 就已经存在，但现在随着[ha proxy 2.0](https://www.haproxy.com/blog/haproxy-2-0-and-beyond/)的推出，这个“世界上最快、使用最广泛的软件负载平衡器”已经跃进了云原生计算，它增加了一个 [Kubernetes 入口控制器](https://www.haproxy.com/blog/haproxy-2-0-and-beyond/#kubernetes-ingress-controller)，一个[数据平面 API](https://www.haproxy.com/blog/haproxy-2-0-and-beyond/#data-plane-api) ，以及更多努力使自己进一步融入现代基础设施的努力。

HAProxy 社区负责人兼 HAProxy Technologies 首席技术官 Willy Tarreau 在一份公司声明中表示:“HAProxy 2.0 以及新的 HAProxy 数据平面 API 和 HAProxy Kubernetes 入口控制器的发布标志着 HAProxy 重大架构重组的高潮，旨在增加优化现代应用架构支持所需的灵活性和功能。

HAProxy 的产品总监 Daniel Corbett 在接受新版本的采访时解释说，许多功能从早期版本就开始了，HAProxy 1.9 是 2.0 的“一点技术预览”，根据市场变化和社区反馈进行了发展。

“随着时间的推移，我们已经看到市场从基于硬件的负载平衡器向公司和用户探索基于软件的负载平衡器的转变。我们现在看到了向容器、Kubernetes 和微服务的巨大转变，”Corbett 说。“我们一直在观察这些趋势，并听取普通社区中的用户反馈，因此 HAProxy 2.0 专注于这些云和基于容器的环境。我们花了大量时间与我们的社区合作，以确保该产品能够支持云原生环境。”

HAProxy 2.0 最显著的特性包括[云原生线程和日志记录](https://www.haproxy.com/blog/haproxy-2-0-and-beyond/#cloud-native-threading-logging)、[第 7 层重试](https://www.haproxy.com/blog/haproxy-2-0-and-beyond/#layer-7-retries)、[完全 gRPC 支持](https://www.haproxy.com/blog/haproxy-2-0-and-beyond/#grpc)、[端到端 HTTP/2 支持](https://www.haproxy.com/blog/haproxy-2-0-and-beyond/#end-to-end-http-2)、原生支持[向 Prometheus](https://www.haproxy.com/blog/haproxy-2-0-and-beyond/#prometheus-exporter) 公开指标，以及 [Kubernetes 入口控制器](https://www.haproxy.com/blog/haproxy-2-0-and-beyond/#kubernetes-ingress-controller)，该控制器通过允许 Kubernetes 集群将流量路由到服务，为 Kubernetes 带来 HAProxy，并提供 TLS 卸载和支持除此之外，HAProxy 2.0 增加了一个[数据平面 API](https://www.haproxy.com/blog/haproxy-2-0-and-beyond/#data-plane-api) 和对[多语言可扩展性](https://www.haproxy.com/blog/haproxy-2-0-and-beyond/#polyglot-extensibility)的支持，这两者都有助于增加 HAProxy 的可扩展性。

根据该公司的声明，数据平面 API“代表了 HAProxy 在可扩展性方面的另一项重要进步，通过展示“一种用于动态配置 HAProxy 的现代 REST API，包括动态添加或删除前端、后端和服务器，创建 ACL 规则，插入 HTTP 路由指令，以及设置 IP 和端口绑定，在任何环境下提供真正的动态配置管理。”与此同时，Polyglot 可扩展性意味着添加新的流处理卸载引擎(SPOE)库和示例，这使得用 C 语言以外的语言(HAProxy 是用 C 语言编写的)扩展 HAProxy 变得更加容易，如 Golang、Python、Lua 和。网芯。

[HAProxy Technologies 的高级内容策略师 Nick Ramirez](https://www.linkedin.com/in/nick-ramirez-1b44624/) 解释说，ha proxy 进入云原生环境并努力增强可扩展性，这为基于软件的负载平衡器打开了一个充满机遇的新世界。

Ramirez 说:“传统上，人们熟悉在他们的网络边缘使用 HAProxy，这些新的架构正在将代理服务器转移到这些新的架构中，如 Kubernetes。“对我们来说，能够在那里见到他们，并为他们提供他们一直渴望的功能，如数据平面 API，真是令人激动。如果没有 HTTP restful API，要将代理集成到类似服务网格的东西中真的很难，所以现在我们有了它，它将打开各种各样的大门。”

Corbett 指出，服务网格对于 HAProxy 来说并不是新的领域，它实际上是 Airbnb 创建的早期服务网格 [SmartStack](https://medium.com/airbnb-engineering/smartstack-service-discovery-in-the-cloud-4b8a080de619) 的一部分。因此，这似乎是显而易见的下一步。

“HAProxy 有参与服务架构的历史。我们有兴趣进一步扩大我们在这些领域的支持，”Corbett 说。“HAProxy 存在于最初的服务网格中，我们将看看我们能做些什么来集成到今天的服务网格架构中。”

除了 HAProxy 2.0，开源负载平衡器背后的公司也宣布了其首届社区用户大会， [HAProxyConf 2019](http://haproxyconf.com) ，将于 2019 年 11 月 12 日和 13 日在荷兰阿姆斯特丹举行。

HAProxy 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>