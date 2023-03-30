# “Cloud Native”和“Kubernetes”到底是什么意思？

> 原文：<https://thenewstack.io/what-do-cloud-native-and-kubernetes-even-mean/>

底特律——这不是一个反问句。随着系统和团队变得越来越分散，技术行业有一个真正的守门语言问题。这太复杂了，一个人无法理解。当然，[开源首先是禁止性的英文](https://thenewstack.io/inclusion-at-scale-in-the-mozilla-and-kubernetes-open-source-communities/)。除此之外， [云原生景观](https://landscape.cncf.io/) 宽达数千种产品——而这只是几种景观中的一种！

谢天谢地，今年的 [KubeCon + CloudNativeCon 北美](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)做了一些稍微不同的事情。它仍然有许多最新、最闪亮的技术，以及针对精英 DevOps 组织的大量讨论。但日程表上也排满了 101 首曲目，并欢迎许多特殊兴趣小组(SIG)。它还就如何支持这些高度分散的、通常是自愿的社区给出了许多建议。

建立在开源基础上的科技行业，正在考虑其对各个层次的人们理解云原生和通常在它背后的协调的迫切需求。这些不是大学计算机科学课程中教授的概念。此外，虽然 Kubernetes 的使用率稳步上升，但贡献池却停滞不前。那么，还有什么地方比 cloud native 最大的节目更适合开始学习呢？今天，我们回顾今年的一些见解，了解云原生和 Kubernetes 对我们行业的未来意味着什么。

## 定义原生云

我们的 [定义云原生](https://twitter.com/jkriggins/status/1526549574839681026?s=20&t=BBdTtdWxOhN-CR7VlOwK5g) 之旅始于 5 月的 KubeCon Europe，当时新的 Stack 在巴伦西亚现场调查了云原生影响者，简单地问了一个问题:你如何定义云原生？如果你谈论的是云原生技术，正如 DataStax 的[克里斯多佛·布拉德福德](https://twitter.com/bradfordcp)和[马特·奥弗斯特里特](https://twitter.com/omnifroodle)分别描述的那样，这都是关于可组合的、统一的和分布式的部分。DataDog 的[杰森·李](https://twitter.com/gitbisect)补充说，云原生是分布式和可扩展的。这个技术定义，就像 HarnessIO 的 Uma Mukkara 所说的那样，经常与不可变的、声明性的和短暂的微服务和容器联系在一起——云原生让你扩展得如此之快，以至于任何代码块都不应该被视为宝贵或脆弱的。

云原生是关于允许组织访问速度和可靠性的技术选择。Fiberplane 的 Elena Boroda 说:“Cloud native 描述了部署速度更快的应用程序，因为不需要部署硬件或软件。

[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)的 [Julie Gunderson](https://twitter.com/Julie_Gund) 将 cloud native 定位为“云上的开发和工程”，试图阻止团队专注于“原生”部分，因为很少有企业是在云中孵化的。Syntasso 的 Paula Kennedy 回应了这一观点，强调云原生不是构建在云中，而是以一种允许公司最大限度地利用云的方式来构建，这使得“应用程序是可扩展的、有弹性的，不必担心自己运行硬件。”SUSE 的 Divya Mohan 补充说，这应该能够安全可靠地在所有云提供商之间实现。

归根结底，不容易定义的原生云不仅仅与技术有关，也同样与人员和流程有关。云原生技术是由组织采用云原生思维驱动的，正如 CloudNativePG 的 [Gabriele Bartolini](https://twitter.com/_GBartolini_) 所说，这需要一种 [DevOps](https://thenewstack.io/category/devops/) 文化。

“大多数人说云原生是容器、微服务[和]动态编排，这是事实，但它还不止这些，”容器解决方案公司的[皮尼·雷兹尼克](https://twitter.com/pini42)提醒道。“还有组织变革、敏捷流程、协作文化和正确的预算。所有这些使得公司能够更快地向客户交付价值，并交付更好的产品。如果这些事情中的任何一个不一致，那么该技术将不会真正将你从失败中拯救出来。”

这种思维方式通常被称为“设计云优先”，正如 VMware 的 Dawn Foster 所说。不是走 [提升和转移路线](https://thenewstack.io/app-modernization-why-lift-and-shift-isnt-good-enough/) ，而是一个组织[开发一个云本地策略](https://thenewstack.io/how-to-build-a-roadmap-to-app-modernization/)，该策略决定谁、何时、做什么以及为什么要对哪些架构部分进行优先级划分或不划分。

最后，Aqua Security 的[Anas Urlichs](https://twitter.com/urlichsanais)提醒我们，基于 Kubernetes 等开源软件的云原生也是跨云原生社区合作的机会，因为没有一个产品会统治所有产品。大多数公司可能会依赖几十个来组成他们的新堆栈，这意味着[云原生生态系统](https://thenewstack.io/category/cloud-native/)必须是可持续的。

在上周的 KubeCon North America 上，[云原生计算基金会](https://cncf.io/?utm_content=inline-mention)执行董事 [Priyanka Sharma](https://www.linkedin.com/in/pritianka/) 甚至将开源社区中的人称为“云原生者”，这让混淆和包容更加严重

归根结底，云原生的挑战(或者说好处)在于采用者的眼光。这就是为什么思科的 Michael Chenetz 开始与客户接触时会问他们:云原生对你来说意味着什么？在开始谈论之前，你需要明确你在谈论什么。

## 云本地术语表源于定义 Kubernetes 的需求

正如我们从 [西蒙·沃德利](https://thenewstack.io/simon-wardley-on-mapping-our-way-to-a-common-language/) 中学到的，我们需要寻找共同的语言，以便朝着同一个方向前进。然而，定义原生云的工作通常是在首席技术官的办公室里进行的。

[Catherine Paganini](https://twitter.com/CathPaga) 

“我们的技术团队会尝试向我解释，但他们总是假设比我多得多的背景。可用的内容是高度技术性的，也没有多大帮助，”她告诉新的堆栈。“所以我买了一本计算机科学入门书，开始学习基础知识，然后是分布式系统教科书。这时候事情开始有意义了。这是非技术人员在谈到云原生时所缺少的所有背景，没有这个基础你就无法理解，”她继续说道。

不可否认，新的堆栈在这种云原生混乱中扮演了一定的角色。这个网站上第一次提到 Kubernetes 可以追溯到 2014 年，但帕格尼尼的 2019 年[Kubernetes](https://thenewstack.io/primer-how-kubernetes-came-to-be-what-it-is-and-why-you-should-care/)简介，概括了她的自学，是这个网站第一次专注于为非技术观众定义 Kubernetes 和云计算。

三年后，帕格尼尼开始了新的旅程，来定义什么是云原生。云原生计算基金会推出了 [云原生词汇表](https://glossary.cncf.io/) 。她解释说，作为词汇表的维护者，该项目旨在满足三个社区需求:

1.  **来自可信、厂商中立、社区驱动的来源的定义。“当你谷歌一种云的原生术语时，你很可能会得到一个供应商提供的定义，”她解释道，这通常带有产品偏见。而那些在谷歌上的排名往往不是最新的。**
2.  **非技术人员也能看懂的内容。**云原生转换不是免费的——它们通常需要数千万美元。领导团队必须了解什么是云原生，以便构建和传达自上而下的战略。帕格尼尼说:“但云原生内容大多是为技术受众编写的，让没有技术背景的人很难理解。”销售和营销也留下了定义的碎屑。
3.  **好云多语种原生内容。**英语一直是开源贡献的障碍。“大多数云原生内容都是英文的，但接触到的绝大多数人都是非英语母语者，”她说。"理解这些复杂的概念已经够难了，更不用说用外语了."

该项目的目标是正面满足这些需求，创建通用语言，“无论他们是云原生人员还是经验丰富的工程师，”帕格尼尼继续说道，“用它来了解云原生人员或教育他人。”

云原生术语表仅在一年前发布，但已经被翻译成:

*   英语
*   **韩语**
***   **西班牙语*****   **意大利*****   **葡萄牙语*****   **普通话*****   **孟加拉语*****   **印地语**************

 ******这个术语表项目现在需要什么？这是一个活生生的开源项目，所以需要 [更多的开源贡献者](https://glossary.cncf.io/contribute/) 和翻译者，当然！

## 通过大规模学习促进 Kubernetes 的成长

Kubernetes 不一定是 cloud native 的同义词，但它肯定是 CNCF 最大的开源项目，在全球范围内吸引了 560 万开发人员使用它。仅去年一年就有 170 万新用户加入。但是一个开源社区依赖的不仅仅是用户，它需要贡献者。随着越来越多的技术栈依赖于 Kubernetes orchestration，Kubernetes 项目——以及整个云原生社区——现在取决于引入更多的人，无论是技术人员还是非技术人员。提供大规模培训至关重要。

“一般来说，云原生技术，特别是 Kubernetes，可能不是对初学者最友好的话题，” [Le Tran](https://www.linkedin.com/in/leutran/) ，Veeam 的 [KastenIO 的一名技术人员上周在 KubeCon NA 阶段轻描淡写地说。](https://www.kasten.io?utm_content=inline-mention)

“我们作为一个社区，继续伸出援助之手，继续通过开放的学习工具和平台搭建通往我们世界的桥梁，这一点很重要，”她在演讲中继续强调，需要更多方式来自主进入云原生世界。

大约一年前，来自底特律汽车行业的 Tran 自己跨过了那座桥，进入了 Kubernetes 世界。“在那个时候——哇！—我对 Kubernetes 一无所知。我对集装箱技术一无所知。我对网络传输一无所知。我甚至不知道 GoLang，”她承认道，并指出了理解 cloud native 的几个障碍。"所以我真的进入了一个我不知道自己不知道的世界."

因此，Tran 做了任何新手都会做的事情，她开始在谷歌上搜索自学的方法。她把自己描述为“现在可以操作了”，并且能够引导自己进入新的主题，最近潜入了识别和授权的重要世界。但这花了一年时间，她说，她还有很多东西要学。

Tran 说，像许多不熟悉云世界的人一样，她发现学习资源的广度令人窒息。“一方面，当你加入一个新的社区时，手头上有这么多的材料是不可思议的。另一方面，当你像我一样是新手，看着这些大量的资料时，你常常会想，我该从哪里开始呢？”这场斗争延伸到整个开源社区，包括找出从哪里开始贡献[](https://thenewstack.io/how-to-find-a-mentor-and-get-started-in-open-source/)。

Tran 非常依赖免费的、以初学者为中心的资源。她大声喊出了她认为特别吸引人、高质量和有趣的 Kubernetes 学习材料:

如果 Kubernetes 社区——以及云原生和开源社区作为一个整体——要继续发展，就必须在支持文档、入门指南、演示等方面进行投资。

“我们可以一起继续在我们的世界中搭建桥梁，帮助像我一样踏上学习之旅的人们，”Tran 结束了她的主题演讲。

***你呢？你最初是如何了解到什么是云原生的，什么是 Kubernetes 的？有什么资源推荐？让我们在推特上了解一下**[**@ JKRiggins**](https://twitter.com/jkriggins)**和**[**@ TheNewStack**](https://twitter.com/thenewstack)**。***

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>******