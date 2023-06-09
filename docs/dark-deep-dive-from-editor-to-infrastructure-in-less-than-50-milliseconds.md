# 深度潜水:从编辑器到基础设施不到 50 毫秒

> 原文：<https://thenewstack.io/dark-deep-dive-from-editor-to-infrastructure-in-less-than-50-milliseconds/>

关于 Dark 的介绍，请参见“ [Dark，一种用于‘无部署’部署的新编程语言](/dark-a-new-programming-language-for-deployless-deployments/)”

将自称为“为无部署后端构建的语言”的 [Dark](https://darklang.com) 描述为仅仅是一种编程语言可能会低估这个项目的宏伟抱负，这个项目表面上打算将软件生命周期的几个方面整合到一个不再存在语法错误的环境中，基础设施不需要第二次思考，从代码到生产的时间不到 50 毫秒。

在一份宣布 Dark 从私有 alpha 变为私有 beta 的公司声明中，Dark 被更恰当地描述为“一种整体编程语言、编辑器和构建后端的基础设施”，这是 Dark 联合创始人 Paul Biggar 对新堆栈的看法。

“黑暗比传统语言包含了更多。关于 Dark 的关键是它也包含了基础设施，所以另一种思考方式是它占据了 AWS 或 Heroku 或 Google Cloud 占据的空间。你不需要考虑，你只需要写代码，我们会为你处理基础设施。“我们对 Dark 的意图是，它是一个基础设施编译器。因为我们有关于您的程序如何运行的所有信息，我们有流量，我们有代码，我们有数据，我们可以及时决定什么是您应用程序的最佳架构，并自动为您构建。”

虽然 Biggar 承认 Dark 仍然处于早期阶段——“今天的实现与那时大不相同，更多的是处于早期阶段，”他谈到 Dark 的基础设施编译能力——作为持续集成和持续交付(CI/CD)平台 CircleCI 的前创始人和首席执行官，Biggar 已经花了很多心思来讨论这个主题。Biggar 在一篇冗长的博客文章[中阐述了团队对 Dark 的渴望，描述了一种完全在线的语言，从 IDE 到部署，只要输入到基于 Web 的 IDE 中，就可以立即用于生产。](https://medium.com/darklang/how-dark-deploys-code-in-50ms-771c6dd60671)

有几个关键的设计选择使 Dark 成为现在的样子:它直接使用抽象语法树(AST)进行操作，它对从自己的版本到不同版本的代码的所有内容都使用特性标志，并且它没有解析器，Biggar 称之为“关于 Dark 的一件有趣的事情”。

在典型的编译器和解释器中，解析器创建 AST。它是从文件中提取文本，并将其转化为实际的表示，以显示语言的含义。它有一个花哨的名字，但它是一个非常简单的概念，”比格说。“相反，Dark 做的是编辑器直接在 AST 上操作。这意味着，当您在编辑器中键入内容时，我们直接在 AST 上进行转换，这使我们能够做真正强大的事情。它极大地简化了基础设施的大部分工作方式。我认为如果没有它，50 毫秒的部署是不可能的。”

关于 Dark 是否是编译语言，Biggar 说对于用户来说没有可见的编译器。“你只需编写代码，50 毫秒后它就会运行。今天的实现就是黑暗被解读。未来的实现是，首先对 Dark 进行解释，然后用即时编译器对其进行编译。”

虽然 Dark 现在可能刚刚进入私人测试阶段，但该公司表示，已经有客户在 Dark 上运送了整个产品，如提供个性化航班交易的订阅 SaaS[Altitude](https://usealtitude.com)，以及项目跟踪工具 [Birb](https://hellobirb.com) 。

除了“无部署性”, Dark 也是无错误的——至少在语法方面。Biggar 解释说，虽然你的代码可能无法达到你的预期，但它仍然会运行。

语法错误是分析器突出显示的错误。所以，如果你没有一个解析器，你不可能有一个解析器错误，”比格说。“您可以创建不想创建的 AST，但您创建的所有内容都将是有效的 AST，并且永远不会出现分号问题。”

CircleCI 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>