# Brain.js 为浏览器和 Node.js 带来了深度学习

> 原文：<https://thenewstack.io/brain-js-brings-deep-learning-to-the-browser-and-node-js/>

[Brain.js](https://brain.js.org/) 是一个 JavaScript 库，用于在浏览器或 Node.js 上部署神经网络，它使用计算机的 GPU(图形处理单元)进行计算，或者在 GPU 不可用时使用纯 JavaScript。

Brain.js 的首席开发者是 [Robert Plummer](https://twitter.com/robertlplummer) ，他白天是 iFIT 的全栈工程师。我向他寻求更多关于 Brain.js 的信息，包括它的起源、目前的用途以及未来的计划。

正如 Plummer 项目的名称所示，[神经网络](https://en.wikipedia.org/wiki/Artificial_neural_network)是模拟生物大脑工作方式的计算机系统。神经网络由连接的节点组成，松散地模仿大脑中的神经元。也像大脑一样，神经网络需要根据输入系统的数据进行训练——这是一种被称为深度学习的机器学习类型。

Brain.js 的主要优势在于它使用了世界上最流行的 web 编程语言 JavaScript。此外，根据 IBM 开发人员教程，用 Brain.js 构建的神经网络驱动的应用程序“可以用少得惊人的代码来创建。”

## 用例

那么浏览器中的神经网络有哪些用例呢？根据 Plummer 的说法，它们是“无限的”，但是他给出了来自 Brain.js 社区的几个例子。“我见过人们用它来管理农业社区的种子，”他说，“我也见过人们用它来预测某个地方的股市价格或天气。”

他警告说，在这个阶段，输入 Brain.js 驱动的网络应用程序的数据需要监督训练。他说，无监督学习和强化学习还没有进入图书馆。

我问 Brain.js 与用 Python 或 R 这两种机器学习中常用的语言编程神经网络相比如何。JavaScript 也有同样的威力吗？

Plummer 证实使用 JavaScript“同样强大”，但他指出使用数字处理部分“有一些开销”。然而，他说，“我们提供使用 GPU 的能力，这是 GLSL [OpenGL 着色语言]，是 C++的子集。”他补充说，这与使用 Python 或 R“非常相似”。

## Brain.js 的历史

尽管 Plummer 是 Brain.js 的主要开发者，并且自 2016 年以来一直致力于该项目，但该库源于由 [Heather Arthur](https://twitter.com/heatherchars) 创建的一个名为 [brain](https://github.com/harthur/brain) 的项目。亚瑟将她的项目描述为“一个简单的神经网络库”然而，她在 2014 年左右停止了维护。在[和 *brain* 社区的一些讨论](https://github.com/harthur/brain/issues/72)之后，Plummer 在 2016 年 1 月克隆了 Arthur 的项目——brain . js 就这样诞生了。

顺便说一句，希瑟·亚瑟在 2017 年写了一篇博文解释为什么她不仅放弃了大脑，还放弃了她所有的 GitHub 项目。事实证明，每一个都是“个人兼职项目”，她发现很难维持所有这些项目，因为她没有“组织支持”她继续说，有“大量乏味的工作”，这导致她宣布“GitHub 破产”

也许 Arthur 的 brain 走在了她那个时代的前面，但幸运的是，她的工作激励了一群 JavaScript 开发者(Plummer 也在其中)继续并扩展这个项目。

至于为什么 Plummer 对大脑感兴趣并想继续下去，他告诉我，在 Arthur 的项目之前，他“从未见过神经网络发展得如此简单易懂。”

“JavaScript 是一种美丽的语言，”他说。“这很简单，没有理由说它不具有很强的表演性。有些事情仍然在阻碍它，但它正在缓慢但肯定地向前发展。”

## Brain.js 自 Fork 以来是如何发展的

Plummer 创办 Brain.js 已经六年半了，所以我问现在和 Arthur 当初的项目有多大不同？

“在其最初的化身中，它只是一个前馈神经网络，能够输出一个单一的算法——基本上是一个很长很长的代码行中的单一训练神经网络，”他回答说。[前馈神经网络](https://www.analyticsvidhya.com/blog/2022/01/feedforward-neural-network-its-layers-functions-and-importance/)是一种节点连接不形成回路的神经网络。

“从那以后，”Plummer 继续说道，“我们也增加了 GPU。所以你可以用 JavaScript 写，然后编译成 GLSL(或者 C++的子集)；这花了两年半到三年的时间。”

具有讽刺意味的是，在维护 Brain.js 项目方面，Plummer 似乎遇到了与 Arthur 类似的问题——缺乏支持。他是这个项目中唯一活跃的开发人员，不得不在日常工作时间之外从事这项工作。

关于 Brain.js 的工作，Plummer 说:“我的日常工作很忙，我没有尽可能频繁地接触它，这些年来，我的开发人员来了又走。我向他们伸出援手，你知道[……]但在大多数情况下，只有我一个人。”

普卢默把他仅有的一点业余时间大多花在了修复 bug 上。但他也开始研究“强化神经网络，强类型”，[这是](https://www.baeldung.com/cs/reinforcement-learning-neural-network)一类旨在根据经验自动改进的算法。

## JavaScript Heads:试试 Brain.js

很多深度学习项目将继续使用 TensorFlow 之类的平台，或者像 IBM Watson Studio 或 Google Cloud AI 平台这样的大公司平台。但如果你是一名 web 开发人员，想要在浏览器或 Node.js 上尝试深度学习，那么 Brain.js 是值得一试的。尤其是当你有种子要管理或者股票价格要预测的时候。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>