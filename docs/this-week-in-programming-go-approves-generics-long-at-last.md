# 本周编程:Go 终于批准了泛型

> 原文：<https://thenewstack.io/this-week-in-programming-go-approves-generics-long-at-last/>

欢呼吧，所有的地鼠们，在经历了[多年](https://thenewstack.io/week-programming-go-2-0-question-complexity/) [年](https://thenewstack.io/this-week-in-programming-specifically-generic/)[辩论](https://thenewstack.io/this-week-in-programming-gophers-dig-into-generics-go-2-0-and-gophercon-2018/)之后，关于 Go 编程语言是否将采用泛型的问题终于在本周得到了解答，上个月提出的[提案](https://thenewstack.io/this-week-in-programming-has-the-time-finally-come-for-generics-in-golang/)得到了[的接受](https://github.com/golang/go/issues/43651#issuecomment-776944155)。

在这份[最新提案](https://blog.golang.org/generics-proposal)中， [Golang](https://golang.org/) 团队成员 [Ian Lance Taylor](https://research.google/people/author37504/) 写道，自 2009 年该语言首次发布以来，泛型一直是“最常被要求的语言特性之一”，但即便如此，它的采用也不无担忧。Taylor 在他的提案介绍中解释了泛型的概念:

“泛型可以为我们提供强大的构建模块，让我们更容易地共享代码和构建程序。泛型编程意味着编写函数和数据结构，其中一些类型留待以后指定。例如，您可以编写一个对任意数据类型的切片进行操作的函数，其中实际的数据类型仅在调用该函数时指定。或者，您可以定义存储任何类型值的数据结构，其中要存储的实际类型是在创建数据结构的实例时指定的。

正是这种价值主张——能够编写可重用的代码——让一些开发人员兴奋不已，并一直在背后推动。

虽然我们不需要重新讨论反对采用泛型的各种论点，但现在一个提案终于通过了[提案流程](https://github.com/golang/proposal)，一个新的担忧在几个用户中发出了声音:当用锤子呈现时，[一切看起来都像钉子](https://en.wikipedia.org/wiki/Law_of_the_instrument)。

然而，这并不是第一次，一个新的语言特性面临这种恐惧。当通道被引入到语言中时，它们也成为了一个特征，一时间，[把一切都变成了钉子](https://github.com/golang/go/issues/43651#issuecomment-777622945)。随着时间的推移，这种担心逐渐消失，现在的希望是，随着仿制药的采用，同样的事情也会发生。

只有时间会告诉我们，现在，在你们所有的地鼠能够得到期待已久的功能之前，还有一段时间。至少根据最初的提议，目标“将是在今年年底之前有一个完整的，尽管可能没有完全优化的实现供人们尝试，可能是 Go 1.18 测试版的一部分。”

现在，在继续了解过去一周编程领域发生的事情之前，这里有一个视频，看看未来几年随着云原生一切的出现，编程的潜在范式转变。

[https://www.youtube.com/embed/FeRg-7Sr1L8?feature=oembed](https://www.youtube.com/embed/FeRg-7Sr1L8?feature=oembed)

视频

## 本周的节目中

*   **模式匹配对 Python 来说是不是太远了？**泛型并不是本周唯一有争议的编程语言，Python 指导委员会做出了[决定，接受](https://lwn.net/ml/python-dev/61D540B9-2FE5-4CC8-8038-5654B1D325C7%40python.org/)大量 Python 增强提案(pep ),统称为模式匹配 pep。“我们承认模式匹配对 Python 来说是一个广泛的变化，在整个社区达成共识几乎是不可能的，”该委员会写道，尽管如此，他们“有信心在 PEP 634 等中指定的模式匹配将是 Python 语言的一个伟大补充。”一位反对者找到了 iProgrammer 的页面，标题是“ [Python 采用模式匹配——厨房水槽下一个](https://www.i-programmer.info/news/216-python/14342-python-adopts-pattern-matching-kitchen-sink-next.html)”虽然他们“不认为模式匹配是添加到 Python 中的一件坏事”，但他们认为它的添加是特性膨胀的一部分。他们写道:“这似乎是一个只有微小优势的非必需品。”“然而，它确实符合语言的生命周期:首先，它小巧、紧凑、可爱；然后，它添加了许多程序员遗漏的部分；然后，它增加了其余部分，包括厨房的水槽，安于一个臃肿的老年，等待一种新的简洁而简单的语言来取代它。”

*   **谷歌提升其 Python 支持:**在其他 Python 新闻中，谷歌提供了围绕其对 Python 生态系统的[支持的更新，指出该语言对](https://cloud.google.com/blog/products/open-source/supporting-the-python-ecosystem)[谷歌云](https://cloud.google.com/)及其客户都“至关重要”，作为[谷歌应用引擎](https://googleappengine.blogspot.com/2008/04/introducing-google-app-engine-our-new.html)和[云功能](https://cloud.google.com/functions)的运行时，以及其他内部用途。目前，该公司表示将增加对 [Python 软件基金会](https://www.python.org/psf/)的支持，“捐赠超过 350，000 美元以支持三个特定的 PSF 项目，重点是改善 Python 生态系统的供应链安全性”，其中包括针对 [Python 包索引](https://pypi.org/)的生产化恶意软件检测，对基础 Python 工具和服务的改进，以及 2021 年的 CPython 常驻开发人员，他将全职帮助 CPython 项目优先维护并解决其积压问题。谷歌还表示，它将继续向该基金会提供谷歌云基础设施的实物捐赠，并使[谷歌云公共数据集](https://cloud.google.com/public-datasets)计划成为[PyPI 下载统计数据和 PyPI 项目元数据的新公共数据集](https://console.cloud.google.com/marketplace/product/gcp-public-data-pypi/pypi)的新家。

*   **Rust 基金会诞生:**在本周的其他一些大型编程语言新闻中， [Rust 基金会](https://foundation.rust-lang.org/)本周早些时候正式[推出](https://foundation.rust-lang.org/posts/2021-02-08-hello-world/)，与[亚马逊网络服务](https://aws.amazon.com/blogs/opensource/congratulations-rustaceans-on-the-creation-of-the-rust-foundation/)、华为、[谷歌](https://opensource.googleblog.com/2021/02/google-joins-rust-foundation.html)、[微软](https://cloudblogs.microsoft.com/opensource/2021/02/08/microsoft-joins-rust-foundation/)和 [Mozilla](https://blog.mozilla.org/blog/2021/02/08/mozilla-welcomes-the-rust-foundation/) 承诺在两年内“每年投入超过百万美元的预算来开发服务、程序和活动，以支持 Rust 项目维护者构建尽可能好的 Rust。”正如我们之前详述的那样，Rust 团队发现自己去年有点被颠覆了，因为 Mozilla，这个开源语言的创始人，裁掉了 250 名员工，其中很多是 Rust 的贡献者。现在，六个月过去了，这个基础已经成为现实，Rust 的未来似乎已经确定。正如之前在关于基金会的常见问题解答中所解释的，Rust 基金会将会把精力更多地放在处理法律问题、拓展、托管基础设施和总体支持社区上，而不是指导语言本身的未来。为此，Mozilla 已经将所有商标和基础设施资产移交给基金会，包括 crates.io 包注册，并且[一个新的董事会](https://foundation.rust-lang.org/board/)已经成立，五名董事来自五个创始成员公司，五名董事来自 Rust project leadership。
*   最后，如果你碰巧是一个开源软件项目的一部分，并且需要帮助编写文档，谷歌[已经](https://opensource.googleblog.com/2021/02/the-2021-season-of-docs-application-for-organizations-is-open.html)宣布，它现在[接受组织申请](https://docs.google.com/forms/d/e/1FAIpQLSd3oGOB6vdfUIb8tjrByYBfESlK6VYK9slwNejJABuSWMK42g/viewform)2021[Docs 季](https://developers.google.com/season-of-docs)，这是一个专门为此而创建的程序。去年，该项目有 [64 个成功的标准长度技术写作项目](https://opensource.googleblog.com/2021/01/season-of-docs-announces-results-of.html)，前年有 [44 个文档项目](https://developers.google.com/season-of-docs/docs/2019/participants)。今年的努力“将继续支持更好的开源文档，并为熟练的技术作者提供获得开源经验的机会”，面向组织的[申请](https://developers.google.com/season-of-docs/docs/organization-application-hints)现在开放，截止时间为 3 月 26 日 18:00 UTC。对于有兴趣参与的技术作家，有一个[指南](https://developers.google.com/season-of-docs/docs/tech-writer-guide)可用，任何关于该计划的问题可以发送到 season-of-docs@google.com。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>