# Rust:快速发展的编程语言的下一步是什么？

> 原文：<https://thenewstack.io/rust-whats-next-for-the-fast-growing-programming-language/>

编程语言 Rust 在过去几年里越来越受欢迎。在其最新的开发者行业报告中，分析公司 SlashData 表示，Rust“在过去的 24 个月中，规模增长了近两倍，从 2020 年 Q1 的 60 万开发者增加到 2022 年 Q1 的 220 万。”

[Rust 基金会](https://foundation.rust-lang.org/)最近[宣布](https://foundation.rust-lang.org/news/2022-03-31-cgp-is-open-announcement/)其 2022 年社区补助计划，该计划的预算[为](https://foundation.rust-lang.org/grants/)625，000 美元。该计划将给予被选中的 Rust 维护者每人 12，000 美元的资助。在上个月的一个 AMA 视频中，Rust 基金会的执行董事 Rebecca Rumbul 说这些资助不仅仅是给现有的维护者，也是为了鼓励新的人加入这个项目。“我们想奖励已经在这里的人和已经做得很好的人，”她说，“但我们想确保 Rust 是可持续的，这需要有一个能够学习的人的管道。”

为了更多地了解 Rust 的发展——以及为什么它越来越受到 C 和 C++等传统编程语言的青睐——我对 Rumbul 进行了一次电子邮件采访。

**TNS: SlashData 称 Rust 是“发展最快的语言社区”。是什么推动了这种快速采用？它是否会以 C/C++等较老的编程语言为代价？**

[![](img/7031bad69eba74d06875cb5f35c4df92.png)](https://cdn.thenewstack.io/media/2022/05/b801fc5b-1516846291007.jpeg)

Rust 基金会执行董事丽贝卡·伦布尔

我认为这种增长有很多因素——语言本身很有趣，具有挑战性，并且令人满意。安全性和存储安全性使人们能够充满信心地进行创作。维护者和贡献者社区是包容和支持的，随着对 Rust 开发人员的需求不断增加，Rust 也是寻求增强其专业前景的开发人员的一个很好的选择。

我还不确定这种增长是以其他语言为代价的——我们发现 Rust 用户通常是已经非常熟悉 C++等语言的人。

我对 SlashData 报告中的这条评论很感兴趣:“它主要用于物联网软件项目，但也用于 AR/VR 开发，最常见的是用于实现 AR/VR 应用的底层核心逻辑。”今年以来，我一直对 3D 网络应用[](https://thenewstack.io/croquet-woos-javascript-devs-with-a-web-based-metaverse/)****(又名** [**元宇宙**](https://thenewstack.io/babylon-js-hints-that-microsoft-metaverse-will-be-web-based/) **)的兴起着迷——为什么 Rust 在这类应用中的核心逻辑比其他选项更好？****

 **一个完整的 AR/VR 应用可以用多种语言编写。例如，你可以使用 C#和 Unity 来实现图形。Rust 是应用程序底层核心逻辑的一个很好的选择，因为它的安全配置文件(例如，在运行时和内存安全之前捕获 bug)、库(板条箱)的可用性以及创建高效二进制文件的能力，这对于您想要部署应用程序的客户端可能很重要。

在上周由 Linux 基金会提交给白宫的一份 [**开源软件安全计划**](https://8112310.fs1.hubspotusercontent-na1.net/hubfs/8112310/OpenSSF/White%20House%20OSS%20Mobilization%20Plan.pdf?hsCtaTracking=3b79d59d-e8d3-4c69-a67b-6b87b325313c%7C7a1a8b01-65ae-4bac-b97c-071dac09a2d8) **中，它指出“内存安全语言，如 Rust、Go 和 Java”越来越受到 C 和 C++等语言的青睐。但是 Rust 在安全性方面与提到的另外两种语言 Go 和 Java 相比如何呢？**

根据您正在开发的用例或应用程序，您可能更喜欢一种语言而不是另一种。这三种语言都被认为是“内存安全”的，因为它们帮助开发人员避免了一类关于如何访问和使用内存的错误。例如，它们可以防止缓冲区溢出，缓冲区溢出允许恶意访问内存。蠕虫和勒索软件攻击可以归因于这样的错误。

尽管这两种语言管理内存的方式不同。Go 和 Java 在运行时有自动内存管理。Rust 采用了一种不同的方法，在运行程序或部署库之前，确保在编译时有一个内存安全的程序。很多用途在很大程度上取决于个人喜好。

鉴于最近的增长，Rust Foundation 来年的工作重点是什么——有什么特别的优先事项吗？

Rust 基金会致力于支持社区、促进采用和开发可持续模式来实现这一目标。我们很快将宣布首届“社区资助计划”的获奖者，该计划将包括一些奖学金和项目资助，我们将致力于确保这些个人和项目得到支持，为 Rust 生态系统做出有意义的贡献。

我们将继续投资保护我们的基础设施，我们希望在接下来的几个月内宣布招聘一名新员工(基础设施工程师)。我们还希望确保尽可能多的人可以使用 learning Rust，我们正在研究如何投资教育资源。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**