# WebAssembly:当你讨厌 Rust 却热爱 Python

> 原文：<https://thenewstack.io/webassembly-when-you-hate-rust-but-love-python/>

WebAssembly 的主要属性之一是它如何适应部署的许多不同的语言——至少在理论上是这样——只要有 CPU 设备可以运行指令集。Wasm 可以运行的语言除了 JavaScript 之外，还包括 [Rust](https://thenewstack.io/rust-by-the-numbers-the-rust-programming-language-in-2021/) 、 [Go](https://thenewstack.io/go-1-18-the-programming-languages-biggest-release-yet/) 。NET、C++、Java、[PHP](https://thenewstack.io/php-has-survived-for-26-years-because-it-keeps-evolving/)——和 [Python](https://thenewstack.io/an-introduction-to-python-for-non-programmers/) (下面有很多关于 Python 的内容)。

作为早期的 web 浏览器应用程序，Wasm 已经并将继续与 JavaScript 紧密结合。最近，Rust 加入了竞争，它与 JavaScript 的集成，甚至在没有 JavaScript 的情况下单独运行 WebAssembly 应用程序，都显示出很大的前景。

但是让我们看看开发者。例如，许多开发人员都在与 Rust 作斗争。对于许多人来说，即使不是大多数从零开始学习它的人，甚至是那些可能相当熟悉 C++的人来说，这被认为是非常困难的，因为 c++与它有许多共同的属性。当然，有许许多多的 JavaScript 程序员深入参与了 web 应用程序和移动应用程序的开发，这对于这些人来说很好，但是它将把我们其他人引向何方呢？

尤其是 Python，它是最受欢迎的编程语言之一，正如我们所知，它非常适合机器学习、边缘情况(在许多情况下像 JavaScript)和其他应用程序。很多人(包括这位作者)喜欢它，因为它相对容易学习，而且非常干净。理论上，WebAssembly 可以容纳 Python 和其他语言，但它在 Wasm 中的实际使用仍然有限。但这种情况正在改变。好消息是将 WebAssembly 用于 Python 已经开始出现。

Fermyon Technologies 的首席执行官兼联合创始人马特·布彻(Matt Butcher)对此表示赞同，但他表示将“更进一步”。事实上，要使 WebAssembly 不仅仅是一项利基技术，它绝对必须获得大多数(如果不是全部)顶级语言的支持。这包括像 Python 这样的脚本语言。"

具有讽刺意味的是，对于一年前今年 2 月成立的 Fermyon 来说，这家初创公司的口号之一是广泛的语言支持对 Wasm 的成功至关重要。“从 web 开发到机器学习，Python 是一门至关重要的语言，”Butcher 说。“如果没有一流的 Python 支持，我很难想象 WebAssembly 能发挥出它的全部潜力。”

事实上，Python 最终将在 Wasm 中为许多应用程序展示其价值，在这些应用程序中，Python 比 JavaScript 和/或 Rust 更出色。机器学习和大数据处理就是很好的例子。Butcher 指出，这些应用程序的开发人员“长期以来一直把 Python 当作他们的通用语言。“WebAssembly 可以为这些生态系统提供很多东西——特别是在安全性和可移植性方面，”Butcher 说但是这种潜力只有在顶级 Python 支持下才能实现。"

Python 也一直是 web 应用程序后端的首选语言。“有了丰富的包和技术，Python 在这个领域也有很多优势，”Butcher 说。

## 数据科学方面的大成就

许多数据科学开发人员期待着有一天他们能够轻松利用 Wasm 更加无缝地部署他们的 Python 代码，而不必针对不同的 edge 和其他环境进行重新编译，从而为分布式部署提供支持。由于数据科学，特别是深度学习用例，已经为 Python 的流行做出了巨大贡献，在 Wasm 边缘运行推理模型的能力可以大大简化这些模型的部署、操作、升级和可扩展性，[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉新堆栈。

Volk 说，能够在 Wasm 上训练机器学习模型将使数据科学家能够受益于 Wasm 的能力，即“缩小到零”以最大限度地降低成本，并几乎立即按需扩大到任意数量的节点。“这可以让组织使用昂贵的 GPU，以更有效的方式加速深度学习模型的训练，因为单个工作负载可以使用这种硬件‘轮班’，”沃尔克说。“我希望看到的是一个用于 Python 的 Wasm SDK，它允许我轻松地安装任何 Python 库，以便开发人员和数据科学家可以非常快速地建立可弃置和易于移动的环境，”Volk 说。

Volk 说，如果 Wasm 可以帮助即时 Python 运行时可用，而不会给开发人员带来麻烦，也不会给托管者带来开销成本和安全问题，这将大大降低许多公民开发人员和数据科学家的准入门槛，他们经常因必须创建自己的开发环境而感到恐惧。此外，“结合在任何支持 Wasm 的机器上运行结果代码的能力，这可以大大加快实验速度，并说服更多的专业人士采用 Python，”Volk 说。

## 对…有效

同样，Python 的势头也在增长。但是 Wasm 支持还没有完全准备好。“Python 是世界上最流行的编程语言之一，它的 WebAssembly 实现似乎进展很快，”Butcher 最近在一篇[博客文章中写道。“虽然它还没有准备好投入使用，但我们预计它将在 2022 年上半年投入使用。”](https://www.fermyon.com/wasm-languages/python)

但是工作需要完成。虽然 Python 由于其受欢迎程度而相对容易销售(毕竟，与其他语言相比，Rust 开发人员社区较小，如 [Sehyo Chang、](https://www.linkedin.com/in/sehyo/) [InfinyOn 的](https://infinyon.com/) CTO、使用 Wasm 进行事件流和处理以降低延迟，注意到了)，并且正在成为数据科学和机器学习的主导语言——成功不是必然的。Chang 说:“我们还致力于支持 Python 作为一流语言，特别是在 WebAssembly 方面。”“然而，在 WebAssembly 中支持 Python 存在重大挑战，解决这些挑战需要一些时间。”

随着[CPython](https://github.com/python/cpython)——Python 引用解释器—[em scripten](https://emscripten.org/)——和基于 WASI 的实现将很快成为现实。Chang 说，由于 CPython 是最受欢迎的 Python 运行时环境，因此从逻辑上来说，使其能够在上运行将会刺激的普遍采用。

虽然 WebAssembly 正在成为一种通用技术，并且“将永远在浏览器中占有一席之地”，但 Esmcripten 支持对于浏览器功能非常重要。同时，WASI 对于浏览器之外的应用也是必要的，Butcher 说。“CPython 团队明智地选择引入对两者的支持，让两个阵营的开发人员都可以使用世界上最流行的编程语言之一，”Butcher 说。

## Python 潮流

许多组织，无论是初创企业还是老牌企业，都在增加或寻求增加 Wasm 支持，这是可以理解的。

[VMware](https://tanzu.vmware.com?utm_content=inline-mention) 最近增加了对 [Wasm 语言运行时](https://github.com/vmware-labs/webassembly-language-runtimes/)的 Python 支持。根据该项目的文档，在其文档中，Wasm 语言运行时提供了流行的语言运行时，如 Ruby 和其他语言以及 Python，它们预编译为 WebAssembly，经过兼容性测试，并在上游语言的新版本发布时保持最新。

它为 wasm32-wasi 目标提供了一个 Python 构建。基于 CPython(Python 的主流、基于 C 的实现)中已经可用的 WASI 支持，额外的库和使用示例使其尽可能易于使用，以增强运行时，VMware 的员工工程师 [Asen Alexandrov](https://bg.linkedin.com/in/asen-alexandrov-5546a122) 在[博客帖子中写道。](https://wasmlabs.dev/articles/python-wasm32-wasi/)

Chang 说，InfinyOn 正在努力支持 Python 成为“我们智能模块技术中的一等公民”。他说，这肯定会刺激在 WebAssembly 环境中支持 Python 的进一步发展。

Fermyon 将很快发布一个 Python SDK 用于 Spin。这个 Python SDK“完全是由 CPython 团队的工作实现的。”事实上，“Wasm Python SDK 是我们最常要求的特性之一，”Butcher 说。

请继续关注关于 Wasm 的这些和其他 Python 替代品如何工作以及开发人员如何利用它们的更多报道。也就是说，Fermyon 提供了一个带有命令行指令的[教程](https://www.fermyon.com/blog/python-wag)来展示如何使用 Python 来为 [WAGI](https://github.com/deislabs/wagi) 创建一个模块，这将很快成为新堆栈教程的基础。

敬请关注。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>