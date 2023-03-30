# 本周节目:副驾驶的代沟

> 原文：<https://thenewstack.io/this-week-in-programming-github-copilot-and-the-generational-divide/>

上周，GitHub [推出了 GitHub Copilot](https://github.blog/2021-06-29-introducing-github-copilot-ai-pair-programmer/) ，该公司将这一功能称为“你的人工智能配对程序员”，互联网上的许多人立即对这一新功能爆发了[的义愤](https://twitter.com/eevee/status/1410037309848752128?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1410037854235893765%7Ctwgr%5E%7Ctwcon%5Es2_&ref_url=https%3A%2F%2Fthenewstack.io%2Fthis-week-in-programming-github-copilot-copyright-infringement-and-open-source-licensing%2F)，而[的其他人](https://thenewstack.io/github-copilot-a-powerful-controversial-autocomplete-for-developers/)则说“哇，这真酷。”

愤怒的要点归结于一个事实，即 GitHub Copilot 是使用 OpenAI Codex 构建的，它使用 GitHub 上几乎所有公开可用的代码作为其训练集——包括带有病毒性版权许可的代码，如 [GPL](https://www.gnu.org/licenses/gpl-3.0.en.html) 。然而，正如我们上周所讨论的，法律领域的许多初步审查似乎与 GitHub 的审查一致，GitHub 将整个事情视为“合理使用”的案例更不用说， [GitHub 的服务条款](https://docs.github.com/en/github/site-policy/github-terms-of-service)也有一个非常[相关的段落](https://docs.github.com/en/github/site-policy/github-terms-of-service#d-user-generated-content)，其中所有用户基本上都签署了他们的代码被公司用于各种用途的权利，这可能广泛适用于这里看到的场景。

不出所料，上周的辩论延续到了本周，而且至少有一起诉讼似乎正在进行中。“ [Programming Rust](https://www.oreilly.com/library/view/programming-rust-2nd/9781492052586/) ”的开发者和合著者 Nora Tindall 表示，在 GitHub 承认他们使用“所有公开的 GitHub 代码”训练 Copilot 之后，她已经联系了电子前沿基金会和自由软件基金会，寻求集体诉讼。

这场争论与上周相比没有质的变化，许多开发者认为 Copilot 创建的代码本质上是一种“衍生”作品。与此同时，本周又出现了另一篇文章，不仅再次认定 [GitHub Copilot 没有侵犯你的版权](https://juliareda.eu/2021/07/github-copilot-is-not-infringing-your-copyright/),还认为限制 GitHub 使用 copyleft 许可的举动实际上可能是不明智的。

在博文中， [Julia Reda](https://juliareda.eu/en/) ，一位在担任欧洲议会成员期间专注于版权改革的研究员，提出了与我们上周看到的类似的问题，但也认为对 GitHub Copilot 的反应与 copyleft 许可证的最终目标是对立的。

“因为一家大公司——即 GitHub 的母公司微软——从分析自由软件中获利，并在此基础上建立商业服务，所以使用版权法禁止微软说的想法对版权所有者来说似乎是显而易见的，”她写道。然而，通过这样做，copyright left 实际上是要求将版权扩展到那些有充分理由不受版权保护的行为。这些扩展将对版权所有许可证寻求推广的非常开放的文化产生致命的后果。”

显然，我们不会很快弄清这场辩论的真相，在合法性问题上，也许只有通过诉讼(以及不可避免的上诉等等)，我们才能在这个似乎是新的法律领域找到坚实的基础。但 Reda 的这一观点是对这一整个磨难的另一个很好的支点，这一次不是争论副驾驶是好是坏，合法还是非法，而是专注于对它的反应，以及它可能如何沿着世代线绘制。

在他的 Twitter 帖子中，Chef 联合创始人兼 System Initiative 首席执行官 [Adam Jacob](https://www.linkedin.com/in/adamjacob) 讨论了围绕 Copilot 的讨论可能如何在许多方面受到开源的发展、公司资金的影响以及那些通过努力使开源软件“合法”而生存的人和那些出生在现有系统中的人之间的不同观点的影响。

对于 Jacob 来说，围绕 Copilot 的整个“混乱”似乎是一个脆弱的问题，也许一些旧的想法被认为是理所当然的，但与此同时，也有新的想法需要被听到和考虑，而不是被驳回。他写道，反驳这种反弹“相当于说现在的孩子不懂‘真正的音乐’”。“对于创造现状的人们来说，这是一次怀旧和优越感之旅。”

我只想知道一件事——如果 Copilot 作为一个自由和开源软件发布，人们的反应会是一样的吗？

## 本周的节目中

*   根据软件开发者和 Rust for Linux 项目维护者 [Miguel Ojeda](https://ojeda.dev/) 的[消息](https://lore.kernel.org/lkml/20210704202756.29107-1-ojeda@kernel.org/)，Linux 中 Rust 的[(可能)包含在我们三月份写的 Linux 内核](https://thenewstack.io/this-week-in-programming-rust-likely-headed-for-linux-kernels-development-branch/)中似乎进展顺利。该消息包括项目进展的几个更新，其中包括对测试的支持，测试版编译器，ARM 和 RISCV 架构，以及“支持足够好，内核开发人员可以开始致力于子系统的 Rust 抽象，并编写驱动程序和其他模块。”Ojeda 还指出，该项目已经获得了微软、ARM、IBM、谷歌和互联网安全研究小组的支持，将 Rust 纳入 Linux，以及后两者的财政支持。对于那些有兴趣了解更多信息的人，请留意为今年的 Linux 管道工会议(LPC)提议的几个讲座，以及“一个关注 Rust 和 Linux 内核的新会议”，第一个会议将在今年的 LPC 之前以虚拟方式举行。
*   **Java、C 和 Python 争夺位置:**与以往一样， [TIOBE Index](https://www.tiobe.com/tiobe-index/) 每月跟踪编程语言的流行程度，这个月他们看到了过去的回声，因为他们注意到两种顶级语言与他们在 2001 年开始跟踪它们时一样。“第一个 TIOBE 索引的前 3 名是 Java、C 和 C++。今天的故事看起来惊人的相似。现在最早的 3 种编程语言是 C、Java 和 Python。有趣的是，这三种语言比以往任何时候都更加接近。位置 1 和位置 3 的差别只有 0.67%。”当然，我[不会把太多的股票放在这种东西上](https://thenewstack.io/this-week-in-programming-ignore-the-rumors-of-cs-meteoric-rise/)，但是观看编程语言流行的无休止的赛马是很有趣的，不是吗？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>