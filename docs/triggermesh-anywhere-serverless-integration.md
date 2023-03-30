# TriggerMesh:无服务器集成

> 原文：<https://thenewstack.io/triggermesh-anywhere-serverless-integration/>

最近的 [Cloud Foundry 调查](https://thenewstack.io/why-serverless-is-being-adopted-at-a-faster-rate-than-expected/)报告称，无服务器技术作为最新的热门事物，有大量的[炒作，然而它的增长速度与 2016 年容器评估和采用的速度相当。](/cutting-through-the-hype-when-serverless-works-and-when-it-doesnt/)

联合市场研究公司刚刚发布的[报告](https://www.openpr.com/news/1903172/21-99-billion-industry-expected-by-2026-for-serverless)估计，到 2025 年，全球无服务器技术市场将达到 219.9 亿美元。

位于北卡罗来纳州卡里的初创公司 TriggerMesh 专注于无服务器功能和云原生基础架构的集成层，使组织能够构建跨多个云和数据中心环境的企业级应用。

实际上，它使所有基础设施能够与无服务器功能共享它们的事件数据，并且无服务器功能和基础设施能够将它们的事件数据共享回事件总线。

“把它想象成类似于[扎皮尔](https://zapier.com/)或[If This Then than](https://ifttt.com/)。我们监听和过滤事件流，然后利用这些构建器来触发功能，”联合创始人马克·辛克尔说。

他把它比作雅虎。Pipes ，由曾经的搜索引擎巨头提供的一项服务，允许用户在一个更大的工作流程中将不同的任务捆绑在一起。

“这可能是一个很好的例子，过滤所有的数据，得到你想要的，这样你就可以触发你的功能，”他说。“所有这些事件总线都会收集大量数据，但将这些数据整理到一个地方，作为云原生事件堆栈的一部分，这在今天并不存在。”

### 集成层

Hinkle 和 TriggerMesh 的联合创始人 Sebastien Goasguen 在 Citrix 相遇，他们在那里开发 Apache CloudStack。Goasguen 继续在他创建的名为[skip box](https://www.linkedin.com/company/skippbox/about/)的公司创建了无服务器框架 [Kubeless](https://kubeless.io/) ，这是 Knative 的前身，该公司被 Bitnami(现在是 VMware 的一部分)收购，但 Bitnami 没有选择将 Kubeless 扩展到他想要的程度。

与此同时，Hinkle 成为 Linux 基金会的营销副总裁，后来成为 Node.js 基金会的执行董事。

他们在 2018 年创立了 TriggerMesh。

“我们想追求无服务器的工具和基础设施，我们认为这将与行业的发展方向相吻合，”Hinkle 说。

他们早期的大部分工作都集中在[Knative](/knative-enables-portable-serverless-platforms-on-kubernetes-for-any-cloud/)——trigger mesh Knative Lambda 源，以提供从 AWS 到启用 Knative 的集群上的功能的跨云触发器，以及 [TriggerMesh Knative Lambda 运行时](https://github.com/triggermesh/knative-lambda-runtime)——但该公司现在专注于为无服务器功能和云原生基础设施提供集成层。

GitLab 是该公司的第一个客户，TriggerMesh 为其构建了定制的无服务器发布平台。

“我们希望为我们的用户提供一种简单的方法，将 Kubernetes-native 无服务器工作负载部署到他们的 Kubernetes 集群中，而不必成为(当时)新生的 Knative 项目的专家，”他说

[Daniel Gruesso](https://www.linkedin.com/in/danielgruesso/)

，产品经理，配置，在 GitLab。

“TriggerMesh 团队对无服务器架构有着深入的了解，并且是少数几个在 Knative 方面有经验的团队之一。除了他们的知识和经验之外，他们还有很好的专业素养，并分享我们的开源基因。

“The tools and knowledge provided by TriggerMesh allowed us to quickly ship off our first iteration of [GitLab Serverless](https://about.gitlab.com/product/serverless/). We’ve had very positive responses from both the open-source community as well as Knative project maintainers. We had a very positive experience working with the team and are very happy to see them grow.”

据 Hinkle 称，GitLab 是一个一次性项目，该公司仍在建设其基础技术，约有 100 名早期采用者对该产品提供反馈。它正致力于在三月下旬在 KubeCon Europe 推出一款预览产品。

大多数早期采用者仍然致力于无服务器策略。Hinkle 说，他们使用 TriggerMesh 来发布应用程序，然后他们会考虑如何使用事件源来触发整个企业的事情，并与他们的做法更加一致。他们也在考虑对有状态应用程序使用无服务器，而不是最初的无状态设计。

该公司最近筹集了 300 万美元的种子资金，由 Crane Venture Partners 和 Index Ventures 牵头。

Crane Venture Partners 的联合创始人兼合伙人斯科特·塞奇(Scott Sage)说:“有大量互不相连的应用程序无法充分受益于云计算和增强的网络连接。

“大多数公司都有云应用和内部应用的某种组合，随着越来越多的应用(通常来自不同的供应商)，集成的需求从未像现在这样大。我们认为 TriggerMesh 的解决方案是满足这一需求的理想选择，这使他们成为一项引人注目的投资。”

Redmonk 分析师 [James Governor](https://redmonk.com/team/james-governor/) 在[的博客文章](https://redmonk.com/jgovernor/2020/01/24/triggermesh-serverless-integration-meets-message-oriented-middleware/)中写道，消息总线肯定会成为无服务器世界的一部分，在 AWS Lambda 之外将会有一个触发器和事件的世界。

“随着我们越来越多地进入一个混合、多云和多 SaaS 的世界，我们将需要把基于容器的功能和 IBM 长期以来通过 MQSeries 支持的遗留事件源的新世界结合在一起，”他说。

他说，TriggerMesh 很好地映射到了 [CloudEvents](https://github.com/cloudevents/spec) 规范，也映射到了谷歌计划通过收购 AppSheet 来定义的世界。

“TriggerMesh 正在为无服务器时代构建面向消息的中间件，同时使用内部和云应用程序的企业(本质上意味着所有企业)可能会发现这种方法引起了共鸣，”他说。

“看看 TriggerMesh 能否构建出一种编程模型，让企业能够利用他们已经在 MQ 等平台上完成的面向服务的架构工作，这将是一件有趣的事情。如果服务得到了很好的描述和管理，它们就可以被云服务访问。一些低级代码概念很好地映射了这一点。”

### 传统应用也是如此

TriggerMesh 提供了一个声明性的 API 和工具来定义构成现代应用程序的事件流和函数。

[https://www.youtube.com/embed/sffGr_uwxYM?start=21&feature=oembed](https://www.youtube.com/embed/sffGr_uwxYM?start=21&feature=oembed)

视频

到目前为止，它已经发布了 EveryBridge，这是一款类似于[亚马逊的 EventBridge](https://aws.amazon.com/eventbridge/) 的活动巴士。EveryBridge 从 VMware Vsphere、IBM MQ、Solace 甚至自定义应用程序等事件源中获取实时数据，并使用这些事件来触发 Kubernetes 上托管的各种公共云和无服务器产品的功能。

“作为一个行业，人们已经开始使用无服务器的全新应用程序，并取得了非常非常好的成功。尤其是在 JavaScript Node 社区，这些人已经为优步、Twitter 和网飞等公司编写了应用程序(并对其进行了扩展)，”辛克尔说。

“现在传统企业会说，‘你知道，我们不是绿地。我们有这些占用大量计算的应用程序。他们不是节点应用程序，他们是 Java 应用程序，他们是 Python 应用程序，他们是其他运行时。”

“他们有这些传统应用程序，不完全适合亚马逊、谷歌或微软的云，所以我们提供集成工具，让他们能够利用触发这些应用程序的优势，如果他们选择迁移到无服务器模式的话。”

该公司最接近的竞争对手是像 [Mulesoft](https://www.mulesoft.com/) 这样的第一代集成商，“尽管他们过去主要做的是集成数据和做更多的 ETL，”Hinkle 说，而 TriggerMesh 正在更多地与 Zapier 这样的公司合作，在应用程序之间创建交互。他说，像戴尔[Boomi](http://boomi.com/)和[jitter bit](https://www.jitterbit.com/)这样的公司适合这个领域，尽管这些公司不是为云原生而建立的，但现在正在努力成为云原生。

该公司刚刚在 [GitHub](https://github.com/triggermesh) 上发布了三个额外的 Knative 事件源——IBM MQ、VMware vSphere 和 Azure Event hub Channel controller 以及一个 TriggerMesh Openshift 操作器。

展望未来，该公司计划添加更多的事件源，并致力于创建一个更简单的界面，以便用户可以快速添加事件源。

Linux 基金会、Cloud Foundry 和 OpenShift 是新堆栈的赞助商。

图片由来自 Pixabay 的 ktphotography 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>