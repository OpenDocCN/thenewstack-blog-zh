# 模糊化:一种古老的测试技术成熟了

> 原文：<https://thenewstack.io/fuzzing-old-testing-technique-comes-age/>

专有开发和开源开发都倾向于开发人员多于测试人员。结果，自动化测试变得越来越普遍。在过去的一年里，fuzzing——用虚拟或随机数据进行测试——变得特别普遍，而且它的流行似乎可能会继续下去。

Fuzzing 的名字比概念本身还新。计算机科学家 Gerald Weinberg 回忆说，20 世纪 50 年代末，当他在 IBM 和 Mercury Project 工作时,“我们的标准做法是通过输入从垃圾中取出的穿孔卡片来测试程序。我们还使用了随机数字穿孔卡。在那些日子里，我们没有联网，所以我们不太担心安全，但我们的随机/垃圾甲板经常出现不良行为。

温伯格[补充道](http://secretsofconsulting.blogspot.ca/2017/02/fuzz-testing-and-fuzz-history.html)“我认识的每一个程序员都使用垃圾甲板技术。”在接下来的几十年里，fuzzing 继续被广泛使用，尽管现在的名字是在 1988 年由威斯康辛大学的[巴顿·米勒](http://pages.cs.wisc.edu/~bart/)教授的一次课堂项目后开始使用的。在那之前，它被称为随机测试或猴子测试。

Fuzzing 目前的受欢迎程度可以说是始于谷歌自 2012 年以来引入了一项名为 ClusterFuzz 的云服务，该云服务通过一系列 fuzzing 测试来提高 [Chromium 网络浏览器的安全性。这种做法有几个副产品。例如，](https://blog.chromium.org/2012/04/fuzzing-for-security.html) [Behdad Esfahbod](http://behdad.org/) 在将字体渲染器 HarfBuzz [移植到 Chromium](https://github.com/harfbuzz/harfbuzz/issues/139) 时使用了 ClusterFuzz。在开发者中，fuzzing 在 2014 年被用于了解 Shellshock 病毒的能力时获得了更多的认可。

然而，fuzzing 在 2016-17 年已经广为人知。2016 年 9 月，微软开始 [Project Springfield](https://www.microsoft.com/en-us/research/project/project-springfield/) ，这是一个基于云的 fuzzing 服务，用于检测安全漏洞。同样，在 2017 年初，谷歌的 ClusterFuzz 扩展为 [OSS-Fuzz](https://github.com/google/oss-fuzz/) ，这是一个由 [Linux 基金会](https://www.linuxfoundation.org/)的[核心基础设施倡议](https://www.coreinfrastructure.org/)联合发起的项目，旨在提高关键开源应用的安全性。1917 年 5 月，OSS-模糊宣布它正在与 47 个开源项目合作，并且已经发现了超过 1000 个漏洞，[包括 264 个潜在的安全漏洞](https://opensource.googleblog.com/2017/05/oss-fuzz-five-months-later-and.html)。OSS-模糊的测试包括检查内存泄漏；堆、全局和堆栈缓冲区溢出、堆栈溢出、超时和其他常见错误。

最近，fuzzing 的声誉受益于 Linux 创造者 Linus Torvalds 在讨论 4.14 Linux 内核开发时的支持。托瓦尔兹在一封电子邮件中写道，“值得一提的是，人们做了多少随机模糊处理，以及(如何)找到东西。我们总是做 fuzzing(谁还记得老的“ [crashme](https://packages.debian.org/sid/crashme) ”程序，它只是生成 randomcode [sic]并跳转到它？我们曾经很早就积极地这样做了)，但是人们已经做了一些很好的目标[原文如此]驱动子系统的模糊化，等等。这些努力带来了各种各样的解决方案。”

这种对 fuzzing 的兴趣爆发的原因还没有被分析，但总的趋势似乎足够简单。在过去，测试经常被忽视，自动化是一种明显的方法，可以在不增加成本或招募新开发人员的情况下提高测试水平。同样值得注意的是，公众对安全性的关注促使公司和开源项目迅速改进他们的测试。特别是在开源领域，应用程序的成熟通常意味着手动测试比以往任何时候都更加耗时和低效。在这种情况下，今天起毛变得越来越有意义。

## 图书馆如何使用模糊化

为了理解模糊化是如何以及为什么成为一种常见的测试实践，有一个例子是有用的。免费许可的办公套件 [LibreOffice](https://www.libreoffice.org/) 就是这样一个例子。 [Red Hat](https://www.openshift.com/) 开发者和长期 LibreOffice 贡献者 [Caolán McNamara](https://caolanm.blogspot.com/) 解释说，过去该项目在自己的硬件上使用[美国 Fuzzy Lop](http://lcamtuf.coredump.cx/afl/) (afl)。麦克纳马拉本人已经尝试使用 afl [来测试用户界面崩溃](http://caolanm.blogspot.ca/2015/10/finding-ui-crashes-by-fuzzing-input.html)，尽管这一系列测试尚未完全实现。

然而，LibreOffice 在 OSS-fuzz 宣布后不久就开始使用它，“在过去的一年里，我们稳步增加了 Fuzz 目标，并启用了更多的 Fuzz 引擎，”他说。LibreOffice 测试的重点是图形格式的导入过滤器，如。巴新和。jpeg 和诸如 Microsoft Word 的文本文件格式。docx 和 LibreOffice 自己的。开放文档文本格式。一些文本文件过滤器也被 LibreOffice 的姐妹项目[文档解放项目](https://wiki.documentfoundation.org/DLP)单独模糊化，该项目为过时和过时的专有格式开发过滤器。

目前，LibreOffice 有 43 个使用 OS-fuzz 的 Fuzz 目标，并计划再增加 3 个。这些目标使用了 OSS-模糊的三种资源:默认的 libFuzzer、afl 和[未定义行为杀毒软件](https://clang.llvm.org/docs/UndefinedBehaviorSanitizer.html) (ubsan)。到目前为止，这个工具组合[已经识别出 349 个 bug](https://bugs.chromium.org/p/oss-fuzz/issues/list?can=1&q=libreoffice)，除了[一些超时 bug 无法重现](https://github.com/google/oss-fuzz/issues/977#issuecomment-343765661)之外，全部修复。

除了模糊化，麦克纳马拉说，“我们通过加载从各种公开的 Bugzilla 附件下载的大量文档(不到 100，000 个)来持续对我们的导入过滤器进行崩溃测试。”该项目使用 [afl-cmin](http://www.tin.org/bin/man.cgi?section=1&topic=afl-cmin) 来寻找使用最多代码路径的每种格式的最小子集，并且[公开存储它们](http://dev-www.libreoffice.org/corpus/)，以便它们可以被其他也使用导入过滤器的项目使用。

“Fuzzing 对我们真的很有用，”麦克纳马拉总结道。“这是无情的搜出痛苦的案件。我们已经发现并修复了数百个遗留错误，随着 OSS-模糊技术被整合到我们的持续测试中，我最满意的是，我们在新错误出现在我们的代码后的第二天就检测到了它们，远远早于它们出现在发布版本中。”

## 模糊化的极限

冒着指出显而易见的风险，尽管 fuzzing 可以简化测试，但简单地实现它不足以减少 bug 或加强安全性。正如前 openSUSE 主席[理查德·布朗](https://twitter.com/sysrich)所指出的，“模糊表明*可能*存在 bug，而不是*实际*存在 bug。”换句话说，模糊化的结果通常仍然需要人类的判断。Hanno bck 写了一篇关于 fuzzing 的开发者博客，他在对比了对他的。黛比和。如果基础设施不存在来支持或纠正它们，rpm 包管理器就是模糊了许多用途的结果。

尽管如此，当伴随着标准的测试程序时，模糊化已经多次证明了它是用同样的资源做更多事情的一种方式。在过去的一年里，fuzzing 已经形成了自己的风格，在未来，它的适应性只会增加。

谷歌、Linux 基金会、微软和红帽都是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>