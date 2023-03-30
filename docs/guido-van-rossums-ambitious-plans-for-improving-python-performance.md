# 吉多·范·罗苏姆提高 Python 性能的雄心勃勃的计划

> 原文：<https://thenewstack.io/guido-van-rossums-ambitious-plans-for-improving-python-performance/>

Python 的创造者吉多·范·罗苏姆清楚地记得去年 11 月加入微软之前他一直在做什么。在 Dropbox 工作了七年后，“我真的完成了那里的工作……我想，‘哦，我会和我的妻子一起去旅行，我们会去骑自行车旅行，我们会和朋友聚在一起。’然后疫情发生了，生命是相当有限的！”他在与微软首席云倡导经理 Francesca Lazzeri 的问答环节中回忆道。

在这次采访中，他解释了他正在做的最新工作，让 CPython 编译器运行得更快，这是他[在为期两天的“](https://github.com/faster-cpython/ideas/blob/main/FasterCPythonDark.pdf) [Python 语言峰会](https://us.pycon.org/2021/summits/language/)第二届虚拟 PyCon US 2021 大会上宣布着手的项目

“退休后，我坐在家里感到无聊。我申请了微软并被录用了。我有选择项目的自由。我选择回到我的根，”他说。

当然，CPython 是 Python 编程语言的核心——它的默认实现，也是 Python 代码的解释器和编译器。那么，van Rossum 决定组建一个由微软资助的团队来最终尝试让它更快的背后有什么故事呢？

[https://www.youtube.com/embed/aYbNh3NS7jA?feature=oembed](https://www.youtube.com/embed/aYbNh3NS7jA?feature=oembed)

视频

## 不是机器学习

涡轮增压 CPython 并不是他加入微软的初衷。

在最初的几个月里，“我实际上只是在公司里定位自己，几乎与随机的人开会，他们正在用 Python 做有趣的事情:当然是在机器学习的背景下；天蓝色；笔记本；Excel —应有尽有！”他回过头来看，这几乎是一次系统性的搜索，寻找他将关注的项目。

他很快意识到机器学习并不适合自己。

van Rossum 认为机器学习是“一个非常大的领域”,它的发展促进了 Python 的发展。他认为机器学习领域“因为 Python 而变得更加成功……这是一种非常好的共生关系。”但是 van Rossum 随后承认，他是一生中一直忽视机器学习的人之一。“我确切地知道如何用 Python 构建一个 web 服务器或 web 客户端，或者做一些与数据库或用户界面有关的事情。我不知道如何开始编写机器学习的框架，甚至不知道如何做一个简单的机器学习应用程序。”

虽然他尝试过辅导课，并与“微软机器学习领域的各种聪明人”交谈过，但我意识到，试图为该领域做出贡献将是一个错误，“因为，在他看来，“你必须花三到四年时间攻读该领域的博士学位，然后也许你可以贡献一些有用的东西。我不知道这是不是你的经历，但这就是我的感觉！”

“所以最后，我决定回到我的根本，召集一个团队，开始致力于让 Python 更快，”他说

但这是一个非常贴近他内心的项目——有几个原因。“我很高兴我们将作为核心开发人员*和*作为微软员工或承包商，直接为 CPython 做出贡献。”ZDNet 指出[五名 Python 核心开发人员已经为微软](https://www.zdnet.com/article/python-programming-we-want-to-make-the-language-twice-as-fast-says-its-creator/)工作——除了范·罗森，还有埃里克·斯诺、布雷特·坎农、史蒂夫·道尔和巴里·华沙。Van Rossum 的团队已经为 Python 3.10 贡献了“一些小东西”——但就在他们推出更快的 Python 之前，它进入了测试阶段。“所以现在我们觉得我们有大约一年的时间来证明我们确实可以在 Python 性能上取得进展，3.11 将比 3.10 快得多。”

## 有什么计划？

van Rossum 承认其他团队已经在研究同样的问题，包括 Instagram 的 CPython 的[性能导向型](https://pyfound.blogspot.com/2021/05/the-2021-python-language-summit-cpython.html)分支 [Cinder](https://github.com/facebookincubator/cinder) ，以及类似的 [Pyston](https://github.com/pyston/pyston) 项目，还有 [Pyjoin](https://github.com/microsoft/Pyjion) ，它希望给 CPython 安装一个 C API，以便最终可以连接到即时编译器。“所以，我想说的是，让 Python 变得更快突然回到了新闻的头版，我希望我和我的团队能够为这个领域做出一些贡献。我*难道*不了解*那个*地区……”

他演讲中的一张幻灯片以“这是微软回报 Python 的方式”结尾。

在他的演讲中，van Rossum 还详细阐述了加速 Python 的一项具体工作，他称之为“[‘香农计划’](https://github.com/markshannon/faster-cpython)”开发者 Mark Shannon 去年 10 月发布到 GitHub 上)，它的目标是在接下来的四个版本中使用自适应解释器、运行时改进和针对小代码区域的即时编译器等技术将 CPython 的速度提高五倍。显然，这个计划满足了 van Rossum 的项目需求，Mark Shannon 现在成为了他更快的 Python 团队的一部分。

这个团队还包括埃里克·斯诺，他最近在一篇微软开发者博客文章中被提到。它吹捧 Snow 的实验，展示了 CPython 对同一进程中多个解释器(称为“子解释器”)的支持，作为尝试利用多线程性能的一种方式。van Rossum 后来在他的 Q & A 中扩展了这个想法，称之为“我们已经有很长一段时间了，但它有各种问题，慢慢地我们似乎正在迁移到多个子解释器的版本，子解释器之间根本没有共享数据，除了它们都生活在同一个进程中，你可以非常有效地在它们之间切换。

“在这一点上，一旦每个子解释器拥有自己的全局解释器锁，我们将有一种不同的方法来使用您需要的所有核心，因为在某种意义上，您可以剥离工作线程，除了工作子解释器。这可能是比共享一切的多线程更有效的模式，就像我们在 Java 或 C++中所做的那样。”

他们还将探索 Shannon 关于自适应字节码解释器的想法，以及其他提高速度的领域，包括帧堆栈的布局、异常处理和编译器。Python 增强提案 659 提供了一个改进性能的自适应解释器的计划细节，“推测性地专门处理它当前操作的类型或值”(在非常小的区域)。这将对性能提高多少？“很难得出有意义的数字，”提案解释道，“因为这在很大程度上取决于基准和尚未完成的工作。大量的实验表明速度提高了 50%。即使加速只有 25%，这仍然是一个值得的改进。”

InfoWorld 注意到他们把最好的留到了最后:[即时编译的想法](https://www.infoworld.com/article/3618691/pythons-creators-unveil-speedup-plans-for-python.html)。“在他的演讲中，van Rossum 建议在 Python 3.11 之后考虑这样的计划，因为首先通过更有针对性的更改获得任何性能改进是有意义的。”

他们能够将 CPython 的速度提高一倍吗？“我们还远不能确定……”一张幻灯片警告道，同时补充说团队“乐观且好奇”(后面的一张幻灯片承认，要实现 5 倍的性能，“我们必须有创造力。”)

但是除了他们正在做的事情，范罗森还强调了*他们将如何*去做。在他的演讲中，van Rossum 承诺微软资助的团队将与 Python 的核心开发人员进行完全开放的合作。在标题为“一切开源”的要点下，他明确声明所有的代码库(以及所有相关的讨论)都将对世界开放。van Rossum 补充说，“我们也会负责维护和支持”，这是为 CPython 带来平稳增量变化的持续努力的一部分。(“没有长寿的分叉/分支，没有惊喜的 6000 行拉取请求。”)

在演讲的最后，van Rossum 分享了 URL——CPython 被分入一个名为 [faster-cypython](https://github.com/faster-cpython/) 的存储库，问题在 [faster-cpython/ideas](https://github.com/faster-cpython/ideas) 被跟踪。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>