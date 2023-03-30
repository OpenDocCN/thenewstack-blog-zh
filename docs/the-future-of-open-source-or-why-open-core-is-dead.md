# 开源的未来，或者为什么开放核心已死

> 原文：<https://thenewstack.io/the-future-of-open-source-or-why-open-core-is-dead/>

[](https://www.linkedin.com/in/orweis/?originalSubdomain=il)

 [或 Weis

或 Weis，Permit.io 联合创始人兼首席执行官，五岁开始玩电脑，历任开发者、军官、研究员。在以色列情报部队服役后，他在多家网络安全和大数据公司担任首席工程师，并担任国防部的顾问，以及 Netline communication s Technologies 的网络安全解决方案副总裁。或者是 Rookout 的联合创始人兼首席执行官。](https://www.linkedin.com/in/orweis/?originalSubdomain=il) [](https://www.linkedin.com/in/orweis/?originalSubdomain=il)

让我们开门见山吧:如今，开源你的核心业务产品是一个坏主意。如果你建立的项目开始与你的核心产品直接竞争，或者让其他人吃了你的午餐，你会对它不满意，不管它是否成功(有时是因为成功)。

不要混淆我所说的意思是我总体上反对开源。相反，作为一名开发人员，我使用许多开源工具，通过贡献定期参与，甚至自己也构建了几个。

**我相信开源是(并将会是)所有现代软件栈的基石**。
这是实现有意义的对话、建立真正的社区来解决复杂问题和促进行业标准(由标准协会采用，或随着项目变得越来越重要而实际创建)的最佳方式之一。说到创建社区，你希望一个社区能够提供真正的价值。否则，为什么要创建它？

## 那么，开放核心改变了什么？

早在 2010 年代，像 Redis T1、T2、MongoDB T3 和 Red Hat 这样的公司创建的开源项目大受欢迎，并取得了巨大的成功，在他们的项目上提供了额外的企业版本和专业服务。MongoDB 的首席执行官曾表示，当时， [公司在核心 MongoDB 开源项目](https://www.protocol.com/enterprise/mongodb-open-source-database) 上花费了大约 50%的研发预算。

问题是，时代变了。以前，一个项目可能需要数年时间才能获得显著的影响力。这使得依赖于开放核心模型的企业能够创建项目，培育项目，然后找到正确的方法来开始商业提供。现在事情进展得更快了。现在尝试这样做，很有可能你会与你自己的开源产品竞争，或者有人会更快地在你的项目上构建一个产品。留给你的只有你做的残羹剩饭。

## 通过艰难困苦而学到

Docker 有一个非常强大的 OSS 产品，但最终蚕食了它自己的市场份额。Docker 的反应是开始限制自己的 OSS 产品，这激怒了 OSS 社区，造成了商业和开源产品之间的冲突。

Elastic 非常快速有效地发展了它的 OSS，但是当 OSS 变得非常大的时候 [其他公司开始在它上面提供 SaaS](https://opensourceconnections.com/blog/2021/01/15/is-elasticsearch-no-longer-open-source-software/)(像 Logz.io、AWS 和 Coralogix)。由于他们的市场(基本上是他们创造的)被严重削弱，他们别无选择，只能转向另一个领域(网络安全)。如今软件采用的速度比十年前快得多，以至于在市场被接管之前，Elastic 几乎没有时间认识到这个问题。他们的“主场优势”比其他任何东西都更成了累赘。

认识到这一转变，MongoDB 自己退出了他们最初采用的开放核心模型， [改变了管理免费开源 MongoDB 项目的许可条款](https://www.protocol.com/enterprise/mongodb-open-source-database) 。你对开放核心项目看得越多，你就会发现越多的公司在努力保持与自身增长、项目增长压力以及周围加速发展的市场之间的平衡。

## 更好的前进方式:开放基金会

那么这里有什么选择呢？我建议找到一个真正的问题，您的开源解决方案可以帮助解决这个问题，补充您的业务，但不会放弃核心价值，并通过坚持以下三个关键原则与市场保持一致:

1.  **真实:**项目需要**增加真正的价值，并真诚地提供价值。**在一个快节奏和互联的市场中，开发人员很容易发现将他们推向其他产品的“窍门”。
2.  避免利益冲突:开源项目不应该让你的公司陷入利益冲突。当你推动公司发展时，随着需求的增加，你会遇到市场压力。与使用你的开源软件的竞争对手相比，这可能会限制你的发展或大大降低你的速度。支持、发展和壮大开源软件是一项繁重的工作，你的竞争对手可能会轻易获得你的利益，这可能会给你的公司带来死亡之吻。
3.  **使项目独立:**开发人员应该能够享受项目所提供的一切，而不依赖于不遵守这些原则的其他组件。如果你的 OSS 项目是有价值的，但是进入它有障碍——其他项目将通过减少所说的障碍来废黜它。

如果您坚持这些原则，您可以创建一个开源产品来补充您的核心产品。它授权、支持、增强、启用产品，或者是产品的一部分，但不是产品本身或其核心。这将允许您享受开源社区的所有好处，而没有损害您的产品核心供应的风险。

这一策略已经被数十家公司采用。

**([Spinnaker](https://github.com/spinnaker/spinnaker))**Google**([Kubernetes](https://github.com/kubernetes/kubernetes))**Meta**([React](https://github.com/facebook/react))都创造了巨大成功的 OSS 产品，为开发者和社区提供了真正的价值，而没有放弃他们产品的核心价值。小一点的公司也在用这种模式——**komo dor**([valid kube](https://github.com/komodorio/validkube))，**Up9**([Mizu](https://github.com/up9inc/mizu))，我自己的公司，[**permit . io**](http://www.permit.io)([OPAL](https://github.com/permitio/opal))。**

 **当我们共同创建我们的开源项目 OPAL 时，我们希望为开发人员提供一种标准的方法，使权限随着云中的动态变化而更新。我们推广这个项目，希望人们使用它，不管他们是否曾经为我们的 SaaS 产品支付过一分钱( [Permit.io](http://permit.io) )。

**我们的开源项目做得越好，规模越大，对我们的产品就越有利**，这正是你在考虑将开源作为一项业务时想要的动力。

开源不会消失，开源基金会是开源商业策略发展的下一步。我很高兴看到它带给世界的所有令人惊叹的社区、产品和标准；以及随之发展的令人惊叹的(协调一致的)企业。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**