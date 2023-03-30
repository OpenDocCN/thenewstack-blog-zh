# Kubernetes 的状态:关键挑战和人工智能的作用

> 原文：<https://thenewstack.io/the-state-of-kubernetes-key-challenges-and-the-role-of-ai/>

[](https://www.linkedin.com/in/adamlagreca/)

 [亚当·拉格雷卡

亚当是 B2B DevOps 的精品公关机构 10KMedia 的创始人。此前，他是 DigitalOcean、Datadog 和 Gremlin 的通信总监。](https://www.linkedin.com/in/adamlagreca/) [](https://www.linkedin.com/in/adamlagreca/)

有很多文章赞美库伯内特人的优点。多年来，这一直是 DevOps 世界的主导主题。所以我们就简单陈述一下:Kubernetes 赢了。这是编排容器的实际方式，也是云原生应用的核心。

那现在怎么办？

嗯，我认为有趣的对话正在社区和更广泛的生态系统中发生。我们如何为 Kubernetes 用户提供更好的支持？我们如何构建更好的工具？我们如何理解和管理这些分布式的复杂系统？

我想和一些为复杂问题构建尖端解决方案的人谈谈，这些复杂问题是由于采用 Kubernetes 以及更广泛的容器/微服务而产生的。我问了一些问题，比如:库伯内特斯将走向何方？为什么这么复杂？人工智能有什么作用？

下面是一些要点，然后是完整对话的链接，供感兴趣的人参考。

Kubernetes 是一个超级大国。Kubernetes 的腾飞并非偶然，尽管它很复杂。一个工程师现在可以从他们的笔记本电脑上部署容器，这在过去需要一个专家团队来完成。容器化应用程序并协调其部署的能力意味着前所未有的规模和敏捷性。

**Kubernetes 比较复杂。**正如有人曾经说过的:没有解决方案，只有取舍！Kubernetes 一开始可能感觉像魔术一样，但团队通常会相对较快地发现自己不知所措。就像一块坏掉的手表，当事情出错时，通常需要专业知识才能找到问题所在。

**Kubernetes 社区非常重视安全性。**默认情况下，Kubernetes 带有锁定的控制平面，没有特权容器，API 之间的加密，限制服务之间通信的能力等等。它还是声明性的，因此您可以在部署之前确保更高的安全性，也称为“左移”然而，有足够多的旋钮，你可以无意中使事情变得更加不安全。如果您没有完成正确的过程，比如直接编辑部署而不是清单，或者如果您关闭了默认的安全控制以使您的生活更轻松，那么这种安全优势就消失了。

坚持用香草。 Kubernetes 可定制性很强，API 也越来越好。也就是说，没有理由让事情变得不必要的复杂。不要让宣传把你拉进过度设计你的应用程序，这也会引入不必要的安全问题。有时候，您需要的只是部署在 EC2 上的一个简单的应用程序。同样值得注意的是，每个云提供商都为 Kubernetes 创建了不同的配置，例如，AKS (Azure Kubernetes 服务)与 EKS 不同。(亚马逊的弹性 Kubernetes 服务)。您可以实践混沌工程来更好地理解这些系统，并在它们影响客户之前根除潜在的故障场景。

**AI 来了，但还没到。**特别是在运营领域，人工智能介入并修复问题的想法已经成为多年来讨论的话题(也称为“AIOps”)。随着 GitHub Copilot 等产品的推出，我们实际上看到了这种对话的进一步左移。但事实仍然是，机器可能会向你显示一个尖峰，但你仍然需要一个人来为它赋值并采取特定的行动。Kubernetes 也不例外。我们将看到大量趋势数据和机器学习涌入产品，帮助团队解决 Kubernetes 的问题并做出更好的决策，但人类暂时仍将保持在方向盘上。

**Kubernetes 不一定适合所有人。**在整个谈话过程中，有一点被反复提及，那就是 Kubernetes 并不适合所有人。或者至少它并不适合所有人。在您的组织中，理解哪里是必要的，哪里更传统的基础设施就足够了，这是一件值得思考的事情。

Kubernetes 圆桌会议的与会者是:

*   奥斯汀·帕克——light step 的开发者代言人
*   马特·约翰逊——Bridgecrew[的开发商代言人](https://bridgecrew.io/?utm_content=inline-mention)
*   Tammy Butow——Gremlin 的首席现场可靠性工程师
*   liran Haimovitch——首席技术官和 [Rookout](https://www.rookout.com/?utm_content=inline-mention) 的联合创始人
*   itiel shw artz——首席技术官和 [Komodor](https://komodor.com/) 的联合创始人

观看以下完整视频:

[https://www.youtube.com/embed/QQlvljKSTy4?feature=oembed](https://www.youtube.com/embed/QQlvljKSTy4?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>