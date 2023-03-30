# 驯服云:集中开发者体验

> 原文：<https://thenewstack.io/taming-the-cloud-centralizing-the-developer-experience/>

这是由三部分组成的系列文章的第二部分。这是第一部分。

 [丹尼尔·布赖恩特

丹尼尔是大使实验室(前身为 Datawire)的开发者关系总监。Daniel 是一名 Java 拥护者，是 TechBeacon DevOps 100 的影响者，并为几个开源项目做出了贡献。](https://www.linkedin.com/in/danielbryantuk/) 

我们认为，云原生软件开发已经永远改变了[开发者的体验](https://thenewstack.io/how-the-developer-experience-is-changing-with-cloud-native/)。

正如这个由三部分组成的系列文章中的第一篇[所探讨的，没有单一的开发者体验，尤其是在云原生环境中。云原生工具有很多，即使各种平台都围绕 Kubernetes 作为一种构建标准，平台差异也是不可避免的，因为业务目标通常会驱动开发人员平台的设计方式。在许多情况下，随着云原生平台的集中化，开发人员的体验也是如此。](https://thenewstack.io/the-cloud-native-paved-path-developer-experience/)

本文是一个由三部分组成的系列文章的第二部分，该系列文章的特色是从与云原生思想领袖的讨论中获得的见解。它深入探讨了云原生技术在不同组织中的独特发展道路，并研究了每个组织如何为自己的开发人员和组织找到合适的平衡点。它还讨论了如何通过固执己见但灵活的开发人员平台来集中开发人员体验，从而支持云原生生态系统中的业务目标。

## 驯服云原生生态系统:真实世界中的 Kubernetes

在现实世界中使用 Kubernetes 已经帮助许多组织“驯服”了不断蔓延的云原生生态系统，以满足他们的业务目标和开发人员的需求。Kubernetes 被广泛视为通用框架或默认编排系统，正如我们在许多访谈中所回应的那样，它提供了构建标准和相关抽象的通用工具。Zipcar 的 DevOps 平台工程师 Bo Daley 解释说:“我们大多数人都不做通用的工作，所以我们可以[使用 Kubernetes 作为框架](https://www.getambassador.io/developer-control-plane/developer-control-planes-a-platform-engineers-point-of-view/)，并构建我们的抽象，与我们自己的业务问题相关。”Kubernetes 提供了一个稳定但灵活的构建基础。

同时，“[铺平道路](https://thenewstack.io/the-cloud-native-paved-path-developer-experience/)”不应该等同于将开发人员束缚在严格的约束中，或者在他们喜欢的工具中没有选择。在 Kubernetes 的基础上构建并选择一个推荐的“中间地带”或一组最佳实践可以转化为开发人员的效率，但不会将任何人局限于特定的工具。我们采访的受访者都赞同这种方法，其中最著名的是前 CNCF 的 Cheryl Hung:[使用 Kubernetes 来构建和推广一个标准平台，这个平台足够模块化，可以实现开发者自治](https://www.getambassador.io/developer-control-plane/developer-control-planes-a-developers-point-of-view/)。

## 给开发者一个控制平面

尽管 Kubernetes garners 大张旗鼓，但正如 Kelsey Hightower 所指出的，“T4”仍然是最后一英里的技术单靠 Kubernetes 无法解决开发者面临的挑战。Kubernetes 提供了急需的基础设施和更好的 API。毕竟，正如苹果公司的谢丽尔·洪(Cheryl Hung)在大使实验室的播客中分享的那样，“[基础设施很难](https://www.getambassador.io/developer-control-plane/dcp-insights-cheryl-hung/)”但是开发人员需要一个控制平面，让他们信任过程的每一步。也就是说，开发人员编码、打包代码，并检查他们是否有正确的依赖关系来运行代码……但是如何部署代码呢？

关于开发人员在部署方面需要了解或做多少事情，有很多讨论，但我们采访的大多数专家都强调，在现实世界的实现中，开发人员只需要能够相信，如果他们提供代码和配置，平台将按照指定运行应用程序。从本质上讲，集中式开发人员平台应该为开发人员提供一种简单的方式来表达他们对基础架构的期望，正如 Hightower 所解释的，相信它能够“保持状态，聚合状态，并随着时间的推移保持状态的真实性”。 [Kubernetes 恰好是我们所认为的通用控件](https://www.getambassador.io/developer-control-plane/dcp-insights-kelsey-hightower/)。

在实践中，Kubernetes 已经被证明是现实世界部署的坚实基础。Zipcar 的 Daley 说得很好，“我们专注于开发人员的体验，并让开发人员了解他们的工作如何与系统中的其他组件交互。我们希望为生产铺平一条无缝的道路。”这是集中式开发人员控制平面从概念跳到现实的地方。

## 实现业务目标:围绕 Kubernetes 聚合

在商业环境中，开发人员平台和整体开发人员体验是由最能支持业务成果的东西驱动的。正如前 CNCF 生态系统倡导者凯蒂·加曼吉(Katie Gamanji)在复述她在 2018 年在康泰纳仕实施集中式开发者平台的经历时所解释的那样，“考虑到非常明确的业务目标和时间表，[集中化平台](https://www.getambassador.io/developer-control-plane/dcp-insights-katie-gamanji/)及其开发推动了采用已经被证明是行业内某种标准的工具的需求，如 Kubernetes。对于相当简单的媒体平台的业务关键型生产实施，需要广泛接受的标准。”

## 总结:创造有用的、可用的开发者体验

引入开发人员控制平面对支持和实现业务目标大有帮助。正如咨询公司 OpenCredo 的首席技术官/首席执行官 Nicki Watt 解释的那样，“人们的期望是，某个[价值将来自一个组织正在投资的平台](https://www.getambassador.io/developer-control-plane/dcp-insights-nicki-watt/)。它的构建方式应该由最终目标来驱动。如果是为了限制自由和实现成本节约，平台将以一种方式构建，但如果目标是创新，它将以完全不同的方式构建和实现。”

理想情况下，平台的设计和构建既要考虑组织的需求，也要考虑开发人员的体验。如果一个组织能够培养更好的开发人员体验，它将获得效率收益。同时，通过精心制作的控制平面、标准和合理的工作流，组织通过提供坚实的基础作为跳板来支持和尊重他们的开发人员。

正如退伍军人联合家庭贷款公司的内部开发人员和安全平台产品负责人 Alan Barr 所分享的那样，“有了正确的抽象，开发人员的认知负荷和‘辛劳’自然会减轻。希望[开发者体验是有用的。其中一部分是对工具和平台本身保持谨慎，永远不要在内部工具上走捷径。”另一部分是记住，开发人员是为人类创建应用程序的人，这需要机械的同情和“面向好客”的关注，确保开发人员感到他们面前的道路没有路障，并且开发人员控制平面是他们感到受鼓舞而采用和使用的东西，以实现业务和个人目标。](https://www.getambassador.io/developer-control-plane/developer-control-planes-a-platform-builders-point-of-view/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>