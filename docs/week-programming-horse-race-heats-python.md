# 本周编程:Python 让语言赛马热了起来

> 原文：<https://thenewstack.io/week-programming-horse-race-heats-python/>

每个人都喜欢赛马，不管这些马是真正的马、浏览器、网络标准还是编程语言。在本周的编程中，赛马仍然很活跃，因为我们研究了几种不同的顶级语言，包括一篇建议我们完全重新思考我们的堆栈的帖子(正如我们经常做的那样)。

本周首先，[开发人员公布了他们认为最需要学习的前五种](https://www.techrepublic.com/article/which-are-the-most-important-programming-languages-to-learn-developers-reveal-their-top-five/)编程语言，几乎没有明显的惊喜——JavaScript 和 Java 共同领先，C++、Python 和 SQL 紧随其后。PHP、Swift、Ruby、NoSQL 和 Haskell 也榜上有名。

虽然不在名单上，但该研究的创始人指出——不管结果如何 COBOL 这样的语言应该被视为“公司愿意为利基语言支付高价的更广泛趋势，[在今年的 Stack Overflow 调查](https://www.techrepublic.com/article/what-are-the-highest-paid-jobs-in-programming-the-top-earning-languages-in-2017/)中强调了这一点，该调查发现，“专注于 Clojure、Mozilla 的 Rust、Erlang 派生 Elixir 和谷歌创建的 Go 等相对罕见语言的开发人员薪酬最高。”然而，在跳到 COBOL 之前，还要注意“在英国的 Glassdoor.com 上搜索 COBOL 职位会返回 57 个职位，而 JavaScript 程序员职位有 844 个。”

虽然 Python 在该榜单上排名第三，但 Stack Overflow 最近根据 GDP 对[编程语言和喜欢它们的国家之间的关系](https://stackoverflow.blog/2017/08/29/tale-two-industries-programming-languages-differ-wealthy-developing-countries/)进行了基于数据的调查，并成功利用了数据驱动的新闻报道[Python 的惊人增长](https://stackoverflow.blog/2017/09/06/incredible-growth-python/)根据其分析，在高收入国家，“Python 有充分的理由成为增长最快的主要编程语言”，而在低收入国家，Python 仍然占据着一席之地，只是落后了。

除了堆栈溢出编写器之外，还有一个有趣的地方:

*我们不想引发任何“语言战争”一种语言的用户数量并不意味着它的质量，当然也不能告诉你哪种语言更适合特定的情况。然而，考虑到这一点，我们认为有必要了解开发人员生态系统是由哪些语言组成的，以及这个生态系统可能会如何变化。*

抛开“难以置信的增长”不谈，[InfoWorld](https://www.infoworld.com/article/3223224/python/why-python-and-c-cant-displace-java-c-or-c.html#jump)中的一个观点认为 Python 和 C#无法在这场竞赛中取代 Java、C 或 C++:

*Python 和 C#早就准备好成为下一个重要的编程语言，但由于它们的局限性，这种情况还没有发生，Tiobe 报告的作者指出:“C#不是前三名语言，因为它在非 Windows 世界的采用率仍然很低。另一方面，Python 是动态类型的，这是大多数大型和/或关键软件系统使用它的障碍。”*

最后，在猜测你日常使用的每一个工具的领域中，InfoWorld 再次考虑为你的下一个编程项目考虑[均值与 LAMP 堆栈。开发者网站对 MEAN stack 的注释“就在几年前，MongoDB、Express.js、AngularJS 和 Node.js 还在引起人们的关注。现在他们已经长大并联合起来，一起做着严肃的工作，从庞大的 LAMP 阵营中挖走了不少开发人员。”](https://www.infoworld.com/article/2937159/javascript/mean-vs-lamp-for-your-next-programming-project.html)

这里的最终结论是什么？“对于可以从灵活性、简单性和性能中受益的绿地项目，走中庸之道可能会让你的生活比你想象的更好。”

好了，这周的赛马到此为止。以下是我们在本周的编程中发现的其他一些引人注目的事情:

*   虽然 Python 可能正忙于试图超越所有的竞争对手，但它仍然有一些缺陷，并且在 Python 路线图上有[四个主要修复，包括缩短启动时间，加快命名元组，重构 CPython 内部 API，以及(可能)放弃 Python 的](https://www.infoworld.com/article/3221482/python/4-major-fixes-on-the-python-roadmap.html)[全局解释器锁](https://stackoverflow.com/questions/1294382/what-is-a-global-interpreter-lock-gil)。
*   IBM 本周宣布了一整套用于量子计算的新 Jupyter 笔记本电脑，以及他们连接到互联网供你使用的量子计算机的实验能力。20+ Jupyter 笔记本专注于 IBM 的 [QISKit](https://github.com/QISKit) (量子信息软件开发工具包)。来自博客:“无论你是一名量子研究科学家，试图研究量子态的基本原理，还是一名希望了解你实际上如何解决化学或优化问题的开发人员，或者是一名好奇如何构建量子游戏的人，你都会喜欢我们刚刚发布的内容。在此邀请您加入已经在该系统上运行的 100 多万次实验。”
*   对于那些为谷歌的各种开源项目做出贡献的人，如[、Kubernetes](https://kubernetes.io/) 、 [AMP](https://www.ampproject.org/) 或 [Dart](https://www.dartlang.org/) ，谷歌本周宣布将[公开《谷歌开发者文档风格指南》](http://developers.googleblog.com/2017/09/making-google-developers-documentation.html)“以允许开发者文档之间更加一致。”Google notes 的[开发人员文档风格指南](https://developers.google.com/style/)更像是一份参考资料，而不是坐下来边喝咖啡边阅读的东西……但是无论什么都能让你开心，对吗？
*   上周我们注意到谷歌发布了 [ARCore](https://developers.google.com/ar/) ，它是苹果 [ARKit](https://developer.apple.com/arkit/) 的翻版。本周，我们将与增强现实基金和孵化器 [Super Ventures](http://www.superventures.com/) 的合伙人 [Matt Miesnieks](https://twitter.com/mattmiesnieks) 一起回顾 ARCore 如何优于 ARKit？ Miesnieks 深入研究了每辆车的细节，发现这两辆车确实(与赛车主题保持一致)并驾齐驱。“开发者应该关注的事情，”他写道，“是构建人们关心的 AR 应用程序确实具有挑战性。学习如何在 ARKit 或 ARCore 上构建比学习构建什么要容易得多。”至于产品本身，他说“作为一种技术解决方案，它们在性能上非常接近。当谈到你现在可以构建的用户体验时，用户实际上是难以区分的。ARKit 在硬件/软件集成和更可靠的跟踪方面有一些技术优势。ARCore 在映射和更可靠的恢复方面有一些优势。”
*   最后，Rust 发布了 [Rust 2017 年调查结果](http://blog.rust-lang.org/2017/09/05/Rust-2017-Survey-Results.html)，该调查主要从当前用户的角度出发，但也从那些留下它的用户的角度出发，发现它在未来的主要关注领域——根据受访者的说法——应该是更好的人体工程学、文档、库支持、IDE 支持和不太陡峭的学习曲线(按此顺序)。

专题图片:“夏延”，弗雷德里克·雷明顿的青铜雕塑，1907 年，纽约大都会艺术博物馆，公共领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>