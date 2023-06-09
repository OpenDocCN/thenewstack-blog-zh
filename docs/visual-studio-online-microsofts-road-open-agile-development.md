# 微软开启敏捷开发之路

> 原文：<https://thenewstack.io/visual-studio-online-microsofts-road-open-agile-development/>

软件开发中最古老的经验法则之一是[康威定律](https://en.wikipedia.org/wiki/Conway%27s_law)，它表明“设计系统的组织……被限制生产这些组织的通信结构的副本的设计。”或者，正如人们常说的，“不要发送你的组织结构图。”紧随其后的是它最近的推论，逆向康威定律，它指出你可以通过为你想要的组织设计软件来改变组织。

这就是发生在 [Visual Studio Online](https://www.visualstudio.com/) 和微软身上的事情。

VSO 最初于四年前作为 Visual Studio 的 [Team Foundation Server](https://msdn.microsoft.com/en-us/library/ms364061.aspx) 的在线版本发布，现已成为微软建立内部开源生态系统的一个中心。与此同时，它为 Redmond 的开发团队提供所需的工具，以从单一应用程序转移到现代跨平台服务架构的持续交付，并建立首席执行官塞特亚·纳德拉支持的内部开源文化。这两个角色可能看起来相距甚远，但他们现在正朝着同一个方向推动微软的协作开发工具——同时使微软成为一个更加开放的公司。

我们最近采访了微软的 Brian Harry 和 Nicole Herskowitz，讨论了微软的企业开发平台正在做什么，以及它是如何超越其内部团队基础的。Herskowitz 解释说，现在每个公司都是软件公司，但“这是他们如何区分”这是重点。但是软件对商业日益增长的重要性意味着软件开发方法需要改变。“让他们变得更敏捷、更高效至关重要。Herskowitz 说:“他们需要更快，根据最终用户的反馈迭代他们的应用程序。像 VSO 这样的工具对此至关重要，它提供了一种替代大量使用电子邮件的流程的方法。

这也不仅仅是发展。这是更广泛的 DevOps 行动的一部分，改变了团队的工作方式——即使是在微软。“我们的团队已经改变了，”Herskowitz 指出。“我们从每隔几年发布一次瀑布开发的盒装软件转变为每三周发布一次服务。”这导致 VSO 团队重新思考他们的工具:“我们必须做出改变，现在我们的客户也在改变。因此，我们了解他们的需求，这确实会影响我们为帮助他们解决这些问题而开发的工具。”

这一变化反映了用户如何将 VSO 构建到他们现有的开发工具链中。微软曾经是一家非常“我们的方式或高速公路”的公司。如果你使用微软的开发工具，你就使用了它的项目管理工具，它的源代码库，它的测试和构建链。这一切都在改变，因为它的客户开始使用各种工具和技术——微软也是如此。

将 VSO 作为应用生命周期管理框架开放的过程意味着它需要成为一种工具，您可以将其他工具插入其中，并且可以与其他工具和服务互操作。哈利解释了团队是如何实现的:“第一步是支持 REST 和 OAuth，用服务挂钩来支持跨服务的事件。然后，我们可以构建与一系列不同工具的集成，如用于票证管理的 [Zendesk](https://www.zendesk.com/) ，用于管理任务板的 [Trello](https://trello.com/) 。还有一个多路复用代理，它有数百个额外的东西，比如用于项目管理的 [Asana](https://asana.com/) 。

微软意识到它无法满足所有开发者的所有需求，这意味着 VSO 将继续成为该公司跨平台和开放开发者战略的重要组成部分——未来的版本将增加对流行的开源代码库 Github 的支持。随着微软将自己的开源代码从 [CodePlex](https://www.codeplex.com/) 转移到 Github，这是一个合乎逻辑的举动。

Harry 指出，这不是唯一的变化:“除此之外，我们还投资于下一代构建工具，支持跨平台和跨技术。”这个新的构建工具对于微软的开放开发将会非常重要；开箱即用，它将能够支持从 Xcode 到 Node.js 到 Java 到. NET 的所有构建。“我们有运行在 Mac 和 Linux 上的代理来支持那里的交付，”Harry 说。还可以选择使用新的构建工具和 VSO 来与其他构建系统集成。NET 团队使用它们来处理 Jenkins 服务器。

Harry 指出，VSO 仍然缺少治理工具。“这将取决于一个组织有多成熟，以及它的代码在法律上有多敏感。”对于有复杂需求的公司来说，这可能意味着与黑鸭公司的 T1 或 T2 帕拉米达公司的 T3 工具及其咨询服务的整合。不太复杂的组织将能够使用像 JFrog 的 [Artifactory](http://www.jfrog.com/open-source/) 这样的工具。他很清楚这种差距不会持续太久，他告诉我们，“作为我们努力的一部分，我们将确保为客户提供解决方案。”

VSO 的变化不仅仅是支持其客户的问题。随着关键技术的开源，它们也反映了微软内部的变化。正如 Harry 所说，“GitHub 的一些集成是因为它是开源领域的一个重心，正因为如此，微软在那里托管了许多自己的开源项目。因此，我们考虑进行 GitHub 集成的一个原因是我们自己的需求，以及我们希望利用我们的 VSO 能力，在开放环境中主持开发工作的愿望。”

将微软自己的开发团队引入 VSO 影响了开发。正如 Harry 解释的那样，“我们当然有我们在其他地方没有达到的规模要求。”目前微软内部有超过 20，000 名开发人员在使用 VSO，这是迄今为止使用该工具的最大的用户群。他告诉我们:“活动目录的规模 VSO 带来的人数，推动我们为大型团队做出改进。”。

这是一条双行道，Harry 说:“我对将更广泛的微软带到 VSO 感到兴奋的原因之一是，它创造了一个真正好的途径来利用微软的能量来构建工具，以帮助 VSO 变得更好。”Harry 指出了最近的发展:“两三年前，我们宣布了一个新的 wiki 体验，改进了 VSO 欢迎页面。它由微软的另一个团队构建，并为 VSO 做出了贡献。”

同样，新的构建系统也受益于与微软内部其他团队的合作。他说:“负责大量 Android 和 iOS 开发的办公室团队为构建系统贡献了大量东西，以处理代码签名和他们在 Android 和 iOS 中需要的其他关键功能——这些将成为商业版本的一部分。”Harry 对事情的进展很满意，评论道，“这正是我们试图在公司内部实现的内部开源生态系统。”

正如 Herskowitz 告诉我们的，“这是我们如何支持开放平台、连接各种不同服务的一个更广泛的例子。作为一家公司，我们正在向非常开放的开发方式转变——拥抱社区来帮助我们进一步扩展我们的技术和工具的开发。随着开发从使用传统瀑布式流程构建的小团队和大代码块中脱离出来，这种变化反映在公司的工具中。"社区正在采用小的工作单元，将代码分支，并将其带到新的地方."

构建促进开放性的工具是成为更加开放的公司的关键，而 VSO 是改变微软开发文化的关键。微软的任何人都可以获得 VSO 的源代码，任何人都可以签出代码，并向团队提交 pull 请求。随着 VSO 和 [Yammer](https://www.yammer.com/) 缩短了微软的旧流程，随着它的组织结构图发生了巨大的变化，也许是时候停止发布你的组织结构图了。

特色图片[通过](https://www.flickr.com/photos/vanessa_gerlach/9589596291/in/photolist-9HLptU-qd45T4-4Bo5g-bmFhxi-6NNCPV-qXbp9i-9J8xRS-fsKYf7-6G7VPs-dMxnbJ-fBpbT6-ptYoEx-fkwby5-oTTZqC-q2bhFN-8X2ygd-rxVN6X-Lm7rq-5q9CJY-2NMwfp-5SGDbH-etXju6-8iXnMA-8eomwi-qfqsht-f8c1kt-CXXmC-6Uxvyr-9kqk5g-oiZCWp-ow7Gm6-6FvvQT-5cmovm-5UsLwb-r8qF5m-4nKHw7-pBCXGL-ctJVNU-dzKdCQ-q2hKgt-d85HTL-dAwbNi-buDqo9-7mVAJt-4Bdt5i-dimyDU-6HF8in-fnvJqR-eS7JVx-ao4361) Flickr 知识共享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>