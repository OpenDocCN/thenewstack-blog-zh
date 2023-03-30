# 本周节目:GitHub 重新向伊朗开放

> 原文：<https://thenewstack.io/this-week-in-programming-github-opens-back-up-to-iran/>

为了遵守美国对 T2 的贸易制裁，GitHub 封锁了一些地方——克里米亚、古巴、伊朗、朝鲜和叙利亚——访问它的网站已经有一年多了，但本周该公司宣布,[再次在伊朗完全可用。](https://github.blog/2021-01-05-advancing-developer-freedom-github-is-fully-available-in-iran/)

“今天我们宣布一项突破:我们已经获得了美国政府的许可，向伊朗的开发者提供 GitHub。这包括为个人和组织提供的所有服务，私人和公共的，免费和付费的，”GitHub 首席执行官 [Nat Friedman](https://github.com/nat) 在一篇博客文章中写道。

Friedman 指出，虽然他们继续向这些国家公开回购，但他们也开始与外国资产控制办公室(OFAC)打交道，申请许可证，他形容这是“在受制裁国家倡导广泛和开放 GitHub 的漫长而密集的过程。”

弗里德曼在一篇[黑客新闻评论](https://news.ycombinator.com/item?id=25648849)中称之为“纯属巧合”，这个消息对一家公司来说来得正是时候，该公司在前一天突然[失去了对 GitHub](https://twitter.com/sebslomski/status/1344219609923276801) 的账户访问，当时据说一名员工“在看望他在伊朗的父母时打开了他的笔记本电脑。”

虽然此举受到伊朗许多开发者的欢迎(尽管许多人指出使用 VPN 是一种常见的解决方案)，但 GitHub 表示，它“正在与美国政府合作，以确保克里米亚和叙利亚的开发者也获得类似的许可证”——这一点似乎引发了一些困惑。

## 本周的节目中

*   **Wasmer 采用通用 WebAssembly GA:**[Wasmer](https://wasmer.io/)，该公司一直致力于通过创建通用二进制文件使 web assembly 在 JavaScript 之外可访问，[发布了 Wasmer 1.0](https://medium.com/wasmer/wasmer-1-0-3f86ca18c043) ，带来了改进的运行时和编译器性能以及新功能，包括更好的错误处理、更强大的 API、交叉编译、headless Wasmer 等等。Wasmer 采用多种不同语言编写的代码，允许用户将其编译成独立的二进制文件，可以在任何操作系统和浏览器上运行，现在该公司表示，该工具已准备好投入生产。此外，该公司表示，最新版本的 Wasmer 现在支持新的苹果 ARM 架构，用户可以通过安装 CLI 或在自己选择的语言中嵌入 Wasmer 来开始使用。

*   **2020 年文档季结束:**作为一名开发人员，除了注释代码，你最不想做的事情就是编写面向用户的文档。对于开源开发者来说，这就是谷歌的[Docs](https://developers.google.com/season-of-docs)季可以提供帮助的地方，因为该项目每年都将技术作家与开源项目配对，以帮助创建文档。因此，2020 年是该项目运行的第二年，谷歌本周宣布了 2020 年计划的[结果，声称有 64 名作家](https://opensource.googleblog.com/2021/01/season-of-docs-announces-results-of.html)[成功完成了他们的项目](https://developers.google.com/season-of-docs/docs/participants)，预计 3 月份将完成 18 个更大的项目。如果你对获得一些帮助来记录你的项目感兴趣，一定要注册 2021 年文档季的[公告邮件列表](https://groups.google.com/group/season-of-docs-announce)。
*   Python 再次坐上了 TIOBE 的头把交椅:TIOBE 指数，根据搜索引擎结果对编程语言受欢迎程度进行的[排名](https://thenewstack.io/this-week-in-programming-ignore-the-rumors-of-cs-meteoric-rise/)，宣布了其年度“年度语言”公告，[有史以来第四次将该奖项授予 Python](https://www.tiobe.com/tiobe-index/) 。该项目领导写道，“这是一年中最受欢迎的编程语言”，Python 在 2020 年上升了 2.01%，他们将其归功于“学习语言的容易程度和高生产率”，以及它的众多用例。如果编程语言赛马是你的囊中之物，请继续阅读。

*   **Rust 1.49 增加了架构:**随着 Rust 1.49.0 的[发布，该语言现在已经将 64 位 ARM Linux 架构提升到](https://blog.rust-lang.org/2020/12/31/Rust-1.49.0.html) [Tier 1 支持](https://doc.rust-lang.org/stable/rustc/platform-support.html)，这为该语言在该架构上正确测试提供了最高的支持保证。同时，64 位 ARM macOS 和 Windows 架构都达到了 [Tier 2](https://doc.rust-lang.org/stable/rustc/platform-support.html) 。除此之外，还有一些标准库的变化，可以在[详细发行说明](https://github.com/rust-lang/rust/blob/master/RELEASES.md#version-1490-2020-12-31)中找到。另一个独立但相关的消息是，上周的一篇博客文章评论说，Rust 现在在基准测试中总体上比 C 快，尽管 tho 仍然比 C++略慢。
*   **Ruby 3.0 拥有 3 倍的速度提升:**自 2015 年开发以来， [Ruby 3.0.0 最近发布](https://www.ruby-lang.org/en/news/2020/12/25/ruby-3-0-0-released/)，宣称目标是提高性能、并发性和类型。具体来说，宣布这一消息的博客文章引用了 Ruby 创造者 Yukihiro Matsumoto 的话，称“Ruby3 将比 Ruby2 快 3 倍”，又名 [Ruby 3×3](https://blog.heroku.com/ruby-3-by-3) 。根据一篇深入该语言最新版本历史的 [DevClass 文章【the Ruby 社区“把重点放在改进 JIT 上，以提高频繁调用相同方法的应用程序的性能。为此，他们解决了 JIT 代码和编译过程本身，避免了垃圾收集或在后台执行，并减少了 Ruby 和 JIT 线程之间的锁数量。Ruby 3.0 从 2.7 开始还引入了许多新特性，包括“多个方法共享的本机函数的重复数据删除例程，对一些 C 方法的方法内联支持，以及实例变量的改进，如核心类中的访问优化，以及冗余检查的减少。”](https://devclass.com/2021/01/04/ruby-3-programming-language/)

*   **回顾 2020 年:**我们知道，在现实世界中，你可能很少想回顾 2020 年，但就软件开发而言，可能会有一些过去一年的事情需要反思，所以我们想以一些来自网络的综述来结束。首先，NodeSource 博客提供了 2020 年 Node.js 的[十大亮点](https://nodesource.com/blog/need-to-node-vol-69)，包括 Node.js 15 的[发布。与此同时，GitHub 回顾了 GitHub 教育课堂，Docker 查看了 2020 年点击率最高的 Docker 博客文章，脸书回顾了 2020 年的连接创新，更快的应用程序和零网络的进展。ITPro 还关注了 2020 年的主要 DevOps 趋势，而新的 Stack 回顾了 2020 年被遗忘的故事，并提供了大编辑团队的回顾回顾。现在，到 2021 年！](https://nodejs.medium.com/node-js-v15-0-0-is-here-deb00750f278)

特色图片 par Serkan 土耳其人德皮沙贝。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>