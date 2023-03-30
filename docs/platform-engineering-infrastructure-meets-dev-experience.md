# 平台工程:基础设施满足开发体验

> 原文：<https://thenewstack.io/platform-engineering/platform-engineering-infrastructure-meets-dev-experience/>

"[平台工程](https://blog.getambassador.io/is-platform-engineering-the-new-devops-or-sre-472ed97a1885)"是一个你最近可能听说过的概念，尤其是如果你在云原生软件领域工作。这仅仅是炒作，还是越来越多的讨论背后有什么实质性的东西？这种向以[开发者为中心的平台](https://thenewstack.io/from-kubernetes-to-paas-to-developer-control-planes/)发展的趋势从何而来？

 [丹尼尔·布赖恩特

丹尼尔是大使实验室(前身为 Datawire)的开发者关系总监。Daniel 是 Java 冠军和 TechBeacon DevOps 100 影响者。他参与了几个开源项目。](https://www.linkedin.com/in/danielbryantuk/) 

在听到关于平台工程及其在塑造和支持[开发者体验](https://thenewstack.io/how-the-developer-experience-is-changing-with-cloud-native/)中的作用的传言后，我开始将我所做的工作与我在更广泛的云原生社区中看到的讨论联系起来。

在减少开发人员认知负荷和复杂性的“铺路”的支持下，开发人员对其代码的所有权发生了转变。在对该领域进行更深入的探索后，我收集了一系列资源和见解，解决了几个关键问题:什么是平台工程，它的目标是什么，以及为什么云原生组织正在集中其开发人员的体验？

这条推文迅速传播开来，并继续得到关注，主要是因为这个话题似乎触及了人们的神经。云原生工程组织正在快速发展，吸纳新的开发人员并构建越来越复杂的软件。每个人都在寻找解决复杂性和认知负荷问题的切实可行的方法，如果不加以控制，这些问题会减缓进展并造成不必要的麻烦。围绕构建开发者平台来应对这些挑战的共识正在形成。例如，2021 年 Humanitec 对 1，850 个工程组织的调查表明[大多数已经在构建或计划构建他们自己的内部开发平台](https://humanitec.com/blog/top-10-fallacies-in-platform-engineering)。

## 什么是平台工程，为什么重要？

[https://www.youtube.com/embed/WCyiUWIB1wU](https://www.youtube.com/embed/WCyiUWIB1wU)

视频

[平台工程](https://youtu.be/qtSS_uCBSas?t=190)的想法是创建一个平台([一切似乎都在某种平台上运行](https://twitter.com/thecodecleaner/status/1149631511164940290))，或者一个控制平面，为开发人员提供一个[集中的、自助式的“铺设路径”来快速安全地交付和运行应用](https://www.infoq.com/news/2017/06/paved-paas-netflix/)。

我对这个主题的想法是由网飞在创建自己的内部开发平台和支持其开发团队的工具链方面的开创性工作引发的。我当然不是唯一一个看到网飞创造“[全周期开发人员](https://netflixtechblog.com/full-cycle-developers-at-netflix-a08c31f83249)”的方法的人这意味着网飞的开发人员开始负责他们软件的端到端生命周期:编码、测试、运输和运行他们自己的应用程序。

“您构建它，您运行它”的运动在某种程度上已经被云原生工程组织作为目标模型引用，并引发了不同类型的开发人员平台或控制平面的蓬勃发展的生态系统。这些主要是围绕开发人员工作的组织的需求和目标而设计的。

没有“放之四海而皆准”的道路。世界上的[谷歌可能希望他们的开发人员专注于他们的核心工作，编码](https://www.getambassador.io/developer-control-plane/dcp-insights-cheryl-hung/)，而不用考虑相应软件的运输和运行。在这种情况下，考虑或负责基础设施与其说是增值活动，不如说是分散注意力。其他云本地组织可能会组建一个平台工程团队，并要求他们与[一个致力于增强开发团队能力的站点可靠性工程团队合作。](https://www.getambassador.io/developer-control-plane/dcp-insights-mario-loria-from-cartax/)

这里发生了三件关键的事情，即使内部开发者平台的实现有无数的变化。

*   **筒仓正在被打破**:随着向集中控制平面的推进，[平台工程、站点可靠性工程(SRE)和开发者体验/支持(DX)](https://blog.getambassador.io/the-rise-of-cloud-native-engineering-organizations-1a244581bda5) 团队，被共同的使命(如[谷歌 SRE 的书](https://sre.google/sre-book/eliminating-toil/)中所概述的)团结在一起，比以往任何时候都更频繁地相互交流和合作。
*   **铺平道路的平台工程构建理解**:不管最终结果如何——比如开发人员对整个软件生命周期的责任——组织正在走向规范化，并要求开发人员理解整个生命周期。即使开发人员从未被要求发布软件，培养开发人员对 sre 和 DevOps 角色的同理心以及对基础设施的理解似乎更为常见。
*   **每个人都在构建平台，但这并不意味着很容易**:大多数开发者平台旨在降低复杂性，并让开发者[自助访问](https://www.getambassador.io/developer-control-plane/dcp-insights-cheryl-hung/)他们工作所需的一切。但是对于每个组织来说，铺平这条道路的平衡是不同的，特别是当一个组织考虑不同类型的开发人员时——99%的开发人员构建了大多数真实世界的应用程序，并且依赖于遗留软件，而不是直言不讳的少数人/开发人员影响者。一个服务于两者的平台应该是什么样子的？

## 新德沃普斯和 SRE，还是组织文化的关键？

公司创建的平台取决于许多因素，其中许多因素与内部开发人员没有什么关系。顶层考虑通常侧重于现有的组织文化、关键业务目标和公司的云成熟度。许多公司围绕业务目标设计了他们的[平台，并投资开发该平台，因为他们期望获得一定的投资回报](https://www.getambassador.io/developer-control-plane/dcp-insights-nicki-watt/)，例如开发人员的生产力或实现成本节约。团队的组成及其角色如下。

这些商业和文化元素可以驱动，或者至少对最终的平台产生巨大的影响，团队看起来像什么，开发人员需要承担多少自由和责任。

“一些组织的成立是为了让开发者能够承担他们想要的一切；其他的是孤立的，更喜欢“包含”开发人员。技术咨询公司 OpenCredo 的首席执行官/首席技术官 Nicki Watt 表示:“无论开发人员拥有拥有整个软件生命周期的完全自由，还是受到组织或平台限制的更多约束，开发人员都有权承担越来越多的责任，这有助于开发更好的软件和更好的团队。

另一个例子是 [Alan Barr，退伍军人联合家庭贷款](https://www.getambassador.io/developer-control-plane/developer-control-planes-a-platform-builders-point-of-view/)的内部开发人员和安全平台产品负责人，他在保守的金融服务领域获得了一个集中开发人员控制平台的内部买入。他通过[围绕释放开发人员效率](https://www.getambassador.io/developer-control-plane/dcp-insights-alan-barr/)构建商业案例，关注客户需求、控制成本、自动化流程、确保安全性，以及将开发人员和服务人员从消防职责中解放出来，从而解决了开发人员平台的需求。

给予开发人员更多责任和自助服务平台的动力是否消除了开发人员或 SRE 的责任？不。相反，平台工程是这些功能的发展，而不是替代。

[来自 Zipcar](https://www.getambassador.io/developer-control-plane/developer-control-planes-a-platform-engineers-point-of-view/) 的 DevOps 平台工程师 Bo Daley 讲述了他在开发人员支持方面的经验。他说，它从更传统的 DevOps 方法转向建立一个集中式平台，为开发人员提供一条从本地编码到更有效地交付生产的铺平道路。

[CartaX 的 Mario Loria 呼应了 Daley 的观点](https://www.getambassador.io/developer-control-plane/dcp-insights-mario-loria-from-cartax/)，“sre 在引导开发人员通过学习曲线走向全面的自助服务和服务所有权方面发挥着关键作用。但是，作为一名 SRE，不应该由我来定义您的应用程序如何部署，或者在什么时候需要回滚，或者在什么时候需要更改，或者何时应该修改其健康检查。开发者应该有能力——也有权力——做出这些决定。”

我在云原生领域交谈过的大多数领导者都同意，尽管平台本身可能因组织而异，并且 DevOps 和 SRE 转变所扮演的支持角色也不同，但平台本身有助于开发人员实现组织的期望。然而，这个平台不仅是一个基本的“铺路”，也是一个出发点。该平台是一个中央自助服务中心，可以提供标准的体验，并作为探索铺设路径以外的跳板，只要开发人员也对结果负责。

## 平台如何支持开发者体验？

我认为[平台工程师的角色](https://blog.getambassador.io/the-rise-of-cloud-native-engineering-organizations-1a244581bda5)是检查从源代码到产品的整个软件开发生命周期，并建立一个工作流程，使应用程序开发人员能够快速编码和发布软件。虽然这基本上是正确的，但很明显有许多方法可以实现这一点。理解各种真实的开发者体验对于构建合适的平台至关重要。正如[开发人员体验并不比这些平台现在旨在简化的微服务](https://www.getambassador.io/developer-control-plane/developer-control-planes-a-ctos-point-of-view/)架构更加单一一样，这些平台本身只会支持开发人员体验，直到它们在现实世界中被采用和使用。

一个组织可以尝试做好每一件事:关注业务案例，获得内部支持和预算，全心全意地相信平台工程是提高效率的途径。但是尽管如此，[如果一个组织没有考虑到使用平台的开发人员的需求和输入，他们注定会失败](https://www.reddit.com/r/devops/comments/stuep4/weve_spent_months_building_this_platform_devs/)。开发人员不太可能采用不包含他们的反馈和首选工作流的平台。

平台可以通过寻求开发者的视角并围绕这一视角构建最终的平台来支持开发者体验。正如软件是为最终用户构建的一样，平台客户(开发人员)需要相信工具是为他们构建的，并考虑到了他们的挑战。也就是[用共情](https://www.getambassador.io/developer-control-plane/dcp-insights-kelsey-hightower/)打造。

## 构建开发人员平台的最佳实践

创建有效的开发者平台需要的不仅仅是满足开发者需求的技术框架。这不仅仅是改变开发人员、开发人员和软件工程师的角色。这不仅仅是理解业务目标，尽管这也是一个关键因素。相反，支撑成功的平台工程努力的最佳实践集中于文化和心理因素。

*   **倾听你的听众(开发者)的意见，并切实地进行开发**。如果您正在为您的开发人员构建一个平台来减少辛劳、提高生产率并减轻认知负荷，那么首先要关注 99%的现实世界中的开发人员，他们负责组织所依赖的许多关键应用程序的稳定性。
*   **人性化，鼓励同理心**:凯尔西·海托华广泛地谈到了[对最终用户的同理心](https://www.getambassador.io/developer-control-plane/developer-control-planes-a-cloud-leaders-point-of-view/)，并将其提升为软件开发过程的一部分。您组织中的开发人员，或者说，开发人员体验，需要对在您组织的软件上工作的人感同身受。
*   **利用平台让开发人员尽最大努力**:Alan Barr 延续了 Hightower 的移情工程概念，他还强调了 Twilio 的“好客”重点作为创建一个以开发人员为中心的平台的例子。消除阻碍开发人员最佳工作的挑战。
*   **建立双向理解**:组织和开发人员之间的默契是他们努力相互理解。如果组织提供良好的开发者体验，开发者同意将[机械同情](https://www.getambassador.io/developer-control-plane/dcp-insights-nicki-watt/)带到他们的工作中，并愿意[对他们的代码](https://www.getambassador.io/developer-control-plane/dcp-insights-kelsey-hightower/)及其潜在的下游影响负责。

记住这四点，值得重申的是，大多数平台都是由开发团队的需求驱动，自下而上地被成功采用的。高管们在高尔夫球场上购买平台并强制要求在办公室使用的日子已经一去不复返了。今天，开发者是平台领域的国王和王后。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>