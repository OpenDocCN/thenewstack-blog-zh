# 本周编程:挑剔的开发者选择 GIF

> 原文：<https://thenewstack.io/this-week-in-programming-choosy-developers-choose-gif/>

这些年来，它已经被彻底挑剔过了，但显然我们都在为如何在 Twitter 上再次念出“GIF”而争吵。才过了 32 年吧。

虽然网络语言学家格雷琴·麦卡洛克说她已经写了关于这件事的“权威文章”[，文章基本上说这两种情况都有可能发生，但我个人认为网页设计师阿龙·巴兹内](http://mentalfloss.com/article/69147/why-pronunciation-gif-really-can-go-either-way)(他成功地保护了域名[howtoreallypronouncegif.com](http://howtoreallypronouncegif.com/))的观点非常简单，非常有说服力:“这是最自然、最符合逻辑的发音方式。这就是为什么当每个人第一次遇到这个词时，他们会用一个硬 g，”Bazinet 这样描述这场辩论的起源:

*“GIF 图像格式的创造者，CompuServe 的史蒂夫·威尔海特在决定发音时，说他故意选择模仿美国花生酱品牌 jif，CompuServe 的员工经常说‘挑剔的开发者选择 GIF(Jif)’,播放 Jif 的电视广告。如果你听到有人发 GIF 的音带软 G，那是因为他们对这段历史有所了解。”*

[https://www.youtube.com/embed/CBtKxsuGvko?feature=oembed](https://www.youtube.com/embed/CBtKxsuGvko?feature=oembed)

视频

然而，麦卡洛克指出，这种差异存在于语言的许多部分，应该被接受，而不是武器化。

关键是，这个世界上还有很多其他单词的拼写根本没有翻译成预期的发音。

林克德。集装箱。SQL。这些只是几个例子。

有时候，我想知道这是不是技术世界通过选择明显违背常理的发音来辨别谁是内行，谁是技术专家——麦卡洛克提到的武器化。这就像休斯顿街(对《纽约客》来说，这是“how-stin”而不是德克萨斯的“hyu-stuhn”)或沙发街(亲爱的波特兰…“cooch”)。实际上)或庄园路。(奥斯汀喜欢这里的“may-ner”)。

如果发音是“容器-迪”和“链接器-迪”，为什么没有视觉线索？至少为什么没有大写的 D？还有为什么把“SQL”念成“sequel”呢？

因为这是进入酷孩子俱乐部的秘密密码……或者，更确切地说，是进入这个以文本交流为主的新时代的结果，在这个时代，发音仅次于单词的创造。在过去，口语首先出现，然后被编纂成字母和拼写，但现在情况发生了变化，我们发现自己花了几十年的时间来辩论它是“gif”还是“jif ”,因为发明这个标准的人碰巧想以某种方式发音这个单词。

也许真正的解决办法是永远懒散地生活，忘记所有“说话”的事情——反正它只是一个遗留应用。

## 本周的节目中

*   **GitLab 增加秘密检测，开源 ChatOps:** 从本周开始，git lab[发布了 11.9 版本](https://about.gitlab.com/2019/03/22/gitlab-11-9-released/)，增加了一些有趣的功能，比如多个合并请求批准规则，最值得注意的是[秘密检测](https://about.gitlab.com/2019/03/22/gitlab-11-9-released/#detect-secrets-and-credentials-in-the-repository)。新功能扫描每个提交，以确保它不包含秘密，如 API 密钥，当它发现某些内容时，它会立即提醒开发人员合并请求，让他们有时间使有铅凭据无效并创建新凭据。(更多关于 GitLab 竞争对手 GitHub 的这类问题，请参阅 scope。)GitLab 的新版本也有助于审查过程，增加了“更好的控制和更多的结构以及[合并请求批准规则](https://about.gitlab.com/2019/03/22/gitlab-11-9-released/#merge-request-approval-rules)”GitLab 已经允许用户指定合并何时需要某人的批准，现在“可以向合并请求添加多个规则，以明确要求单个批准者，甚至要求来自特定组的许多批准者。”最后，GitLab 还决定[开源](https://about.gitlab.com/2019/03/22/gitlab-11-9-released/#move-chatops-to-core) [ChatOps](https://docs.gitlab.com/ee/ci/chatops/) ，它称之为“一个强大的自动化工具，允许你执行任何 CI/CD 作业，并直接从 Slack 和 Mattermost 等聊天应用程序接收作业状态。”
*   **与此同时，在 GitHub:** 谈到漏洞和代码库，ProgrammableWeb 讲述了一些[研究的故事，表明猖獗的 GitHub 数据泄露](https://www.programmableweb.com/news/research-indicates-rampant-github-data-leaks/brief/2019/03/22)，你猜对了，“数量惊人的 API 令牌和密钥”这份总结报告，题为“[它能坏到什么地步？描述公共 GitHub 存储库的秘密泄露](https://www.ndss-symposium.org/wp-content/uploads/2019/02/ndss2019_04B-3_Meli_paper.pdf)，”描述了对 GitHub 上大约 13%的开源存储库进行的为期六个月的扫描，发现“超过 100，000 个存储库遭受秘密信息泄露”，每天都有数千个新的泄露发生，称这个问题非常严重，远远没有解决。GitHub 回应称，许多泄露的令牌很可能是无效的，他们自己的做法“包括在泄露被公开的几秒钟内通知服务提供商”，以及采用“[令牌扫描](https://help.github.com/en/articles/about-token-scanning)”，该扫描“通知服务提供商超过 1 亿个潜在的令牌匹配，以进行验证和撤销。”

*   **微软和脸书推出开源 Python 工具:**本周，Python 社区迎来了两款新的开源工具。首先，InfoWorld 告诉我们[微软的 Python 快速类型检查器](https://www.infoworld.com/article/3379122/microsoft-unveils-speedy-type-checker-for-python.html#tk.rss_opensourcetools)，名为 [Pyright](https://github.com/Microsoft/pyright) ，这是一个针对 Python 的开源静态类型检查系统，“旨在比现有的 Python 类型检查解决方案如 Mypy 更快。”该工具是用 TypeScript 编写的，在 Node.js 上运行，不需要现有的 Python 运行时即可运行，主要意思是“用作 Visual Studio 代码插件，但也可以作为独立的命令行工具运行。”微软夸口说 Pyright 比其他用 Python 编写的 Python 类型的检查器“通常 5X 更快”，比如 Mypy、Pytype 和 Pyre 接下来，脸书宣布它是[开源 Python 测试运行器](https://code.fb.com/open-source/python-test-runner/) (ptr)，它允许开发者运行 Python 单元测试套件。Python Test Runner“搜索一个存储库，以找到在其安装文件中定义了单元测试的 Python 项目”，然后“用配置好的启用步骤并行运行每个套件。”它可以在 Linux、MacOS 和 Windows 上运行，并且可以在 [Github](https://github.com/facebookincubator/ptr) 和 [PyPI](https://pypi.org/project/ptr/) 上获得。
*   **Swift Five 是活的:**接下来，关于 Swift 5 的[发布，苹果称之为“语言进化的一个重要里程碑”根据新闻稿，随着 Swift 应用程序二进制接口](https://swift.org/blog/swift-5-released/) (ABI)的[稳定性，“Swift 运行时现已包含在苹果平台操作系统的当前和未来版本中:macOS、iOS、tvOS 和 watchOS”，重点是 Linux、Windows 和其他操作系统，因为这些操作系统上的 Swift 开发已经成熟。最新版本还包括“字符串的重新实现、运行时对内存的独占访问、新的数据类型以及对动态可调用类型的支持。”一个](https://swift.org/blog/abi-stability-and-more/)[游乐场](https://github.com/twostraws/whats-new-in-swift-5-0)可以用来玩一些新功能，用于 Swift 5 的 Swift 编程语言的更新版本[也可以在](https://docs.swift.org/swift-book/)[苹果书店](https://itunes.apple.com/us/book/the-swift-programming-language/id881256329?mt=11)免费获得。

[https://www.youtube.com/embed/WlgJs_G8Co8?feature=oembed](https://www.youtube.com/embed/WlgJs_G8Co8?feature=oembed)

视频

*   我们应该害怕企业驱动的编程语言吗？这是 Matt Asay 在[InfoWorld](https://www.infoworld.com/article/3383246/programming-languages-are-now-driven-by-corporations-should-we-be-worried.html#tk.rss_opensourcetools)最近的一篇报道中提出的问题，在这篇报道中，他展示了编程语言发展的一些历史，并展望了由企业驱动的[编程语言的趋势](https://www.infoworld.com/article/3383246/programming-languages-are-now-driven-by-corporations-should-we-be-worried.html#tk.rss_opensourcetools)。Asay 将 20 世纪 90 年代称为“随心所欲的黑客时代”，描绘了一幅“一个饥饿的博士生可以即兴创作一种新的编程语言，几年内全世界都在使用它”的画面。当然，这与 2010 年代相比，当时“企业驱动的语言占主导地位”，而且“正如 Kotlin 和 Go 等语言越来越受欢迎所证明的那样，似乎一种新的编程语言获得巨大成功的唯一途径是得到大公司的慷慨支持。”请继续阅读一些有见地的分析，了解语言正在发生什么，以及企业如何仍然试图以这样或那样的方式将每个人都锁定在开源或不开源的范围内。
*   在我们本周离开之前，还有一些事情需要指出。首先，JAXEnter 向我们讲述了 [Mozilla 如何结合 Python 和 JavaScript，在您的浏览器](https://jaxenter.com/mozilla-iodide-python-157213.html)中创建交互式数据科学，并使用了一个名为碘化物的工具，这是一个“用于网络科学交流和探索的开源实验工具”然后还有 [Pyodide](https://github.com/iodide-project/pyodide) ，它“编译 Python 科学堆栈以在 WebAssembly 中运行。”有一个[演示你可以和](https://alpha.iodide.io/tryit)一起玩，还有一个[游览](https://alpha.iodide.io/notebooks/154/)，但是他们注意到整个事情还在 alpha 阶段，所以买家要小心。我们注意到的下一个有趣的事情是 [Codestream](https://www.codestream.com/) ，它被 [SDTimes 称为代码](https://sdtimes.com/softwaredev/codestream-google-docs-for-code/)的 Google Docs。Codestream“与 ide 中的代码放在一起，允许开发团队轻松地审查和评论代码”，而不是让开发人员之间的评论讨论或不得不单独处理所有事情来混淆您的代码。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>