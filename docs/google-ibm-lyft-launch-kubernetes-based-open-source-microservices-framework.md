# 谷歌、IBM、Lyft 推出基于 Kubernetes 的开源微服务框架

> 原文：<https://thenewstack.io/google-ibm-lyft-launch-kubernetes-based-open-source-microservices-framework/>

[谷歌](https://google.com)、 [IBM](http://ibm.com) 和 [Lyft](http://www.lyft.com) 公开披露了一个历时六个月的开源项目，他们一直致力于构建一个基于 [Kubernetes](https://kubernetes.io/) 的微服务框架，该框架可以添加负载平衡、加密、基于策略的治理和向现有服务报告，而无需任何代码更改。该项目名为 Istio，于去年 11 月启动。

在 Kubernetes 实例上安装 Istio 会导致在每个服务的入口和出口点使用代理的服务网格。这个代理是 Lyft 的[特使](https://github.com/lyft/envoy)，加上 IBM 和[谷歌](https://groups.google.com/forum/#!forum/istio-dev)的一些改进，它允许遗留和现有服务轻松集成到典型的集群服务中，如安全、治理和监控。

谷歌的产品经理 Varun Talwar 领导 Istio 和 gRPC，这在 Istio 中是受支持的，但不是必需的。“我们认为 Istio 是一个服务网，”塔尔瓦说。“作为服务和网络之间的基础设施层，你可以将其注入到现有服务、传统服务和云服务中，并获得所有这些功能，”Talwar 说。

这些功能包括诸如报告、监控、治理以及经常出现问题的服务到服务的认证和安全性等企业圣杯。“运营商获得了一个策略驱动的控制平台，他们可以说，‘我希望这个策略适用于我的所有服务，或者针对这些特定的服务’，两者几乎都可以独立运行，”Talwar 说。

Istio 项目本身包含许多子工具，但是 Talwar 将其分解为三个关键部分。第一部分是 Istio proxy，本质上是 Envoy，Lyft 去年年底开源的一个项目。通过在每个服务的入口和出口点部署 Envoy，可以捕获流量和数据。

塔尔瓦说，这导致了 Istio 的第二大部分。“在 Kubernetes-land，我们用魔法自动注射。然后是 [Istio 混音器](https://github.com/istio/mixer):控制平面。对于每个请求，特使可以进行访问控制检查。我应该限制等级吗？“它在白名单上吗，”混血儿可以对基于政策的事情说是或不是，”塔尔瓦说。

Mixer 和 Envoy 还可以联合使用日志记录和监控来处理所有这些服务。Talwar 说，Mixer 旨在将这些信息发送到多个日志记录系统。此外，他说这个 alpha 标志着 Istio 团队已经将该系统带到了 Kubernetes 上的工作状态，并打算在未来的版本中将其移植到其他云平台。

也许这个新的微服务框架最有趣的部分，也是最后一个主要部分，是它在服务之间提供[认证](https://github.com/istio/auth)和安全性的能力。Talwar 说，这个问题经常被讨论，客户一直在努力寻找更好的解决方案来解决这个难题，即处理数以千计的安全密钥，这些密钥就像它们所附着的容器一样短暂。

“人们不通过很多方式来提供安全服务，或者通过这些库来提供服务。我们有制造和分发证书的[证书颁发机构]。塔尔瓦说，你可以在服务之间进行强认证，以后你就可以说，‘只有这个服务可以和那个服务对话’。

Istio 的当前版本将安全密钥存储在 Kubernetes Secrets 中。Talwar 说“仅仅是强服务认证的概念本身就是一个巨大的胜利。您可以部署 Istio 并说，“我主要想要的是安全部分”，而不是针对其他部分的策略，并启用一些服务而不启用其他服务。这种方式很灵活。”

目前，Istio 的版本是 0.1.3，尽管 0.1.4 即将发布，周一将出现一些测试问题，以[推迟这个新版本](https://groups.google.com/forum/#!topic/istio-dev/tCWrr7nw-oo)。

Talwar 希望开发人员知道，Istio 旨在使他们的生活更轻松，同时通过其策略管理功能减轻运营和管理员的痛苦。“我们正在开发一个开放的微服务框架，它与语言无关。所有的好处都是一致的，拥有这样一致的约束是非常好的。如果你不想改变任何代码并获得很多好处，那么像这样的统一基础在使开发人员生活更容易方面做了很多，”Talwar 说。

特征图像[通过](https://unsplash.com/?photo=6lWqkLIh5L8) Unsplash。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>