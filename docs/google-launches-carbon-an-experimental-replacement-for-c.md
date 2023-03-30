# 谷歌推出 Carbon，一个实验性的 C++替代品

> 原文：<https://thenewstack.io/google-launches-carbon-an-experimental-replacement-for-c/>

由于对 C++的缓慢发展感到沮丧，谷歌工程师推出了一种新的“实验性”开源编程语言，称为 Carbon，作为古老但老化的 C++的可能继任者。

正如微软[构建](https://thenewstack.io/typescript-and-the-power-of-a-statically-typed-language/) Typescript 来更新 JavaScript，而 Kotlin 的创建是为了弥补 Java 的不足，Carbon 可以作为 C++的后继语言[，它为开发人员提供了一个简单的起点，让他们可以使用一种新的语言来解决诸如内存安全和泛型等现代开发概念。](https://9to5google.com/2022/07/19/carbon-programming-language-google-cpp/)

谷歌工程师 [Chandler Carruth](https://github.com/chandlerc) 本周在多伦多的 CPP North C++会议上介绍了这种语言。

## 枯萎 C++

Carruth [在 GitHub 页面上解释说](https://github.com/carbon-language/carbon-lang/blob/trunk/docs/project/difficulties_improving_cpp.md)，长期以来，C++一直是构建性能关键型应用程序的首选语言，但它也受到了许多问题的困扰，这些问题阻碍了现代开发人员。它积累了几十年的技术债务，带来了许多过时的做法，这些做法是该语言的前身 C 的一部分。C++的守护者优先考虑向后兼容性，以便继续支持广泛使用的项目，如 Linux 及其软件包管理生态系统，Carruth 指责说。

这种语言的发展也受到官僚委员会程序的阻碍，这种程序以标准化而非设计为导向。这使得添加新功能变得困难。C++在很大程度上有一个隔离的开发过程，在这个过程中，一个[选择委员会](https://isocpp.org/std/the-committee)做出重要的决定，这是一个瀑布式的过程，可能需要几年时间。

“委员会的结构旨在确保国家和公司的代表性，而不是建立一个包容和欢迎的团队以及积极为语言做出贡献的专家和人士社区，”卡鲁斯写道。“与委员会和标准的接触受到限制且费用昂贵，出席会议是获得发言权的必要条件，决策由出席者现场投票做出。”

Carruth 希望通过一个更加开放的[社区主导的环境](https://github.com/carbon-language/carbon-lang/blob/trunk/CODE_OF_CONDUCT.md)来制造碳。该项目将在 [GitHub](https://github.com/carbon-language/) 上维护，并在 [Discord](https://discord.com/invite/ZjVdShJDAs) 上讨论。

虽然 Carbon 最初是谷歌的一个内部项目，但开发团队最终希望在年底前将谷歌或任何其他单一公司的贡献减少到 50%以下。他们最终想把这个项目交给一个独立的软件基金会，在那里它的开发将由志愿者领导。

## 盒子里有什么？

设计者希望在年底发布一个核心工作版本(“0.1”)。Carbon 将建立在现代编程原则的基础上，包括一个[泛型系统](https://github.com/carbon-language/carbon-lang/blob/trunk/docs/design/generics/overview.md#what-are-generics)，这将消除检查和重新检查每个实例化代码的需要。

C++中缺少的另一个非常需要的特性是内存安全。内存访问错误是安全漏洞的最大元凶之一。Carbon 设计人员将寻找更好地跟踪未初始化状态的方法，设计支持动态边界检查的 API 和习惯用法，并建立一个全面的默认调试构建模式。随着时间的推移，设计者计划建立一个安全的碳子集。

根据文档，该语言将支持:

*   性能关键型软件
*   软件和语言进化
*   易于阅读、理解和编写的代码
*   实用的安全和测试机制
*   快速和可扩展的开发
*   现代操作系统平台、硬件架构和环境
*   与现有 C++代码的互操作性和从现有 c++代码的迁移。

开发团队还将着手创建一个内置的包管理器，这是 C++非常缺乏的。

下面是一些翻译成 Carbon 的 C++代码。首先，C++代码:

[![](img/4e37f7a7225e5721c533160bb1951030.png)](https://cdn.thenewstack.io/media/50657eb5-cpp_snippet.svg)

这是用碳写的同一个函数:

[![](img/0cc2037ad32b9a961d060c9ef6b8c32f.png)](https://cdn.thenewstack.io/media/30e03f42-carbon_snippet.svg)

开发团队计划编写翻译工具，将 C++代码移植为 Carbon 代码。

## 那为什么不生锈呢？

Rust 是另一种最近开发的语言[，专门用于解决](https://thenewstack.io/microsoft-rust-is-the-industrys-best-chance-at-safe-systems-programming/)内存安全性能应用的需求。那为什么不直接用铁锈呢？在 CPP North 的演讲中，Carruth 建议那些使用 Rust 的人继续使用它。Carbon 是给那些在 C++中已经有很大的代码库，很难转换成 Rust 的开发者用的。Carruth 特别提到了 Carruth 所谓的“后继语言”，它建立在一个已经存在的生态系统之上，这里是 C++。

“它是围绕与 C++的互操作性以及现有 C++代码库和开发人员的大规模采用和迁移而设计的，”文档解释道。这意味着语言应该像 C++一样高性能，它应该无缝地提供，并提供与 C++的双向互操作性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>