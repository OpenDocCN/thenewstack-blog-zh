# 为什么你应该关心 Docker

> 原文：<https://thenewstack.io/why-you-should-care-about-docker/>

当我漫步在 Docker con 激动的谈话中时，我在想:我该如何向我在波特兰的妻子解释 Docker，因为她呆在家里，看着我 18 个月大的儿子生病，担心着他。Docker 到底有什么吸引我的地方，让我跑到 600 英里以外的地方去和 30 岁的书呆子在一起？

现在 Docker 上的许多新闻都要求你了解 cgroups、systemd 和 LXC 的变幻莫测。用这些技术开始对话是结束对话的一种可靠方式，除非您遇到堆栈溢出或服务器故障级别超过 1K。我想发现除了这些高度技术性的术语之外，是什么让人们对 Docker 感到兴奋，并找出是什么让他们的工作变得更容易，是什么简化了商业应用程序，是什么让公司变得更强大。

### Docker 加速了技术的采用，即使是在保守的组织中

昨天午餐时，我与来自一家大型财富 500 强金融服务公司的两位开发人员进行了交谈。他们描述了将新技术引入他们的环境有多困难。大型组织中的安全专业人员注定要对新技术说“不”，这是更进步的群体(如喜欢采用和使用新技术的开发人员)之间的持续冲突。

Docker 作为一个标准化的交付系统，将资源分配和安全隔离的责任推到容器中，将该责任从安全或操作角色列表中移除。虽然这不是一个灵丹妙药，但是如果安全团队只负责验证 Docker 容器过程的安全性，他们就更有可能批准新技术。这是一个游戏改变者。

### Docker 使得维护遗留操作系统和代码变得很简单

Docker 使得保留遗留操作系统变得很简单，不管你运行的是什么版本的 Linux。与上述问题相关，许多大型组织都有老化的遗留系统和代码库，他们必须支持这些系统和代码库。小型新创公司没有这个问题。当我向来自 Heroku 的 [Fabio Kung](http://fabiokung.com/) 和 [Rafael Rosa](http://www.grokpodcast.com/) 询问这个问题时，Fabio 指出 Docker 使得支持遗留系统和代码变得微不足道。您不必运行昂贵的裸机服务器来托管每个遗留系统。有了 Docker，您可以获得一个替代重量级虚拟机的廉价方案(只要您的遗留系统是或运行在 Linux 变体上)。Docker 减少了维护旧系统的痛苦和成本，甚至将处理过程记录到版本化的“docker 文件”中。

### Docker 快速减少“运输”痛苦

高管和决策者容忍 CI 服务器、单元测试或敏捷开发实践，但他们真正关心的是一件事:交付代码，开发链中的最后一个周期，通常称为“部署”具有讽刺意味的是，即使有了上面提到的所有工具，部署仍然是开发人员的一大痛苦。正如 Spotify 工程师 Rohan Singh 昨天向我强调的那样，在提交最终的测试代码和让它在最终的生产服务器上运行之间，仍然有一个巨大的痛点。Docker 极大地简化了这最后一步，这对于高管、开发人员来说意义重大，可以更快地将功能展现在客户面前。

### Docker 为财富 500 强解决的问题和它为创业公司解决的问题一样多

当我在会议上与人们交谈时，我最感兴趣的是来自许多大型组织的开发人员如何看到使用 Docker 的巨大价值。Docker 的采用和开发速度如此之快，你可能会认为只有初创公司和早期采用者才能跟踪它，但事实证明，Docker 很快就向大型和小型组织展示了它的相关性。

随着大大小小的公司采用 Docker 并为其做出贡献，这些好处会越来越多。来到 2014 年 DockerCon 展会是一个激动人心的时刻。

克里斯·道森(Chris Dawson)是泰迪·海德(Teddy Hyde)的开发者和创造者，这是一个建立在 Twitter bootstrap 之上的平台，使用了 [Jekyll 博客平台。](https://github.com/mojombo/jekyll)

Flickr 图片[通过](https://www.flickr.com/photos/seabamirum/7509500378/in/photolist-crA9Qs-e8V7H-f3Hqp-bVmzMo-5Dr23u-7X55Dw-5PHqHN-5PDc56-8ynvXF-748sv1-4ffNRo-8TiRny-8TfK16-8TiRjb-8TfJZc-8TiRdE-8TiQVL-8TfJQ4-8TfJXV-8TiRmf-8TfK3M-8TfJVx-8TiRgL-8TiQZ5-8TiQSY-8TiRfj-8TiR5j-8TfJM8-2RChM8-gbhjZ4-g3BUfe-e32SYq-4vg18G-eHjdu2-5V6ayv-9TdTXT-9rgYeo-hNQNYz-hNRzTJ-hNRRiR-hNRPRx-8zLHw-hNRmqJ-JeoRX-cziADW-fEzRWH-hmgUxv-hjWqN8-8oqCks-hjXygF)知识共享

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>