# 本周编程:Perl 7 带来了“不同的、更合理的、更现代的缺省值”

> 原文：<https://thenewstack.io/this-week-in-programming-perl-7-brings-different-saner-more-modern-defaults/>

当谈到不可靠的版本编号时，我总是想引用一个古老的 Monty Python 语言, Perl 当然也不例外。本周,[发布了 Perl 7](https://www.perl.com/article/announcing-perl-7/) ，他们写道，“主要是 Perl 5.32。”

正如我们[之前探索过的](https://thenewstack.io/this-week-in-programming-less-than-random/)，从 Perl 5 到 Perl 7 的跳跃是因为 Perl 6 成为了一种与其前身完全不同的语言，以至于它决定这么做，最近被重命名为[樱庭落](https://raku.org/)并开始过自己的生活，非常感谢。在这个话题上，Perl 7 声明说“很久以前，我们认为一个非常雄心勃勃的重写工作将取代 v5.8。简而言之，那并没有发生，语言已经继续过着它自己的生活。所以，7 是下一个可用的数字。就是这样。它只是下一个基数。”如果您认为简单地转移到 Perl 7 很奇怪，该团队提供了几个其他奇怪版本号的例子，这样您就可以愉快地继续您的生活，希望再也不要提到 Perl 6。

继续前进，或者回到过去，Perl 7 基本上只是 Perl 5.32，“但是具有不同的、更合理的、更现代的缺省值。”本质上，Perl 7 添加了一些默认的东西，以前你每次都必须在代码的开头声明这些东西。至于 Perl 5 发生了什么，它将进入长期维护模式，这意味着它可能还有大约十年的支持时间。

那么，除了缺省值之外，Perl 7 还有什么新特性呢？这里的答案还是…没那么多。虽然有些东西从 Perl 5.32 中消失了，但是他们写道“再一次，这本质上是 Perl 5.32，旋钮和刻度盘在不同的地方。”与此同时，新的特性，如[后缀解引用](https://www.effectiveperlprogramming.com/2014/09/use-postfix-dereferencing/)或新的 isa 操作符，无需你做任何事情就可以使用。“这就是主要版本提供的新社会契约的好处。这是一个硬边界，新功能可以默认存在于一侧，而不会干扰另一侧，”他们写道。

总之，它们提供了一点 tldr“Perl 7 是具有不同设置的 v5.32。如果不是一团糟，你的代码应该可以工作。预计一年内会有用户发布。”

## 本周的节目中

*   **Python 希望添加模式匹配…再次:**这不是 Python 社区第一次陷入这种困境，在 2001 年[和 2006 年](https://www.python.org/dev/peps/pep-0275)[之前，他们至少两次考虑过模式匹配，但他们再次希望添加模式匹配语法，InfoWorld](https://www.python.org/dev/peps/pep-3103) [为我们带来了关于最新](https://www.infoworld.com/article/3563840/python-may-get-pattern-matching-syntax.html) [Python 增强提案(PEP) 622](https://www.python.org/dev/peps/pep-0622/) 的完整故事。他们写道，新提案“将最终为 Python 带来模式匹配语句语法”，并“为 Python 程序员提供更具表现力的处理结构化数据的方式，而不必求助于变通方法。”注意，这个特性在许多其他语言中都很常见，比如 C 语言中的 switch/case，模式匹配“允许根据给定变量或表达式的值采取多种可能的操作之一。”虽然之前的提议因缺乏支持而遭到拒绝，但 Python 创造者[吉多·范·罗苏姆](https://gvanrossum.github.io/)和其他几个人一起，再次尝试“为对象匹配提供正则表达式，而不仅仅是简单的 if/elif/else 替代”，提出了一个“受 Rust 和 Scala 中模式匹配工作方式启发”的提议
*   **亚马逊的无代码 Honeycode 到来:** [亚马逊网络服务的](https://aws.amazon.com/)最新工具，[亚马逊 honey Code](https://www.honeycode.aws/?&trk=el_a134p000003yCxVAAU&trkCampaign=pac-edm-2020-honeycode-homepage&sc_channel=el&sc_campaign=pac-edm-2020-honeycode-website_links-adoption-jeff_barr_blog_post_link&sc_outcome=Enterprise_Digital_Marketing&sc_geo=NAMER&sc_country=US)[于本周](https://aws.amazon.com/blogs/aws/introducing-amazon-honeycode-build-web-mobile-apps-without-writing-code/)推出，完全托管的 AWS 服务使其用户能够构建移动和网络应用程序，而无需编写任何代码。目前处于测试阶段，Honeycode 以一种熟悉的电子表格格式出现，如果你熟悉 Excel 或另一个电子表格程序中的公式，它的操作与你想象的差不多。在门外，Amazon Honeycode 附带了一些常见应用程序的模板，如创建待办事项列表或管理库存，这些模板是可定制的，随着您做出的更改而部署。该工具还包括许多“内置的、触发驱动的操作，可以生成电子邮件通知和修改表格”，以及“一长串内置函数”，看起来像是其他电子表格程序中的函数。首先，请访问 [Honeycode Builder](https://builder.honeycode.aws/) 网站并创建一个帐户。

[https://www.youtube.com/embed/zPupFm0BBFw?feature=oembed](https://www.youtube.com/embed/zPupFm0BBFw?feature=oembed)

视频

*   **WWDC 2020 年:**本周，苹果全球开发者大会首次进行了虚拟演示，至少[一些人](https://twitter.com/lizrice/status/1275121070870233090)认为这是对通常的直播形式的巨大改进。虽然我们不打算深入探讨这个问题，但看起来 iOS 开发者(或者你正在开发的任何其他基于苹果的操作系统)有很多新功能值得期待。本周,[推出了 Xcode 12](https://developer.apple.com/news/?id=qbomldbb) ,它带来了新的设计和默认构建通用应用的能力，增加了 [WidgetKit](https://developer.apple.com/news/?id=ou1gpq68) ,这是一个使构建 iOS、iPadOS 和 macOS 小工具更容易的框架，以及[推出了应用剪辑](https://developer.apple.com/news/?id=na4c37vj),允许开发者在用户下载完整应用之前提供某种应用预览。除此之外，苹果还为[机器学习](https://developer.apple.com/news/?id=aym5xv8b)和[增强现实](https://developer.apple.com/news/?id=1u5zg8ak)提供了更新，例如更容易地与第三方培训库合作的能力，以及 ARKit 4 的引入，它说“引入了全新的功能，使你的应用程序中的 AR 体验更加逼真。”当然，这只是皮毛，但是如果你想了解更多的细节，你可以看看今年发布的 18 个最大的公告。
*   **GitHub 增加 dependent bot 动作更新:**GitHub 的自动化依赖更新工具 dependent bot 如果不能更新还有什么用，对吧？嗯，GitHub 宣布[依赖机器人现在更新你的 GitHub 动作工作流程](https://github.blog/2020-06-25-dependabot-now-updates-your-actions-workflows/)，而不是要求你手动更新。随着这一变化，[dependent bot 版本更新](https://help.github.com/en/github/administering-a-repository/keeping-your-actions-up-to-date-with-github-dependabot)将定期检查您的工作流文件及其使用的操作，以查看是否有新版本可用，如果有，您将收到一个更新您的工作流以使用新版本的请求。如果这是您想要使用的特性，您需要将一个[dependent bot . yml 配置文件](https://help.github.com/en/github/administering-a-repository/enabling-and-disabling-version-updates#enabling-github-dependabot-version-updates)签入到您的存储库中。

*   **继续关注 Jakarta EE9 和云原生:**接下来，ADT 为我们带来了几个关于 Jakarta 的故事，Jakarta 是最近几年被 Eclipse 接管的新命名的 Java。这一点实际上是 Eclipse Jakarta EE 9 的主要特性之一，Eclipse Foundation 本周刚刚宣布了 Jakarta EE 9 的发布——“Jakarta ee9 的发布标志着 javax 的最终过渡。*命名空间(Oracle 拒绝放弃)到 Eclipse 的 jakarta。*.这个版本更新了所有的 API 来使用 jakarta。*在包名中，”ADT 写道。除了这一改变， [Eclipse Foundation](https://www.eclipse.org/org/foundation/) 还发布了 [Eclipse Transformer 项目](https://projects.eclipse.org/projects/technology.transformer)来帮助用户使用 javax 运行应用程序。*他们不想重新编译的名称空间。除了这个候选版本， [Eclipse Foundation 还发布了其 2020 年雅加达/爪哇调查结果](https://adtmag.com/blogs/watersworks/2020/06/eclipse-2020-java-survey.aspx)，ADT 再次对其进行了总结。简而言之，[调查结果](https://outreach.jakartaee.org/2020-developer-survey-report)“显示 Jakarta EE 8 的使用和对云原生 Java 的整体兴趣显著增长”，Spring Boot 的受欢迎程度略有下降，而 Red Hat 的 Quarkus 则有所上升。
*   **IBM 的开源新冠肺炎 Jupyter 笔记本:** [IBM](https://www.ibm.com/) 已经[发布了开源 Jupyter 笔记本](https://developer.ibm.com/blogs/open-source-jupyter-notebooks-analyze-covid-19-data/)来帮助分析实时新冠肺炎数据，这些笔记本处理该公司所说的一些“更平凡的任务”，例如查找权威数据，清理数据，使数据易于被 Pandas 和 Scikit-Learn 等工具消化，甚至建立一组初始报告和图表。 [COVID notebooks](https://github.com/CODAIT/covid-notebooks) 使用 [Jupyter notebooks](https://jupyter.org/) 进行每一个初始数据分析步骤，并从诸如[新冠肺炎数据存储库](https://github.com/CSSEGISandData/COVID-19)和纽约时报[美国](https://github.com/nytimes/covid-19-data)存储库中的冠状病毒(新冠肺炎)数据等来源提取基础数据。该公司提供了一些关于他们如何构建笔记本的见解，指出他们“使用常见的 Python 数据科学库，包括 [Pandas](https://pandas.pydata.org/) 、 [Numpy](https://numpy.org/) 、 [Matplotlib](https://matplotlib.org/) 、 [seaborn](https://seaborn.pydata.org/) 和 [scipy.optimize](https://docs.scipy.org/doc/scipy/reference/optimize.html) ”以及“我们作为 [Elyra 项目](https://github.com/elyra-ai/elyra)的一部分构建的[图形工作流编辑器](https://elyra.readthedocs.io/en/latest/getting_started/overview.html#notebook-pipelines-visual-editor)，以将我们的笔记本绑定到您可以运行的工作流中整个项目可以在 GitHub 上找到。

亚马逊网络服务是新堆栈的赞助商。

来自 Pixabay 的 seukyong lim 的特写图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>