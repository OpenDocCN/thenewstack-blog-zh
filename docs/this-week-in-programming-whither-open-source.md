# 本周编程:开源比以往更好也更差

> 原文：<https://thenewstack.io/this-week-in-programming-whither-open-source/>

本周，我们看到了两条截然相反的科技新闻，很难想象它们会占据相同的现实。首先，Register 给我们带来了 Linux Journal [第二次](https://www.linuxjournal.com/content/so-long-and-thanks-all-bash)[关闭](https://www.linuxjournal.com/content/linux-journal-ceases-publication-awkward-goodbye)的故事，也是 25 年后[、](https://www.linuxjournal.com/content/linux-journal-ceases-publication-awkward-goodbye)最后一次，该杂志的主编[向专有软件](https://www.theregister.co.uk/2019/08/08/linux_journal_closes_again_editor_says_os_buried_under_proprietary_software/)开了最后一枪，告诉 Register 他担心“如果目前的趋势继续下去，我们可能会回到一个专有软件、供应商锁定和封闭协议的世界，就像 1994 年之前的世界一样。”

与此同时，InfoWorld 的开源爱好者 Matt Asay 本周表示，开源从未像现在这样强大，而且“从来没有比现在更清楚的证据表明我们正处于开源的黄金时代。”

也许这两种观点可以占据同一个宇宙？

注册处引用 Linux 杂志编辑凯尔·兰金的话说:

*Linux 和 FOSS 比以往更加隐蔽。GitHub 上的许多自由/开源软件项目最终都被用作专有软件的构建模块。如此多的公司似乎通过帮助他们所依赖的上游项目来支持自由/开源软件，也选择保持他们自己编写的项目的私有性。尽管 Linux 主导着云，但是越来越多使用云的开发人员和系统管理员通过专有 API 和专有服务来使用云。*

另一方面，Asay 指出 Kubernetes、TensorFlow 和 Azure Functions 等众多功能证明了“开源从未如此健康”，写道“云——是的，所有这些——是公开其操作的开源基本构件。谷歌率先推出 Kubernetes 和 TensorFlow 等项目，理所当然地获得了赞誉，但其他公司也纷纷效仿。

当然，对于什么构成了这样一个黄金时代，观点有很大的不同。对 Rankin 来说， [2007 年是那个时代](https://www.linuxjournal.com/content/what-linux-journals-resurrection-taught-me-about-foss-community)，那时“自由/开源软件的拥护者[……]经常在运行 Windows 或 macOS 的专有笔记本电脑上展示自由/开源软件的好处。”然而，Asay 指出，与此同时，Red Hat 首席执行官吉姆·怀特赫斯特呼吁企业更多地参与开源，这导致了当今的复兴，其中“这种参与既发生在精英层面(公共云)，也以更主流的方式发生，迎来了开源的黄金时代。”

关于情人眼里出西施，对吧？

如果这对你来说还不够，为什么不从分析编程语言开始你的周末呢:

[https://www.youtube.com/embed/6EdFiISk22k?start=1&feature=oembed](https://www.youtube.com/embed/6EdFiISk22k?start=1&feature=oembed)

视频

## 本周的节目中

*   **GitHub 全面推出 CI/CD:** 继[去年推出动作](https://thenewstack.io/this-week-in-programming-github-dives-into-devops-with-actions/)之后，GitHub 已经[通过](https://thenewstack.io/github-expands-into-continuous-integration-and-deployment/)[增加 CI/CD 功能](https://github.blog/2019-08-08-github-actions-now-supports-ci-cd/)满足了每个第一次看到该功能的人的最终愿望。当然，CI/CD 领域的其他人都发表了他们自己关于这个主题的博客文章——参见 [GitLab 关于其在该领域进展的更新](https://about.gitlab.com/2019/08/07/a-look-ahead-for-gitlab-cicd/)和 [BitBucket 对其产品的类似总结](https://bitbucket.org/blog/10-things-to-look-for-when-adopting-a-cloud-ci-cd-tool) —因为 GitHub 加入这场争斗肯定会对他们的底线构成威胁。这里最简洁的部分可能是您现在可以对 CI/CD 工作流进行开源处理。GitHub Actions 现在支持 Node.js、Python、Java、PHP、Ruby、C/C++、。它允许用户“在任何平台上自动构建、测试和部署你的项目，包括 Linux、macOS 和 Windows。”说到 GitHub，Actions 的 CI/CD 功能将与 11 月 13 日至 14 日举行的 [GitHub Universe 2019](https://github.blog/2019-08-01-why-you-need-to-be-at-github-universe-2019/) 同时上市。

*   **脸书开源滥用内容检测技术:** ProgrammableWeb 为我们带来了[脸书开源其视频和照片匹配技术](https://www.programmableweb.com/news/facebook-to-open-source-video-and-photo-matching-technology-to-stop-abusive-content/brief/2019/08/05)的消息，该技术旨在“减少有害的互联网内容，如剥削儿童、恐怖主义宣传和图形暴力。”[时间匹配内核](https://github.com/facebook/ThreatExchange/tree/master/hashing/tmk)基本上使开发者可以通过检测相似的(如果不是相同的)内容来轻松阻止视频的病毒式传播。同样，脸书的照片匹配技术 PDQ 也为图片提供了同样的功能。
*   **Android Q 在发布前达到最终测试版:**谷歌宣布 Android Q 的[最终测试版更新，最新 Android 的预期发布只有几周时间。对于开发人员来说，这当然意味着是时候确保您的应用程序已经为这些变化做好准备了。所以，现在是时候给 Android Q 一个测试，确保它与新的隐私功能相结合，并且不使用受限制的非 SDK 接口，等等。当然，仅仅是功能性是最起码的——Android Q 还提供了你可以实现的新功能，比如黑暗主题、手势导航、支持可折叠设备以及其他](http://android-developers.googleblog.com/2019/08/final-beta-update-official-android-q.html)[新功能和 API](https://developer.android.com/preview/api-overview.html)。

*   关于 Quarkus 的最新消息: JAXEnter 采访了自称“Java 冠军”[的 Alex Soto](https://www.linkedin.com/in/asotobu) 关于[轻量级 Java 框架 Quarkus](https://jaxenter.com/quarkus-whats-next-for-the-lightweight-java-framework-160793.html) 的下一步。到达版本 0 . 20 . 0——Soto 指出该框架每两周推出一个版本——他们经历了最新的功能，包括对 OAuth 2 的支持和如何在微软 Azure 中部署 [Quarkus](https://quarkus.io/) 的指南，以及项目的历史等等。对于那些不熟悉 Quarkus 的人来说，[新的堆栈也在今年早些时候描述了该技术](/red-hats-quarkus-brings-natively-compiled-java-to-kubernetes/)，而且 Soto 的一份 [Quarkus 备忘单](https://jaxlondon.com/quarkus-beginners-guide-cheat-sheet/)也可以在 JAXEnter 上找到。如果你不想点击进入，这里有一个要点:“这是一个开源项目，这意味着 1.0.0 版本将在准备好的时候准备好，但我们计划在日历年内推出。我们对 Quarkus 的代码质量非常有信心——至少运行时代码调用的框架是坚如磐石的(Netty、Vert.x、RESTEasy、Hibernate ORM、Camel 等)。).它不在 1.0 中的原因是我们还没有准备好将一些扩展 API 固定下来。我们还在完善生态系统模型，并希望它在 1.0 发布时出现。也就是说，我们知道很多公司正在生产 Quarkus。最终，版本号只是一个数字，我们以一种生产就绪的方式处理所有版本。”

*   **Visual Studio 代码 Python 扩展更新:**微软针对 Visual Studio 代码的 Python 扩展已经[发布](https://devblogs.microsoft.com/python/python-in-visual-studio-code-august-2019-release/)并附带[共 76 期](https://github.com/Microsoft/vscode-python/blob/master/CHANGELOG.md)被关闭，包括 [Jupyter 笔记本单元格调试](https://twitter.com/davorabbit/status/1149062343231455238)，一个 insiders 程序的引入，以及对自动缩进和 Python 语言服务器的改进。“insider's program”是可选择加入的，它允许您“通过每周或每天自动安装 Python 扩展的最新内部版本，在发布日期之前尝试新的功能和修复”，同时 Python 语言服务器的改进增加了一些新功能[到“转到定义”和“转到声明”注意，微软也已经开始 A/B 测试一些功能，如果你不想参与其中，只需在 Visual Studio 代码](https://github.com/microsoft/python-language-server/issues/1138)中[禁用遥测。](https://code.visualstudio.com/docs/getstarted/telemetry)

https://twitter.com/donnacamos88/status/1158474560989204482

红帽是新堆栈的赞助商。

来自 Pixabay 的 Couleur 的特写图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>