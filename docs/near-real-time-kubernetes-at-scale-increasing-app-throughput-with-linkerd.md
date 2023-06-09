# 接近实时的大规模 Kubernetes:通过 Linkerd 将应用吞吐量提高 10 倍

> 原文：<https://thenewstack.io/near-real-time-kubernetes-at-scale-increasing-app-throughput-with-linkerd/>

[](https://entaingroup.com/)

 [斯蒂芬·里尔登

一个人的乐队让演出持续进行，斯蒂芬·里尔登是恩泰贸易解决方案团队的 DevOps 工程师，使用 IaC 工具、混沌工程测试工具和端到端监控在云中操作数百个 Kubernetes 节点。他的主要职责是操作可靠性，保持平台的弹性和可用性，最重要的是对开发人员来说。](https://entaingroup.com/) [](https://entaingroup.com/)

Entain 是一家全球体育博彩运营商。您可能熟悉我们的品牌。立博、珊瑚、BetMGM、bwin、Sportingbet、Eurobet、partypoker、partycasino、Gala 和福克西宾果等名字都是恩泰恩家族的一部分。

当谈到体育博彩，说速度是必不可少的将是轻描淡写。当达拉斯牛仔队得分时，这些数据需要近实时处理，否则公司会赔钱。

为了应对这一挑战，澳大利亚恩泰的交易解决方案/ Feeds 团队在云原生技术上构建了一个尖端的交易平台，包括多个[云原生计算基础](https://cncf.io/?utm_content=inline-mention)项目，如 Kubernetes、gRPC 和 Linkerd。

在这篇文章中，我们将分享我们的旅程和经验教训。

一份外卖？尽管你听说服务网格非常复杂和困难，但这不是真的——尤其是当你使用 Linkerd 的时候。

## 恩泰的交易平台

 [史提芬格雷

作为澳大利亚恩泰恩交易解决方案团队的负责人，史提芬格雷管理着一个平台和团队，该平台和团队每年为数十亿项体育和比赛结果定价。Steve 在保险、健康、旅游、老虎机和赌博行业拥有丰富的经验，在设计解决方案、建立团队和敏捷转型方面拥有 20 年的经验。](https://entaingroup.com/) 

澳大利亚交易解决方案团队负责日夜处理进入企业价格管理系统的大量数据。尽快将这些数据提供给平台至关重要。

该交易平台基于 Kubernetes，由大约 300 个微服务组成，每个集群超过 3，000 个 pod，分布在多个地理区域。

为了创造收入，恩泰恩依靠基于结果概率的体育价格。随着用户对直播事件下注，平台每秒处理数千个请求，体验必须尽可能实时。任何中断不仅会影响用户体验，还会影响报价的准确性，并最终影响收入。即使是很小的延迟冲击也会产生巨大的影响。

## 性能、规模和可靠性方面的挑战

我们运行一个 24×7 的环境，并利用[Amazon Web Services](https://aws.amazon.com/?utm_content=inline-mention)spot 实例来保持低成本。为了确保平台和应用的弹性，我们还使用混沌工程工具和实践。我们的环境在不断变化，但尽管如此，我们的工作是确保可靠的应用性能。

虽然微服务和 gRPC 帮助我们实现了更高的效率和可靠性，但 Kubernetes 中的默认负载平衡影响了性能。有时，来自服务中的单个 pod 的请求最终会到达另一个服务的单个实例或多个实例。虽然这种方法有效，但对平台有负面影响。首先，我们需要非常大的服务器来容纳高流量。此外，我们无法使用水平扩展来处理我们预期的大量请求。这反过来影响了我们利用 spot 实例或及时处理大量请求的能力。

我们还苦于缺乏智能路由。为了实现我们的可用性目标，我们在一个地区(澳大利亚)的多个 AWS 可用性区域(AZ)中部署了独立的集群。这样就不会有人成为单点故障。虽然这对于较小的 Kubernetes 部署来说可能不是问题，但在 Entain 的规模和请求量下，跨 AZ 流量成为了延迟和成本的有形来源。不必要地跨越 AZ 边界的交易会降低平台性能，导致额外的 AWS 费用。

## 通过服务网络快速轻松地获得收益

为了解决这些问题，我们选择了 CNCF 开源服务网格 [Linkerd](https://linkerd.io/) 。

当我们将它推广到所有的 pod 时，Linkerd 的微代理接管了实例之间的路由请求。我们的平台能够立即将流量从发生故障的吊舱或正在旋转的吊舱中路由出去。

负载平衡的改进立竿见影。因为 Linkerd 具有 gRPC 感知的负载平衡，所以它立即修复了 Kubernetes 上的 gRPC 负载平衡问题，并开始在所有目的地 pods 之间适当地平衡请求。

借助 Linkerd，我们获得了两大业务收益:1)该平台可以处理 10 倍以上的请求量，2)我们能够使用水平扩展向服务添加更小的 pod。这使我们能够访问更广泛的 AWS spot 实例，并进一步降低我们的计算成本，同时提供更好的性能。

还有一个意想不到的附带好处。Kubernetes 的负载平衡天真地使用循环法来任意选择端点，基本上是在端点列表中循环，并在它们之间分配负载。这导致请求被路由到集群上的任何节点，而不考虑延迟、饱和或与调用服务的接近度。

另一方面，Linkerd 会查看所有潜在的端点，并根据延迟的[指数加权移动平均值(EWMA](https://linkerd.io/2016/03/16/beyond-round-robin-load-balancing-for-latency/))选择最佳目标。当我们将 Linkerd 添加到我们的集群中时，我们看到了更快的响应时间和更低的跨 AZ 流量成本。Linkerd 内置的 EWMA 路由算法可自动将更多流量保持在可用区域内，从而大幅降低带宽成本，每天可节省数千美元。我们没有任何配置！

这种差异是显著的——它在我们的监控中立即可见，并导致了全面的改进。我们的带宽使用峰值消失了，CPU 在整个平台上保持平稳。我们从一小部分服务器以其线速(20gbit/s)全速运行到一个平衡状态，没有服务器持续超过 9gb/s——Linkerd 带来了巨大的变化。

## 交钥匙服务网，简单的方法

选择服务网格时，您可以选择简单或困难的路线。引用[活跃的](https://buoyant.io/)团队，服务网背后的工程师的话，我们需要“所有的服务网，但没有服务混乱”

我们考虑过 Istio，但是经过一些研究，我们得出结论，我们需要一个团队来运行它，因为我们的平台很复杂。这太复杂了，需要持续的、积极的关注。是的，它有很多很棒的功能，但是我们并不需要全部。日常使用应用程序时，你没有时间去调整和微调它。

由于我们没有足够的带宽来学习和运行一个复杂的新工具，Linkerd 对简单性的承诺确实很有吸引力，并且是 Kubernetes 本地的，可以与我们当前的架构一起工作。不需要引入大量新的自定义资源定义或强制应用程序或环境重构。

我们花了五到六个小时来安装、配置和迁移 300 个服务到服务网格。这只是 go-get-command，然后是安装过程，工作就完成了！就这么简单，而且很管用。

## 我们都是快乐的露营者

一周之内，我们将 Linkerd 带入了大规模、高性能的 Kubernetes 集群。在单个 Kubernetes 命名空间中有 3，000 个 pod，我们进行了大规模部署。这可能很难相信，但只有一个 DevOps 工程师管理我们的整个基础设施，他是最快乐的露营者。

没有人必须成为服务网格或代理专家。Linkerd 只是坐在后台做它的工作。它解决了我们的 gRPC 负载平衡问题，并增强了标准 Kubernetes 结构，使我们无需重新配置我们的应用程序即可向前发展。我们将请求量上限提高了十倍以上，降低了运营成本，并达到了可用性目标。它不仅解决了我们试图解决的问题，甚至解决了我们没有意识到的问题。

每当一项服务或应用出现故障，澳大利亚娱乐停止下注，都会产生直接的财务影响。我们必须确保我们是可用的、可靠的、坚如磐石的，而 Linkerd 是我们实现这一目标的战略的一部分。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>