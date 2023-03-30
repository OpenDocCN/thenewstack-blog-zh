# 本周编程:“我们永远不会授权你的软件”

> 原文：<https://thenewstack.io/this-week-in-programming-we-are-never-ever-ever-licensing-your-software/>

如果你看看可用的[多种开源许可，你会注意到一个共同的主题——它们都](https://choosealicense.com/licenses/)[允许在商业产品的创作中使用开源代码](https://opensource.org/faq#commercial)。虽然这些[最近关于亚马逊等大公司的混乱](https://thenewstack.io/this-week-in-programming-open-source-or-merely-ajar/)，在他们提供的商业化产品中使用开源代码可能看起来像是一种新的趋势，但这几乎是开源中最古老的故事，以新的和创造性的方式一次又一次地上演。见鬼，这实际上是开源的起源。

本周，围绕开源许可的争论又有了新的进展，来自[cocroach db](https://www.cockroachlabs.com/)的一些消息称，他们[将根据“MariaDB 最初创建的](https://www.cockroachlabs.com/blog/oss-relicensing-cockroachdb/)[商业源许可(BSL)](https://mariadb.com/bsl-faq-mariadb/) 的一个极其宽松的版本”重新许可，并进一步远离 [Apache License 2 (APL)](https://www.apache.org/licenses/LICENSE-2.0.html) 。该公司之前已经将[转换为](https://www.cockroachlabs.com/blog/how-were-building-a-business-to-last/)cockoroach db 社区许可证(CCL) ，旨在“确保超过评估期的企业功能的商业使用是付费的。”

在一篇博客文章中，该公司现在解释了其在“[为什么我们要重新许可 cocroach db](https://www.cockroachlabs.com/blog/oss-relicensing-cockroachdb/)”背后的想法，写道“我们过去对正确商业模式的看法依赖于开源软件世界的一个关键规范:公司可以围绕强大的开源核心产品建立业务，而无需更大的技术平台公司来提供相同的产品即服务。这种规范不再适用。”

接着，他们解释说，在 BSL 下，“cocroach db 用户可以将 cocroach db 扩展到任意数量的节点。他们可以使用 CockroachDB 或将其嵌入到他们的应用程序中(无论他们将这些应用程序交付给客户还是作为服务运行)。他们甚至可以在内部将 it 作为服务来运行。唯一不能做的事情是，在不购买许可证的情况下，以服务的形式提供 CockroachDB 的商业版本。”

新许可证的“滚动时间限制”为三年，之后该许可证转换为标准的 Apache 2.0 许可证，该公司承认，“这意味着 CockroachDB 核心不再是开源的(根据 OSI 的开源定义)，尽管完整的源代码仍然可用，并且除了构建 DBaaS 以外，任何商业用途都是允许的。”

来自开源领导者的反应，比如布莱恩·坎特里尔和 T2·史蒂夫·奥格雷迪，一点也不复杂。

与此同时，其他人说，像[亚马逊这样的公司目前的难题是采用开源并将其用于自己的货币化](/what-the-fork-amazon/)，或者仅仅作为一种扼杀竞争的服务来提供，这是这部电影的预期结果。

https://twitter.com/glendturner/status/1135011215082528769

然而，谷歌的“开源人”克里斯·迪博纳(Chris DiBona)在这个非开源的新世界中只要求一件事:许可清晰。

好了，现在你知道了——这是情景喜剧中的又一集，告诉你如何抓住不属于你的东西。正如[开源倡议](https://opensource.org/)在其 FAQ 中明确列出[，“开源许可不得歧视个人或团体。给每个人自由意味着也给邪恶的人自由。”](https://opensource.org/faq#commercial)

[https://www.youtube.com/embed/536IF8lJch4?feature=oembed](https://www.youtube.com/embed/536IF8lJch4?feature=oembed)

视频

## 本周的节目中

*   **开发者的 WWDC:**这可能是一种趋势，这些天的开发者大会一定要抛出一堆消费者新闻，以保持在头条位置，苹果的全球开发者大会(WWDC)也不例外，其[999 美元的显示器支架](https://www.businessinsider.com/apple-monitor-stand-price-reaction-misses-point-2019-6)。除此之外，ProgrammableWeb 提供了一份关于 iOS13 的所有[开发者工具的概要，苹果在一份](https://www.programmableweb.com/news/apple-quietly-reveals-ios-13-developer-tools/2019/06/05)[声明](https://www.apple.com/newsroom/2019/06/apple-unveils-groundbreaking-new-technologies-for-app-development/)以及非主阶段开发者会议中悄悄透露了这些工具。新功能中的关键是 [SwiftUI](https://developer.apple.com/xcode/swiftui/) ，“苹果用于创建应用程序 UI 的用户界面框架”，这使得开发人员可以很容易地在众多苹果设备上实时看到界面变化，因为它使用了“iOS、macOS、watchOS、tvOS 和 iPadOS 中内置的相同 API”。ProgrammableWeb 指出，通过 SwiftUI，“苹果在后台处理所有繁重的工作”，并“让开发者在构建原生 macOS 应用程序方面有了巨大的领先优势。”接下来， [ARKit 3](https://developer.apple.com/augmented-reality/) “取得了一些真正惊人的飞跃”，它能够解释人们在空间中移动，允许人们“在虚拟物体的前后走动”，以及一次跟踪多达三张脸的能力。当然，还有一些新的[机器学习](https://developer.apple.com/news/?id=06032019e)功能，以及 Core ML 和 Create ML，使其更容易“构建、训练和部署机器学习模型，而不需要机器学习专业知识”，并根据需要在 CPU、GPU 和神经引擎之间切换。最后，苹果通过苹果 ID[更深入地进入 ID 游戏，用户可以使用苹果 ID](https://developer.apple.com/news/?id=06032019d) 登录应用和网站，甚至将 Face ID 和触控 ID 带入这些登录。在 ProgrammableWeb 的文章中没有真正提到的最后一点是 App Store 审查指南有一些[更新，值得审查，这些更新涉及隐私和其他问题。往前走！](https://developer.apple.com/news/?id=06032019j)

*   **GitHub 上的 Swift 包支持:**现在，当我们到达开发者新闻的 GitHub 部分时，我们从最后一条苹果新闻开始，那就是 [GitHub 包注册将支持 Swift 包](https://github.blog/2019-06-03-github-package-registry-will-support-swift-packages/)。你可能已经听说过，GitHub 最近推出了“GitHub Package Registry 的有限测试版，这是一种包管理服务，可以轻松地在源代码旁边发布公共或私有包”，支持 JavaScript (npm)、Java (Maven)、Ruby (RubyGems)。NET (NuGet)和 Docker 图像。现在，它也支持 Swift 包，有了 [Swift 包管理器](https://github.com/apple/swift-package-manager)，“一个单一的跨平台工具，用于构建、运行、测试和打包您的 Swift 代码。”
*   **Stashing & Rebasing 来到 GitHub Desktop 2.0:** 这就是它的要点——[GitHub Desktop 2.0 已经发布](https://github.blog/2019-06-05-github-desktop-expands-to-support-stashing-and-rebasing/)，除了发布过程中宣布的许多功能，如[解决合并冲突](https://github.blog/2018-11-14-github-desktop-1-5/)或[合著者提交](https://github.blog/2018-02-26-github-desktop-1-1-is-now-available/)，但人们最感兴趣的功能是 Stashing 和 Rebasing。本质上，stashing 意味着当你临时改变上下文时，你可以很快地将你的工作放在一边——“如果你还没有准备好提交你的工作，你可以选择将你的改变带到新的分支或者保留在你当前的分支，”GitHub 解释道。与此同时，Rebasing 允许您从提交历史中隐藏合并提交，以提供一个更加“干净的提交历史”的外观。在潜在有趣的数字方面:GitHub Desktop 2.0 的 150 名贡献者，迄今为止已有“数百万”的下载量，以及“每月有超过 50 万人积极开发该应用。”
*   **GitHub 加入微软团队:**对于那些在微软团队而不是 Slack 的人来说，有了 [GitHub 加入微软团队](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/GitHub-Code-better-together-with-GitHub-and-Microsoft-Teams/ba-p/659444)，你们的生活可能会变得更加轻松。GitHub for Microsoft Teams 应用程序可以从 Microsoft Teams 应用程序商店安装，并将“支持标签、消息传递扩展、机器人和个人应用程序功能。”例如，GitHub Bot 将允许您访问所有存储库、问题和拉式请求的列表，搜索、查看详细信息、添加评论等，为您提供完整的 ChatOps 体验。同样，您可以配置应用程序来通知您新的请求、推送、问题和评论。

*   **谷歌推出“TensorNetwork”库:**谷歌已经[发布了 TensorNetwork，这是一个“高效张量计算的开源库”](http://ai.googleblog.com/2019/06/introducing-tensornetwork-open-source.html)，DevClass [提供了一些关于](https://devclass.com/2019/06/06/google-levels-up-on-machine-learning-introduces-tensornetwork-library/)的背景，写道[新库](https://ai.googleblog.com/2019/06/introducing-tensornetwork-open-source.html)旨在帮助物理学家和机器学习研究人员实现利用称为张量网络的稀疏数据结构的算法谷歌与 [Alphabet 子公司 X](https://x.company/) 和 [Perimeter 理论物理研究所](https://www.perimeterinstitute.ca/)一起开发了这个新的图书馆，“后者最近成为今年早些时候发布的黑洞图像背后的合作者之一，”并且建立在——你猜对了——谷歌的“流行数值计算图书馆 [TensorFlow](https://www.tensorflow.org/) ”之上如果你真的想知道真相，请务必阅读谷歌人工智能团队的博客，或者更深入地阅读科学论文。当然，你也可以在 GitHub 上找到它，它是在 Apache 2.0 许可下提供的。
*   **预览 Python 3.8:** JaxEnter 报道 [Python 3.8.0 beta 1 已经到来](https://jaxenter.com/python-3-8-beta-1-159152.html)，截止[2019 年 6 月 4 日](https://www.python.org/downloads/release/python-380b1/)，标志着“功能冻结”，也就是说“从现在开始，将不会包含任何新功能。”该版本是最终版本之前的四个测试版预览之一，下一个测试版计划于 2019 年 7 月 1 日发布——完整的[发布时间表](https://www.python.org/dev/peps/pep-0569/)可获得详细信息。有关测试版新特性的更多信息，请点击至。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>