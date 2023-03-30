# Go 仿制药准备好黄金时间了吗？

> 原文：<https://thenewstack.io/are-go-generics-ready-for-prime-time/>

正如我们这些年来[讨论过](https://thenewstack.io/this-week-in-programming-has-the-time-finally-come-for-generics-in-golang/) [无数次](https://thenewstack.io/this-week-in-programming-gophers-dig-into-generics-go-2-0-and-gophercon-2018/) [次](https://thenewstack.io/this-week-in-programming-go-approves-generics-long-at-last/)一样，开发人员期待泛型的加入已经很久了。该功能是十多年来最受欢迎的功能，它终于在上个月随着 Go 1.18 的发布而备受庆祝。

自从期待已久的功能发布以来，已经有大量的教程、演示和讨论，但本周讨论发生了一些变化，人们质疑该功能是否真的准备好了。

在他公司博客上的一篇博文中，[梁赫群·马蒂](https://twitter.com/vmg)，他为 MySQL 兼容的无服务器数据库平台 [PlanetScale](https://planetscale.com/) 工作，写道[泛型可以让你的 Go 代码变慢](https://planetscale.com/blog/generics-can-make-your-go-code-slower)。

在他的博客文章中，Martí说，虽然有些人反对泛型，因为他们担心这种语言会变成“一个冗长而企业化的 Java-lite，带有泛型工厂，或者更可怕的是，一个退化的 HaskellScript，用单子代替 ifs”，但其他人只是希望泛型能提供“一个关键的特性，以大规模实现干净和可重用的代码。”然而，在这种动态之外，存在着第三方，他属于这一方:“对泛型本身不感兴趣，但对[单态化](https://en.wikipedia.org/wiki/Monomorphization)及其性能影响感兴趣的系统工程师。”

Martí写道，通常有两种方法来实现泛型。首先，您可以使用“装箱”，其中指针有助于抽象所有“事物”(他在本讨论中首选的非技术术语)，即函数将以“相同的方式外观和行为”进行操作。这是用于 Go 接口、Rust 中的 dyn 特征和 C++中的虚类的方法，但是他说它们“受限于它们的表达能力和它们的运行时开销。”其次，您可以使用单态性，这实质上是“为它必须操作的每个独特事物创建一个不同的函数副本”，并且在历史上一直是在各种语言中实现泛型的选择，因为它“归结起来就是在结果代码中用更长的编译时间来换取显著的性能提升。”

然而，单形化的缺点是它创建了更多的代码，所以 Go 采取了一种中间路线，使用一种称为"[GC shape stenciling with dictionary](https://github.com/golang/proposal/blob/master/design/generics-implementation-dictionaries-go1.18.md)"的方法 [Rick Branson](https://www.linkedin.com/in/rickbranson/) ，PlanetScale 的软件工程主管，在一封电子邮件中提供了这一点的概要。

“在一些非常真实的情况下，为通用代码的每种类型排列生成特定的代码会显著增加编译时间和最终编译的可执行文件的大小，以至于出现问题。在某些情况下，它甚至会导致代码执行速度变慢！所以 Go 编译器实际上不会为每一种类型的排列生成新的代码。它使用了许多启发式方法，包括“GC 形状模板”,这种方法通过权衡来保持合理的排列数量。在某些情况下，这些折衷以不利的方式降低了性能，因为生成的机器码不可能是那种精简、平均、专用的代码。它在执行时必须支持更广泛的类型。布兰森写道:“这篇博文讨论了很多内容。

马蒂在这篇博文中花了很多时间，对造成这种情况的细节进行了非常专业、格式优美的深入探讨，我们将让这篇摘要代替，但如果你渴望更多的细节，它们就在那里。然而，除此之外，我们得到的是一个更简洁的清单，列出了如何获得当前设计的泛型的最佳性能，以及 Martí关于 Go 如何修改其设计以进一步提高运行时性能的建议。

Martí在一封电子邮件中总结了他对此事的看法，他写道:“对于系统语言(以及任何编译语言)来说，正确的权衡是在编译时支付前期成本，以在运行时生成零成本的泛型抽象。这是基线，也是我认为唯一明智的方法:首先，你让编译器在任何情况下都生成最好的代码。然后，对编译器进行基准测试，如果速度太慢，就对编译器进行优化。顺便说一句，如果你的语言的编译器是用你的语言编写的(就像 Go 的情况)，让它生成更好的代码也会加速编译器本身！”

## 本周的节目中

*   **Visual Studio 2022 获得 GitHub Copilot:** 无论你在哪里登陆围绕 GitHub Copilot 的[伦理考量，该公司所谓的“人工智能配对程序员”，你可能不得不承认这是一个有趣的工具，甚至可能有所帮助。到目前为止，它只能在 GitHub Codespaces 和 Visual Studio Code 中在线使用，但现在该公司表示](https://thenewstack.io/this-week-in-programming-github-copilot-copyright-infringement-and-open-source-licensing/) [GitHub Copilot 现在可用于 Visual Studio 2022](https://github.blog/2022-03-29-github-copilot-now-available-for-visual-studio-2022/) 。去年，GitHub 在技术预览版中推出了 Copilot，从那以后，Visual Studio 2022(T8 于去年年底推出)一直是最受欢迎的 IDE。虽然你仍然需要注册等待名单，GitHub 正在增加更多的容量，所以请确保[尽快注册](https://copilot.github.com/)。一旦你收到一封电子邮件说你已经加入了，只要按照指示做，你就可以开始运行了。

*   【Goto 到底有什么危害？当然，到现在为止，你已经听说过[各种被认为是有害的东西](https://thenewstack.io/this-week-in-programming-mostly-harmless/)，最初是由[埃德格·迪克斯特拉 1968 年的](https://en.wikipedia.org/wiki/Edsger_Dijkstra)论文 [GOTO 被认为是有害的](http://www.u.arizona.edu/~rubinson/copyright_violations/Go_To_Considered_Harmful.html)引发的嗯，本周有一篇博客文章越过了我们的 feed，对 goto 的危害性做了一些解释，goto 是一种后来在 BASIC 编程语言中流行的指令，可用于跳转到不同的代码行，我们认为值得分享。如果你曾经想知道为什么 goto 被认为是有害的(T9)，或者可能认为“goto 是有害的被认为是反应过度”，正如作者所说的一些人所做的那样，他认为这是“因为随着程序复杂性的增加，非结构化跳转可能导致无法理解程序中正在发生的事情，即使是在小程序中。”这个论证是通过展示两个几乎相同的流程图来实现的，右边的流程图的不同之处仅在于它有一个 goto 参数。左边的流程图有 72 条独特的路径。右边的流程图用虚线表示一个非结构化的跳转，它有 93，748，416，840 个唯一的路径，”作者解释道，然后补充道“现在想象一个程序有 10 或 100 个这样的跳转？”看起来确实有害。
*   **RedMonk 的语言排名找到了稳定性:**你正在阅读的日历上可能已经是 4 月了，但[2022 年 1 月的 RedMonk 编程语言排名](https://redmonk.com/sogrady/2022/03/28/language-rankings-1-22/)刚刚出炉，该分析公司写道，“本季度的运行情况——就像现在的几个运行情况一样——是稳定的，”这是他们近年来看到的趋势。事实上，在过去的三个季度中，20 种语言中有 17 种保持稳定，Redmonk 思考这是否是“行业使用的代表，还是更类似于过程工件？”他们认为，也许我们正在进入一个时代，“在这个时代，各种语言已经找到了各自的利基和与它们特定竞争对手的水平。”关于哪些东西移动了(或大部分没有移动)的所有细节，请阅读 RedMonk 对持续不变的排名的分析，以及他们提供的许多警告。这个季度最大的搬家公司？C++下降了两位，在这一点上，你的猜测和他们一样好。(也许是[为了内存安全，才锈](https://thenewstack.io/rustls-looks-to-provide-a-memory-safe-replacement-for-openssl/)的举动？)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>