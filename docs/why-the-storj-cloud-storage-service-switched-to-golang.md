# Storj 云存储服务为何转向 Golang

> 原文：<https://thenewstack.io/why-the-storj-cloud-storage-service-switched-to-golang/>

Golang 的拥护者称， [Go 编程语言](https://golang.org/)的流行归功于几个因素:速度、健壮性和多功能性。在最新的 New Stack Makers 播客中，我们将探索分布式存储提供商 [Storj](https://storj.io/?utm_content=inline-mention) 如何使用 Go 来支持其开发和运营，以成为“存储领域的 Airbnb”

本期节目的嘉宾是 Storj 首席技术官[JT·奥利奥](https://www.linkedin.com/in/jtolds)和 Storj 软件工程师[娜塔莉·维拉萨娜](https://www.linkedin.com/in/natalievillasana)。《新书库》创始人兼发行人亚历克斯·威廉姆斯和 TNS 新闻编辑达里尔·塔夫脱主持了对话。

[为什么某存储提供商采用 Go 作为其编程语言](https://thenewstack.simplecast.com/episodes/why-one-storage-provider-adopted-go-as-its-programming-language)

Villasana 说，Storj 转向 Golang 在几个方面都有意义，特别是在调试方面。

Villasana 描述了她切换到 Go 的恐惧，但很快意识到该语言对于手边的编程需求的优势。维拉萨纳说，内存管理和指针等方面“让它看起来要复杂得多”。"但实际上，从长远来看，围棋让事情变得简单多了."

在 Olio 之前工作的一家公司，Go 是一种比 Python 更快的编程语言，Python 是该公司之前选择的编程语言。Olio 描述了团队成员如何“手动”音译他们 90，000 行 Python 代码库中的每一行

“我们把所有的工程师分成小组，并把文件分配给每个工程师团队，”奥利奥说。“他们成对编程，音译，所以在这个过程结束时，我们有两个相同的代码库，包括单元测试，包括序列化格式——这是完全相同的逐行 Python 和 Go。”

Olio 在博士研究期间了解了 Golang 的稳健和优雅。“感觉就像以前我们试图只用肌肉来建造一个人，一旦我们有了类型系统，就像有骨头来悬挂肌肉一样。这就像是编译器强制执行的结构，”奥利奥说。“在重构方面，我们原本预计需要几个月时间的一系列事情，现在几天就完成了。真是难以置信。”

当 Olio 加入 Storj 担任工程总监时，该公司也有 160，000 行 JavaScript。Olio 认为 JavaScript 在支持 Storj 的环境和扩展目标所需的架构变更方面带来了更多困难(当时，该公司已经在管理 150PB 的广告存储)。

“我进来后，很有兴趣地说，‘嘿，让我们试试围棋吧’……团队就像鱼对水一样，每个人都做得很好，”他说。“我们可以谈论更多关于 Storj 的具体决定，但我个人的 Go 历史是，我是一个持怀疑态度的采纳者，后来成为了一个大粉丝。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>