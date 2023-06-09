# 红帽 OpenShift 第 1 部分:从齿轮到码头

> 原文：<https://thenewstack.io/red-hat-openshift-part-1-from-gears-to-docker/>

在我们关于 Red Hat OpenShift 的两个故事的第一部分中，Scott Fulton 介绍了平台即服务的架构。在第二部分中，我们将进一步探讨当开发人员打算在新的 Red Hat OpenShift v3 上部署应用程序时，Kubernetes 如何改变他们对应用程序的思考方式。

Red Hat 的 OpenShift 通过使应用程序能够独立于支持它们的底层平台进行开发，帮助改变了数据中心。当 PaaS 被认为是“公共平台”的同义词时，OpenShift 帮助推广了私有 PaaS 的概念:一个用于在可用的基础设施上轻松部署和维护以任意数量的通用语言编写的应用程序的系统，从内部开始并扩展到公共资源。

OpenShift v3 和 v2 是同一个品牌。两者都允许开发人员使用相同的语言部署模块化的、在某种程度上是分布式的软件。但是版本 3 背后的概念——资源如何管理和交付背后的心智模型或隐喻——已经完全改变了。

用一种更隐喻的方式来说，乘坐福特雷鸟的整个想法从 57 年的车型到 61 年的车型发生了根本性的变化，增加了一个后座。当你把双座汽车换成四座汽车时，你不必回到驾驶学校。同样，当您从 OpenShift v2 迁移到 v3 时，您不必重新学习如何开发。但是一旦你搭载了额外的乘客，你可能会发现你正在开车去一些你以前不会去的地方，并且会停下来。

## 论支持码头工人

“这是一个重大的架构转变，”Red Hat 的产品管理总监 Joe Fernandes 在接受 New Stack 采访时表示。“事实上，我们已经为此努力了两年。追溯到 2013 年 9 月，Docker 公开发布三个月后，Red Hat 发布了一份新闻稿，称我们支持 Docker，我们正在与 Docker，Inc .合作。”

Fernandes 回忆了当时的一次新闻发布会，Docker(当时的 dotCloud)首席执行官 Ben Golub 参加了这次发布会，当时他宣布红帽打算将 Docker 架构引入 OpenShift 和红帽企业 Linux (RHEL)。

