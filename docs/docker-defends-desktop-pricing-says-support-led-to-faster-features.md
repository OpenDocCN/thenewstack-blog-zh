# Docker 为台式机定价辩护，称支持带来了更快的功能

> 原文：<https://thenewstack.io/docker-defends-desktop-pricing-says-support-led-to-faster-features/>

8 月底，Docker 宣布他们将对其广受欢迎的 [Docker 桌面](https://www.docker.com/products/docker-desktop)的价格进行[调整，此举在 Twitter 和 Hacker News 等网站上遭到了](https://www.docker.com/blog/updating-product-subscriptions/)[一阵批评](https://thenewstack.io/this-week-in-programming-docker-and-the-internet-of-entitlement/)，同时还有围绕潜在替代品的[讨论](https://thenewstack.io/this-week-in-programming-the-docker-dogpile-continues/)。

从外部的角度来看，这似乎是一个不受欢迎的举动，但上周，Docker 恳求不要同意，因为 Docker 首席执行官 [Scott Johnston](https://www.linkedin.com/in/scottcjohnston) 在一篇[博客文章](https://www.docker.com/blog/accelerating-new-features-in-docker-desktop/)中写道，他们已经看到“来自我们社区的压倒性的积极支持，包括个人开发者和企业”，并且“支持是如此积极，以至于我们能够在我们的[公共路线图](https://github.com/docker/roadmap)中加快我们的投资和交付几个高度要求的 Docker 桌面功能。”

我们采访了 Johnston，讨论了新的变化以及围绕 Docker Desktop 价格变化的喧嚣，其中涉及对员工超过 250 人或年收入超过 1000 万美元的公司收取订阅费。

约翰斯顿说，与社交媒体上似乎存在的反弹相反，此举“产生了成百上千的线索，成千上万的席位被转化为机会，并进入漏斗。”

对于受这些价格变化影响的公司，Docker [表示](https://www.docker.com/pricing/faq)它“相信”其客户会在 2022 年 1 月 31 日之前合规。

至于公司实际上从 Docker Desktop 转向使用自己的开源替代产品的前景，Johnston 说，在 4.0 版本中，公司收到了如此多的反馈，并做了如此多的回应，他认为这是不可能的。

“五年来，我们已经发布了四个主要版本，下载量高达数亿次。永远不要说永远——这是软件，当然，有人可以备份一卡车的钱，把钱扔给一群工程师等等——但是，假设一夜之间，人们可以在他们的桌面上用一堆开源软件拼凑出一个解决方案，你知道，只要你看看那里的数字，“约翰斯顿说。“那等于五年几百个工程人月的工程投资吗？我的意思是，我会让你做数学。”

Johnston 还指出了 Gartner by analyst[Fintan Ryan](https://www.gartner.com/analyst/82961/Fintan-Ryan)最近关于[公司应如何管理 Docker Desktop](https://www.gartner.com/en/documents/4005890/quick-answer-how-should-we-manage-the-recent-licensing-changes-to-docker-desktop-) 最近许可变更的报告，并指出该报告“在投资回报率方面，在让开发人员花时间为企业构建应用程序与花时间 DIY 他们的本地环境并维护该环境方面，下降得非常明显”，以及所有与安全和工程资源相关的成本。

Ryan 在邮件中进一步解释道:“现在我们还没有看到与 Docker 桌面直接可比的替代产品，但是一些替代产品，加上额外的工作，是存在的。”。“我们的建议是仔细评估更换 Docker Desktop 的机会成本(在工程时间和成本、持续维护、使用的功能方面)与许可费用的对比。对于一些拥有非常大的团队的组织来说，这可能是有意义的，但对于许多组织来说，这是没有意义的。

除了这种成本效益分析，[的 Matt Carter](https://www.linkedin.com/in/matthewecarter) ，Docker 的营销副总裁，也指出“如果你在一家小公司，如果你在一个从事开源项目的非营利组织，使用 Docker 桌面的大多数人仍然可以免费使用它”，并且 Docker 任何产品的开源许可都不会改变。

至于那些“被高度要求的 Docker 桌面功能”，它们包括 Docker Desktop for Linux 的[开发者预览版，预计将于 2022 年 1 月底全面上市，Docker 桌面卷管理添加到免费的](https://www.docker.com/community/get-involved/developer-preview) [Docker 个人](https://www.docker.com/products/personal)层，以及 Docker Compose 2.0 的加速全面上市。

Johnston 指出 Docker Desktop for Linux 不仅仅是简单地将更多的开发者添加到可以使用 Docker Desktop 的列表中。

“这不仅仅是为了开发一致性，他们还可以应用一致的安全策略，对安全软件供应链、开发人员下载的内容进行一致的管理。Johnston 说:“对于开发者来说，Linux 占据了 20%到 25%的市场份额，但对组织的价值要大得多。

对于 [Docker Compose](https://docs.docker.com/compose/) 2.0，Docker 团队完全重写了原始工具，从 Python 迁移到 Go，并添加了与 AWS 和 Azure 的集成，对[苹果 M1 硅](https://www.apple.com/newsroom/2020/11/apple-unleashes-m1/)的支持，以及对桌面 GPU 的支持。约翰斯顿解释说，从 Python 到 Go 的转变意义重大，因为 Go 不像 Python 那样是一种解释语言，因此速度更快。

“让一个工程团队重写现有功能，你可能会说这不是最好的投资回报，但我们知道这对用户来说很重要，让他们获得编译语言的速度，”他解释道。

虽然这些是 Docker 桌面用户近期可以期待的功能，但 Johnston 也表示，Kubernetes 的兼容性也是该公司未来关注的一个领域。

“我们不断听到开发者希望进一步简化在 Kubernetes 上构建和部署应用的过程。我们有一个特性，它抽象出了 Kubernetes 的复杂性，并使 Docker Compose 用户易于部署。你会看到我们继续在那里投资，让事情变得更简单，”约翰斯顿说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>