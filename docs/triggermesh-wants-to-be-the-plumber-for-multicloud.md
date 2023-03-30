# TriggerMesh 想成为 Multicloud 的水管工

> 原文：<https://thenewstack.io/triggermesh-wants-to-be-the-plumber-for-multicloud/>

[](https://twitter.com/ricmac)

 [理查德·麦克马努斯

理查德是《新书库》的高级编辑，每周撰写一篇关于云原生互联网未来发展的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) [](https://twitter.com/ricmac)

在云原生生态系统中，多云是一个经常被使用的术语。简而言之，这意味着在您的 it 环境中使用多个云平台。这通常也只是你的多管齐下的云服务方法的开始——有[成千上万](https://landscape.cncf.io/)基于云的产品为核心平台增加了额外的功能。 [TriggerMesh](https://triggermesh.com/) 就是其中之一，它将多云作为未来的关键市场驱动力。它的目标是将所有不同云平台(以及遗留 IT 系统)上的数据和服务连接在一起。

但是实际上，多重云有多普遍呢？根据一些分析师的说法，多云更多的是炒作而非现实。因此，我询问了 TriggerMesh 联合创始人兼首席产品官 Sebastien Goasguen 的看法。

“这又是定义不同的事情之一，”他回答道。“对我们来说，多云是指一个企业拥有不同的 SaaS 提供商和基础架构提供商，例如 Salesforce、OracleDB 和 AWS。但对其他人来说，多云关乎数据中心工作负载的可移植性。如果是后者，那么我同意多云并不流行——大多数用户选择一种云并使用它。但我们看到企业正在加速向云迁移，并使用更多的 SaaS 提供商。”

如果从 SaaS[软件即服务]的角度来看，Goasguen 认为多云是“一个集成问题”换句话说，需要一种方法来利用互联网的关键属性——网络——将分散的 SaaS 数据连接在一起。如果你使用的是通用平台，比如万维网，那么链接数据就很容易了——你只需使用 HTTP over TCP/IP。但是每个云平台都有自己定义数据的方式，以及如何使用数据；而且有时候和其他平台不兼容。

对于 Goasguen 和他的联合创始人 [Mark Hinkle](https://twitter.com/mrhinkle) 来说，解决方案是在云计算中采用[的无服务器范式](https://thenewstack.io/theres-a-service-for-that-amazon-web-services-and-serverless-computing/)——特别是定义了第一波无服务器浪潮(我们仍处于其中)的功能即服务(FaaS)模型。

## 事件驱动架构的兴起

无服务器是一种事件驱动的架构。例如，领先的 FaaS 平台 [AWS Lambda](https://aws.amazon.com/lambda/) ，将只运行代码(函数)来响应事件。TriggerMesh 连接不同平台的服务的方式是“编排事件以将这些服务缝合在一起。”

在今年早些时候的新堆栈播客中，Goasguen 甚至说“云原生架构的未来[…]将是事件驱动的。”

考虑到微服务是云原生应用的主流架构，这是一个很大的挑战。

“我们的想法是基于对可扩展性和使用独立服务的需求，”Goasguen 说，并补充说他不反对事件驱动的微服务。相反，这是一个选择最适合您需求的架构的问题。

“建立一个基于容器的微服务不会帮助我将云服务缝合在一起，”他继续说道。“但是，如果我可以监听来自 Salesforce 的事件，对它们做出反应并发出其他事件，那么我就可以构建一个自治系统，它的各个部分可以独立扩展，并利用同类最佳服务的安全性。”

## 如何使用触发器网格

Goasguen 提到 Salesforce 是因为它是其最新解决方案的客户，这是一个亚马逊 EventBridge 集成，[允许用户](https://triggermesh.com/2020/08/triggermesh-adds-integration-with-amazon-eventbridge/)“用 AWS EventBridge 连接几乎任何非 AWS 事件源。”他解释说，它的工作原理是，TriggerMesh 使用 EventBridge“作为一种轻松到达 SQS(亚马逊简单队列服务)的方式，并使用我们的合作伙伴资源代理任何事件——比如当你在 Salesforce 中添加客户时。”

TriggerMesh 的其他当前用例包括向多个目的地交付有效负载、日志聚合和过滤、用于分析的数据湖备份以及基础架构工作流自动化。

开发人员实现这种功能有多容易？毕竟，今天的云原生环境对开发者来说可能是一种令人眩晕的体验——这部分解释了低代码的兴起。所以我问 Goasguen 一个开发者如何使用 TriggerMesh 用户界面是视觉工具吗？或者是否需要大量编码？

“我们两者都提供:低级 API 清单和无代码可视化编辑器，”他回答道。“我们是 API 驱动的，我们所有的功能都可以通过 OpenAPI 规范访问，因此你可以通过 CLI[命令行界面]使用 TriggerMesh。因为我们使用 Kubernetes，所以 Kubernetes 客户端工作得很好。我们在上面构建的 UI 利用了这些 API，并提供了一些快捷方式来构建和编辑部署集成所需的一些对象。”

TriggerMesh 使用 Kubernetes 的 [Knative](https://knative.dev/) ，这是 Kubernetes 的开源无服务器框架。Goasguen 说，如果 TriggerMesh 客户想要使用“原始 API”，那么“他们需要了解如何管理 k8s 对象以及如何编写它们。”但同样，客户可以使用 TriggerMesh 可视化编辑器来避免处理 Kubernetes 带来的臭名昭著的复杂性。

## 无服务器的下一步在哪里

TriggerMesh 是第一批建立在 AWS Lambda 无服务器平台之上的创业公司之一。但正如我们在 Docker 看到的那样，推动范式转变的公司(Docker 案例中的容器)不一定会成为长期的主导平台。Kubernetes 作为编排容器的开源解决方案出现，并迅速篡夺了 Docker 在生态系统中的首要地位。人们想知道这种模式是否会在无服务器中重复。无服务器的开源平台会出现并把行业带到下一个水平吗？鉴于 AWS Lambda 的[功能相对有限](https://thenewstack.io/how-thundra-tackles-serverless-limitations-and-platform-power/)，这不是一个不合理的问题。

Goasguen 没有回答这个问题，但他指出，除了 AWS Lambda，无服务器生态系统还有更多的东西。

“Lambda 是一个提供功能托管的无服务器产品，是无服务器的典型代表。但是，任何隐藏了基础架构配置和扩展复杂性的云产品都是无服务器的。[AWS] Aurora 是无服务器的，从 Google 运行的 Cloud 是无服务器的，TriggerMesh 是无服务器的。”

正如我在上周关于 Cloudstate 的专栏文章中所讨论的，他也对作为下一代特性的有状态无服务器保持警惕。“让我们保持简单，让国家暂时置身事外，”Goasguen 的观点是。

最终，Goasguen 只想专注于为无服务器世界“建造管道”。他喜欢将雅虎管道比喻为 TriggerMesh。“这是一个伟大的应用程序生成器，它将第一批云服务组合在一起，”他在谈到雅虎现已倒闭的 Web 2.0 服务时说。简而言之，他希望 TriggerMesh 成为多云时代的水管工——一切都与管道有关。

[第 115 集:云端无服务器应用流](https://thenewstack.simplecast.com/episodes/episode-115-serverless-application-flows-in-the-cloud)

TriggerMesh 和 Amazon Web Services 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

*目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过推特[或脸书](https://twitter.com/thenewstack)[访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈:](https://www.facebook.com/thenewstack/)[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>