# Knative 无服务器 Kubernetes 的开局并不顺利

> 原文：<https://thenewstack.io/knative-serverless-kubernetes-is-off-to-a-bumpy-start/>

我真的很喜欢 [Knative](https://knative.dev/) 。这是云计算对[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)、[λ](https://aws.amazon.com/lambda/)的回答。这是一个[开源](https://www.redhat.com/en/topics/open-source/what-is-open-source)社区项目，集成了[无服务器](https://thenewstack.io/category/serverless/)、云原生应用和 [Kubernetes](https://kubernetes.io/) 。这个游戏的名字是让开发人员能够专注于他们的代码，并消除供应和管理服务器的繁琐工作。但是我不太喜欢已经达到 1.0 水平的 Knative。

这只是一个版本号，但是当我今天看到 1.0 时，特别是在一个开源项目中，我期望一个已经有多年生产使用的程序。我期待成熟的代码像以往一样值得信赖。而 [Knative 1.0](https://knative.dev/blog/articles/knative-1.0/) 就不是这样了。

相反，当发布团队出来说，“Knative 是由许多一起版本化的组件组成的。这些组件具有不同的成熟度，从“实验性”到“已正式发布”(普遍可用)。我们仍然希望保持版本同步，因此决定将所有组件转移到版本 1.0。组件的 GA 水平是单独标记的。”

实验性的？在 1.0 版本中？真的吗？

为什么？他们解释说，“两个原因:一个面向用户，一个面向贡献者。面向用户的主要原因是，当用户了解他们已经安装了什么和什么一起工作时，它给了用户一个单一的数字。更小的、面向贡献者的原因是，我们所有的基础设施都是为管理单一版本号而设计的，考虑到第一点，更新它以支持多个版本号似乎不是一个很好的时间利用。”

真的吗？我对单一平台下的多个版本的程序没有任何问题。我的意思是，我们运行 Linux，不是吗？你困惑吗？我没有。

至于你的基础设施被设置为管理一个单一的版本号…好吧，我不会这样做，但无论如何。

展望未来，他们补充道，“除非我们等待与 Knative 相关的所有事情都完成，否则我们总会有一些组件或特性处于 alpha 或 beta 状态。虽然这有时发生在组件边界，但也可能发生在组件内部，因此版本号不能作为“是否正式发布”的唯一指标"

他们还补充说，该项目“将清楚各种组件或功能的成熟度，并沿着 GA 或 retirement 的路径移动功能。”你知道，在我看来，用很多词来描述你们大多数人用版本号来描述的东西没有任何问题。

这一切意味着什么？Knative 的核心组件，如发球和事件将[普遍可用(GA)](https://github.com/knative/community/blob/main/mechanics/MATURITY-LEVELS.md#stable) 。各种扩展组件，包括服务/事件功能、net-*插件、渠道/代理和源代码将处于 Alpha、Beta 或 GA 状态。要了解每个组件的情况，您需要查看它们的 README.md 或文档页面。

这听起来仍然让我困惑。Knative 总是有点令人困惑，这没有任何帮助。它从三个独立的部分开始:服务、事件和构建。Knative Build 被分拆出来，成为了 [Tekton 项目](https://tekton.dev/)。

今天 Knative 为您提供活动和服务。正如谷歌软件开发人员 [Ahmet Alp Balkan](https://www.linkedin.com/in/ahmetalpbalkan/) 所说，“[这造成了混乱](https://ahmet.im/blog/knative-positioning/)这可能会影响采用决定，因为这个项目实际上做了两件事；一个都没有。对于一个试图了解 Knative 更多的开发人员来说，问“我必须两个都用吗”、“我能分别安装它们吗”这样的问题是完全正常的，由于感觉到的复杂性，他们最终没有使用这个项目。

尽管如此，正如 Balkan 指出的，“它带来了大量的功能，如基于请求的自动伸缩、并发控制、肉屏蔽、具有流量分流能力的可重复部署(修订)、回滚、开箱即用的遥测、扩展到零等等，这些都是[开发人员真正关心的](https://twitter.com/simonw/status/1395502868199710721)。

抛开这些不谈，下面是 Knative 1.0 带来的好处。它将使您能够在无服务器应用程序中使用事件驱动的架构。具体来说，它:

*   提供快速、可扩展、安全、无状态的服务。
*   有一个专门的 API，为常见的应用程序用例提供了更高层次的抽象。
*   提供可插拔组件，使您能够使用自己的日志记录和监控、网络和服务网格程序。
*   理论上可以在任何可以运行 Kubernetes 的地方运行。
*   支持多个 HTTP 路由层。这包括 Istio、Contour、Kourier 和 Ambassador
*   为 HTTP/2、gRPC 和 WebSockets 提供支持。
*   支持 GitOps、DockerOps 和 ManualOps
*   支持许多常见的编程工具和框架，如 Django、Ruby on Rails、Spring 等。

展望未来，Knative 将会以极快的速度推出六周发布代码。用户会采用吗？它已经很受欢迎，而且潜力很大。

正如 Balkan 所观察到的，“Knative Serving 不仅仅是一个‘构建模块’，它更有用:我认为它是在 Kubernetes 上运行微服务所缺少的服务层(T1)。”而且，“如果你在 Kubernetes 上做的只是运行服务，你可以只使用 Knative 服务 API，在 Kubernetes 上几乎不用接触任何其他东西。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>