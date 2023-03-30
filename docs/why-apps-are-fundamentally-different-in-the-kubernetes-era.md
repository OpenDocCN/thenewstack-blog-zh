# 为什么在 Kubernetes 时代应用程序会有根本的不同

> 原文：<https://thenewstack.io/why-apps-are-fundamentally-different-in-the-kubernetes-era/>

在上周新堆栈的一篇客座博文中， [Spectro Cloud](https://www.spectrocloud.com/) 的 [Tina Nolte](https://www.linkedin.com/in/tinanolte) 写了当前容器和 Kubernetes 时代的云计算状态(她称之为“云 2.0”)。我发现她对应用程序如何变化的评论特别有趣。在云 2.0 中:

“你的应用看起来不一样。它的架构和构造都不同。它的行为不同。一般来说，你不会把旧的工作负载搬到这个世界上；这些应用以前是不存在的。”

Kubernetes 包含了很多东西——在很多方面，它现在是云的默认操作系统。但是，如果我们仅从应用程序上下文来看，它确实是一个现代的应用程序服务器。[Alexis Richardson](https://twitter.com/monadic),[weave works](https://www.weave.works/)的创始人兼首席执行官，作为[对诺尔特的回应](https://twitter.com/monadic/status/1253776249769656325)说。

但诺尔特似乎暗示的是，在 Kubernetes 时代，应用程序本身已经发生了根本性的变化——这不仅仅是服务器的变化。她在文章中进一步指出，开发人员正在用“微服务和深度平台服务”做的事情与旧的 web 开发模型非常不同。

我联系了诺尔特，问她是否愿意进一步解释为什么应用程序现在是一种不同的野兽。

“云 2.0 中的应用是云原生的，”她回答道。"它们是分布式的，可以根据需求上下扩展，并且对故障具有弹性."

“这是 Kubernetes 真正闪耀的地方，”她继续说道。“它侧重于管理应用程序的分布式计算方面。这并不是说你不能将遗留应用程序提升并转移到由 Kubernetes 管理的容器中——人们可以。然而，这通常是通向真正分布式应用环境的旅程中的一步。”

Kubernetes 应用程序与众不同的另一点是，由于它们的分布式和可伸缩性，它们通常要复杂得多。除此之外，Kubernetes 本身就是一个庞大的、有时很笨拙的平台。加上 Kubernetes 相对较新，所以它的第三方服务生态系统仍在建设中。所有这些意味着 Kubernetes 的开发者体验往好里说是困难的，往坏里说是极其复杂的。

另一个不利于开发者的因素是 Kubernetes 本质上是一个基础设施平台。虽然 DevOps 近年来已经弥合了开发人员和 IT 团队之间的差距，但 Kubernetes 仍然更适合后者。

在去年 12 月的一次播客中，受人尊敬的行业分析师[贾纳基拉姆·MSV](https://janakiram.com/)告诉[新的堆栈](https://thenewstack.io/kubernetes-its-not-easy-but-whats-to-come/)，“Kubernetes 被认为是基础设施，并且仍然是现代应用程序的基础设施，但它缺乏应用程序的上下文。这是采用 Kubernetes 的开发者面临的最大障碍之一。”

然后还有配置要处理。在最近一篇关于新堆栈的文章中，[艾米丽·奥米耶](https://thenewstack.io/author/emily-omier/)曾[将](https://thenewstack.io/reality-check-a-peek-at-the-developer-experience-with-kubernetes/)Kubernetes 上的开发者体验描述为“一个大杂烩”她接着指出:

“一方面，它简化了复杂应用程序的调配和管理。但它也可能很快让开发人员陷入一种配置地狱般的境地，而且——尽管这可能不是 Kubernetes 本身的错——架构混乱，因为不同的 it 团队很难整合到现有的运营中。”

所有这些都是为了说明，与传统的 web 开发相比，Kubernetes 中的开发人员体验是非常不同的。

但让我们回到诺尔特最初的观点:在这个时代，应用程序本身已经发生了根本性的变化。

至少有一个行业倡议试图定义什么是“现代应用程序”，以及如何最好地开发它。去年 10 月，微软和阿里巴巴联合推出了一个名为[开放应用模型](https://oam.dev/) (OAM)的开源项目。贾纳基拉姆·MSV[将其](https://thenewstack.io/what-does-the-open-application-model-oam-and-rudr-mean-for-kubernetes-developers/)描述为“定义现代应用程序的规范，不管它们部署在哪里。”

在 OAM 应用程序交付生命周期中，有三个关键角色:web 开发人员、应用程序操作人员和基础设施操作人员(其中一些角色可能是部分甚至完全自动化的)。下面的描述告诉我们开发人员在图片中的位置:

“为了让开发人员专注于实现应用程序的业务逻辑，应用程序操作员(人工或自动操作平台)负责操作任务。这为开发者提供了“无服务器”的体验。开发者只需要开发并打包应用，然后交付给应用运营商。”

这里最有趣的可能是最终的应用程序需要所有三个角色来扮演他们的角色。这不再是简单地将一个应用发布到一个 web 服务器(云或不云)的情况，任何开发人员都可以在“云 1.0”或更早的版本中轻松做到这一点。现在，开发人员需要将它交给操作人员来完成部署。

事实上，你甚至可以说现代的 web 应用程序本质上已经和服务器融为一体了。开发人员的工作可能以容器结束，但应用程序本身现在扩展到基础设施中，无法与它区分开来。

我不会假装理解贾纳基拉姆·MSV 在他关于 OAM 的文章中的详细程度(如果你是开发人员，请[阅读](https://thenewstack.io/what-does-the-open-application-model-oam-and-rudr-mean-for-kubernetes-developers/)),但是这个摘录很好地总结了为什么现在的应用完全不同:

“OAM 的核心前提是，开发人员的工作结束于从源代码构建容器映像，而操作人员的工作从那里开始。运营团队负责将一组容器映像作为单个应用程序进行配置和部署。”

问题是“单一应用程序”由大量对象组成，其中一些超出了开发人员的知识范围。这是网络历史上第一次，开发者不能完全控制他们的创作。

管理 Kubernetes 的云本地计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>