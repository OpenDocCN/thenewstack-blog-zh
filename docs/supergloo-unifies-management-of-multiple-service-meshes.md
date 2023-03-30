# SuperGloo 统一了多个服务网格的管理

> 原文：<https://thenewstack.io/supergloo-unifies-management-of-multiple-service-meshes/>

随着公司试验服务网格或者公司内不同的团队采用不同的网格，管理多个版本的挑战成为现实。根据 [Solo.io](https://www.solo.io/) 的创始人兼首席执行官[艾迪特·莱文](https://github.com/ilevine)的说法，或者会。

这家总部位于马萨诸塞州剑桥的公司最初以混合应用程序网关 [Gloo](https://github.com/solo-io/gloo) 而闻名，并提出了莱文所谓的“多网状”管理，称为 [SuperGloo](https://github.com/solo-io/supergloo) 。像 Gloo 一样，它使用函数作为一系列网格技术的公分母，包括 [Linkerd](https://thenewstack.io/linkerd-reaches-1-0-provides-communications-service-mesh-cloud-native-ops/) 、 [Istio](https://thenewstack.io/is-istio-the-most-next-gen-next-gen-firewall-ever/) 、 [AWS App Mesh](https://thenewstack.io/aws-app-mesh-amazons-own-service-mesh-for-microservices/) 、[hashi corp consult](https://thenewstack.io/hashicorp-extends-consul-to-support-other-service-meshes/)等等。

“也许他们正在使用 Istio on-prem，但在 AWS 上，他们需要使用 App Mesh……也许在 Google 上你使用 Istio，但在 prem 上你使用 Consul。或者你有不同的组选择不同的网格。有一种趋势是，你应该在 Kubernetes 中安装一个大型集群，使其成为多租户，并安装许多小型集群，而不是安装一个大型网格。这让我相信将会有不止一个网格，它们将会无处不在，”莱文说。"对于组织来说，操作这一切可能是一个问题."

ESG 的高级分析师 Edwin Yuen 称之为即将到来的挑战，尽管他认为 Solo 已经做好了迎接挑战的准备。

“有很大的兴趣。面对如此多的选择，这几乎就像是一种压力，”他说。

“这不仅仅是管理多个网格，而是抽象层，以便您可以混合这些部分。…我们还没有看到比网格更高的管理水平。”

## 开源项目

“服务网格成为了云本地计算架构的重要组成部分，并带来了许多竞争对手。Solo.io 已经看到了这个市场是如何形成的，并创建了 SuperGloo 来提供一个抽象层，允许开发人员进一步构建云原生堆栈，而无需受正在使用的服务网格风格的限制。这是一个聪明的定位，有利于云计算原生计算社区，也为 Solo.io 的 SuperGloo 插件创建了一个平台，”Ovum 分析师迈克尔·阿佐夫说。

像 Solo 的其他项目一样，如基于[特使](https://thenewstack.io/the-envoy-proxy-finds-a-home-at-the-cncf-amazon-web-services/)代理的 [Gloo](https://thenewstack.io/meet-gloo-the-function-gateway-that-unifies-legacy-apis-microservices-and-serverless/) ，以及用于微服务和 Kubernetes 的调试器 [Squash](https://github.com/solo-io/squash) ，SuperGloo 是开源的。该公司的计划是将其构建的功能商业化——它最近发布了其 gateway [GlooE](https://www.solo.io/glooe) 的企业版。

Solo 的解决方案是在一个组织内使用的不同网格之间建立一个[平面网络](https://medium.com/solo-io/the-multi-mesh-vision-and-how-supergloo-will-bring-it-to-life-a89891d8815c)，将它们作为一个组来管理和监控。它使安装和配置变得简单，并集中控制第三方工具和插件。

单个 API 控制加密、遥测和跟踪等功能，并统一日志记录和跟踪。SuperGloo 会自动配置现有的 Prometheus、Grafana 和 Jaeger 安装，以便从网格中提取数据，并且无需编辑 YAML 文件和 Kubernetes 配置图。

它与入口控制器集成，用于组合管理北/南和东/西流量，并允许用户将任何服务网格与 SuperGloo 处理安装和配置的任何入口配对。

客户希望采用服务网格。他们认为这项技术非常可靠，但他们不知道采用哪一种，所以他们正在尝试不同的技术，莱文说。

“今天一切都很复杂。她说:“如果你想在 Istio 上运行的服务中重试一次，你必须创建四个不同的服务，然后创建重试。

“一旦你安装了 Supergloo，一切都是一个开关。你想要可观察性吗？还是你不想要可观察性？你想要证书吗？还是你不想要证书？…开箱即用，非常简单明了；用户不应该做任何事情。”

Levine 说，该公司正在构建一套名为 Dr. Gloo 的工具，并将很快开放源代码。第一个，GlooShot，是 mesh 上面的混沌工程。它将在不改变应用程序的情况下为应用程序提供弹性，并将与多种编程语言一起工作。

“这一切都将基于这样一个理念，即我们需要关注运行在这些网格之上的应用程序的健康状况，”她说。

在 [KubeCon + CloudNativeCon 北美 2018](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2018/) 的[新堆栈制造商](/kubecon-pancake-podcast-the-state-of-service-meshes-and-istio/)小组讨论期间，服务网格的状态是主要话题。

VMware 负责网络和安全的副总裁兼首席技术官[Pere monc lus](https://www.linkedin.com/in/pere-monclus-a73218)告诉该小组，服务网格形成了为微服务提供身份并了解它们之间的交互的基础，并有助于为它们附加策略、安全和其他控制。

## '安全毯'

Yuen 预见多网格管理将成为一个类似于多云管理的问题。

“对于那些希望从现有的单片应用程序中进行迁移工作的人，当然，还有那些试图在微服务和无服务器之间做些什么的人——只是将所有这些功能整合在一起，可能只是取代应用程序的一部分，我认为这将非常有趣，”他说。

“对于许多尚未采用微服务或无服务器或尚未开始迁移的公司来说，这实际上是一种尝试。当他们出去雇佣一些团体，这些团体将会成为某些网格的拥护者，我认为这也是 SuperGloo 聚集的地方。

“[它]回答了企业关于他们的应用方向的许多问题。这几乎就像一个技术安全毯。他们可以完成他们想完成的事情。但对于那些稍微保守一点或害怕开枪的人来说，他们可以用非常分阶段的方式来做。”

KubeCon + CloudNativeCon 和 VMware 是新堆栈的赞助商。

特征图片: [Swtiruty Rgbytw](https://www.flickr.com/photos/stanislav_roudavski/) 的《CT_Mesh 13》。根据 CC BY-SA 2.0 获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>