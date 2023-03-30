# 本周编程:GitHub Codespaces 的可移植开发环境

> 原文：<https://thenewstack.io/this-week-in-programming-github-codespaces-portable-dev-environment/>

当我坐在这里写本周的专栏时，我正在做一些对我来说罕见的事情——使用一台真正的台式电脑、显示器、键盘、鼠标、扬声器，全部九个。我作为一名日常用户放弃台式机已经有十年了，其中大约一半的时间都在使用我值得信赖的 Chromebook，但那当然是作为一名作家，而不是开发者。

并不是说[不可能将 Chromebook 用于开发目的](https://thenewstack.io/week-programming-dogfooding-developers-chromebooks/)，但这往往是一项有点复杂的任务，有很多如果、和但是。然而，本周，我们在 GitHub Codespaces 的[到来，以及新更名的 Visual Studio Codespaces](https://github.blog/2020-05-06-new-from-satellite-2020-github-codespaces-github-discussions-securing-code-in-private-repositories-and-more/#codespaces) 的[旁边，看到了技术联姻的成果。如果你迷失在细节中，认为你看到了重影，你是也不是——这场婚姻是微软和 GitHub 的婚姻，红利在于科技记者](https://devblogs.microsoft.com/visualstudio/introducing-visual-studio-codespaces/)[欧文·威廉姆斯](https://char.gd/blog/author/owen)所说的[的到来，这意味着你的电脑不再重要](https://char.gd/blog/2020/github-codespaces-means-your-computer-doesnt-matter-anymore)。

好的，备份——微软制作了一直受欢迎的 [Visual Studio 代码](https://code.visualstudio.com/)，它最近以基于浏览器的 [Visual Studio Online](https://visualstudio.microsoft.com/services/visual-studio-online/) 的形式提供，在他们宣布更名的博客帖子中，他们写道“开发人员发现 Visual Studio Online 不仅仅是一个‘浏览器中的编辑器’。他们说‘这个云托管的开发环境的功能使它成为我想写所有代码的地方’。”所以现在， [Visual Studio Codespaces](https://visualstudio.microsoft.com/services/visual-studio-codespaces/) 就是那个空间，[降低了价格](https://devblogs.microsoft.com/visualstudio/introducing-visual-studio-codespaces/#lower-price)和[增加了功能](https://devblogs.microsoft.com/visualstudio/introducing-visual-studio-codespaces/#added-features)，比如一个“基本”实例类型，有两个虚拟内核、GB RAM 和 64gb SSD 存储。但是为什么就此打住呢？为什么不把那个婴儿放在 GitHub 上面？

是的，他们做到了，Williams 称之为“容器优势的终极体现，移动到云中，使你拥有的硬件完全无关紧要。”微软真的已经[给自己买了一个开发栈](https://thenewstack.io/this-week-in-programming-microsoft-buys-itself-an-open-source-javascript-dev-stack/)，嗯？在 GitHub 上托管您的代码，从 npm 中提取 Javascript 包，并在 Azure 上运行所有这些，同时在代码空间中编码。

Williams 解释说，GitHub 不需要在每台设备上设置您的环境，而是自动获取您的所有依赖项、SSH 密钥、[个人点文件](https://help.github.com/en/github/developing-online-with-github-codespaces/personalizing-github-codespaces-for-your-account)并配置您的远程环境，“就像您在现有的计算机前一样”，他认为这一结果具有开创性。

“从能够在设备之间移动时完成工作的角度来看，很难低估这是多么令人兴奋——这意味着我不需要从 iPad 切换到 Surface Book 来快速修复错误，也不需要启动一个环境。威廉姆斯写道:“我可以直接进入编辑器，修复错误，运行终端命令，验证它是否正常工作，然后推送代码。

这场革命的真正部分是，对于那些仍然依赖台式机工作站或笔记本电脑的人来说，Chromebook(甚至 iPad)现在提供了一个副本开发环境，可以直接插入到现有的配置和堆栈中，使远程开发变得轻而易举。如果你问我的话，我觉得很不错。

## 本周的节目中

*   **GitHub 推出讨论&更多:**除了代码空间，GitHub 本周在其 [2020 卫星虚拟会议](https://githubsatellite.com/)上推出了其他几个功能，包括 [GitHub 讨论、保护私有存储库中的代码，等等](https://github.blog/2020-05-06-new-from-satellite-2020-github-codespaces-github-discussions-securing-code-in-private-repositories-and-more/)。例如，GitHub Discussions 为软件社区提供了一种在代码库之外协作的新方式，而不是依赖于拉请求。它提供了问答功能、用于更好地组织对话的线索化格式，甚至还有一个存放常见问题解答和其他协作文档的地方。新的[代码和秘密扫描](https://github.blog/2020-05-06-new-from-satellite-2020-github-codespaces-github-discussions-securing-code-in-private-repositories-and-more/#security)功能建立在现有集成的基础上，现在可用于私有存储库，而 [GitHub 私有实例](https://github.blog/2020-05-06-new-from-satellite-2020-github-codespaces-github-discussions-securing-code-in-private-repositories-and-more/#private)提供“即使是严格监管的客户的协作”如果你错过了公告，不要担心，你可以随时观看整个 12 小时的会议。

*   **VS Code 增加 GitHub 问题集成:**到现在为止，几乎民间传说[上下文切换是开发人员生产力的祸根](https://simpleprogrammer.com/context-switching/)，因此似乎每个新的 IDE(或代码编辑器)功能都提供了某种集成来防止这种令人担心的疏忽。最近的一个此类特性是本周在 Visual Studio 代码中添加了 [GitHub 问题，它作为](https://code.visualstudio.com/blogs/2020/05/06/github-issues-integration) [GitHub 拉请求和问题](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)扩展(以前称为 GitHub 拉请求)到来，与 Visual Studio 代码 1.45 兼容。“问题和拉请求经常是携手并进的，”VS 代码团队写道，作为将两者合并成一个扩展的解释，并指出他们使用了一个扩展而不是烘焙它，因为不是每个人都使用 GitHub。如果你真的想深入扩展，让 GitHub 团队展示，而不是讲述。

[https://www.youtube.com/embed/T6sW1Dk9B4E?feature=oembed](https://www.youtube.com/embed/T6sW1Dk9B4E?feature=oembed)

视频

*   **反思新冠肺炎期间的开发人员习惯:**鉴于 GitHub 在开发人员世界中有些独特和无处不在的地位，本周我们提供了来自 GitHub 的最后一个花絮，因为该公司在新冠肺炎早期考察了[开发人员的生产力、工作节奏和协作。在其特别的 Octoverse 报告中，它探讨了向远程工作的转变如何影响开发人员，重点关注三个主题:生产力和活动、工作节奏和协作。虽然调查结果表明，当将 2020 年的前三个月与 2019 年同期相比时，](https://github.blog/2020-05-06-octoverse-spotlight-an-analysis-of-developer-productivity-work-cadence-and-collaboration-in-the-early-days-of-covid-19/)[开发人员的活动基本保持一致](https://github.blog/2020-05-06-octoverse-spotlight-an-analysis-of-developer-productivity-work-cadence-and-collaboration-in-the-early-days-of-covid-19/#firsttheme)，但与此同时，[工作节奏发生了变化](https://github.blog/2020-05-06-octoverse-spotlight-an-analysis-of-developer-productivity-work-cadence-and-collaboration-in-the-early-days-of-covid-19/#secondtheme)，开发人员的工作时间变长了，并对倦怠产生了一些影响。从好的方面来看，该公司发现[人们正在更多地合作，尤其是在开源项目上](https://github.blog/2020-05-06-octoverse-spotlight-an-analysis-of-developer-productivity-work-cadence-and-collaboration-in-the-early-days-of-covid-19/#thirdtheme)，其中许多项目实际上可能会解决与流行病相关的问题。点击查看预期的图表和详细信息。
*   **Android 11 测试版在新冠肺炎重新安排:**谷歌为你们这些 Android 开发者写了一些新的 [Android 11 测试版计划](http://developers.googleblog.com/2020/05/android-11-beta-plans.html)，指出“当我们开始计划 Android 11 时，我们没有预料到这些变化会在世界上几乎每个地区发生在我们所有人身上。”作为回应，该公司已经制定了一个新的时间表，在本周发布了第四个开发者预览版，将 Beta 1 迁移到 6 月 3 日。作为谷歌 I/O 的替代，该公司将于美国东部时间 6 月 3 日上午 11 点开始推出[# Android 11:Beta 发布秀](https://developer.android.com/android11)，展示“Android 开发者的 Android 新功能”。

https://youtu.be/gqJEcy57hA8

*   **WWDC 虚拟化:**谈到移动开发和取消的开发者大会，WWDC 苹果开发者大会宣布[将于 6 月 22 日举办“第一个全球在线 WWDC”](https://developer.apple.com/news/?id=05052020a)。为了跟上进度，该公司建议下载苹果开发者应用程序，对于“学生开发者”来说，还有一周多的时间向 [Swift 学生挑战赛](https://developer.apple.com/wwdc/swift-student-challenge/)提交 Swift 操场，以赢得一些 WWDC20 奖品——因为毕竟没有奖品的会议是什么？
*   C 和 PHP: 最后，本周，我们有几个故事围绕着一些古老的编程语言，这些语言在现代堆栈中仍然占有一席之地。首先，JAXEnter 评论说 [C 超过 Java 成为月度 TIOBE 指数中排名第一的编程语言](https://jaxenter.com/c-programming-may-2020-171598.html)，该指数根据搜索引擎结果跟踪编程语言的受欢迎程度。TIOBE 指数将 C 语言排在第一位，并认为原因可能是“原因之一可能是冠状病毒”，以及“嵌入式软件语言如 C 和 C++越来越受欢迎，因为它们被用于医疗设备的软件中。”至于 PHP，本周一篇文章登上了《黑客新闻》的头条，文章认为 [PHP 在 7.4](https://lwn.net/SubscriberLink/818973/507f4b5e09ab9870/) 版本中显示出了它的成熟。今年是 PHP 诞生 25 周年，作者写道“希望随着年龄的增长，智慧和成熟会随之而来”，现代 PHP“已经发展到能够应对过去的批评，以及未来的发展。”继续读下去，看看 PHP 中 OOP 的发展，适当的依赖管理和第三方扩展，以及这种语言中如此多的人讨厌的安全性的增加——因为他们指出的可能根本不是好理由。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>