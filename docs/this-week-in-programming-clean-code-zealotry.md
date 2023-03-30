# 本周编程:清洁代码狂热

> 原文：<https://thenewstack.io/this-week-in-programming-clean-code-zealotry/>

一切都变得更好，干净整洁，对吗？在 T1 之前，我们从来没有进行过这样的辩论。

好吧，撇开讽刺不谈，开发人员可以努力确保他们的代码尽可能的干净、整洁和高效，本周，[丹·阿布拉莫夫](https://overreacted.io/)在一篇博客文章中对[的干净代码](https://overreacted.io/goodbye-clean-code/)说再见，这篇文章探讨了这种对干净代码的渴望以及它是如何达到不尽如人意的结果的。

在检查一位同事的代码时，Abramov 发现了一个明显的机会，可以将事情分解成可重用的部分，并组合它们的行为。

“代码是总大小的一半，重复的部分完全消失了！如此干净，”他写道。不幸的是，他的兴高采烈只持续了这么长时间，直到他的老板要求他恢复这些变化。"我不情愿地答应了，但过了几年我才明白他们是对的。"

阿布拉莫夫给那些仍在喋喋不休地谈论“干净”代码的开发人员上了一课:

一旦我们学会了如何创建[抽象](https://www.sandimetz.com/blog/2016/1/20/the-wrong-abstraction)，每当我们看到重复的代码时，就会很容易获得这种能力，并从稀薄的空气中提取抽象。经过几年的编码，我们看到重复无处不在——抽象是我们新的超能力。如果有人告诉我们抽象是一种美德，我们会吃了它。我们会开始评判其他不崇拜“清洁”的人

不要做一个干净的代码狂热者。干净的代码不是目标。这是一种试图从我们正在处理的系统的巨大复杂性中找到某种意义的尝试。当你还不确定一个变化会如何影响代码库，但是你在未知的海洋中需要指导时，这是一种防御机制。

现在，关注编程世界的最新消息，因为在几周的假期后，我们有一些东西要谈。

https://www.youtube.com/watch?v=2BdBfsXbST8

## 本周的节目中

*   据 InfoWorld 报道，熊猫 1.0 Python 包带来了突破性的变化:熊猫 Python 数据分析包，其名字来源于“panel data”，正在向 1.0 迁移，并带来了一些[大的突破性变化](https://www.infoworld.com/article/3513440/pandas-10-brings-big-breaking-changes.html)。InfoWorld 写道，1.0 候选版本的到来“移除了许多功能，并摒弃了许多其他功能”，并且需要 Python 3.6.1 或更好的版本，所以如果你在这一点上仍然落后…稍后再详细说明。总的来说，熊猫 1.0 的变化意味着熊猫的一些 API 现在是[向后不兼容的](https://dev.pandas.io/docs/whatsnew/v1.0.0.html#backwards-incompatible-api-changes)，并且有一个列表[所有的特性都被否决](https://dev.pandas.io/docs/whatsnew/v1.0.0.html#deprecations)。至于未来的弃用，Pandas 已经为 Pandas 的未来版本采用了[新的支持政策，确保弃用和 Python 版本支持的变化将仅限于主要版本——“次要版本将弃用特性，但不会删除它们；InfoWorld 写道:“主要版本将会删除一些特性。如果你使用的是旧版本的 Pandas，这篇文章提供了各种更新的方法，我们建议你在更新之前通读一遍。](https://dev.pandas.io/docs/development/policies.html#policies-version)
*   **你对 Python 2 的生命终结有什么计划？**在[进行的一项关于 Python 2 最终寿终正寝的调查](https://www.activestate.com/resources/white-papers/python-2-eol-survey-results/)发现，大约一半的受访者[没有 Python 2 寿终正寝的计划](https://sdtimes.com/softwaredev/report-50-of-companies-dont-have-a-plan-for-python-2-eol/)，31%的组织没有 Python 3 迁移计划。如果你的 Python 更新落后了十年，那么这篇关于 [Mercurial 的 Python 3](https://gregoryszorc.com/blog/2020/01/13/mercurial's-journey-to-and-reflections-on-python-3) 之旅和反思的博客文章可能会帮助你摆脱那 50%的人，他们发现自己完全没有为即将到来的更新做好准备。在这篇文章中，作者提供了“对 Mercurial 的 Python 3 移植工作的大部分事实叙述，以及对向 Python 3 的过渡和 Python 语言生态系统作为一个整体的更有见解的评论。”

*   **GitHub for Android Beta 到来:**哦，技术——这是一把双刃剑，不是吗？作为一个在过去十年的大部分时间里都是远程工作者的人，我非常清楚在手机上查看我的电子邮件和 Slack 以及所有工作内容是多么有用，同时，这又是多么麻烦。好吧，你下一个最喜欢的球和链刚刚抵达 Android，亲爱的开发者，随着[GitHub for Android beta](https://github.blog/2020-01-14-the-github-for-android-beta-is-here/)的[到来。GitHub 在其博客上写道:“有了 GitHub for mobile，无论你身在何处，你都可以灵活地推进工作，并与你的团队保持联系，”GitHub 没有提到它有多可怕和多棒，它将能够在海滩上直接评论 GitHub 问题。该公司在 2019 年 GitHub Universe 活动期间推出了 GitHub for mobile，推出了 iOS 测试版，现在已经推出了](https://github.com/mobile) [GitHub for Android beta](https://github.com/mobile) 。
*   **迈向 PHP 8:** PHP 7 与过去的 PHP 大相径庭，任何 PHP 开发者都会让你知道，PHP 的下一个版本预计将于今年某个时候发布。如果你正在积极地用 PHP 开发，这可能是值得关注的事情，这篇关于 PHP 8 中的[新特性的博客文章说，这将是“一个最新的列表，列出了预期会出现的东西:新特性、性能改进和突破性变化。”除了突破性的变化，PHP 8 还有一些值得期待的特性，包括](https://stitcher.io/blog/new-in-php-8)[、JIT 编译器](https://stitcher.io/blog/new-in-php-8#jit-rfc)和[联合类型](https://stitcher.io/blog/new-in-php-8#union-types-rfc)，如果你担心突破性的变化，它们在[升级](https://github.com/php/php-src/blob/master/UPGRADING#L20)文档中有完整的列出，尽管作者指出不必太担心，因为“这些突破性的变化在以前的 7 中已经被否决了。*版本，所以这些年来你一直保持更新，升级到 PHP 8 应该不难。”
*   **Git 2.25 引入部分克隆&稀疏校验:**Git 的最新版本——GitHub 和 GitLab 等服务背后的版本管理工具——有一个新版本正在开发中，GitHub 博客提供了 Git 2.25 的一些[亮点](https://github.blog/2020-01-13-highlights-from-git-2-25/)。随着 git 2.25 的[发布，有了新的特性和错误修复，其中最值得注意的是“部分克隆支持”和“稀疏检出”“部分克隆”确切地说是对回购协议的克隆，只是克隆了部分回购协议，而不是全部，但这种克隆的执行及其含义可能会更复杂一些。这个特性在 Git 中还处于试验阶段，GitHub 还不支持它。同时，稀疏签出允许类似的功能，因为它允许您签出特定回购的一部分，而不是全部。在这样的博客文章中。在 2.25 中，Git 向为所有用户带来成熟且可配置的部分克隆支持又迈进了一步。“git 稀疏检出命令背后的想法很简单:让用户尽可能容易地使用部分克隆和稀疏检出，”他们写道。它可以做四件事:设置要签出的路径列表，打印当前列表，以及完全启用或禁用稀疏签出关于 git 2.25 中其他新特性的完整细节，请查看完整的博客文章。](https://lore.kernel.org/git/xmqqtv4zjgv5.fsf@gitster-ct.c.googlers.com/)

*   **脸书的 2019 年开源:**现在还是一月，所以“一年回顾”的帖子不是不可能的……我猜。脸书的工程博客本周回顾了其[开源年](https://engineering.fb.com/open-source/open-source-2019/)，指出 2019 年是“我们[开源](https://opensource.facebook.com/)工程师忙碌的一年”，发布了 170 个新的开源项目，使总数达到 579 个[活动库](https://opensource.facebook.com/)。这篇博客文章介绍了去年一些最大的发布，包括对脸书开发的开源深度学习平台 [PyTorch](https://pytorch.org/) 的补充， [React](https://reactjs.org/) 和 [React Native](https://facebook.github.io/react-native/) JavaScript 库， [Hermes](https://engineering.fb.com/android/hermes/) ，开源 JavaScript 引擎， [Magma](https://engineering.fb.com/open-source/magma/) ，一个帮助运营商部署移动网络的平台，以及简化 Python 应用程序开发的框架 [Hydra](https://engineering.fb.com/open-source/hydra/) 换句话说，我们可以感谢脸书同时促成了《真理与幸福》的消亡，同时也在开源软件领域取得了长足的进步。
*   **Oooh，开发人员的(另一种)字体:** JetBrains，Kotlin 和 IntelliJ IDE 的制造商，已经为开发人员推出了 [JetBrains Mono，](https://www.jetbrains.com/lp/mono/)这是一种免费的开源字体——鉴于开发人员对字体和黑暗模式等东西的喜爱，我们认为我们不能错过在这里包括它。该字体旨在提高代码的可读性，并做一些事情，如在零内放置一个点，以帮助区分它与大写的“o”。最有争议的方面，它将[显示为](https://news.ycombinator.com/item?id=22053998)，来自字体的“连字”使用，这是由两个或更多连接符号组成的字符-换句话说，您的注释代码将不再是几个破折号，而是显示为合并的破折号。

来自 Pixabay 的 Sasin Tipchai 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>