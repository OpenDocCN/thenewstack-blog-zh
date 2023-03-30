# 谷歌对 Istio 的管理在云原生社区引发了质疑

> 原文：<https://thenewstack.io/googles-management-of-the-istio-service-mesh-raises-questions-in-the-cloud-native-community/>

当 [Istio](https://istio.io/) 服务网格在 2017 年 11 月第一次[提议](https://github.com/cncf/toc/pull/70)被纳入[云本地计算基金会(CNCF)](https://www.cncf.io/) 时，[仍然是 v.02](https://istio.io/latest/news/releases/0.x/announcing-0.2/) ，只有不到六个月的时间，然而它的目标是跳过大多数年轻项目进入的入门级，而是申请纳入二级孵化层。虽然该项目主要由谷歌和 IBM 创建，并有许多其他贡献者，如雅虎、Apprenda、Concur 和 AT & T，但它遭到了质疑——它太新了，还没有真正被采用，还有一些技术问题。就在提议提出一个月后，拉取请求被关闭，没有任何评论。

“社区中的许多提供商都在推动 Istio 去 CNCF，一开始，事情有点复杂，因为说实话，它还没有准备好，”Solo.io 首席执行官解释说，谷歌不想在它有一个强大的基础之前提交这个项目。“如果地基不是很好，你把它放在那里，人们会在上面建东西，这就像一座建筑，最终会倒塌。”

从那时起，许多人就一直期待着，一旦准备就绪，它将被移交给 CNCF，加入其云原生兄弟姐妹的行列。本月早些时候，谷歌有效地结束了这些期望，推出了[开放使用共享](https://openusage.org/) (OUC)的，Istio 是三个创始项目之一。当我们第一次与谷歌和 Alphabet 的开源总监[克里斯·迪博纳](https://en.wikipedia.org/wiki/Chris_DiBona)谈论这次发布时，他说这确实是前面提到的基金会[谷歌云首席执行官托马斯·库里安今年早些时候提到的基金会](https://www.protocol.com/google-cloud-kurian-istio-foundation)，当时他说 Istio 将会捐给一个基金会。然而，几天后，我们再次找到了迪博纳，他坚定地表示，无论“基金会”与否，OUC 只做商标和商标生意。

DiBona 在最近的 [New Stack Context 播客](https://thenewstack.io/the-new-stack-context-google-launches-a-trademark-office-for-open-source/)中表示:“开放使用共享的目的是解决围绕开源项目中的商标问题，并确保它们得到适当的共享，并与开源定义保持一致。“我们不从事基金会业务。我们不是做营销的。我们不是做会议生意的。我们不是这些项目的管理或指导委员会。我们在那里严格管理商标。我们的目标不是成为 Linux 基金会、Apache 软件基金会或软件自由保护协会。”

> “现在 Istio 和谷歌所做的事情与把它交给基金会的结果是一样的。至于最终用户，我是一个最终用户，我真的不在乎，对吧。是一回事。”— Solo.io 首席执行官艾迪特·莱文

尽管如此，CNCF 及其周围地区的人以及期待 Istio 被授予 CNCF 的其他人的第一反应是反对。CNCF 首席技术官 Chris Aniszczyk 表示，他们的社区成员“对谷歌选择不将 Istio 项目贡献给 CNCF 感到困惑”，而 Istio 创始成员 IBM [写道](https://developer.ibm.com/components/istio/blogs/istio-google-open-usage-commons/)它不同意 OUC“因为它不符合社区对开放治理的期望”IBM 进一步解释说，“在项目开始时，有一个协议，该项目将在成熟时贡献给 CNCF”，并简单地说，“谷歌应该重新考虑他们最初的承诺，并把 Istio 带到 CNCF。”

谷歌认为 OUC 不是一个基金会，在项目管理中没有任何作用，除此之外，该项目最近已经采取措施，通过[提议更新 Istio 指导委员会章程](https://github.com/istio/community/pull/361/)，解决该项目由谷歌控制的指控。该提案旨在扩大指导委员会的席位数量，限制任何一家公司占据多数席位，并通过向那些“通过代码和非代码贡献”做出贡献的人开放更多席位，进一步保证开放的治理。

然而，另一方面，一些 Istio 最终用户对 OUC 将解决 Istio 商标问题的消息表示支持。

提供“企业就绪”Istio 订阅的 Tetrate[写道](https://www.tetrate.io/blog/istioouc/)Istio 商标转移到 OUC“对整个项目来说是一件好事——这可能会让一些人感到惊讶——但事实上，这也是 CNCF 存在的主要目的:成为一个持有商标的中立机构。”

同样，Solo.io 的莱文在一封电子邮件中写道，“Istio 的治理一直是开放和欢迎的，但是——和其他人一样——我们和我们的客户对其所有商标都归谷歌所有的事实感到不安。所以我们很高兴 Istio 的商标现在由一个独立的组织拥有和管理。”Levine 进一步解释说，他们“相信这一举措将增加 Istio 开发者和用户的信心”，并且“最终，这是我们所有在 Istio 社区的人所希望和努力的。”

至于 Levine 是否希望 Istio 交给一个基金会，她说她不一定认为有必要。

“由 CNCF 管理一个项目意味着三件事:商标管理、支持项目自我管理和市场营销。Istio 已经有了一个成功的开放治理模式，它从其广泛的社区中获得了充足的市场营销，而作为独立组织引入的 OUC 负责商标，”Levine 写道。“总的来说，我觉得 Istio 已经具备了所有的基础，我认为没有理由让 CNCF 来管理它，这自然会带来自身的复杂性。”

另一个商业 Istio 产品, [Aspen Mesh](https://aspenmesh.io/) 的营销主管 Zach Jory 说，他们“看不到它有意义地改变项目方向或治理”,他进一步反驳了 Istio 需要搬到 CNCF，以便对采用者和贡献者开放和值得信赖的观点。

“事实证明，CNCF 是开源项目的好去处。我对 CNCF 如何超越技术管理、市场营销、合作伙伴关系和生态系统发展印象深刻。话虽如此，我们并不认为 CNCF 是开源、云原生项目能够蓬勃发展的唯一地方。坦率地说，我们发现 CNCF 和供应商占了这方面谈话的绝大部分——很少有我们交谈的最终用户和客户关心 CNCF 会员资格，”Jory 在一次电子邮件采访中写道。“贡献者和用户关心的 bits 仍然受 Apache 2.0 许可证的管理，加入 CNCF 或其他管理机构不会使该项目更加开源。”

当然，并非所有人都同意这一评估，而是对形势提出了更为悲观的看法。

[威廉·摩根](https://www.linkedin.com/in/wmorgan)是[浮力](https://buoyant.io/)的首席执行官，该公司背后的 CNCF 成员 [Linkerd](https://linkerd.io/) 服务网格，他认为这一切都是谷歌保持控制的更邪恶的举动。

“我认为，谷歌为 Istio 创建一个定制基金会，表明谷歌希望保留对该项目的控制权。我认为其合作伙伴的反应尤其能说明问题:谷歌如此渴望这一点，以至于它愿意公开违背它与合作伙伴达成的协议。这很不寻常。虽然关于基础、商标和治理的争论可能看起来很迟钝，但是开源消费者对这些问题越来越成熟，因为他们回答了关于他们所依赖的软件的基本问题；像“谁来决定这个东西到底做什么？”这样的问题。”摩根在一封邮件中写道。

更进一步，Amalgam Insights 的分析师 Tom Petrocelli(T1)得出了一个合乎逻辑的结论:当一个开源项目没有按照你想要的方式发展时，放弃它，继续前进。

“在最好的情况下，这给许可过程增加了不必要的复杂性，尤其是对商业开源公司而言。在最坏的情况下，这在软件上施加了一个额外的控制层，而不必说它仍然是开放的核心，”Petrocelli 在一封电子邮件中写道。“CNCF 和 IBM 显然对此感到恼火，对此我并不感到意外。它的意义如此之小，以至于你会立即认为它是邪恶的东西。我对 Istio 社区的建议是，立即用一个新名字将这个项目分叉，并将锁、库存和桶转移到项目所属的 CNCF。”

[第 125 集:克里斯·迪博纳——谷歌推出开源商标局](https://thenewstack.simplecast.com/episodes/episode-125-chris-dibona-google-launches-a-trademark-office-for-open-source)

Aspen Mesh 和 Cloud Native Computing 社区是新堆栈的赞助商。

来自 Pixabay 的 artverau 特写图片

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特[或脸书](https://twitter.com/thenewstack)[访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈:](https://www.facebook.com/thenewstack/)[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>