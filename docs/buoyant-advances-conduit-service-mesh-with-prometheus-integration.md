# Prometheus Integration 推动了管道服务网的发展

> 原文：<https://thenewstack.io/buoyant-advances-conduit-service-mesh-with-prometheus-integration/>

作为开源项目 Linkerd 和 Conduit 服务网格项目的幕后支持者，浮力公司本周在 T2 的 kube con+CloudNativeCon Europe T3 上展示了它的发展势头。

CNCF 云计算基金会的[孵化项目【Linkerd 为云原生应用提供了一个](https://www.cncf.io/projects/)[独立的通信层](https://thenewstack.io/linkerd-reaches-1-0-provides-communications-service-mesh-cloud-native-ops/)。它处理诸如服务发现、负载平衡、故障处理、工具和服务路由等方面，将通信层与应用程序代码完全分离。

Conduit 是浮力公司专门为 Kubernetes 设计的新服务网格[，在去年 12 月的 KubeCon 上推出，其中](https://thenewstack.io/conduit-lightweight-service-mesh-kubernetes/)[服务网格](https://thenewstack.io/kubecon-2017-pancake-podcast-service-mesh/)是一个热门话题。

在本周哥本哈根的活动中，Linkerd 的生产用户将进行大约七场演讲，其中包括支付处理器平台架构师 Edward Wilde。 [Israel Sotomayor](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2018/program/schedule/) ，电子商务 API 供应商 [Moltin 的基础设施工程师；](https://moltin.com/)和 [Oliver Beattie，](https://kccnceu18.sched.com/speaker/oliver52)网上银行工程主管 [Monzo](https://monzo.com/) 。在线音乐平台 [SoundCloud](https://soundcloud.com/) 、软件供应商 [BigCommerce](https://www.bigcommerce.com/) 、社交媒体监测公司 [Brandwatch](https://www.brandwatch.com/) 和其他公司的代表将在 [Linkerd 深潜会议](http://sched.co/Dz03)期间进行闪电对话。

“在过去的几个月里，我们已经看到对这两个项目的兴趣激增，Conduit 有点吊起了 Linkerd 社区的胃口，”乐观的首席执行官 T2·威廉·摩根·T3 说。

“在林克尔德这边，雪球正从山上滚下来，并且速度越来越快，”他说。诸如 [Salesforce](https://www.salesforce.com/) 、 [Expedia](https://www.expedia.com/) 、 [Planet Labs](https://www.planet.com/) 和 [WePay](https://go.wepay.com/) 等公司为最新版本贡献了代码。

“一些勇敢的人”也在生产中使用管道，他说，但还不准备谈论它。

“渠道不再是前前阿尔法。我们现在正式进入阿尔法了。这不再只是一个实验，”他说。

去年 12 月，他将 Conduit 描述为“所以 alpha，它只支持 [HTTP/2](https://http2.github.io/) ”最新版本 [Conduit 0.4.1](https://github.com/runconduit/conduit/releases) ，现在也支持 HTTP/1.x、gRPC 和所有 TCP 通信。

“Linkerd 功能非常强大，但要真正使用所有配置选项还需要一段时间。我们想把这个想法发挥到极致:如果你什么都不用做呢？如果您只需要安装它会怎么样？”摩根说。

新版本在普罗米修斯号的顶部有一个从地面开始建造的遥测管道。它提供顶级服务控制面板，无需任何配置。

“我们的重点不仅是让你更容易理解你在 Kubernetes 上运行的服务，而且是在出现问题时挖掘和调试它们。我们在 Conduit 生态系统中有一系列工具，允许您在每个服务的基础上检查顶线指标，服务之间的请求路径以及请求本身，而无需您对代码进行任何修改，或者对您在 Kubernetes 上的运行方式进行任何实质性修改。因此，应用程序使用什么协议，用什么语言编写，都无关紧要。如果它在 Kubernetes 上运行，它可以给你所有这些权力。”

其中一个工具是流量切片和切块的能力，不仅仅是通过这个服务发生了什么，而是通过这个服务如何被其他服务调用。那么反过来，这个服务是如何调用其他服务的呢？这不是总体成功率，而是每个呼叫者或被呼叫者的成功率。他说，在微服务中，这往往是潜在问题行为的隐藏指标。

如果一个服务有 75%的成功率，它会告诉你出了问题，但不会告诉你是哪里出了问题，也不会告诉你是服务本身的问题还是它调用的七个问题之一。因此，通过能够按依赖者或被依赖者分解延迟、请求量和成功率，您可以开始跟踪调用链，而不必像分布式跟踪那样做任何事情，分布式跟踪通常涉及代码修改。

另一个工具将允许您检查请求:“显示从服务 A 到服务 b 实时发生的所有请求。”"给我看看延迟在这个范围内的."您可以使用这些构建块来构建您需要的调试和检查工具包。

0.04.1 版本还包括针对每个 Kubernetes 部署的预配置 [Grafana](https://grafana.com/) 仪表盘，以及增强的亚毫秒 p99 延迟。

浮力正在为这两个项目提供商业支持。

“我们的目标不是围绕技术，而是如何通过微服务，采用云原生世界，让人们获得成功，”摩根说。“如果没有周围的环境，没有理解技术、知道如何操作技术并围绕技术建立可用性生态系统的人，技术本身就毫无意义。”

[浮力](https://buoyant.io/)和[云本地计算基金会](https://www.cncf.io/)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>