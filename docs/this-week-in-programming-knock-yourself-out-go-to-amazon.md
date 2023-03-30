# 本周编程:“把自己弄晕，去亚马逊”

> 原文：<https://thenewstack.io/this-week-in-programming-knock-yourself-out-go-to-amazon/>

“如果你想在一个便宜的地方经营一些东西，你可能会选择去亚马逊，而这对我们来说首先是无法盈利的。把自己敲出来，去亚马逊。”

这是 YugaByte 联合创始人兼首席技术官[卡蒂克·阮冈纳赞](https://www.linkedin.com/in/kranganathan)本周对[商业内幕](https://www.businessinsider.in/this-startup-is-giving-away-all-its-database-software-for-free-as-open-source-and-it-says-its-not-afraid-of-oracle-or-amazon/articleshow/70252801.cms)谈到他的公司决定[将 YugaByte DB 许可改为 100%开源](https://blog.yugabyte.com/why-we-changed-yugabyte-db-licensing-to-100-open-source/)时所说的话。在详述这一决定及其背后原因的博客文章中，阮冈纳赞宣布 [YugaByte DB](https://github.com/YugaByte/yugabyte-db) 现在在 Apache 2.0 许可下是 100%开源的，包括所有“以前关闭源代码的商业企业功能，如分布式备份、数据加密和读取副本。”

以前，YugaByte 一直采用开放核心模型，将企业功能保持在专有许可下。虽然该公司将在 Apache 2.0 下开放这些功能，但公告中潜在的更有趣的部分是关于他们将如何利用他们的 YugaByte 平台，他们现在发布的是来自 [Polyform 项目](https://polyformproject.org/)的可用的免费试用[许可证](https://polyformproject.org/licenses/free-trial/1.0.0/)。该许可证不符合开放源代码的标准，而是在试用期内提供源代码，在此期间，公司可以“在少于连续 32 个日历日的时间内评估软件是否适合特定的应用程序。”

Business Insider 写道，Polyform 项目是“一种全新类型的软件许可协议，由[…]一个开源许可律师团队撰写，其中包括律师希瑟·米克(Heather Meeker)，他是帮助 MongoDB 和其他人对抗主要云提供商的防御行动的杰出人物。”

阮冈纳赞写道:“一个健康的商业企业是持续投资开源软件的必备条件，尤其是在单一厂商[开源软件]项目的背景下。”。“开放核心货币化模式是最近许可争论的焦点。对于数据库和数据基础设施公司来说，开放核心传统上意味着为单独的商业版本保留某一类‘企业’功能。”

阮冈纳赞在副标题“DB 货币化已死，DBaaS 货币化万岁”下阐述了公司对货币化话题的想法

“我们 YugaByte 相信，如果 AWS 想要建立一个基于 OSS 项目的管理服务，几乎没有什么可以阻止它——来自 AWS 的竞争只是开发 OSS 所要付出的代价。包括 AGPL 在内的限制性许可可以降低 AWS 的速度，但不能阻止它，因此这种许可的真正影响是降低用户采用率。即使 AWS 建立了一项服务，这也是对 OSS 项目持久力的一个很好的验证，并让用户更加相信他们的投资将通过多方竞争得到保护。但这意味着商业 OSS 公司现在不得不与 AWS 竞争，竞争的优势在于出色的 DBaaS 体验，而不是核心 OSS DB 的优势。”

所以你有了它，开源数据库货币化的传奇和处理竞争的各种方法的另一个篇章。(还？只需点击下面推文中的链接。值了。)

## 本周的节目中

*   **为了安全，Rust 应该取代 C 和 C++吗？**今年早些时候，[我们看了微软安全工程师](/this-week-in-programming-blame-the-language-or-the-programmer/)[马特·米勒](https://twitter.com/epakskape)的一次演讲，他指出大多数 Windows 漏洞归结为由 C 和 C++引起的内存安全问题。好吧，微软已经决定，也许它应该采取[一种更安全的代码的主动方法](https://msrc-blog.microsoft.com/2019/07/16/a-proactive-approach-to-more-secure-code/)，并且它正在开始一个关于这个主题的博客系列，从把 Rust 作为一种替代的想法开始。"开发人员还想从安全工程中得到什么？"他们问道，并回答说“首先，他们可能希望在学习工具和过程上花费更少的精力来构建没有安全缺陷的特性。”因此，他们提出了内存安全语言，如 Rush 和 C#。虽然他们指出“C++确实有其吸引人的优点，在某些情况下是必不可少的:它非常快，内存和磁盘占用空间小，它很成熟，执行可预测”等等，但他们认为 Rust 结合了其中一些要求，同时还提供了内存安全。他们写道:“我们不应该为解决缺陷提供指导和工具，而应该努力防止开发人员在第一时间引入缺陷。”听起来像个计划，嗯？

*   **Python 3.8 正在向我们走来:**Python 的下一个版本正在路上，SDTimes 本周将在[关注 Python 3.8 的前景](https://sdtimes.com/softwaredev/what-to-expect-in-python-3-8/)，并指出第二个测试版已于本月早些时候发布，使 Python 3.8 的功能更加完整，在 10 月份正式版发布之前，还计划发布两个测试版预览。Python 下一版本中一些值得注意的特性包括赋值表达式、仅位置参数、运行时审计挂钩、Python 初始化配置、vectorcall 和带外数据 pickle protocol 5。同样值得注意的是，SDTimes 写道，去年实施的“[新治理模式](https://sdtimes.com/softwaredev/python-programming-language-gets-new-governance-model/)”引入了“五人指导委员会[……]用于建立标准实践和引入新功能。”根据 Python 团队的一个帖子,“委员会拥有广泛的权力，他们试图尽可能少地行使这些权力；相反，他们利用这种权力建立标准流程，就像其他 801x 系列 pep 中提出的那些流程一样。这遵循了一般的理念，即最好将大的变更分成一系列可以独立审查的小变更:我们不试图在一个 PEP 中做所有的事情，而是专注于为进一步的治理决策提供最小但坚实的基础。”要更深入地了解 Python 3.8，包括一些内幕，请查看 [Linux 每周新闻](https://lwn.net/SubscriberLink/793818/0c6f9dd271021cd4/)帖子。
*   **严格的 C++发布时间表背后的原因:**我们喜欢看一看编程语言的幕后工作，ISO C++标准委员会主席 [Herb Sutter](https://isocpp.org/wiki/faq/wg21#herb-sutter) 介绍了[为什么 C++标准每三年发布一次](https://herbsutter.com/2019/07/13/draft-faq-why-does-the-c-standard-ship-every-three-years/)，简单地写道“WG21 有一个严格的时间表(见 [P1000](https://wg21.link/p1000) ),根据这个时间表，我们每三年发布一次标准。我们不拖延。”为了避免经常出现的时间表为何如此严格的问题，他说这些问题会在“每个周期的这个时候”出现，萨特起草了一份常见问题解答，介绍“我们这样做的原因，以及决定采用这一时间表背后的一些历史。”根据这篇文章，只有两个项目管理选项:“选择功能，或者选择发布时间，无论你选择哪一个都意味着放弃决定另一个的控制权。不可能同时控制两者。”好吧，C++选择了第二个选项，如果你有任何问题，我们建议你阅读 FAQ。

https://Twitter . com/russellbrandom/status/1151491939688222720

*   **脸书开源爱马仕:**如果你对移动应用的性能感兴趣，那么你也会对脸书新开源的针对移动应用优化的[爱马仕 JavaScript 引擎感兴趣](https://code.fb.com/android/hermes/)。在试图找出移动应用程序的性能时，脸书写道，它“注意到 JavaScript 引擎本身是启动性能和下载大小的一个重要因素”，因此他们开始“在移动电话的更受限制的环境中优化 JavaScript 性能。”其结果是一个名为 Hermes 的新 JavaScript 引擎，该引擎“旨在提高应用程序的性能，专注于我们的 React 原生应用程序，即使是在内存有限、存储缓慢和计算能力下降的大众市场设备上。”根据该博客，Hermes 提供了更快的交互时间、更小的下载大小和更好的内存利用率，并通过采用字节码预编译、提前编译器而不是即时编译器以及增强的垃圾收集器策略来实现这一点。要开始，查看在 React Native 上使用 Hermes 的迁移的完整说明。

特征图片:[英国新版 50 英镑钞票上印着艾伦·图灵](https://www.bankofengland.co.uk/banknotes/50-pound-note-nominations)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>