一些分析师总结说，Red Hat 从其首创的系统向面向 Docker 的系统进行了架构上的转变，这是 Docker 容器成为开发人员选择的分区系统的一种让步。费尔南德斯告诉我们，早在做出这样的选择之前，红帽就已经开始朝这个方向发展了。但在这两个里程碑之间，有一个非常重要的进化发展: [Kubernetes，谷歌的容器架构编排系统](https://thenewstack.io/google-offers-container-as-a-service-to-define-kubernetes-place-in-the-cloud-economy/)。谷歌已经采取了所有必要的措施，让 Kubernetes 成为开发者首选的编排系统，包括与可能成为 Kubernetes 竞争对手的公司达成协议:去年 3 月与[CoreOS](https://thenewstack.io/coreos-tightens-fit-with-kubernetes-raises-12m-from-google-ventures/)，4 月与[meso sphere](https://thenewstack.io/mesosphere-now-includes-kubernetes-for-managing-clustered-containers/)。

无论如何，Red Hat 在 2013 年支持 Docker 的决定导致它在 2015 年将 Kubernetes 与 OpenShift v3 合并。

Red Hat 确实决定生产一个小型的企业 Linux 版本，叫做 Atomic T7，用于容器内部，但是即使这样也没有重新发明轮子。

对于许多 OpenShift 开发人员来说，真正改变的——也许是全部——是他们的软件组件被建模的环境。它们是同一种语言，但是它们在一个新的世界中发挥作用，并且以一种新的方式发挥作用。

对 OpenShift 所做的更改反映了 PaaS 行业从业者(包括 Red Hat)的理解，即如果没有互操作性，竞争的 PaaS 平台将被拒绝。

Fernandes 解释说:“与其他 PaaS 供应商一样，我们一直在努力跟上开发人员的需求。“不管你提供什么，他们总是想要下一个伟大的新框架，或者你已经支持的东西的下一个新版本。我们会支持 Node.js 的一个版本，然后另一个版本就会出现。”

每当社区改进一种语言时，支持该语言的平台必须适应。如果每个平台的适应行为都不同，那么适应就不会以敏捷的方式发生(更多信息，请查阅“ [Fragmentation，Android](http://www.webopedia.com/TERM/A/Android_fragmentation.html) ”)。为了让 OpenShift 保持竞争力，它必须支持一种适应方法，而社区的其他成员也会依次支持这种方法。

更重要的是，至少有两个联盟的成立——开放容器倡议和云计算原生计算基金会，Red Hat 是这两个联盟的特许会员——表明一个供应商的 PaaS 平台中的太多差异将使它被挑选出来，而且不是以一种好的方式。

## 换挡

从现在开始，PaaS 平台的差异化价值将以供应商可以应用于核心平台的任何服务的形式出现，以使其对客户来说显得特别。一些人开始称之为“秘制酱”，这是在向消费者承诺一些特别的东西之后，他们甚至不知道当他们得到它时是什么。

OpenShift v3 的“秘制酱”最好看平台的原始价值和差异化来理解。

直到 2012 年春天，OpenShift 唯一没有的东西就是开放。在被红帽收购之前，它一直是一个独立的专利产品。Red Hat 所获得的是一种新颖的划分应用程序的方式，这种方式是围绕一种机械的心智模型建立的。

想象一下，所有参与 OpenShift 安装的服务器都是一个池，分为两种主要类型:代理和节点。代理简化了运行在节点上的应用程序对这些应用程序可能需要的资源的管理请求。应用程序托管在节点上。这是你可能有的最简单的分工。

每个节点中都有应用程序需要能够运行的组件。现在，几乎每个参与数据中心计算的人都声称发明了容器，或者容器的一些关键方面。在 OpenShift 节点中确实存在一些容器化，但是这个比喻是基于所包含的内容。OpenShift 将这些孤立的星团称为“齿轮”。能够在不破坏整个机构的情况下做功的东西是齿轮。单个齿轮与一个用户相关联。它包括用户完成其基本功能(即运行)所需的资源。(外部资源可以通过图书馆连接。)这些资源使用 Linux cgroups 组合在一起。

从抽象的意义上来说，齿轮产生的工作被称为“应用”应用程序不是一个品牌软件，而是由 gears 执行的一项工作。

由其他齿轮可能需要的可重复使用的齿轮组成的结构被称为卡座。在这里，我们再次看到对功能的关注，而不是功能所在的隔间。Red Hat 工程师将插件描述为易于识别的“定义的技术栈”，如 Python、JBoss 或 MySQL，或 MEAN stack (MongoDB、Express JavaScript、AngularJS 和 Node.js)。从零售商的角度来看，你可以看到盒式磁带的想法是如何使经营者能够轻松地提供单点菜单上的服务。您组装构建原始功能所需的现成模块，并在它们的基础上进行构建。

就在几年前，Red Hat 工程师宣称，社区贡献给 OpenShift 的开发工作中至少有 80%是由墨盒组成的。事实上，由于商业 OpenShift Enterprise edition 和免费使用的 OpenShift Origin edition 之间的主要内容差异是企业组件经过更大程度的测试和完善(毫无疑问，是由 Origin 用户进行的)，Origin 用户更多地使用实验性墨盒。

## 道路分叉和合并交通

OpenShift 的基础设施主题帮助 Red Hat 推动了 PaaS 作为基础设施的概念，并促进了至少一场关于 IaaS 和 PaaS 是否应该继续分开处理的公开讨论。

这场讨论在去年达到高潮，当时 Red Hat 的高级云经理 Gordon Haff 发表了一篇文章，题为“IaaS 和 PaaS 会融合吗？”

“对于各种类型的计算资源的一般消费者来说，简单地将 PaaS 视为比 IaaS 更高层次的抽象，”Haff 写道，“忽略了一个重要的区别。PaaS 提供了一种应用程序开发人员主要感兴趣和使用的抽象。当然，IaaS 也可以吸引寻求更多选择和控制的开发人员。”

Haff 接着说，OpenShift 是专门为开发人员提供部署应用程序所需的工具而设计的，这样他们就不会碍事了。从某种意义上来说，PaaS 可能是基础设施，但只针对那些不会太关注它的存在的开发者。具有讽刺意味的是，相比之下，对于商业服务的消费者来说，PaaS 可能是引人注目的，因为它与他们的基本需求无关。换句话说，它是基础设施的一部分，日常云服务消费者并不关心，因此它与 IaaS 的区别非常重要，主要是因为这个原因。

Haff 总结道:“这里的底线是，在一个基本的 IaaS 和一个成熟的开发平台之间有一个连续体。“这个连续体可以被认为是沿着一条轴线，一边是完整的细粒度控制，另一边是各种托管的平台。”他认为，即便如此，将两种服务作为一个整体的一部分来呈现可能也不是最好的方法。

在版本 3 中，OpenShift 已经脱离了它所开创的机械模型，完全进入了一个基于 Docker 的部署模型，该模型以 Kubernetes 作为编排者。

第二部分的下一个:库伯内特角。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>