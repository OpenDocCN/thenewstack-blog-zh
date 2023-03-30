# Mozilla 的 Rust 1.0 Alpha 版本有望取代 C++

> 原文：<https://thenewstack.io/mozillas-rust-1-0-alpha-release-comes-hopes-replacing-c/>

Rust 1.0 的 alpha 版本对于 Mozilla 支持的系统编程语言来说是一个重要的日子。这不是最终的 1.0 版本，但它是编程语言稳定性的下一步，这是为了安全和速度而开发的。所有功能都已就绪，预计不会有重大的突破性变化。核心库是符合特性的。根据[黑客新闻线索](https://news.ycombinator.com/item?id=8863451)，这意味着，例如，Rust 现在将在六周的发布周期。

Rust 团队要求在与路径操作和 I/O 模块相关的库上进行更多的交互，这些库仍然是稳定的。在测试版发布之前，他们需要更多的使用。他们还需要解决 Rust 中已经被标记为稳定的部分的其他问题。建议“在 alpha 周期中，我们建议使用夜间发布，这将随着这些 API 的最终成型而继续发展。”

Rust 是 Mozilla 研发团队的第一个项目，旨在取代 C++。如果说 Rust 有什么原因的话，那就是它提供的安全性，而不是 C++。例如，正如 OpenSource.com 邮报[所引用的，在上次 Pwn2Own 竞赛中发现的 Firefox 中的三个漏洞都是因为 C++(例如，错误管理的指针)。在 Rust 中，这类编程错误甚至无法编译。"](http://opensource.com/life/14/6/mozillas-rust-programming-language-critical-stage)

[https://www.youtube.com/embed/bsVRuwJC15Y?feature=oembed](https://www.youtube.com/embed/bsVRuwJC15Y?feature=oembed)

视频

Rus 被设计成内存安全的，不使用垃圾收集。据 GitHub 称，Rust 最初是由 Mozilla 设计的，旨在成为一个实验性浏览器架构的原型平台。他们还希望它更易于并行化，并且“不容易出现常见的 C++编码错误”

这是铁锈的早期阶段。但是它得到了像阿明·罗纳切尔这样的人的支持，他在十月份写了这篇关于铁锈的文章:

Rust 的内存跟踪概念是否足够强大，以至于我们会将其作为有效的编程模型接受？我不确定。我确实相信尽管铁锈已经可以自立了。即使结果证明借用检查器不健全，我相信它也不会对语言的广泛采用造成任何伤害。它正在发展成为一门非常好的语言，没有 GC 它也能很好地工作，你可以在没有运行时的情况下使用它。

但有一个问题是，像 Mozilla 这样的基金会如何成功地让 Rust 流行起来。提倡者会引用它的实用性，内存共享和速度。但是必须考虑到一些硬性的经济因素。比如 Go，是谷歌支持的。Rust 没有这种企业支持，尽管三星已经投入资源进行开发。

特色图片[通过](https://www.flickr.com/photos/andrec/2893549851/in/photolist-7mivM9-5pGcyx-5fzQ9U-9vhj6a-ak2VXn-5akr6H-nXqyTN-Nr1P7-cUB2o7-rVSQY-bbx7NT-5VyJc1-bvnUkP-4BpdVf-bMkjMT-byqDku-fUNJrv-jDwRZg-3EkFE-j9HCc1-kyzi7D-4n2jy3-ddCVmu-5uqnyL-5SVjS6-b2pnTx-6w1egH-wpvBr-dhVZtQ-4ffZF4-cFisqh-48kjGt-6y4bXT-5fveur-4QCVn9-nC3DGG-cvW4pW-by8qgU-by8pYC-bM37aa-bM36Zc-bM37hK-SWWZ7-eZhTXG-q9MwzZ-o7VLcE-aN28JV-e4MYbV-88eVwS-by8pJu) Flickr 知识共享

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>