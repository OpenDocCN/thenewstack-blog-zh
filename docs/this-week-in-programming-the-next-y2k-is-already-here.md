# 本周节目:下一个 2000 年已经来临

> 原文：<https://thenewstack.io/this-week-in-programming-the-next-y2k-is-already-here/>

我清楚地记得 1999 年除夕的那个晚上。就这些来说，很生动。但是有一件事一直困扰着我，当我们挤在一个朋友的地下室里，想知道飞机是否真的会从天上掉下来。

在午夜时分，我们拿起了固定电话(是的，我们仍然有这些电话),因为我们听说，预计会有这么多的人拿起电话，看看他们是否仍然在同一时间工作，而不是[千年虫](https://www.nationalgeographic.org/encyclopedia/Y2K-bug/)让电话系统瘫痪，不知何故，这一行动反而会。我想如果这个世界要毁灭了，我们也想参与其中。

嗯，没有飞机坠毁，电话工作正常，至少对我们来说，2000 年就这样过去了，变成了笑话和轻蔑的窃笑。当然，事实是[是开发者们长达数年的努力，耗资高达 1000 亿美元](https://time.com/5752129/y2k-bug-history/)，以确保那些飞机不会从天上掉下来，基础设施保持运转。

20 年过去了，我们已经经历了 2000 年，现在是时候看看地平线上的下一个日期时间相关的错误了——2038 年的问题[。就像千年虫一样，2038 年是有问题的，因为“所选存储单元的容量不足”，维基百科关于该主题的文章解释道。更具体地说，Unix 将时间编码为带符号的 32 位整数时间格式，表示自 1970 年 1 月 1 日 00:00:00 UTC 以来经过的秒数，超过 2038 年 1 月 19 日 03:14:07 UTC 的时间会导致整数溢出。](https://en.wikipedia.org/wiki/Year_2038_problem)

这突然成了一个热门话题，不仅仅是因为上周日代表了所有基于 Unix 的系统遇到这个问题的 20 年，而是因为这个问题已经开始了，至少根据开发者约翰·费米娜拉的说法是这样的，他的推特帖子在过去的一周里已经传播了很多次。

Feminella 讲述了一个客户的故事，他的“每夜批处理作业”在上周日(预计 2038 年前 20 年)崩溃，“就任何人的记忆或日志而言，以前从未崩溃过”。巧合的是，已经做了一些改变，所以 focus 首先去了那里，但很快这个问题就被隔离到了一个几十年内都不会发生的问题上。

“但那时，实质性的损害已经造成了，因为当天没有处理捐款。在接下来的两周内，人工赶上进度的成本约为 170 万美元。这个故事的寓意是，2038 年不会“到来”。已经到了。把你的东西修好，”Feminella 总结道。

整件事情有趣的是，你可能从这个故事中得出的一个教训是，不要简单地让代码永远运行而不看它…这基本上就是我们最初如何结束 2038 bug 的。下面的视频更详细一些…

[https://www.youtube.com/embed/MVI87HzfskQ?feature=oembed](https://www.youtube.com/embed/MVI87HzfskQ?feature=oembed)

视频

## 本周的节目中

*   **“另一个不安全的 Sh * t storm”:**如果你已经听到了传言，但错过了这个故事，DevClass 有一个 Rust 框架开发人员的故事，他在显然[有第二个想法](https://devclass.com/2020/01/20/rust-framework-dev-says-im-done-with-open-source-has-second-thoughts/)之前说“我已经完成了开源”。上周，许多例子中使用了明显的“ragequit ”,作为小型开源项目不可持续的进一步证据，但其中更多的是故事道德和人们在网上行为不端的例子。那听起来像一个电视真人秀，不是吗？这里所说的项目是 [actix](https://github.com/actix/actix) ，是微软工程师 [Nikolay Kim](https://twitter.com/fafhrd91?lang=en) 在 2017 年开源的。问题的核心是项目中使用的“不安全”代码的数量，许多人认为这对于一种基于内存安全思想的语言来说太多了。这篇文章列出了许多来回，但是场景的进一步要点是，actix 是一个小但非常受欢迎的开源项目，它跟不上使用它的社区的需求。作为对 Reddit 上一场激烈辩论的回应(这场辩论紧随之前的激烈辩论)，该项目的唯一创建者在决定“仅仅删除回购是不公平的”并将控制权移交给一名贡献者之前起身辞职。
*   锈到底是什么？说到 Rust，StackOverflow 有一篇文章给那些不熟悉这种语言的人，文章回答了[什么是 Rust，为什么它如此流行？](https://stackoverflow.blog/2020/01/20/what-is-rust-and-why-is-it-so-popular/)正如文章指出的，这种语言已经连续四年在 StackOverflow 上成为[最受欢迎的语言](https://insights.stackoverflow.com/survey/2019)，但事实仍然是大约 97%的调查受访者没有使用过 Rust。那是什么呢？“简而言之，”他们写道，“Rust 解决了许多其他语言中存在的痛点，提供了一个坚实的前进步伐，同时带来了有限的负面影响。”这篇博客文章针对不同的开发人员将它分成不同的部分，无论您习惯于垃圾收集、静态类型还是其他系统语言。因此，如果 Rust 是你刚刚听说过但没有真正关注过的东西，这是一个很好的起点，可以了解所有的上升、下降和中间情况。

*   用于分布式系统的 Haskell 式语言: InfoWorld 给我们带来了 [Unison 的故事，这是一种宣传不可变代码](https://www.infoworld.com/article/3514708/unison-functional-language-touts-immutable-code.html)的函数式语言，据说它可以“用一个程序描述整个分布式系统”InfoWorld 写道,[开源语言](https://github.com/unisonweb/unison)已经发布了公开的 alpha 版本，并且“建立在代码不可改变的核心理念之上，并通过其内容来识别”,并指出生产版本预计将在今年晚些时候发布。Unison 背后的另一个核心思想是，它是为构建分布式系统而设计的。现在，在一个公开的 alpha 版本中，计划了多个里程碑式的 alpha 版本，Unison 将于今年发布一个产品版本。如果是实验性的，阿尔法语言是你的最爱，请前往[项目网站](https://www.unisonweb.org/docs)和 [Unison GitHub repo](https://github.com/unisonweb/unison) 查看更多内容。
*   **Python 的速度和 Go、C++一样快？**当你想到 Python 时，你的第一个想法可能不是“快得惊人”，但是 iProgrammer 为我们带来了一篇关于这个主题的[学术论文](https://arxiv.org/abs/2001.02491)，将 Python 与 Go 和 C++进行了比较，使用了 [N 皇后问题](https://leetcode.com/problems/n-queens/)作为基准。虽然标题说 [Python 与 Go 和 C++](https://www.i-programmer.info/news/80-java/13405-python-as-fast-as-go-and-c-the-queens-prove-it.html) 一样快，这种说法当然应该被限定，但仍然是有保证的。症结就在这里:“用 Python、Go 和 C++实现这一点很快证明了 Python 很慢，但包括了 C++所没有的错误检查。为了看看是否可以改进，使用 Numba Python 编译器编译了相同的代码。[……]一旦使用 Numba 编译器进行编译，它在执行速度方面就可以与 C++和 Go 相媲美，同时仍然允许非常快速的原型制作。”同样值得注意的是，新贵语言 Julia 也被认为是最快的语言之一，尽管这一点被放到了附录中。

*   **2020 年的 IntelliJ IDE:**本周最后，JetBrains 的 IDE IntelliJ 提供了 2020 年的[功能路线图，这次是查看一些更高级的功能。在未来的一年中，IntelliJ IDEA 将包括亚洲市场的本地化，将 IDE 用作通用文本编辑器的能力(而不是每次都创建一个空的项目文件)，git staging 支持，以及基于机器学习的进一步文本完成。当我们谈论 JetBrains 时，所有 Kotlin 用户(或非用户——他们也想要你)都可以继续填写](https://blog.jetbrains.com/idea/2020/01/intellij-based-ide-features-roadmap-for-2020/) [2019 Kotlin 人口普查](https://blog.jetbrains.com/kotlin/2020/01/kotlin-census-2019-call-for-respondents/)，这将有助于流行的 Android Java 替代工作背后的团队在未来一年让这种语言对你更好。如果这还不够，你要知道，通过填写人口普查，你还可以参加抽奖，获得科特林音乐节门票和一件科特林 t 恤。所以，就这样了。

专题图片由埃利亚斯施。来自 Pixabay。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>