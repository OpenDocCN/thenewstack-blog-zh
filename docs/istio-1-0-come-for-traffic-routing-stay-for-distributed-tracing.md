# Istio 1.0:为流量路由而来，为分布式跟踪而留

> 原文：<https://thenewstack.io/istio-1-0-come-for-traffic-routing-stay-for-distributed-tracing/>

开源服务网格项目经理[Brian“Red beard”Harrington](https://www.linkedin.com/in/brianredbeard/)指出，虽然第一次使用 Istio 服务网格最初可能会因为它消除了流量路由中的头痛问题，但他们后来可能会对发现该软件的分布式跟踪功能感到高兴。

哈灵顿在接受《新堆栈》采访时说，Istio 正在“努力解决人们在意识到自己有问题之前会遇到的一些问题”。“人们一直非常关注流量控制方面，但我一直非常兴奋的一件事是实现了 [OpenTracing](http://opentracing.io/) 组件。当人们意识到他们需要了解他们的应用程序时，我认为这将是非常非常有益的。”

本周，谷歌[发布了 Istio](https://istio.io/blog/2018/announcing-1.0/) 的首个“生产就绪”版本。Harrington 说，虽然 Red Hat 正在等待更长的时间，以支持其他开源软件的同样方式开始商业提供开源技术，但开源巨头看好服务网格的效用。

Istio 为管理服务提供了一个控制平面，允许它们找到彼此(“发现”)，并通过 API 强制实施流量管理的安全和策略规则。哈林顿说，Istio 是“一个实际的基础设施层，而不是你可以在实际应用程序代码中调整的东西”。“如果您是 Go 开发人员或节点开发人员，组件会自动生成。您不必编写额外的功能。”

借助先进的流量管理，Istio 和 Kubernetes 可以为管理跨多个云甚至内部的一组资源创造条件。它提供故障注入、重试逻辑和断路。流量可以根据特定的最终客户端路由到不同版本的应用程序，或者从一个版本的应用程序缓慢地向另一个版本传输流量，或者检测协议级错误并相应地重新路由。

交通路线不仅可以帮助组织更好地利用他们的资源，还可以加快开发过程。

使用微服务架构，几乎不可能在生产环境本身之外测试特定的服务。Red Hat 在 [Red Hat](https://www.redhat.com/) 的云开发首席架构师 Christian Posta 在[最近的一次播客采访](https://thenewstack.io/red-hats-chief-architect-of-cloud-development-talks-traffic-management/)中解释道，快节奏的 DevOps 实践的兴起导致了代码错误的增加。

由于能够轻松快速地将流量重新路由到特定的服务器，Istio 这样的服务网格可以提供一种在生产中测试代码的方法，通过使用 [canary rollouts](https://thenewstack.io/deployment-strategies/) ，它提供了一种在生产环境中测试复杂应用程序的方法，而无需一次性将其推广到所有用户。

而且，正如 Harrington 指出的，该软件还收集日志、跟踪和遥测数据，并添加安全性和策略，消除了在代码本身中嵌入客户端库来执行这些任务的需要。该软件可用于记录跨服务的流量:捕捉每秒请求数、错误率和延迟。它可以提供一个依赖图来显示服务是如何相互影响的。

这些特性已经被可观察性工具和策略引擎的供应商注意到了。[网络安全管理软件产品](https://www.solarwinds.com/)和 [Datadog](https://www.datadoghq.com/) 正在为他们的监控软件编写 Istio 适配器，来自 [Weaveworks](https://www.weave.works/) 和 [CodeFresh](https://codefresh.io/) 的部署工具也在适配软件。

## 准备好生产了吗？

哈林顿说，虽然谷歌已经宣布 Istio 1.0 版本已经可以生产，但红帽公司仍在等待更多测试完成后再向客户提供。

“最终，围绕 Istio 的社区称这个项目为‘1.0’我很高兴他们达到了这个里程碑，但社区开源项目的 1.0 可能不完全符合企业客户对‘1.0’的看法，”哈灵顿说。

超过 200 名开发人员贡献了超过 4000 个新功能的签到。IBM、VMware、Cisco 和 Red Hat 都对该项目做出了重大贡献。谷歌去年与 IBM 和 Lyft 合作启动了这个项目，现在提供托管 Istio 服务。

尽管如此，Red Hat 计划在制定 Istio 的商业产品之前进行更多轮的测试和性能表征。“我对上游社区非常有信心，能够与他们合作进一步完善软件，”哈灵顿说。该公司正在为技术预览版准备这款软件，并已经在部分客户中进行了测试。

据谷歌称，迄今为止，至少有 12 家公司已经在生产中使用 Istio，包括易贝、笛卡尔实验室、惠普 FitStation，即 PubNub 和 Trulia。 [Auto Trader UK](https://www.autotrader.co.uk/) 使用该软件采用了基于 Kubernetes 的以容器为中心的公共云架构。

[红帽云开发首席架构师谈流量管理](https://thenewstack.simplecast.com/episodes/red-hats-chief-architect-of-cloud-development-talks-traffic-management)

谷歌和红帽是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>