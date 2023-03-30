# Pyscript:面向 99%用户的基于浏览器的 Python 框架

> 原文：<https://thenewstack.io/pyscript-a-browser-based-python-framework/>

用机器语言和 Python 编程的 Raphael Madu ，不确定他是否明白由 [Anaconda](https://www.anaconda.com/) 开发的新 Python 框架 [Pyscript](https://pyscript.net/) 的意义。

这很有趣，他告诉新堆栈，但是机械工程实习生不明白这一点，尽管已经尝试过了，并就此写了一个简短的教程。

“它似乎有很大的潜力，”他说。"但是现在，我还没有看到 Pyscript 的任何东西."

他不是唯一一个看不到这一点的程序员——没关系，Anaconda 联合创始人兼首席执行官[王蒙杰](https://www.linkedin.com/in/pzwang/)说。Pyscript 并没有试图转化专业的 web 开发人员。相反，它是为 99%的非专业开发人员设计的，王说。

“对于那些‘我不明白这有什么必要’的人，我想说的最重要的一句话就是，这与你无关，”他说。“这是为了所有的小学生，你不用花一下午的时间去教他们如何构建自己的第一个应用程序。”

## 灵感来自 HyperCard

今天教一个孩子如何编程是复杂的。除了教他们编程，你还需要教他们如何捆绑 web 服务器架构和云部署。你要“花三天时间教他们，然后他们才能做一个‘Hello World’应用程序，”王说。

除了强烈的正义感之外，启发王的是他自己早期与 HyperCard 一起成长的经历，HyperCard 是一种用于麦金塔电脑的预 web 开发工具包，其中包括一种脚本语言。

“HyperCard 是我的第二或第三种编程语言或环境，我仍然对一个孩子(当时我还是个孩子)开始组装真正的应用程序的简单性感到非常鼓舞，”王说。

在他长期使用 Python 的过程中，他看到许多人将 Python 作为他们的第一语言。他同情这些新手和公民开发者，并希望 Pyscript 能够为他们提供一种快速使用 Python 编写第一个“Hello World”的方法。

## Pyscript 如何工作

最近，[LWN.net](https://lwn.net/Articles/898452/)指出，Python 很容易学，但是编写和发布带有用户界面的 Python 应用程序很有挑战性。王告诉记者，即使使用网络前端也需要编写 JavaScript、CSS 和 HTML。

王解释说，事实证明，部署 Python 的关键是 WebAssembly。去年，Anaconda 开始探索用 Python 和 [WebAssembly](https://thenewstack.io/what-business-problems-does-webassembly-solve/) 所做的工作——像 Pyodide 和 JupyterLite 这样的项目，已经编译了 Python 科学和数字堆栈的一部分，以针对 WebAssembly。

“我们对围绕 Python 和 WebAssembly 开始出现的一些底层工作很感兴趣，”他告诉 New Stack。“我脑海中的想法是，这不仅仅是在浏览器中嵌入一个小的 Python 终端，运行 WebAssembly，而是实际上，让我们将整个浏览器环境开放给所有的 Python 和所有的 Python 数据，然后许多东西开始从那里级联起来。”

WebAssembly 是浏览器(包括移动浏览器)支持的 W3C 标准。正如王向解释的那样，WebAssembly 是一个具有 32 位地址空间的虚拟 CPU 指令集；它可以进行 64 位运算。编译器 Emscripten 可用于将大多数 C 和 C++代码编译成 WebAssembly。他说，因为 CPython 是一个 C 程序，所以 Python 数字堆栈的大部分是用 C 或 C++编写的。

在王看来，通过一些绑定和“语法糖”，Python——不是它的变体，而是它的整体——可以在浏览器中运行，而不会牺牲与生态系统其余组件的兼容性。所以 Pyscript 就是从那里进化而来的。

> “我们对开始围绕 Python 和 WebAssembly 开展的一些基础工作很感兴趣。”

Anaconda 首席执行官王蒙杰

“与任何其他语言相比，Python 的困难在于，Python 的很多能力来自于它对数据分析和数值计算的使用，这需要一套非常庞大、广泛且难以编译的 C、C++和 Fortran 库或包，我们可以称之为它们，”他说。“所以，最近才发生的大提升的一部分是，许多这些库被移植到 WebAssembly 上运行。”

他说，这使得 Python 及其数据扩展系统可以作为一等公民直接在浏览器中运行，与 JavaScript 之类的东西并列。

这一巨大变化使得 Pyscript 成为可能。他说，Anaconda 引入了一些额外的自以为是的框架位，设想有人能够编写一个 HTML 标签，插入一些 Python 代码，然后关闭标签，它就可以简单地在浏览器中工作。

现在，为了运行它，代码访问 Anaconda 的服务器，以实际加载 Pyscript 运行时和包。他解释说，一旦这些被加载到用户的浏览器中，就不再需要连接到服务器上了——它完全在浏览器的本地运行。

“如果你是一名开发人员，你想使用 Pyscript 来发布你的应用，你只需要把 Pyscript 工件、运行时和模块放在你的服务器上，”他说。当用户来到您的服务器时，他们会从您那里加载，然后在他们的浏览器选项卡中运行

他解释说，这实际上是一种点对点的应用程序分发机制，允许人们彼此共享应用程序

“如果他们在一个完全断开的环境中，他们仍然能够使用所有的 Python 堆栈运行成熟的、真正的 web 应用程序，并且他们不必攻击任何人的服务器，”他说。“所以在某种程度上，它有点指向 Web3 的功能，但使用 Python 来进行 Web3 开发。”

Pyscript 还处于测试阶段，还没有准备好投入生产，但是王在 2022 年的 PyCon 大会上做主题演讲时确实觉得它已经准备好了。

## Pyscript 的下一步是什么

Pyscript 仍处于 alpha 阶段，但 Anaconda 计划提高包加载的速度和下载的大小，使它更快。它还致力于增加支持，使它更容易建立用户界面。他说，该团队还在研究数据 IO 和数据持久性，因为构建应用程序后的下一步将是连接到数据库。他说，在几个月内，Pyscript 将“有一些真正好的东西”来支持使用该框架。

Wang 说，Python 社区的反应是积极的，尤其是那些看到了这种语言在构建应用程序方面的努力的 Python 人。

“他们可以通过 Pyscript 看到，现在他们有一种方法可以把东西送到人们手中，”王说。“你会找到那些真正理解你想要做的事情的人，与他们合作，然后继续在此基础上创造伟大的事情。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>