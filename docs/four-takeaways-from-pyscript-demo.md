# 开发人员从 Pyscript 演示中获得的 4 点经验

> 原文：<https://thenewstack.io/four-takeaways-from-pyscript-demo/>

“如果我们能在浏览器中运行 Python，那该多好啊，”Anaconda 高级开发倡导者 [Valerio Maggio](https://www.linkedin.com/in/valeriomaggio/) 在最近的一次网络研讨会上问道，“用`pyscript`重新思考数据可视化。”

他继续通过用多种数据可视化工具演示代码来展示 Anacando 的新语言 [Pyscript](https://pyscript.net/) 到底有多有用。但是首先，他从开发者的角度介绍了他对 Pyscript 的了解。以下是他演讲的四个要点:

## 1.Pyscript 到底是什么？

Maggio 花了大量的时间深入研究 Pyscript 是什么以及它与 JavaScript 和 HTML 有何不同——下面将详细介绍。至于基础——什么是 Pyscript——他解释说这是一种客户端技术，不需要服务器。严格地说，它是通过 HTML 中的几行代码从 Anaconda 调用 Pyscript 实现的。你可以[下载它](https://pyscript.net/)或者添加一些代码到你的页面:

```
<link rel="stylesheet"  href="https://pyscript.net/latest/pyscript.css"  />
<script defer src="https://pyscript.net/latest/pyscript.js"></script>

```

他注意到目前它实际上有两个版本——Alpha，它是冻结的，更稳定，或者你可以下载[最新版本](http://pyscript.net/latest/pyscript.js)。 [Anaconda 也在钉住释放](https://anaconda.cloud/announcing-pyscript-versioning)。他补充道，发布版本遵循 CalVer 的版本约定。

Maggio 解释说:“这是一种奇妙的方法，让 Python 最终与 JavaScript 一起工作来做很多事情。“这是一个环境管理系统。这是一个灵活的框架，允许您创建可插拔的组件。”

他还提到了 Pyscript 的原因。

“这项技术的潜力是多方面的，”他说。“本质上，Pyscript 只是 HTML。但是要说 Pyscript 只是 HTML，也不尽然吧？这比 HTML 稍微强大一些，因为 Pyscript 将整个 Python 生态系统直接引入了浏览器。这个项目的使命是让 99%的人能够编程。”

当然，这是关于 Pyscript 的另一件事，他提醒观众:Pyscript 还没有准备好投入生产，因为它仍在开发中。

## 2.Pycharm 支持 Pyscript

如果您在尝试 Pyscript 之前更喜欢 IDE 支持，Maggio 推荐了用于 Python 的 IDE[py charm](https://www.jetbrains.com/pycharm/)。事实上，他用它制作了网上研讨会上看到的演示文稿。

“Pycharm 在支持 Pyscript 时代的 Pyscript 语法高亮方面做得很好，”他说。“如果你问我，我肯定会推荐使用 PyCharm 作为立即使用 Pyscript 的首选解决方案。公平地说，这是我用来准备这次演讲的。它运行得非常完美。”

Pyscript 中的语法突出显示有助于更容易地重用代码，因为正如他所说的，“如果 HTML、JavaScript 和 Python 一起使用，而 Python 没有被正确地突出显示，将会变得很麻烦。”

## 3.Pyscript 不是 Javascript 的替代品

Pyscript 是一个单页应用程序(SPA)；Maggio 说，从更技术性的角度来看，它只是用打字稿写的。他强调说，这并不是要成为 JavaScript 杀手。

“这里有什么交易？到底是怎么回事？”他说。“嗯，Pyscript 允许在浏览器中使用 Python 来构建交互式 web 应用程序，这是你目前通常用 JavaScript 来做的事情。Pyscript 允许您使用或不使用 JavaScript。

事实上，他在网上研讨会中使用的一些演示涉及直接与 JavaScript 交互，而其他的则没有。

他补充说，它也不仅仅是 Python。

“首先，浏览器中的一个卖点是 Python 但它不仅仅是浏览器中的语言 Python，它更像是浏览器中的 Python 生态系统，”他说。“这是带 JavaScript 的 Python。”

## 4.PHP 共鸣

Maggio 第一次看到 Pyscript 时，他承认这给了他“PHP 的感觉”。他说，这是一个玩笑，但是他补充说 [PHP 的一个最佳实践是使用其他东西](https://thenewstack.io/from-php-to-next-js-what-trivago-learned-rewriting-its-web-app/)。“我们真的在这里做黑暗面吗？我们如何让 Python 成为新的 PHP，顺便说一下，这意味着页面上的人，[…]所以我们真的加入了黑暗面。”

这让他更加仔细地研究 Pyscript。

“我明白，在我面前的是一个全新的生态系统，”他说。“答案很简单，但实际上并不简单，因为 Pyscript 远不止于此——它与 PHP 一类的技术毫无关系。”

他补充说，有了 Pyscript，开发人员可以避免混合 HTML 和 Python 代码，如果这让他们感到困扰的话——这应该让他们感到困扰。

“混合表示和编程逻辑不是一个好的实践，”他说。“在 Pyscript 中，您实际上可以将 Python 代码放在一个单独的模块中，您可以在 timer.py 中编写所有内容。在此示例中，我已经使用 auto-see source 属性导入了 pyscript 时间。因此 Pyscript 实现了最佳实践。”

他演示了计时器脚本:

```
# timer.py
from datetime import datetime
now  =  datetime.now()
now.strftime("%m/%d/%Y, %H:%M:%S")
<py-script src="./timer.py"></py-script>

```

重要的是要记住 Pyscript 也可以在 web 浏览器环境中工作。

他承认，当 Maggio 想到 HTML 代码时，他会想到 JSP 技术。但这需要服务器，而且 Pyscript 是客户端技术，所以不需要服务器，也不需要安装，他指出。

他说，如果开发人员被表示和编程的混合所困扰，请记住，不管是好是坏，使用 JavaScript 也会发生同样的事情。

他的完整演讲提供了更多关于 Pyscript 架构的信息，py script 架构是基于 Pyodide 和 WASM 的，pyo dide 是已经停止的 Mozilla 碘化物项目的副产品。它还展示了 Matplotlib、Seaborn、Bokeh、Panel 和 HvPlot、NetworkX 和 D3.js 的演示。他制作了带有代码链接的[幻灯片，可在网上](https://leriomaggio.github.io/pyscript-dataviz/talk/#s1)的 Pyscript 中获得。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>