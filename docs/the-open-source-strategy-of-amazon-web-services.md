# 亚马逊网络服务的开源策略

> 原文：<https://thenewstack.io/the-open-source-strategy-of-amazon-web-services/>

[](https://twitter.com/ricmac)

 [理查德·麦克马努斯

理查德是《新书库》的高级编辑，每周撰写一篇关于云原生互联网未来发展的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) [](https://twitter.com/ricmac)

您知道亚马逊在 GitHub 上领导着 1200 多个开源项目吗？我也是，直到上周我与亚马逊网络服务公司(AWS)开源战略和营销主管马特·阿萨伊(Matt Asay)交谈。这个数字是我从 AWS 网页上的[开源获得的，经 Asay 确认代表“官方赞助的项目”——这意味着它们是从 AWS 内部开始的开源项目，而不是由 AWS 员工运营的独立项目。](https://aws.amazon.com/opensource/)

Asay 补充说 AWS 实际上也为数千个其他开源项目做出了贡献。“我们贡献的大多数[GitHub]库都不是 AWS 赞助的，”他说。

它最新的开源项目之一是 Aurora PostgreSQL 的 Babelfish，这是在上周结束的为期三周的虚拟会议上宣布的。Babelfish 是一个开源翻译层，可以轻松地从 Microsoft SQL Server 迁移到 Amazon Aurora PostgreSQL——或者任何其他基于 PostgreSQL 的数据库产品。正如我在[我的新闻报道](https://thenewstack.io/amazon-web-services-wants-you-to-migrate-off-legacy-databases/)中提到的，开源 Babelfish 项目对每个人来说都是双赢的(除了微软)。用户获得免费软件，帮助他们摆脱昂贵的数据库系统，而 AWS 从外部开发人员那里获得帮助，以扩展 Babelfish 覆盖的用例。后者很重要，因为正如 Asay 在 AWS 博客文章中提到的，Aurora PostgreSQL 的 Babelfish 目前只覆盖“最常见的应用场景”

“我们正在尝试做不同的事情，让公司能够使用更多的开源软件，”Asay 告诉我，当时我们正在讨论 Babelfish 新闻。"我喜欢从这样的角度来考虑这个问题，你的生活中需要更多的明信片。"他补充说，Postgres 近年来变得非常受欢迎，尤其是在开发人员中，因为“它不断重塑自己，接受像 JSON 这样的东西。”

## AWS 为什么要你用开源？

Asay 提出的更重要的一点是，有一些令人难以置信的开源产品，更多的公司应该利用这些产品。但是，你可能会问，为什么亚马逊应该关心你是否使用更多的开源软件(除了想坚持使用他们的一个大的技术竞争对手)？

就像所有现代开源项目背后的动机一样，答案非常自私:这是因为 AWS 将自己标榜为“构建和运行开源的最佳场所”。因此，当 AWS 谈论开源时，它的眼中有美元的迹象，因为它考虑了所有这些潜在的新云服务客户。

这并不是说自私的动机有什么错。在最近关于开源的系列文章中，Asay 展示了许多项目都是从开发者挠痒痒开始的。这是开源的方式。

## 为什么 AWS 贡献了这么多开源项目

像现在许多其他公司一样，AWS 在自己的产品中大量使用开源软件。例如，Asay 提到了在 re:Invent 上发布的一款名为[亚马逊 Neptune ML](https://aws.amazon.com/neptune/machine-learning/) 的新产品，这是一种使用机器学习从图表数据中进行预测的服务。

“我们没有真正重视的是，在幕后，Neptune ML 依赖于 DGL——或深度图形库——这是一个我们已经为之贡献了一段时间的项目，我们是其中的主要贡献者之一。”

除了在自己的产品中使用大量开源软件之外，AWS 还向开源开发者提供[促销积分](https://aws.amazon.com/blogs/opensource/aws-promotional-credits-open-source-projects/)来吸引他们使用 AWS 产品。它还直接赞助一些项目，通过最近宣布的 [GitHub 公司赞助商](https://github.blog/2020-12-08-new-from-universe-2020-dark-mode-github-sponsors-for-companies-and-more/)计划 AWS 是该计划的创始赞助商之一。Asay 指出，这个项目允许 AWS 将资金“直接送到我们的客户认为对他们很重要的项目上。”因此，AWS 不仅通过像信用这样的举措支持开源开发者，而且对那些开发者关注的项目有很大的影响力。毕竟，如果你是一名从事开源工作的独立开发人员，那么从事一个有 AWS 这样的大赞助者的项目是有意义的。

## 开源作为 AWS 的一种策略

显然，AWS 在开源方面投入了很多；开源反过来也为 AWS 做出了很大的贡献。更好的产品，更多的客户，并通过资助针对他们需求的开源开发来让他们现有的客户满意。

但是 Matt Asay 在 AWS 的工作是做什么的呢？AWS 参与了数以千计的开源项目，他肯定没有时间去关注所有的项目？

Asay 将他的团队描述为“服务团队的服务团队”他告诉我，AWS 中有超过 175 个服务团队，“要么明确地与开源项目合作，要么以某种方式将开源作为他们服务的一部分。”

“我和我的团队的大部分时间都专注于帮助内部团队——服务团队——找出如何有效地参与开源社区并为这些社区做出贡献，”他说。

Asay 花了大量时间与 AWS 合作伙伴合作，如 MongoDB。这带来了一个有趣的问题:他如何向 MongoDB 这样的公司解释 AWS 的开源战略，因为开源，AWS 实际上与*竞争。长话短说:MongoDB 是一家围绕它自己创造的开源技术而建立的公司，却眼睁睁地看着 AWS 推出同一技术的托管服务版本。*

“我们希望成为这些公司运行(他们的软件)的最佳场所，”他回答说，“让他们为客户服务——因为他们的客户最终是我们的客户。”

他解释说，即使一个 AWS 服务团队直接与其客户竞争——在这种情况下，它是 [Amazon DocumentDB(与 MongoDB 兼容)](https://aws.amazon.com/documentdb/)——还有数百个其他 AWS 服务只是想作为客户服务 MongoDB。

“所以在与他们交谈时，”他说，指的是像 MongoDB 这样的合作伙伴，“我们的总体战略是做任何对客户合适的事情。”

我相信 Matt Asay 说的话，因为他是一个正直的人，我知道他热衷于传播开源福音。与此同时，这也是 AWS 采取的一种不真诚的立场——声称它正在帮助 MongoDB 作为客户，同时还通过利用 MongoDB 的开源技术，公开从他们手中夺走 MongoDB 的客户。

但这就是我们如今所处的科技世界。虽然开源确实推动了大量的创新，但五大科技公司的足迹遍布其中也是事实。在过去的十年中，很少有开源软件逃脱了大型技术的影响——微软甚至拥有最受欢迎的开源软件库 GitHub！

至于 AWS，它不仅运行着 1200 个开源项目，并为成千上万个项目做出贡献，而且它还是大量开源代码运行的地方。我毫不怀疑 AWS 的客户会从中受益，用户也一样。但 AWS 受益最大，因为它通过多种方式从开源软件中获得收入。并不是说这有什么错…

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>