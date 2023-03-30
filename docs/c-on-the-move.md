# C++在移动中

> 原文：<https://thenewstack.io/c-on-the-move/>

尽管取代 C++ 或支持主流系统编程语言的努力仍在继续，但适当的 C++标准的工作仍在继续，ISO C++委员会上月完成了该规范最新版本 [C++23](https://en.cppreference.com/w/cpp/23) 的技术工作。

[ISO C++标准委员会主席](http://www.open-std.org/jtc1/sc22/wg21/)兼微软软件架构师 Herb Sutter[在一篇](https://github.com/hsutter)[博客文章](https://herbsutter.com/2023/02/13/c23-pandemic-edition-is-complete-trip-report-winter-iso-c-standards-meeting-issaquah-wa-usa/)中说，简而言之，C++23 功能已经完成，下一个版本 [C++26](https://medium.com/yandex/c-23-is-finalized-here-comes-c-26-1677a9cee5b2) 的工作正在进行中。

## 在野外

与此同时，就开发者的受欢迎程度而言，在野外，C++似乎正在火上浇油。根据编程语言的 [TIOBE 索引](https://www.tiobe.com/tiobe-index/)，上个月 C++是增长最快的编程语言——比上一年同期上升了近 6 个百分点(5.93%)。此外，今年 1 月，TIOBE 授予 [C++](https://thenewstack.io/c-23-standard-wont-have-a-key-parallelism-feature/) 编程语言，因为它在 2022 年获得了最大的人气。总体而言，2022 年 C++的受欢迎程度同比增长了 4.62 个百分点，领先于其他所有产品。2023 年 3 月，C++比去年同期增长了 4.64%，在最受欢迎的语言中排名第四，仅次于 Python、C 和 Java。

“作为一种高级面向对象语言，它的性能非常出色。正因为如此，有可能用 C++开发快速而庞大的软件系统(超过数百万行代码),而不一定会陷入维护的噩梦中。

此外，“性能似乎很重要。C++竞争对手 [Rust](https://thenewstack.io/rust-project-reveals-new-constitution-in-wake-of-crisis/) 再次进入前 20 名(一年前排名第 26 位)，但这次似乎是真的，”TIOBE 说。

C++ [编程语言](https://thenewstack.io/what-should-be-a-students-first-programming-language/)有多种用途，包括构建软件基础设施和资源受限的应用，包括桌面应用、视频游戏、电子商务服务器、网络搜索或数据库，以及电话交换机甚至太空探测器等对性能至关重要的应用。

## 委员会工作

与此同时，随着指导委员会完成 C++23 的技术工作，“没有添加或删除任何功能，我们只是处理适合和完成的问题，并主要专注于解决我们在夏季国际意见投票(委员会草案，或 CD)中收到的 137 条国家机构意见，”萨特写道。“你可以在这里找到 C++23 特性的列表[，其中许多已经在主流编译器和库](https://en.cppreference.com/w/cpp/compiler_support/23)中实现。C++23 的主题是“完善 C++20”，一些亮点包括模块“std”、“if consteval”、“explicit”this”参数、更多 constexpr、更多 CTAD、“[[assume]]”、简化隐式 move、多维和静态“operator[]”、一系列 Unicode 改进。"

此外，“除了 C++23 的工作，我们也有时间在许多后 C++23 提案上取得进展，包括继续在合同、SIMD 执行等方面的工作，”他说。

## Visual Studio 17.5 中的 C++

上个月还见证了微软 [Visual Studio 17.5](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-17-5-released/) 的全面上市，它包含了 C++的新功能，包括现代 C++和游戏开发功能。这个版本还包括几个针对 C++开发人员的生产力增强，包括一个 UE 资产检查器和针对宏扩展的[智能感知](https://thenewstack.io/this-week-in-programming-github-copilot-copyright-infringement-and-open-source-licensing/)改进。该公司表示，所有这些功能都有助于游戏、跨平台或嵌入式应用的开发。

对于 C++23 标准一致性，“我们正在继续我们在 C++23 标准一致性方面的工作，给你几个新的标准库特性供你尝试，”微软 C++团队的 C++开发者倡导者 Sy Brand 在[博客文章](https://devblogs.microsoft.com/cppblog/visual-studio-17-5-for-cpp-devs/#_Toc127193072)中写道:

std::ranges::fold_left、fold_right 和 friends 定义了 [fold](https://en.wikipedia.org/wiki/Fold_(higher-order_function)) 操作，类似于 std::accumulate，但更通用。例如:

std::vector <double>v = {0.25，0.75 }；</double>

auto sum = ranges::fold_left(v，0，STD::plus())；

Brand 解释说，该版本还为 C++提供了新的构建性能、开发人员工作效率和代码安全特性。

## 进化还是别的？

“我不需要搜索 C++代码，所以新的搜索工具对我来说没什么用，”Richard Campbell 说，他是 [CloudArmy](https://cloud.army/) 的非执行主席、[微软地区总监](https://rd.microsoft.com/en-us/)、[微软 MVP](https://mvp.microsoft.com/en-us/) 和[devintercuit](https://www.devintersection.com/#!/)的创始人。

“看看 C++在过去几年中是如何现代化的很有意思——例如将 async 和 await 从 C#添加到语言中，”坎贝尔告诉新堆栈。“关于 C++安全性的整个讨论代表了一个根本性的变化。毕竟，C++是出了名的‘不安全’语言，也就是说，安全的责任在于开发人员和他们的调试器，而不是语言本身。”

坎贝尔解释说，这样做的理由是速度、速度、速度——当你在语言中增加类型和内存安全时，你就为你运行的每一位代码增加了额外的执行步骤。然而，速度有那么重要吗？如今，处理器和内存的速度非常快。有人关心你的函数在不安全的情况下运行 0.05 秒还是安全的情况下运行 0.1 秒吗？

“现在把 Rust 带到桌面上来——一种非常适合 C++通常占主导地位的低级编程的语言，但具有内置的内存安全和其他现代功能，”坎贝尔说。“当像 Mark Russinovich 这样的杰出人物说['…[停止启动任何新的 C/C++项目并使用 Rust](https://twitter.com/markrussinovich/status/1571995117233504257?lang=en)…']时，C++必须发展，否则就会落后。问题是，以什么代价？”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>