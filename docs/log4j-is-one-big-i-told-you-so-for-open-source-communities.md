# 对于开源社区来说，Log4j 是一个很大的“我告诉过你”

> 原文：<https://thenewstack.io/log4j-is-one-big-i-told-you-so-for-open-source-communities/>

又是一周，又一个让互联网屈服的 bug，amirite？

正如 Steven J. Vaughan-Nichols 本周早些时候在开源 Java 日志库 [Apache Log4j](https://logging.apache.org/log4j/) 中所写的 bug 一样，[我们有太多麻烦了](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/)。该漏洞是一种名为 [Log4Shell](https://www.lunasec.io/docs/blog/log4j-zero-day/) 的零日攻击，他写道，“糟糕透顶”，并指出其 [10.0 CVSSv3](https://nvd.nist.gov/vuln/detail/CVE-2021-44228) 评级为 0.1 到 10，允许攻击者“通过远程代码执行(RCE)攻击来攻击你，这可以用来危及你的服务器。”更糟糕的是，另一个 Log4j 漏洞在第一个漏洞之后出现，尽管没有那么严重。尽管如此，沃恩-尼科尔斯写道，第一个漏洞非常严重，它“将在未来几周，甚至几个月内让你夜不能寐。”

到目前为止，我想这一切对你来说都不陌生，但是对于开源开发者和维护者来说，对这个消息的反应是一个堆积的时刻，许多人提供了他们自己版本的“我告诉过你”以及永远相关的 xkcd 漫画[完美地说明了手头的问题。](https://xkcd.com/2347/)

[![](img/bfb1f78294d58d4a103fcdca289df397.png)](https://xkcd.com/2347/)

例如，一个名为 [Xe](https://christine.website/) 的开发者认为[“开源”被打破了](https://christine.website/blog/open-source-broken-2021-12-11)，他写道他们“相信这是‘开源’软件所有主要生态系统问题的完美缩影。”Xe 指出的问题是开源中经常提到的问题——完整代码的维护者完全缺乏资金。在嵌入上面的 xkcd 漫画之前，只需要这篇博客文章的几个小段，Xe 提供了 Alpine Linux 作为另一个依赖的开源项目的例子，但很可能没有得到使用它的人的资助。

“在 Docker 上下文中，它经常被用来为生产中的许多公司提供动力。你认为这些公司中有多少资助了 Alpine Linux 项目？你认为这些公司中有多少会考虑资助 Alpine Linux 项目？”Xe 写道。

明白了。

与此同时，PuTTY 的维护者安德鲁·达克(Andrew Ducker)以维护一个被许多人依赖的开源软件的身份，给出了他自己对这个话题的看法，他简单地写道“互联网(和许多大公司)依赖于人们在业余时间免费维护的软件。这可能是不可持续的。”

同样，谷歌[的 Go 团队成员 Filippo Valsorda](https://blog.filippo.io/author/filippo/) 写道，作为一个在大公司内外都在开源[上建立职业生涯的人](https://github.com/FiloSottile/)，当前的场景[为专业维护人员敲响了警钟](https://blog.filippo.io/professional-maintainers/)。

“开源软件运行着互联网，进而运行着经济。这是 2021 年关于现实无可争议的事实。然而，开源维护者的角色还没有从一个爱好发展成为一个合适的职业。

“灾难性的后果几乎每天都在发生，”瓦尔索达写道，随后他得出结论，“现状是不可持续的”。"

Valsorda 认为，解决方案是，尽管“GitHub 赞助商和 Patreon 是表达感激的好方式”，但它们是“一种极其不严肃的补偿结构”，相反，我们需要将维护者的角色“专业化”。也就是说，把他们放在工资单上。

“这是我希望看到越来越多发生的事情:开源维护者逐渐成为老练的对手，他们用信笺发送‘支持和赞助’的发票，大公司开发评估、批准和支付他们的程序，作为例行公事，以便他们可以从生态系统中获得他们需要的东西。最终，初级维护者的整个职业道路，包括培训，就像一个真正的职业。”

关于整个事件的最后一点——在你刚刚处理完 Log4j 漏洞的一周之后，除了可能的烈酒或假期之外，你可能还需要一个开怀大笑，因此，有人已经建立了一个专门用于 Log4j 迷因的整个网站，这可能会达到目的。

## 本周的节目中

*   **关于整个 Rust“节制问题”:**自从 [Rust 节制团队](https://www.rust-lang.org/governance/teams/moderation)、[在没有任何警告的情况下辞职以抗议](https://thenewstack.io/rust-mod-team-resigns-in-protest-of-unaccountable-core-team/)它所说的“不负责任”的核心团队以来，已经过去了近一个月，该团队负责维护 Rust 社区内的行为准则和社区标准。现在， [Rust Library 团队](https://www.rust-lang.org/governance/teams/library)负责人 [Mara Bos](https://twitter.com/m_ou_se) 提供了一份关于审核问题的[后续报告，这份报告最近在上周作为电子邮件发送给了 Rust 项目的成员。在接下来的报道中，核心冲突仍然没有说出来，因为披露这一点会侵犯“相关人员的隐私，包括报告这一问题的人员的隐私。”然而，Bos 确实添加了更多的背景，写道“在八个月的时间里，包括错误沟通和分歧，这升级为审核团队和核心团队之间的信任问题，”这“最终导致了一种不可行的情况，没有人能够了解完整的背景，使前进的道路变得不可能。”为了解决这个问题，成立了一个新的小组，包括“所有顶级团队领导、基金会的项目总监、所有核心团队成员和新的审核团队成员，以讨论下一步措施。”Bos 表示，他们将带着三个高层次的目标前进。首先，他们将致力于用“公开记录的程序”来修正“处理复杂审核问题的不明确政策”。接下来，Bos 写道“Rust 项目需要调整它的结构来进行治理。”最后，他们计划“解决处于核心团队和前审核团队之间分歧中心的具体审核问题”，并“在我们能够确保这样做不会造成更多混乱的情况下公开讨论”细节和计划。](https://blog.rust-lang.org/inside-rust/2021/12/17/follow-up-on-the-moderation-issue.html)

*   **仿制药终于在 Go 1.18 Beta 中掉落:**没错，漫长的等待终于结束了——[仿制药即将 Go 1.18 Beta 1](https://go.dev/blog/go1.18beta1) 。虽然距离 Go 1.18 正式发布还有几个月的时间，但正如他们所写的那样，这个第一个预览版将“让你踢踢轮胎，兜一圈，让我们知道你遇到了什么问题。”这个版本是第一个支持使用参数化类型的[通用代码的版本，他们说这是“自 Go 1 发布以来最重要的变化，当然也是我们有史以来最大的单一语言变化。”要开始，查看一下关于如何开始使用泛型的简短教程或者上周在 GopherCon 的演讲。当然，泛型并不是这个版本的唯一亮点，所以请查看](https://go.dev/blog/why-generics)[博客文章](https://go.dev/blog/go1.18beta1)或[Go 1.18](https://tip.golang.org/doc/go1.18)的发行说明草案以了解所有细节。也就是说，我们知道泛型是你真正关心的事情，所以我们想我们可能会包括一些关于这个主题的其他帖子。首先，Go 开发者 [Teiva Harsanyi](https://twitter.com/teivah) 写了一篇博客文章，研究了[何时在 Go](https://teivah.medium.com/36d49c1aeda) 中使用泛型，其中他研究了“Go 中的泛型概念，然后深入研究了常见用法和误用。”Harsanyi 查看了几个案例，检查了具体的代码示例，最后建议不要使用泛型，“当它使我们的代码更复杂时”，并建议谨慎。“一般来说，当我们想要回答何时不使用泛型时，我们可以找到与何时不使用接口的相似之处。事实上，泛型引入了一种抽象形式，我们必须记住，不必要的抽象引入了复杂性，”他写道。“让我们不要用不必要的抽象来污染我们的代码，让我们现在专注于解决具体的问题。”除了是否使用泛型的问题之外，围棋开发者 Mark Phelps[首先深入讨论并提供了他自己在围棋](https://markphelps.me/)中尝试泛型的经验[。Phelps 开始将他的“](https://markphelps.me/posts/trying-out-generics-in-go/) [markphelps/optional](https://github.com/markphelps/optional) 库从使用代码生成转换为使用泛型”，并记录了这个过程，指出他喜欢“因为泛型，他能够删除我 95%的代码”，并且他“不确定大多数 Go 开发人员会每天使用泛型，但是如果我们需要它们，知道它们的存在是很好的。”
*   **Python 3.6 EOL 来了:**本周最后一个值得注意的头条，杰克·沃伦已经在 New Stack 上报道过，但值得链接，那就是[是时候向 Python 3.6](https://thenewstack.io/time-to-say-goodbye-python-3-6-is-end-of-life/) 说再见了。“从这个月开始，Python 3.6 对我来说已经死了，”他写道。“对你来说也应该是死的。”语言版本将不再接受错误或安全修复，Wallen 详细介绍了您可以处理这一问题的各种方法，所以请继续前进，看看您是否需要关注-与 Log4j 漏洞一样，答案是“可能如此”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>