# 本周编程:思考 Perl 7 的发展

> 原文：<https://thenewstack.io/this-week-in-programming-pondering-the-evolution-of-perl-7/>

今年早些时候，我们看到了 Perl 7 的[介绍，新版本被宣传为仅仅是 Perl 5.32，“但是具有不同的、更合理的、更现代的缺省值。”当然，虽然这是真的，但在 Perl 社区中还是存在一些普遍的分歧，据 Perl 基金会董事会成员](https://thenewstack.io/this-week-in-programming-perl-7-brings-different-saner-more-modern-defaults/) [Ricardo Signes](https://twitter.com/rjbs?lang=en) 说，他问“到底发生了什么？”

[LWN.net](https://lwn.net/)最近吸引了一些注意力到“提议的 Perl 7 分支”的话题上(评论中的一些人对这个描述有异议，更倾向于将[樱庭落称为这样的](https://thenewstack.io/this-week-in-programming-less-than-random/)),发布了 Signes 对回答这个问题的 Perl 电子邮件列表的完整回复。

正如我们所注意到的，Perl 7 推出时的语气似乎表明变化不大，但迁移到版本 7 的核心思想是，该语言可以超越过去的一些限制。你可能会想到，这样的改变会遇到阻力和困惑，这种情况也不例外。“Perl 7 的核心问题不是版本编号，而是向后兼容性保证，”Signes 在他的回复中写道。“也许有一些向后兼容性可以忽略，而不会干扰绝大多数 Perl 用户，同时使语言更易于使用，并且(非常重要的是)易于*继续*改进。这显然是 Perl 7 计划的核心希望。”

然而，破坏兼容性的问题只是争论的第一点，他在继续讨论第二点之前指出——如果它应该被破坏，那么怎么破坏？在这一点上，Signes 的信息中有一段非常突出:

“目前还没有达成共识，似乎任何两个人之间都没有。没有一个小集团的人会说‘让我们都打破我们一致同意的这五件事，快，在任何人能够阻止我们之前。’我认为有时闻起来是这样，但我一直在讨论我们能够和应该改变什么，为什么，而且没有统一战线，他写道。如果说有什么不同的话，最大的共识是，“改变版本编号，以明确何时会出现重大变化是合理的。”"

他写道，这个计划“是提出一个计划”，为此已经成立了 [Perl 指导委员会](https://github.com/Perl/perl5/wiki/Perl-Steering-Committee)(或者至少正在这样做)，Signes 向那些可能质疑语言向 Perl 7 发展的人提供了一些保证，Perl 7 是下一个版本，并不像表面上看起来那么简单。

“你不应该期望看到一系列不公正的命令从一些秘密机构发布。Signes 写道:“您应该会看到 perl5 移植程序像往常一样运行:提案进入列表，得到讨论，然后被项目经理上下翻动。”。“这已经发生了很多年了。一些提议已经被项目经理讨论过，一些没有。如果您为此删除了任何命名邮件列表，这种情况仍然会发生。PSC 是一种手段，可以表明这种讨论有一个默认的小组。”

如果您正在寻找进一步的保证，Perl 基金会董事会成员 Curtis“Ovid”Poe 也在[一次采访](https://www.perl.com/article/the-perl-ambassador-curtis-poe/)中提供了他对迁移到 Perl 7 的看法，他说他“100%支持这个项目”，并指出“有目标和有计划是有区别的。对目标有广泛的共识，但对计划的共识较少。只要人们能利用这一点找到最佳路径，那就太好了。”

## 本周的节目中

*   **谷歌推出了一个 Chrome 开发门户网站:**鉴于 Chromebook 销售最近的繁荣(同比增长 127%，相比之下其他笔记本电脑的增长率为 40%)，谷歌对进军 Chrome book 变得更加认真，[推出了“技术开发人员、设计师、产品经理和商业领袖专用资源”](https://feedproxy.google.com/~r/blogspot/hsDu/~3/jFYZfTyv-aU/introducing-chrome-os-dev.html)[chromeos . Dev](https://chromeos.dev/en/)。该网站将提供新闻、产品发布、技术文档、代码示例以及专家的实用技巧。谷歌指出，该网站将是完全开源的，并且“考虑到了创建高性能和可靠的渐进式网络应用(pwa)的所有原则和方法。”
*   **Go 1.15 到来时“语言没有变化”:**本周[发布了 Go 1.15](https://blog.golang.org/go1.15) ，根据[的发布说明](https://golang.org/doc/go1.15)，它包括对工具链、运行时和库的实现的许多变化，但语言本身没有变化。突出的变化包括对 Go 链接器的[【实质性】改进](https://golang.org/doc/go1.15#linker)和[大量核心库改进](https://golang.org/doc/go1.15#library)等，该团队表示他们“预计几乎所有 Go 程序都将像以前一样继续编译和运行。”dev class[进一步写了新闻](https://devclass.com/2020/08/12/go-1_15/)，指出对于运行在 AMD64 架构上的某些操作系统,“链接器的速度提高了 20 %,平均需要的内存减少了 30%”。链接器的改进有望在未来的版本中继续，目前，Go 社区可以享受一个几乎没有争议的版本。

*   **Jupyter Book 将“从头开始”重新编写:**如果您希望使用 Python 以互动的方式呈现数据发现，包括实时代码、等式、可视化和叙述性文本，那么 Jupyter 笔记本就是您的不二之选。现在，如果你想把许多这样的笔记本汇编成“出版物质量的书籍、网站和来自包含计算内容的原始资料的文档”，Jupyter 书籍是你可以做到这一点的一种方式。本周，Jupyter 发布了一本全新的 Jupyter 图书，“从头开始重新编写，安装更容易，使用更快，能够在你的书中创建更复杂的出版内容。”目前处于测试阶段，更新后的图书现在由可执行图书项目支持，同时保留了类似的感觉，并“由于下面的新 Jupyter Book 堆栈而具有许多新功能。”他们写道，最大的变化之一是，Jupyter Books 现在支持[显著结构化测试(MyST) Markdown 语言](https://myst-parser.readthedocs.io/en/latest/)，这是 Jupyter Markdown 的超集，意味着 Jupyter 笔记本中的任何默认 Markdown 在 Jupyter Book 中都是有效的。要了解更新的全部细节，请查看帖子或进入[新 Jupyter Book 文档](https://jupyterbook.org/)或[Jupyter Book GitHub 知识库](https://github.com/executablebooks/jupyter-book)。
*   **脸书开放 Python 静态分析器 Pysa:**说到 Python，脸书已经[决定开放](https://engineering.fb.com/security/pysa/)关于 [Pysa](https://pyre-check.org/docs/pysa-basics.html) ，这是一个开源的静态分析工具，用来检测和防止 Python 代码中的安全问题，它的名字是“Python Static Analyzer”的简称该工具建立在他们的 Python 类型检查器 [Pyre](https://pyre-check.org/docs/overview.html) 之上，有助于检测广泛的问题，从框架的正确使用到检测常见的 web 应用安全问题，如 XSS 和 SQL 注入。到目前为止，他们表示，该工具仅在 2020 年上半年就检测到了“我们的工程师在 Instagram 服务器代码库中发现的 44%的问题”，以及“我们根据严重性分类的拟议代码更改中的 330 个独特问题。”如果您想让 Pysa 尝试一下自己的代码，请查看文档[和教程](https://pyre-check.org/docs/pysa-basics.html)。

*   **Visual Studio 和重复编辑:**微软在 Visual Studio 中推出了一项新功能，其中[对于那些用 C#编写代码的人来说，使用 IntelliCode 建议](https://devblogs.microsoft.com/visualstudio/making-repeated-edits-easier-with-intellicode-suggestions/)进行重复编辑将变得更加容易。本质上，IntelliCode 会在您键入时检查您的编辑，在后台创建“通用编辑脚本”，当它发现这些脚本中的一个可以应用于您的代码时，它会在空白处用一个小灯泡告诉您。它使用[散文](https://www.microsoft.com/research/group/prose/)(通过例子进行程序合成)来实现这一点，根据帖子，这不是简单地查看文本变化，而是查看代码的语法结构。有关新功能如何工作的更多细节，请查看描述底层技术的[发行说明](https://docs.microsoft.com/en-us/visualstudio/releases/2019/release-notes)或[研究论文](https://aka.ms/repetitive-edits)。
*   **JetBrains 的洪水:** ADTMag 有一个 [JetBrains 的“产品发布狂欢”](https://adtmag.com/blogs/watersworks/2020/08/jetbrains-product-release-binge.aspx)的综述，它从上个月末开始，包括发布 [IntelliJ IDEA 2020.2](https://blog.jetbrains.com/idea/2020/07/intellij-idea-2020-2-is-released/) 、 [IntelliJ Scala 插件 2020.2](https://blog.jetbrains.com/scala/2020/07/28/intellij-scala-plugin-2020-2-is-released/) 、 [PyCharm 2020.2](https://blog.jetbrains.com/pycharm/2020/07/pycharm-2020-2-out-now/) 、 [CLion 2020.2](https://blog.jetbrains.com/clion/2020/07/clion-2020-2-makefile-cpp20-doctest/) 、 [PhpStorm 2020。唷！这里值得注意的是，IntelliJ IDEA 2020.2 包括对 Java 15 的支持，将于 9 月份发布，以及 JetBrains Space 的测试版](https://blog.jetbrains.com/phpstorm/2020/07/phpstorm-2020-2-release/)。Space 是一个“集成的团队环境”,在过去的八个月中一直处于早期访问状态，现在计划在今年秋天公开发布。该公司目前正在接受测试版访问请求。

苏珊·d·威廉姆斯在 [Unsplash](https://unsplash.com/s/photos/evolution?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>