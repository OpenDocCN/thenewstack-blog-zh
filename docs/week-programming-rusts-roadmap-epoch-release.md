# 本周编程:Rust 的划时代发行路线图

> 原文：<https://thenewstack.io/week-programming-rusts-roadmap-epoch-release/>

我仍然记得我写的第一个关于网络的故事——这是一个关于哪些浏览器正在崛起，哪些正在衰落的快速新闻故事，除了这一切的赛马性质，我真的没有看到全部的含义。我没有意识到，虽然不同技术的受欢迎程度的上升和下降会成为轻松而精彩的头条新闻，但也会为该领域的人们带来实际而有用的见解。最后，仅仅是市场营销和头条新闻就能推动开发人员使用语言似乎令人怀疑(尽管有些人认为仅仅是在谈到[我们现在看到的 Perl6 面临的问题](https://thenewstack.io/week-programming-renaming-perl-save-terminal-unpopularity/))，而是流行是由良好的语言设计、特性、强大的社区和不断发展的技术推动的。

这些天来，正是这些故事告诉我在我的特定世界观之外正在发生什么，你们所有人在这个领域真正在做什么，尤其是那些站在前沿的人。一个[这样的故事](http://www.benfrederickson.com/ranking-programming-languages-by-github-users/)，我们将在稍后进一步研究，告诉我“用户群增长最快的语言是 Go、TypeScript、Kotlin 和 Rust”，这让我在看到我们本周将关注的第一条编程新闻时，耳朵稍微竖起来了一点，这是由负责 Rust 编程语言的 Mozilla 开发人员 [Aaron Turon](http://aturon.github.io/about/) 撰写的 Rust 2018 路线图。

图隆表示，该路线图是根据 2017 年的调查汇编而成的，还有近 100 篇响应#Rust2018 博客帖子的[号召而写的博客帖子，以及“核心团队对时代精神和项目管理的总体感觉”，概述了该语言在未来一年的一些高水平目标，包括定于今年 9 月 13 日发布的“时代发布”。这一划时代的版本将包括“许多已经实现的语言功能”的抛光和稳定，推动几个关键工具、库和文档的 1.0 状态，以及“为中级 Rustaceans 构建资源”的努力，这将“帮助程序员从 Rust 机制的基础知识到知道如何有效地使用它。”此外，《华盛顿邮报》称，Rust 团队将在未来一年壮大，并致力于让 Rust 在全球范围内普及。](https://blog.rust-lang.org/2018/01/03/new-years-rust-a-call-for-community-blogposts.html)

如果你是一个 Rust 开发者，一定要查看完整的路线图，因为它有很多我们没有包括在这里的令人兴奋的细节。除了 Rust，本周我们还有 TensorFlow 的新版本，前面提到的编程语言流行度分析，以及一些更有趣的内容。

## 本周的节目中

*   **谷歌的 TensorFlow 1.5 到来:**谷歌[本周宣布公开发布 TensorFlow 1.5](http://developers.googleblog.com/2018/01/announcing-tensorflow-15.html) ，这是其开源机器学习框架的最新版本。新版本包括对 GPU 加速的更新和对文档的彻底检查(特别是入门部分)，以及对 TensorFlow 的[渴望执行的预览，“一个命令式的、由运行定义的接口，当从 Python 调用操作时，操作会立即执行，”谷歌表示，这使得 TensorFlow 更容易入门，并可以使研发更加直观。此外，面向移动和嵌入式设备的轻量级解决方案](https://developers.googleblog.com/2017/10/eager-execution-imperative-define-by.html) [TensorFlow Lite](https://github.com/tensorflow/tensorflow/tree/r1.5/tensorflow/contrib/lite) 的开发者预览版内置于 1.5 版本中，适用于 Android 和 iOS。TensorFlow Lite“允许您将经过训练的 TensorFlow 模型转换为. tflite 文件，然后可以在低延迟的移动设备上执行。”这样做的好处是，培训不必在设备上进行，设备也不需要将数据上传到云端进行处理。
*   GitHub 用户对语言的分析:这就是之前提到的语言流行度分析，我非常喜欢它的一点是它是数据驱动的，而不是基于调查的。当然，任何方法都有缺陷、警告或缺点，但我认为我更喜欢对给定的数据集进行分析，而不是询问人们的意见。总之，这篇博客文章[根据 GitHub 用户对编程语言进行排名](http://www.benfrederickson.com/ranking-programming-languages-by-github-users/)，所以如果你记住谁是 GitHub 用户，它提供了一些非常有趣的见解。首先，帖子中有一些有趣的统计数据，这些数据是从 GitHub 存档中创建的，其中包含“自 2011 年初以来 GitHub 上的每个公共事件的记录”和“在超过 7500 万个不同的存储库中有超过 12.5 亿个事件。”除此之外，我们从这个数据集得到了一个有趣的分析。

![](img/83356e3b64ba9b0540e4f89ec2341d37.png)

正如作者所指出的，也正如我在本周的介绍中提到的，这些数据的有趣之处不仅仅在于头条新闻和受欢迎程度。“看着这些趋势线，我们可以找出哪些编程语言值得学习，哪些编程语言可能应该避免，”他写道。虽然 JavaScript、Python、Java、C++和 C 处于领先地位，可能不会有什么发展，但用户群增长最快的语言是 Go、TypeScript、Kotlin 和 Rust。因此，作者写道，“在使用 TypeScript 仅仅几周后，我可能再也不想使用 JavaScript 了。”当然，整个分析中可能缺少一种语言，我们将在另一篇文章中研究这种语言——Python。正如该分析所指出的，“Juptyer 笔记本电脑在过去几年中取得了显著而稳定的增长……这主要是因为用于数据科学的 Python 的发展。”

*   **与此同时，还有 Python:** 正如我们过去所见， [Python 在开发者中非常受欢迎](https://thenewstack.io/week-programming-horse-race-heats-python/)。虽然之前的分析可能没有显示出这么多，但本周《应用开发趋势》杂志上的一篇文章着眼于调查结果，显示出[JavaScript 是受欢迎的，但程序员更喜欢 Python](https://adtmag.com/articles/2018/01/25/hackerrank-survey.aspx) 。根据技术招聘公司 HackerRank 的调查，JavaScript 是组织寻求的顶级编程语言，但开发人员更喜欢 Python。很明显，“雇主对获得 JavaScript 和 Java jockeys 更感兴趣”，这两种语言几乎并列最受欢迎，而 Python 位居第三。有趣的最后一点——“然而，当被问及他们更喜欢什么语言时，Python 在所有年龄组中都占了优势，除了 55 岁或以上的人，他们勉强喜欢 c 语言”——这很有趣，因为… [根据 TechRepublic 对同一调查的分析，显然年轻的开发人员讨厌新语言](https://www.techrepublic.com/article/heres-why-younger-developers-cant-stand-new-programming-languages/)。“年轻的开发人员爱上了老的编程语言，”他们写道，“而老的开发人员痴迷于像谷歌的 go 这样的选项。”
*   **关于“解开你的 Git Fuckup”:**这个比其他任何东西都更实用——选择你的关于解开你的 Git Fuckup 的冒险指南。一个简单的 HTML 文档提供了“一个相当全面的指南，帮助你从使用 git 时不希望做的事情中恢复过来。”

https://twitter.com/practicingdev/status/957303154856681472

*   你在你的 DeLorean 上运行 Perl？PERL？！没错，有一个 [DeLorean 在“一个完整的 Linux PC 和桌面监视器上运行 Perl](https://opensource.com/article/18/1/my-delorean-runs-perl) ，该监视器带有一个低端微控制器，以读取来自汽车的模拟测量值。”虽然作者没有提到通量电容器，但他讨论了常见的反应——“为什么是 Perl？？?"—在讨论 Perl 相对于其他更可能的工具的优点之前。点击这个故事，了解 Perl 驱动的 DeLorean 的阴谋，并留下来进行分析。

[https://www.youtube.com/embed/2XmBiYQW8ao?feature=oembed](https://www.youtube.com/embed/2XmBiYQW8ao?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>