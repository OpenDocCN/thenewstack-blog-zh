# Python 3 迁移的挫败感与日俱增

> 原文：<https://thenewstack.io/frustration-mounts-over-python-3-migrations/>

今年 1 月 1 日，Python 2 代码库被冻结。从那一天起，Python 2 将不会有进一步的回溯，实际上，这种语言和它的运行时，实际上是一种过时的技术。核心开发人员 Nick Coghlan 的一个常见问题解答[解释说，这样就结束了“核心开发团队为参考解释器并行维护 Python 2 和 3 的大约 13 年时间”。](http://python-notes.curiousefficiency.org/en/latest/python3/questions_and_answers.html)

Python 2 的最终版本现在正处于测试和发布候选阶段，Python 2.7.18 的最后一个生产版本预计在 2020 年 4 月发布。

虽然 Python 社区中的大多数人都认为 Python 需要彻底改革——尤其是对于[急需且早该提供的 Unicode 支持](https://thenewstack.io/bid-adieu-to-python-2-and-get-ready-for-python-3/)。但是许多拥有非常好的 Python 2 代码的人仍然感到沮丧。这种转变的真实故事分散在网络上，在引领这一努力的现实世界开发者的故事中。

![End of the countdown at Python Clock dot Org (screenshot).](img/7d9db3413f90eba3b7142eedbb0f0f17.png)

## **过渡期的故事**

克里斯·西本曼(Chris Siebenmann)上周简洁地总结了其中的一些挫折，他在 Twitter 上称自己是一名“过度投入的系统管理员”。

“你不必维护的、能正常工作的功能代码是一种资产；它坐在那里，做着有价值的工作，不需要任何工作，”Siebenmann [在博客文章](https://utcc.utoronto.ca/~cks/space/blog/python/Python2DroppingImpact)中写道。“你必须做大量的工作才不会破坏(而不是添加任何特性)的代码是一种负担；你必须工作并承担风险，但你却一无所获。”

但他的立场并没有得到菲尔·罗德斯(Phil Rhodes)的多少同情，他是云/人工智能架构师，创建了开发开源企业软件的 Fogbeam Labs，他在黑客新闻(Hacker News)上提出了反对意见[。“人们已经知道他们需要开始远离 Python 2 大约有 *12 年了。*如果你现在因为 Python 2 即将发布而感到恐慌，你很难不问“你在等什么？”"](https://news.ycombinator.com/item?id=22484876)

大公司也面临着迁移的挑战。LinkedIn 高级软件工程师 Barry Warsaw，他也是 Python 指导委员会的成员，自 90 年代中期以来一直是 Python 的核心开发人员，[在一篇博客文章](https://engineering.linkedin.com/blog/2020/how-we-retired-python-2-and-improved-developer-happiness)中描述了 LinkedIn 为完成其代码库的过渡所做的漫长的“多季度努力”，“经过了大约两个季度的规划和两个季度的执行。”

开发团队从绘制依赖关系开始，以确定工作的优先级——确定 75 个“基础”存储库——然后创建他们内部库的“双语”版本(可以使用 Python 2 或 Python 3)。

Warsaw 引用了多个团队和部门的工作，写道“总共需要迁移大约 550 个代码库(库、应用程序和服务)。”除了面向用户的服务，LinkedIn 还在内部将 Python 用于其 CI/CD 框架、命令行界面和部署以及数据科学工具，在一个非整体蔓延的环境中，Warsaw 描述为“数百个独立的微服务和工具，以及数十个支持库，所有这些都由独立团队在单独的存储库中拥有。”(新的堆栈还[涵盖了 2017 年的其他 LinkedIn Python 迁移](https://thenewstack.io/instagram-makes-smooth-move-python-3/))。

但并不是每个人都感到如此愉快。一月份，开发人员 Wayne Rowcliffe 在 Hacker News 上发布消息称，他的工作场所终于“T12”即将完成向 Python 3 的过渡。

“最终结果是，我上周花了很长时间审查了一个包含 70，000 行更改的拉请求，这是秋季收到的一系列约 10k 行拉请求中的最后一个。所有这一切都是我的一个同事的英勇努力，他完成了一项不值得羡慕的任务:梳理我们的整个代码库，以确定“这是 unicode”。这是字节。这是我们需要编码/解码的 API 边界。等等。

“这是一场噩梦，我很高兴我们已经过去了。”

在后来的评论中，他将他们的策略浓缩为九个字。“我们运行了 linter 和测试套件，直到事情通过。只是当你有 100 万行代码时，要花相当长的时间。”

## 敏锐的洞察力

另一个批评来自旧金山的开发者[格雷戈里·绍尔克](https://gregoryszorc.com/)，他是 [Mercurial](https://www.mercurial-scm.org/) 版本控制工具的维护者。Mercurial 与 Python 社区有着密切的联系——Python 一直使用 Mercurial 作为其存储库，但 2016 年[改用 Git](https://www.phoronix.com/scan.php?page=news_item&px=Python-Moves-To-GitHub)。但是在一篇[博客文章](https://gregoryszorc.com/blog/2020/01/13/mercurial%27s-journey-to-and-reflections-on-python-3/)中，Szorc 描述了他在 2019 年 11 月 5 日 Mercurial 实现 Python 3 支持的过程中所学到的东西——并对他所说的来自 Python 语言内部的瓶颈提出了一些批评。

他写道:“这个项目在 Python 3 端口起步较晚，很大程度上是因为 Python 2.4 和 2.5 的兼容性阻碍了我们的发展。”。“我们放弃了对 Python 2.6 的支持。这大大降低了支持 Python 3 的复杂性，因为 Python 2.7 中有大量的功能，使得针对 Python 2 和 Python 3 都变得更容易，现在我们可以解放双手来利用它了。”

但令人惊讶的是，Szorc 表示，Python 3 版本之间甚至还有一些变化，“我们也不得不覆盖墙纸”，这在 2019 年年中的“最后阶段”出现了。虽然 Python 3.7 的故障最少，但“我们必须付出额外的努力，让 Python 3.5 和 3.6 像 3.7 一样工作。3.8 也一样。”

很快，Mercurial 进行转换的重要日子到来了。在其持续集成系统上(使用亚马逊的 AWS DynamoDB、S3 和 EC2 spot 实例执行作业)，Szorc 开始在 Linux 上测试 Python 3.7、3.6、3.7 和 3.8 版本(以及 Windows 上的 Python 3.7)。但是，尽管它通过了所有的测试，“我认为航运只是一个里程碑——可以说是更长旅程中最重要的一个。还有很多工作要做…我们的用户可能会在 Python 3 上发现长达*年*的各种各样的错误。”

而且在 Windows 上仍然有“一些已知的问题”。

这次经历让 Szorc 有些酸楚。Szorc 写道:“尽管我一直很喜欢 Python——从语言到热情的社区——但我仍然很难理解 Python 如何能够通过选择他们所做的过渡计划给社区带来如此多的困难。”“我相信 Python 的选择代表了一个极好的例子，说明了在管理大型项目或生态系统时不应该做什么。其他大量部署的系统的维护者将受益于花时间理解和反思 Python 的失误……”

“Python 3 的初始方法反映了许多开发人员和项目所做的一件蠢事:试图重写而不是执行增量进化。对于已建立的项目，大规模的重写通常很糟糕。Python 3 也不例外。”

## **其他意见**

当 Szorc 的博客文章出现在黑客新闻的[上时，吸引了 400 多张赞成票，另外还有 339 条评论，包括一位不同意](https://news.ycombinator.com/item?id=22036773)的纽约市软件工程师[。“多年来，我参与了多个使用相同代码库同时支持 python2 和 python3 的重要库和框架……但实际情况并非如此……是的，你必须等待 python-3.4 的发布，以及 python-2.6 大部分被 python-2.7 取代。然后，从 2014 年初开始，制作一个与 python-2.7 和 python-3.4+兼容的干净代码库变得非常简单。”](https://news.ycombinator.com/item?id=22037905)

夏威夷大学的一名学生认为，人们过于相信一个名为 [*2to3*](https://docs.python.org/2/library/2to3.html) 的迁移程序，该程序试图提供一个自动代码翻译器。“2 对 3 的过渡计划根本不起作用，”他们在回应中抱怨道。“他们认为每个人都会在大爆炸中运行 2to3，然后我们都会在几年内切换到 3。

“相反，它拖了十多年，因为在现实中，我们需要编写与 2 和 3 都兼容的代码…直到 3 上有足够多的东西来放弃 2 支持。”

一些人质疑这一努力有什么收获。Brian Davis 是华盛顿的一名电子工程师，他自称是“老派 web dev”[在将“一些”较小的项目转换到 Python 2 之后，分享了他的想法](https://news.ycombinator.com/item?id=22037217)。“对字符串处理的更改让我犯了一个错误，对相对导入的更改需要一些思考。但是最大的挫折是一个烦人的问题:*我为什么要这么做？*

## 其他选项

在某些方面，Python 2 并没有真正消失。例如，有 [Tauthon](https://github.com/naftaliharris/tauthon) ，它是 Python 2.7.17 解释器的向后兼容分支，具有新的语法，还有从 Python 3.x 向后移植的库。Tauthon 可以运行 Python 2.7 代码和 C 扩展，以及 Python 3.x 的一些新特性

开发工具公司 [ActiveState](https://www.activestate.com/) 是为 Python 2 及其标准库以及 Python 包索引中列出的第三方开源包提供商业支持的[。](https://www.activestate.com/company/press/press-releases/activestate-offers-extended-support-for-python-2-beyond-eol/)

尽管如此，大多数开发人员现在生活在 Python 3 的世界中。但最终，也许是默默无闻的努力让 Szorc 的博文获得了 400 多张匿名投票。“移植到 Python 3 所需的努力是惊人的，”他在博客中回忆道。"对于 Mercurial 来说，Python 3 引入了大量的问题，并没有真正解决很多问题. "

他写道:“称 Python 3 的过渡对项目造成了破坏和干扰是一种保守的说法。”“作为一个项目维护者，很自然地会问，如果我们没有被迫执行这个杂耍，我们会取得什么样的成就。”

Pixabay 的 skeeze 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>