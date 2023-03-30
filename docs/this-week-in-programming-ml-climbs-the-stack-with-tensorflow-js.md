# 本周编程:ML 用 TensorFlow.js 爬栈

> 原文：<https://thenewstack.io/this-week-in-programming-ml-climbs-the-stack-with-tensorflow-js/>

随着时间的推移，我们似乎不得不越来越少地在本地“安装”——正如我本周听的一个播客中有人粗略地描述的那样，一切都在不断地向上移动。现代的开发者就像一个乘着巨浪的冲浪者，或者一个设法漂浮在雪崩顶上的滑雪者。也就是说，它们可以是——或者它们可以在海浪中翻滚或被埋在雪中，在这种紧张的隐喻中，水或雪是处理安装软件包和管理依赖关系以及处理越来越多地由其他服务处理的所有本质细节的耗时且紧张的行为。

本周，亲爱的读者，我们再次向你推荐[阿德里安·科勒(Adrian Coyler)总是很有趣的“晨报”博客](https://blog.acolyer.org/2019/02/04/tensorflow-js-machine-learning-for-the-web-and-beyond/)上的一篇文章，在这篇文章中，他看了一篇关于“ [TensorFlow.js:面向网络及未来的机器学习](https://arxiv.org/abs/1901.05350)”的文章

“如果机器学习和 ML 模型要渗透到我们所有的应用程序和系统中，那么它们最好去应用程序所在的地方，而不是相反，”Coyler 写道。“这越来越意味着浏览器和服务器上的 JavaScript。 [TensorFlow.js](https://js.tensorflow.org/) 将 TensorFlow 和 Keras 引入 JavaScript 生态系统，支持 Node.js 和基于浏览器的应用。”

TensorFlow.js 并不新鲜——它是在近一年前发布的，Coyler 提供了几个人们用它做的“大量创造性事情”的例子，他指出，其中“只需点击一下就可以访问所有内容”,因为它们在浏览器中运行。在那里，Coyler 做了他最擅长的事情，并深入研究了是什么使 TensorFlow.js 成为可能，研究了“构建基于 JavaScript 的 ML 环境所涉及的挑战，包括:JavaScript 可以执行的不同环境的数量；提取足够好的性能；跨浏览器兼容性问题；以及它的单线程特性。”

我觉得，这是不断增长的堆栈中最好的部分——作为开发人员，如果你不想知道它是如何工作的，你就不需要知道它是如何工作的。其他人可以处理所有这些细节，你可以浮在上面，愉快地在你的浏览器中训练机器学习算法。所以，如果你愿意……或者不愿意，请继续读下去。

当我们谈到这个话题时，这里有一个简短的视频，来自上周的 O'Reilly 软件架构会议，IBM 的 [Tamar Eilam](https://www.linkedin.com/in/tamar-eilam-457171/) 谈到“云原生编程的未来”，她谈到了开发者在不断增长的堆栈中的位置。

[https://www.youtube.com/embed/e0-9bQSRqA0?feature=oembed](https://www.youtube.com/embed/e0-9bQSRqA0?feature=oembed)

视频

## 本周的节目中

*   **关于 Golang:** 向 New Stack 的一位作家致敬，他的故事我百听不厌，David Cassel 为我们带来了对 Go 产品负责人史蒂夫法兰克王国的采访关于 2019 年 Golang 的一切:模块、泛型、更好的错误处理，应有尽有。也就是说，只要“它”不会对五年多前发布的 Go 1.0 造成突破性的改变，你就给它起名字。有一句关键的话让我印象深刻:“模块是——这不是一个新概念。(*笑*)这是一个存在于很多其他语言中的词。但我们正在采取一种新的、有点创新的方法。”[围棋的不断进化](https://thenewstack.io/this-week-in-programming-golang-2-0-and-how-to-handle-breaking-changes/)已经成为许多人的兴趣点，这种更深入的探索值得那些投资者阅读。另一个独立但相关的消息是，根据一份将 Golang 开发者列为收入最高的报告，显然你们 Golang 开发者这些日子过得相当不错。
*   **反其道而行之:**还记得就在两周前，我们谈论过一个开发者，他说 [Go 教会他 PHP 是浪费时间](https://thenewstack.io/this-week-in-programming-have-you-heard-the-one-about-php/)，他后悔选择了这门语言？好吧，今天我们有一个完全相反的故事，来自[的丹尼·范·库腾](https://dannyvankooten.com/about/)，一位荷兰的“20 多岁的 web 开发人员”，他写道“两年过去了，我们的商店应用程序又由 PHP 驱动了”，因为，首先，“PHP 在过去 3 年中改进了很多”，增加了“[标量参数类型声明](https://secure.php.net/manual/en/functions.arguments.php#functions.arguments.type-declaration)、[返回类型声明](https://secure.php.net/manual/en/functions.returning-values.php#functions.returning-values.type-declaration)、[多重捕捉异常](https://wiki.php.net/rfc/multiple-catch)、令人印象深刻的[性能改进](http://www.zend.com/en/resources/php7_infographic)以及许多其他一般性改进除了 PHP 最近的改进之外，van Kooten 还提到了该语言对他们所采用的整体风格的适应性:“老实说，Go 非常棒。它的简单令人耳目一新，性能无与伦比。如果我们需要一个小的 API 或者需要高吞吐量的东西，我仍然会选择它。然而，我们的商店更加单一，有很多服务器端渲染。虽然这在 Go 中肯定是可行的(正如过去两年所证明的那样)，但对我们来说，现在用 PHP 实现更容易维护。”

*   **ide 已经“Kubernetes-native”了:**回到攀登堆栈的想法，集成开发环境(ide)的世界已经向前迈进了一步，正如我们现在已经开始描述的那样，至少有一些是“Kubernetes-Native”没错， [Red Hat 新发布的 CodeReady Workspaces IDE](https://thenewstack.io/codeready-workspaces-delivers-kubernetes-native-ide/) 不仅是基于网络的，而且全部都在 Kubernetes 上——开发人员都在 Kubernetes pod 中运行他们自己的个人小环境，并且它是外部可链接的。对我来说，这个故事的引语是:“有了 CodeReady 工作空间，从你开始编码的那一刻起，你就在 Kubernetes 的一个容器里。你别无选择，只能呆在库伯内特斯。”
*   **麻省理工学院的《如何成为一名黑客:**这个为期六天的关于“黑客工具”的[课程可以在网上免费获得，并有所有讲座的](https://hacker-tools.github.io/)视频[，由麻省理工学院的三名研究生](https://hacker-tools.github.io/lectures/) [Anish Athalye](https://www.anishathalye.com/) 、 [Jon Gjengset](https://thesquareplanet.com/) 和[何塞·哈维尔·冈萨雷斯·奥尔蒂斯](http://josejg.com/)共同授课。它检查了从[虚拟机和容器](https://hacker-tools.github.io/virtual-machines/)到[外壳和脚本](https://hacker-tools.github.io/shell/)到[点文件](https://hacker-tools.github.io/dotfiles/)等等的一切。它甚至有自己的[子编辑](https://www.reddit.com/r/hackertools/)，并在网上链接到之前的讨论。这就像你的朋友知道的比你多，最终同意坐下来，把一切都告诉你——而你甚至不需要给他们买半打啤酒或比萨饼或任何东西…

*   **开源 GitHub Actions:** 去年[当 GitHub 宣布其 Actions 特性](https://thenewstack.io/this-week-in-programming-github-dives-into-devops-with-actions/)时，每个人都非常兴奋，该特性允许 GitHub 用户自动化工作流，本质上将 DevOps 功能引入了流行的开源库。现在，该公司已经宣布将开放源代码发布 Actions 工作流语言的解析器和规范，以便更大的社区可以创建外部工具来“检查、格式化、合成和可视化工作流文件”，以及其他功能。
*   **调查说！**最后，对于那些参与调查的人，我们有几个建议供您参考。首先，JetBrains 发布了其 [2018 Python 调查](https://www.jetbrains.com/research/python-developers-survey-2018/)的结果，其中显示 Python 越来越多地用于 DevOps 功能。接下来，如果 [Clojure](https://clojure.org/) 恰好是你的囊中之物，那么，Clojure 2019 结果的[状态刚刚发布，发现该语言“因其对函数式编程、不可变数据、交互式 REPL 和易于开发的惯用支持而受到](https://clojure.org/news/2019/02/04/state-of-clojure-2019)[的重视”然后是](https://clojure.org/news/2019/02/04/state-of-clojure-2019#strengths)[Devskiller 2019 年全球技术招聘和技能报告](https://devskiller.com/technical-hiring-skills-report-2019/)，该报告提供了一些漂亮的互动图表，如谁在开发人员测试中得分最高等细节。

专题图片: [IFX 2018](https://www.open19.org/events/ifx-2018/) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>