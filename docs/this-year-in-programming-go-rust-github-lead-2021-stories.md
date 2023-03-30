# 今年的编程:Go、Rust、GitHub 引领 2021 个故事

> 原文：<https://thenewstack.io/this-year-in-programming-go-rust-github-lead-2021-stories/>

好吧，好吧，好吧，我们在这里，已经倾斜到 2021 年的最后几天，鼻拭子从我们的鼻子里伸出来，变焦疲劳已经演变成更像变焦存在恐惧的东西，希望有一两种方法可以防止我们在 2020 年完善的永恒末日滚动。我们[制定了大计划](https://thenewstack.io/this-week-in-programming-whos-headed-to-kubecon/)，[改变了大计划](https://thenewstack.io/this-week-in-programming-is-aws-reinforce-just-the-first-domino-to-fall/)，[思考我们到底有多累](https://thenewstack.io/this-week-in-programming-can-you-feel-the-burn/)，然后后来被告知，别担心，我们会[恢复到疫情之前的生产力水平](https://thenewstack.io/are-you-pre-pandemic-productive-yet/)。

已经一年了，不是吗？

每个星期，我都会坐下来，挑选出我认为最有趣、最重要、最有价值的新闻，以及在软件开发世界(及其相关领域)中似乎人人都在谈论的话题，并将它们编辑到本周的[本周编程](https://thenewstack.io/tag/this-week-in-programming/)专栏中。虽然每周的主题可能会有很大的不同，但有些故事一直伴随着我们，一次又一次地被访问。

也就是说，在我看来，过去一年中有一些突出的故事，我在这里向您展示它们，没有特定的顺序，如果您愿意，可以对过去一年中编程方面的一些重大故事进行简要的，当然也不是包罗万象的概括。

## 十年后，Go 得到了泛型

正如我们[在 2021 年的最初几周写下](https://thenewstack.io/this-week-in-programming-go-approves-generics-long-at-last/)的时候，地鼠们终于迎来了欣喜的时刻，“对于 Go 编程语言是否将采用泛型的问题，在[多年](https://thenewstack.io/week-programming-go-2-0-question-complexity/) [年](https://thenewstack.io/this-week-in-programming-specifically-generic/)[辩论](https://thenewstack.io/this-week-in-programming-gophers-dig-into-generics-go-2-0-and-gophercon-2018/)之后，随着上个月提出的[提案](https://thenewstack.io/this-week-in-programming-has-the-time-finally-come-for-generics-in-golang/)的[接受](https://github.com/golang/go/issues/43651#issuecomment-776944155)，本周终于有了答案。”事实上，泛型的问题已经困扰 Golang 社区很久了，以至于它是我们在这个专栏中解决的第一个话题，并且关于添加泛型的同样的争论早在很久以前就已经出现了。

在今年早些时候提出的最新提议中， [Golang](https://golang.org/) 团队成员 [Ian Lance Taylor](https://research.google/people/author37504/) 评论说，事实上，自 2009 年该语言首次发布以来，泛型已经成为“最常被要求的语言特性之一”。说泛型一直是讨论和辩论的话题是一种保守的说法，甚至泰勒在他的上一份提案中也谈到了该特性的麻烦历史，写道“最早(有缺陷的)尝试之一是在 2010 年添加泛型到 Go。”

然而，这个最新的提议解决了足够多的问题，使[被接受](https://github.com/golang/go/issues/43651#issuecomment-776944155)，2021 年 12 月发布的 Go 1.18 Beta 1 首次提供了人们期待已久的功能。

然而，正如我们在 10 月份提到的，Go 团队决定[稍微踩一下泛型](https://thenewstack.io/this-week-in-programming-visual-studio-code-arrives-on-the-web/)的刹车，并且[不会将该特性直接引入核心库](https://github.com/golang/go/issues/48918)。相反，Go 最初的设计者之一 [Rob Pike](https://twitter.com/rob_pike?lang=en) 的[提议](https://github.com/golang/go/issues/48918#issuecomment-953349439)是暂时将更改转移到 [golang/x/exp 库](https://pkg.go.dev/golang.org/x/exp)，在那里它们“可以在生产中测试，但可以改变、调整和发展一两个周期，让整个社区尝试它们。”根据 Taylor 的评论“在 1.18 中唯一使用类型参数的面向公众的包将是约束包。”

尽管如此，泛型确实最终是可用的，而且有很多人在那里[踢着轮胎](https://markphelps.me/posts/trying-out-generics-in-go/)和[检查什么时候你可能已经想要使用新特性](https://teivah.medium.com/36d49c1aeda)。

当然，这不是今年在围棋领域发生的唯一事情——该项目也很快[接受了将 fuzzing 添加到围棋标准库](https://github.com/golang/go/issues/44551#issuecomment-811607377)的提议，该标准库随后在围棋开发分支中发布[，在围棋 1.17 中发布](https://blog.golang.org/fuzz-beta)[dev . fuzz](https://github.com/golang/go/tree/dev.fuzz)——但泛型绝对是 2021 年围棋的定义壮举。

## Rust 是为了让所有的记忆变得安全

我们会说，2021 年是铁锈的大年。

近年来，许多标题都是关于这种语言有多难学以及围绕它缺乏工具的问题，但 2021 年更多的是关于流行的开源系统语言的众多途径和发展。

2021 年，Rust 越来越成为内存安全的同义词，同样被认为是 C 和 C++以及与安全性相关的新应用的智能替代品。引用一个[最近关于选择 Rust 的采访](https://thenewstack.io/rust-based-cloud-hypervisor-heads-to-linux-foundation/)，“如果你今天想在这一层寻求安全，Rust 是可以使用的语言。就是这样。[……]如果你重新开始，正如我们所做的，你会从生锈开始。”

但正如他们所说，证据就在布丁中，这可以从 Rust 采用的一些大案例中看出，这些案例真正展示了该语言在编程语言领域的成熟。例如，2021 年，Rust 已经严重入侵了 T4 的 Windows T5 和 Linux T7。

早在 4 月份，我们写道[微软正在变得生疏](https://thenewstack.io/this-week-in-programming-microsoft-gets-rusty/)，注意到该公司的[新提供的关于开始使用 Rust](https://docs.microsoft.com/en-us/learn/paths/rust-first-steps/) 的课程，以及[Rust for Windows](https://docs.microsoft.com/en-us/windows/dev-environment/rust/rust-for-windows)的第一个预览版，它允许开发者“通过[Windows 机箱](https://crates.io/crates/windows)直接和无缝地使用任何 Windows API(过去、现在和未来)。”微软之前曾吹捧 Rust 是安全系统编程行业的“最佳机会”,讨论他们打算慢慢从 C/C++转向 Rust 来构建其基础设施软件，今年他们开始这样做了。

至于 Linux，Linux 内核获得树内支持的[想法在 2020 年中期还相当萌芽，但到了 2021 年 4 月，](https://thenewstack.io/this-week-in-programming-linux-kernel-keepers-mull-in-tree-support-for-rust/) [Rust 似乎越来越有可能走向 Linux 内核的开发分支](https://thenewstack.io/this-week-in-programming-rust-likely-headed-for-linux-kernels-development-branch/)，到了 12 月， [Rust 的支持被宣布为“足够好”](https://thenewstack.io/rust-in-the-linux-kernel-good-enough/)虽然支持“仍被认为是实验性的”，但 [Rust for Linux](https://github.com/Rust-for-Linux) 项目维护者 [Miguel Ojeda](https://ojeda.dev/) 写道，“支持已经足够好了，内核开发人员可以开始研究 Rust 的子系统抽象，并编写驱动程序和其他模块。”

而且，如果你需要进一步的证据证明 Rust 对这类事情是有益的，只需看看亚马逊网络服务为 Bottlerocket 所做的努力就行了，bottle rocket 是一个 Linux 发行版，主要是用 Rust 编写的。

## GitHub 使用所有的训练数据(你的代码)

很可能没有哪家公司比 GitHub 在我们本周的编程专栏中提到的更多，今年也不例外。

然而，来自 GitHub 的一个特别的故事确实引人注目:围绕 GitHub Copilot 的[争议，其被认为的版权侵权和围绕开源许可的考虑](https://thenewstack.io/this-week-in-programming-github-copilot-copyright-infringement-and-open-source-licensing/)。

当 GitHub 在 6 月份首次推出 Copilot 时，他们透露它是使用 OpenAI Codex 构建的，并且“在数十亿行公共代码上训练过”，许多人认为这些代码包括病毒性 GPL 许可证下的代码。GPL 许可证要求所有的衍生作品都带有相同的许可证，因此指控立即浮出水面，至少 GitHub Copilot 侵犯了版权。

与 Intellisense 不同，Copilot 不仅仅是完成一行代码，而是给出整个代码块的建议，没过多久，人们就发现该工具吐出了整块容易识别的代码。然而，GitHub 并不是没有想到这一点，GitHub 首席执行官 Nat Friedman [认为](https://news.ycombinator.com/item?id=27678354)Copilot 最常建议的代码已经被转化，属于免费使用，正如[在 OpenAI](https://www.uspto.gov/sites/default/files/documents/OpenAI_RFC-84-FR-58141.pdf) 的一篇论文中概述的那样。不仅如此，正如[的一篇博客文章指出的](https://decoded.legal/blog/2021/06/github-copilot-initial-thoughts-from-an-english-law-perspective)，GitHub 的[服务条款](https://docs.github.com/en/github/site-policy/github-terms-of-service)可能涵盖了他们在训练模型时使用的任何代码。另一个帖子认为，解决这个难题的简单方法是让副驾驶员在吐出逐字代码时简单地提供属性。

另一方面，[一些人呼吁](https://thenewstack.io/this-week-in-programming-github-copilot-and-the-generational-divide/)电子前沿基金会和[自由软件基金会(FSF)](https://www.fsf.org/) 提起集体诉讼，FSF 发出[征稿通知](https://www.fsf.org/blogs/licensing/fsf-funded-call-for-white-papers-on-philosophical-and-legal-questions-around-copilot)，称副驾驶“现状是不可接受和不公正的”然而，到目前为止，据我们所知，没有论文发表，没有实际提起诉讼，也没有对 GitHub 的“人工智能配对程序员”进行任何真正的法律测试。

相反，至少有一份报告称 [GitHub 的 Copilot 用户数量有所上升](https://www.axios.com/copilot-artificial-intelligence-coding-github-9a202f40-9af7-4786-9dcb-b678683b360f.html)，并且该工具已经扩展到了 [JetBrains 的 IntelliJ 和 PyCharm 版本 2021.2 及更高版本](https://github.com/github/copilot-docs/blob/main/docs/jetbrains/gettingstarted.md#getting-started-with-github-copilot-in-jetbrains)和 [Neovim 0.6 预发布版本](https://github.com/github/copilot.vim#getting-started)和 Node.js，以及[，包括对 Java、C、C++和 C#的多行代码完成的支持](https://www.infoworld.com/article/3638550/github-copilot-adds-neovim-jetbrains-ide-support.html#jump)。对于那些发现自己对整件事情感觉不好，但仍然感兴趣的人来说，总有许多开源的 GitHub Copilot 替代品可以尝试。

总的来说，GitHub Copilot 只是 GitHub 自收购微软以来(以及 2021 年)推出的各种功能中的一个(有点争议的)例子，这些功能似乎巩固了微软对许多开发者生命周期的所有权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>