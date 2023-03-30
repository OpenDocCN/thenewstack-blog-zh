# 本周的节目:脸书、平台风险和吃掉你的孩子

> 原文：<https://thenewstack.io/this-week-in-programming-facebook-platform-risk-and-eating-your-young/>

本周，脸书举行了一年一度的 F8 开发者大会。现在，如果你还没听说，脸书最近因为其普遍的，嗯，不可信而陷入了一点[的热水](https://www.theverge.com/2018/4/10/17165130/facebook-cambridge-analytica-scandal)。想象一下——由一个男人领导的公司[引用](https://www.esquire.com/uk/latest-news/a19490586/mark-zuckerberg-called-people-who-handed-over-their-data-dumb-f/)嘲笑他的用户相信他是“愚蠢的混球”,通过再次背叛那些相同用户的信任而陷入困境。大约 20 亿人。

本周的会议采取了一些措施试图重新获得一些信任。根据 SDTimes 的消息，发布会宣布:“专注于构建创造价值的 API，提供透明度和控制，并专注于建立信任。”也许最直接地谈到最近在保护用户数据方面的问题，脸书正在重新开放其应用程序审查流程，专门针对“需要访问专门的 API 或扩展登录权限”的应用程序

根据脸书总结会议的帖子，“人们应该完全控制如何与开发者分享他们的信息。2014 年，我们做出了重大改变，让人们能够对他们选择分享的权限和信息进行精细控制，我们希望这也能反映在你的产品体验中。”

就好像他们在说，“四年前我们给了你保护自己的工具，但你失败了”。

除了对脸书的信任，Daring Fireball 的 John Gruber 直言不讳地说出了在开发一个完全依赖脸书平台或者仅仅使用脸书 ID 作为主要登录方式的应用程序时，你可能会想到的东西——也就是说，任何使用脸书 ID 的公司都是愚蠢的。

“鉴于脸书的垄断地位，这应该是非法的，”格鲁伯写道。“但每一家像这样信任脸书的公司，都应该早就明白这一点。”

另见格鲁伯帖子中引用的推文:

https://twitter.com/SirKneeland/status/991373570730147840

当然，格鲁伯指的是脸书宣布的约会应用功能，以及 Tinder 对使用脸书作为主要登录 ID 的严重依赖。

啊，所谓的“平台风险”，你又抬起了你丑陋的头。当然，你们中那些已经存在足够长时间的人还记得 2011 年 Twitter API 的大溃败——当时该公司基本上关闭了许多在那之前帮助过它的应用程序的访问，只是简单地建立了它认为有价值的那些应用程序的自己的版本。也许这只是另一个提醒，提醒你要注意你的产品基于什么平台，如果有的话。(举例来说，如果你问大多数仍然看好最近几年聊天机器人淘金热的风险投资人，他们会简单地把这当成作为开发者做生意的固有风险之一，请注意。)

现在，说了这么多，让我们看看大公司(包括脸书)本周发布的所有其他公告，你可能会在此基础上构建你的下一个应用程序！(与此同时，一些大而邪恶的公司似乎正在做一些大而邪恶的好事，为大众开发开源工具……)

但是首先…

[https://www.youtube.com/embed/HluANRwPyNo?feature=oembed](https://www.youtube.com/embed/HluANRwPyNo?feature=oembed)

视频

## 本周的节目中

*   **脸书宣布 PyTorch 1.0:** 脸书[宣布 PyTorch 1.0 用于研究和生产](https://code.facebook.com/posts/172423326753505/announcing-pytorch-1-0-for-both-research-and-production/?utm_source=codedot_rss_feed&utm_medium=rss&utm_campaign=RSS+Feed)，这意味着更容易开始人工智能开发。总之，开源人工智能框架“从 Caffe2 和 ONNX 中获取模块化、面向生产的功能，并将它们与 PyTorch 现有的灵活、以研究为中心的设计相结合，为广泛的人工智能项目提供从研究原型到生产部署的快速、无缝路径。”脸书已经使用 PyTorch 支持“许多大规模的脸书产品和服务，包括每天执行 60 亿次文本翻译”，测试版将在未来几个月内推出。
*   **脸书开源其围棋冠军机器人:**脸书的人工智能研究部门已经开源了 ELF OpenGo，这是一个围棋人工智能机器人，已经击败了世界职业围棋冠军。“作为 PyTorch 的一部分，”该公司在声明中写道，“ELF 使研究人员可以通过快速灵活的实验，轻松尝试不同的强化学习想法。”
*   **Swift for TensorFlow 开始开源:**继续 AI 开源主题，谷歌宣布 [Swift for TensorFlow 现已在 GitHub 上开源](https://adtmag.com/articles/2018/05/01/swift-tensorflow.aspx)。TensorFlow 的 Swift 现在是 GitHub 上的一个[开源项目](https://github.com/tensorflow/swift)。据 ADT 杂志报道，该项目于今年早些时候开始，名为“tensor flow integrated with Swift”(tfi ws)，后来更名为目前的化身。据《华盛顿邮报》报道，选择 Swift 是因为该语言的轻量级语法、现代设计、脚本功能、包含解释器及其在笔记本环境中的性能。首先，请务必查看 GitHub 上 Google 的“ [Swift for TensorFlow 设计概述](https://github.com/tensorflow/swift/blob/master/docs/DesignOverview.md)”文档。

*   **谷歌的开源沙盒容器运行时:**继续谷歌的开源路线，该公司宣布了其[开源沙盒容器运行时 gVisor](http://cloudplatform.googleblog.com/2018/05/Open-sourcing-gVisor-a-sandboxed-container-runtime.html) ，并指出，尽管容器已经彻底改变了“我们开发、打包和部署应用程序的方式”，但“许多安全专家[并不建议它们运行不可信或潜在恶意的应用程序](https://opensource.com/business/14/7/docker-security-selinux)。”作为回应，该公司生产了“ [gVisor](https://github.com/google/gvisor) ”，这是一种新的沙箱，有助于为容器提供安全隔离，同时比虚拟机(VM)更轻量级。根据公告，gVisor 提供了“容器的易用性和可移植性，以及虚拟机的资源隔离。”在 GitHub 上查看[回购](https://github.com/google/gvisor)并加入[谷歌群](https://groups.google.com/forum/#!forum/gvisor-users)。
*   谷歌的保密计算开源框架:好的，在我们继续之前，还有一个关于面向大众的利他开源软件的声明。这一次，是谷歌的 [Asylo:一个用于机密计算的开源框架](http://cloudplatform.googleblog.com/2018/05/Introducing-Asylo-an-open-source-framework-for-confidential-computing.html)，帮助开发者创建在[可信执行环境](https://en.wikipedia.org/wiki/Trusted_execution_environment) (TEEs)中运行的应用。“以前，在 TEE 中开发和运行应用程序需要专业知识和工具，”该公司写道。“Asylo 使开发者社区能够更广泛地访问 TEEs，跨越一系列硬件，包括内部和云中的硬件。”更多详情，查看帖子、[快速入门指南](https://asylo.dev/docs/guides/quickstart.html)、[文档](https://asylo.dev/docs)和 [GitHub](https://github.com/google/asylo) repo。
*   **Google Maps 现在包含计费、支持和云需求:**啊，终于——现在我们可以回到业务的正题了。正如 VentureBeat 所指出的，谷歌新的地图平台将于 6 月 11 日开始[提供现收现付、免费支持和云需求，这是“谷歌地图业务的大规模重组”](https://venturebeat.com/2018/05/02/google-maps-platform-arrives-with-pay-as-you-go-billing-free-support-and-cloud-requirement-starting-june-11/)[谷歌地图平台](https://cloud.google.com/maps-platform)“承诺简化的 API 产品、简化的客户体验、现收现付计费的单一定价计划、免费支持、单一控制台和新的行业解决方案”所有这些都包含在内——“从 6 月 11 日开始，您将需要有效的 API 密钥和谷歌云平台计费帐户才能访问核心的谷歌地图 API。”新平台旨在与现有代码一起工作，并将 18 个谷歌地图 API 合并为三个产品——地图、路线和地点。在其[公告](http://mapsplatform.googleblog.com/2018/05/introducing-google-maps-platform.html)中，谷歌为现有用户提供了[指南。](https://cloud.google.com/maps-platform/user-guide)
*   **谷歌的。app TLD:** 来自谷歌的最后一点消息(一家下周将举行开发者大会的公司透露了不少消息，嗯？)公司也有[介绍。app，一个更安全的网络应用之家](http://developers.googleblog.com/2018/05/introducing-app-more-secure-home-for.html)。根据公告。应用程序 TLD 是“专门为应用程序和应用程序开发人员，增加了安全性”，要求所有 HTTPS。应用程序域。

*   **团队堆栈溢出:**也许，如果你厌倦了处理堆栈溢出的一般毒性，那么这将是给你的——[团队堆栈溢出](https://www.joelonsoftware.com/2018/05/03/announcing-stack-overflow-for-teams/)，在这里你可以直接从你的同事那里获得一些毒性！(我开玩笑，我开玩笑…) [团队堆栈溢出](https://stackoverflow.com/teams)“允许您在堆栈溢出上设置一个私人空间，您可以在这里提问，只有您的团队、公司或组织的成员才能看到这些问题。”为什么不坚持使用 Slack 或者创建一个公司维基呢？“任何为此目的使用过 wiki 的人可能都已经发现，实际上并没有太多的知识进入 wiki，而且没有什么特别有用的，没有得到更新，老实说，当你不知道它是否会对任何人有所帮助时，写一堆关于你的代码的 wiki 文档就像是一堆作业。[……]与聊天室不同，搜索实际上是有效的。它会为你找到一个问题及其答案，而不是一段琥珀中的对话。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>