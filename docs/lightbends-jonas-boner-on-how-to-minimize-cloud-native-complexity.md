# Lightbend 的 Jonas Bonér 讲述如何最大限度地降低云的原生复杂性

> 原文：<https://thenewstack.io/lightbends-jonas-boner-on-how-to-minimize-cloud-native-complexity/>

[Lightbend](https://www.lightbend.com/) 赞助了这篇文章。

 [克林·芬利

Klint Finley 是一名专业作家和分析师，专门研究企业计算和开发人员技术。他在《连线》杂志担任了近八年的特约撰稿人，报道了人工智能、云计算和数据科学等主题。他的作品也出现在读写网、TechCrunch 和 BoingBoing 上。Klint 位于俄勒冈州波特兰市。](https://www.linkedin.com/in/klintron/) 

从本质上讲，实现云原生是为了管理复杂性。

“十年前，分布式系统主要是学术界和谷歌、脸书和亚马逊等少数大公司的领域，” [Akka](https://akka.io/) 框架创建者和 Lightbend 首席技术官 [Jonas Bonér](http://jonasboner.com/) 说。“现在，向多核系统、云基础设施、大数据平台和微服务的转移正迫使开发人员进入分布式世界，不管他们喜欢与否。”

这意味着开发人员必须考虑他们在编写运行在单个节点上的单个内核上的单片应用程序时从未考虑过的问题；比如当网络问题阻止组件相互通信时该怎么办，或者如何处理节点故障。

组织才刚刚开始真正解决这个问题。Lightbend 最近对 1，000 多名开发人员和 IT 决策者进行的调查发现，大多数受访者认为利用 Kubernetes 和 containers (34.5%)或转向云基础设施提供商(23.8%)是实现云原生的最重要方面。换句话说，大多数人更多地考虑云基础设施，而不是编写在该基础设施上运行良好的应用程序。

但正如谷歌开发者倡导者 Kelsey Hightower 所说:“在基础设施层尝试‘现代化’应用程序有大量的努力，但在应用层没有同等的投资，想想框架和应用服务器，我们只解决了一半的问题。”

> 这个想法是，云提供商将管理深层的复杂性，让开发人员专注于业务逻辑。你也可以不把它看作抽象，而是固执己见。

简而言之，问题的另一半是管理应用程序级的复杂性。“处理复杂性的标准方法是将其隐藏在一个有漏洞的抽象背后，”Bonér 说。"例如，隐藏你正在通过网络与远程服务对话的事实."

尽管这种模式可能很诱人，但它也有很大的缺点。Bonér 说:“当事情分崩离析时，当节点来来去去或网络出现故障时，所有困难的问题都摆在你面前，你没有办法管理它们，因为它们隐藏在 API 后面。”

具有讽刺意味的是，解决方案实际上可能更抽象，但却是正确的抽象类型。Bonér 表示，企业开发人员将需要越来越多地依赖云和无服务器服务——不仅仅是像 Amazon Lambda 这样的无状态功能即服务平台，还包括提供有状态服务、管理分布式状态、存储和通信的平台，以最大限度地降低他们面临的复杂性。

这个想法是，云提供商将管理深层的复杂性，让开发人员专注于业务逻辑。你也可以不把它看作抽象，而是固执己见。云提供商仍然面临着分布式系统固有的复杂性。但是他们做出了大部分的技术决定。

“这是一种解放，”Bonér 说。“出错的地方越来越少，需要做出的决定也越来越少。您不需要担心使用正确的库或正确的协议，因为所有这些都由后端为您管理。”

企业对这一未来愿景仍存在矛盾。Lightbend 调查发现，52.6%的受访者表示，他们预计将转向不断增加的自动化，而 47.4%的人表示，开发人员仍然需要专注于维护底层系统。与此同时，58.1%的受访者表示，他们更喜欢能够自行配置和扩展的框架，而不是以服务形式交付或通过 API 使用的框架——尽管 66.2%的经理更喜欢转向 API 或以服务形式。

当然，其中总会有取舍。使用无服务器，您可以用对底层系统的一些控制来换取更低的复杂性、更少的系统维护责任和更快的上市时间。但是你必须牺牲的控制力是不同的。“当涉及到这些权衡时，提供商必须提供正确的旋钮，”Bonér 说。找到正确的平衡是 Lightbend 试图通过其 [Akka 无服务器](https://www.lightbend.com/akka-serverless)服务及其开源 [Cloudstate](https://cloudstate.io/) 平台实现的一个重要部分。

“我认为开发者将学会享受这个新世界，在这里他们可以放下很多这些东西，”Bonér 说。“他们不必总是随叫随到，将能够专注于应用程序的本质，专注于提供商业价值的东西。”

*下载您的* [*云原生采用趋势 2020-2021*](https://info.lightbend.com/Cloud-Native-Adoption-Trends-Report.html) *以探索开发人员和 IT 领导之间关于云原生迁移的最高优先级的持续紧张关系。*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>