# Unix 先驱 Brian Kernighan 在这么多年后仍然热爱 AWK

> 原文：<https://thenewstack.io/unix-pioneer-brian-kernighan-still-loves-awk-after-all-these-years/>

Brian Kernighan 可能是我们所拥有的最接近 T2 传奇人物的东西。早在 1970 年，他就创造了“Unix”这个术语，并因在贝尔实验室(操作系统诞生的地方)的开创性工作而被认可。作为 Unix 的 [AWK](https://www.gnu.org/software/gawk/manual/gawk.html) 工具的合著者，即使是 Kernighan 的名字也存在于我们的开发环境中，因为 Kernighan 的最后一个首字母提供了 AWK 名字中的“K”——以及当人们引用 1978 年关于 C 编程的标志性书籍[K&R](https://www.amazon.com/Programming-Language-2nd-Brian-Kernighan/dp/0131103628/ref=asc_df_0131103628)时的“K”。

本月早些时候，Kernighan 接受了 YouTube 频道 Computerphile (拥有 218 万订户)的采访。在与诺丁汉大学计算机科学教授 David F. Brailsford 的聊天中，Kernighan 谈到了从 10 岁孩子的最佳编程到他对 AWK“1977 年非常短的开发周期”的记忆

在简洁明了地描述 AWK 的效用时，Kernighan 几乎成了一个偶然的福音传播者，称 AWK 为“一个什么样的工具适合这项工作的例子”

那是什么样的工作？“如果你有合适的语言，你可以用一行字写下你心中的想法。AWK 是一种让你用一行文字写出来的语言。因为它解决了你在其他语言中可能需要的许多问题。”![](img/76377456df70a4ed47156258a04c529d.png)

Kernighan 承认 Python 是一种语言，如果你在余生中只打算选择一种的话。但是对于 Python，“你需要知道如何获得输入？如何将它分割成各种组件？怎么写出来？所有这些在 AWK 都是免费的，这也是为什么与其他语言的节目相比，AWK 的节目往往非常非常短的原因之一。

"它们的运行速度和 Python 中的速度差不多."

## 输入 Unicode

但是六分钟后，Brailsford 问了一个启发性的问题:Kernighan 是否对 AWK 进行了积极的维护？Kernighan 说，它已经在 GitHub T1 上发布了“相当长一段时间”,还没有正式的发布时间表，并称赞长期的 Unix 程序员 T2 Arnold Robbins T3 完成了“大部分的工作”罗宾斯也是 GNU 项目的 AWK 版本的当前维护者，Kernighan 描述罗宾斯“非常擅长这种事情”和“一个非常好的朋友……我认为*他*实际上在很大程度上是关注它的人。”Robbins 甚至为 AWK 扩充了 Kernighan 自己的测试套件。

但是 Kernighan 并没有完全放弃 AWK 的发展。

“令人尴尬的是，AWK 只处理 ASCII 或 8 位输入，但它根本不处理 Unicode。所以几个月前，”Kernighan 说。

Unicode 是更老、更有限的 ASCII 字符集的继承者，融合了世界上的语言和表情符号

带着期待的笑声，Kernighan 说，“我花了一些时间研究一个令人难以置信的旧程序，现在我有了它，它实际上可以处理 UTF-8[Unicode 子集]输入和输出，这样你就可以有正则表达式，你知道，选择日语字符或类似的东西。这似乎是正确的。”

Kernighan 指出，Robbins 还研究了 egrep，这是一个具有模式识别机制的工具，其解析与 AWK 的“本质上相同”。“代码很漂亮——正确的技术术语是什么？——*高深莫测*。”柯尼根笑了。“但幸运的是，我能够找出足够多的信息，并在其中加入 UTF 处理和 Unicode 处理。”

Kernighan 在 GitHub 上将他的更新描述为“类似于升级版”。但是对于 45 年后他是否还在 AWK 工作的问题，答案是肯定的:“那是真正的工作，试图理解旧代码并插入一些东西进去。我想我已经做对了，但是……它需要更多的测试。”

“我做的另一件事只是一个快速和肮脏的事情，使之有可能处理 CSV 输入-逗号分隔的变量。因为这从来没有真正完成，所以现在如果你有一个简单的 CSV 输入…它会正确地处理输入。这基本上是我所做的所有开发。”

然后他离开去讨论如何测试程序，称这个问题“令人担忧”

## 互联网欢呼雀跃

观察人们的反应很有趣。[在 *Ars Technica* 布赖恩·克尼根打了个招呼，询问他们的美国之行进展如何，并留下了数百行可以为 AWK 增加 Unicode 支持的代码，这是他于 1977 年在贝尔实验室帮助为 Unix 创建的文本解析工具](https://arstechnica.com/gadgets/2022/08/unix-legend-who-owes-us-nothing-keeps-fixing-foundational-awk-code/)

他们的帖子吸引了 360 条评论——不止一条评论表示松了一口气，他们不是唯一一个在 Git 上有问题的人。“没人理解 git cli，”一位评论者写道。"有些人只是比其他人记住了更多的命令。"(那条评论吸引了 249 张赞成票。

所以极客不断出现。在采访的后期，Kernighan 甚至说他已经和《AWK》的另外两位原作者——现在都已经 80 多岁了——以及出版商 Addison Wesley 谈过，关于他们是否需要更新他们 1988 年的书。

Kernighan 诙谐地说，新版本“将处理诸如‘好吧，我们现在至少可以合理地表示 Unicode 字符’之类的事情。”"

“但我认为更普遍的是，今天的计算环境与 35 年或 40 年前相比有了难以置信的不同。你知道，机器要快一百倍到一千倍。记忆要大一百万倍。这改变了你看待事物的方式。

“过去，你无法*负担*在大数据上运行 AWK 程序，现在情况不同了。它以毫秒为单位处理兆字节。这就改变了你可能做出的权衡。”

Kernighan 也不禁注意到，自 1988 年该书第一版以来，我们的工具发生了多大的变化——该书是在 Unix 文档格式化工具 troff 的巅峰时期编写的。

有一次，Kernighan 说他仍然保留着 1988 年 AWK 书的原始文件——以 PostScript 文件格式保存——甚至比. PDF 还要早

## 发布和提交

Kernighan 最近还在忙什么？

事实证明——相当多。

布莱恩·柯尼根今年一月已经 80 岁了——根据柯尼根在普林斯顿大学的网页，他一直定期发表文章。

*   去年，Kernighan 出版了一本新书，探索“新技术带来的社会、政治和法律问题”书名:*了解数字世界:你需要知道的关于计算机、互联网、隐私和安全的知识*。
*   2019 年，Kernighan 还自助出版了一本名为 [*Unix:历史和回忆录*](https://www.amazon.com/UNIX-History-Memoir-Brian-Kernighan/dp/1695978552/) 的 Kindle 电子书，不仅探索了 Unix 的起源，还探索了“它是如何产生的，以及它为什么重要。”
*   2018 年，Kernighan 还出版了*百万，十亿，亿万:在一个太多数字的世界里保护你自己。他的网站将其描述为“一个淹没在大数据(通常是坏数据)中的世界的基本生存指南。”*
*   2015 年，Kernighan 甚至[为 Addison-Wesley 合著了一本关于 Go 编程语言](https://www.gopl.io/)的书。

当然，在 1978 年，Kernighan 撰写了被称为[的世界上第一个“你好，世界”程序](https://www.artsy.net/artwork/brian-kernighan-hello-world)——在 1988 年，Kernighan 与人合著了一本关于[Awk 编程语言](https://en.wikipedia.org/wiki/The_AWK_Programming_Language)的书。

Kernighan 的兴趣是惊人的折衷。2020 年，Kernighan 还与人合著了一篇论文[,讲述了将光学字符识别应用于 1674 年至 1913 年间 18 万页法庭记录的现实挑战。他们的论文指出，英格兰和威尔士中央刑事法院的官方记录“the Proceedings of the Old Bailey”为测试光学字符识别在历史文件上的表现提供了“理想的基准”。](https://www.cs.princeton.edu/~bwk/obo.pdf)

由于 180，000 页的人工抄本已经存在，他们能够使用它们来测试三个顶级的基于云的 OCR 服务的准确性:[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)’[text ract](https://aws.amazon.com/textract/)；微软 Azure 的[认知服务](https://azure.microsoft.com/en-us/services/cognitive-services/)，以及谷歌云平台的[愿景](https://cloud.google.com/vision/docs)。

“我们的结果发现，AWS 的中值错误率最低，Azure 的中值往返时间最低，谷歌云平台的低错误率和低持续时间的最佳组合。”

自 2000 年以来，Kernighan 一直是普林斯顿大学计算机科学系的一员(今年春天，该系教授了一门关于“数字人文”的课程，探索数字表现(和其他技术)如何被用于从文学、语言、历史到音乐、艺术和宗教的方方面面。(“数字人文数据本质上是混乱的，”这门课程的描述解释道，“甚至在学习开始之前，总是有相当大的努力致力于清理它。”)

Kernighan 的班级承诺举办一次研讨会,“旨在建立工具和开发技术，帮助人文学者更有效地处理他们的数据。这可能包括机器学习、自然语言处理、数据可视化、数据清理和用户界面设计，以便让刚刚开始学习技术的学者能够使用这些过程。”

因此，Kernighan 可能不可避免地会开始考虑 Unicode 字符…

[https://www.youtube.com/embed/GNyQxXw_oMQ?feature=oembed](https://www.youtube.com/embed/GNyQxXw_oMQ?feature=oembed)

视频

* * *

# WebReduce

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>