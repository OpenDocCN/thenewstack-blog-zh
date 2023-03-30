# 本周编程:微软的 Power Fx“低代码”语言

> 原文：<https://thenewstack.io/this-week-in-programming-microsofts-power-fx-low-code-language/>

在过去的一周，微软举行了一年一度的 IT 和开发者大会， [Microsoft Ignite](https://myignite.microsoft.com/home) ，会上发布了许多新产品和新功能，其中包括[推出的微软 Power Fx](https://powerapps.microsoft.com/en-us/blog/introducing-microsoft-power-fx-the-low-code-programming-language-for-everyone/) ，它称之为“面向所有人的低代码编程语言”现在，在现实中，[微软 Power Fx](https://aka.ms/PowerFxDocs) 其实并不那么新，而是一个开源“基于微软 Excel 的低级代码公式语言”的名字，它已经成为微软无代码 [Power Apps canvas](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/getting-started) 的基础。

根据微软的说法，这一版本令人兴奋，因为 [Power Fx 是开源的](https://github.com/microsoft/power-fx)，它基于[最近制作的图灵完整的](https://thenewstack.io/microsoft-excel-becomes-a-programming-language/) Excel 语言，并且因为它是“为低代码构建的”他们指出，第一点很重要，因为 Power Fx 基于“数亿人已经在使用的精确语法”，而不是目前估计有 1170 万软件开发人员在编写 JavaScript。

除此之外，Power Fx 的重要性可能在于希望它能够成为一座桥梁，正如项目经理 Greg Lindhorst 在 Power Fx 的更深入介绍[中所写的那样:“它支持从‘无代码’到‘专业代码’的全方位开发，中间没有悬崖，使不同的团队能够合作，节省时间和费用。”](https://powerapps.microsoft.com/en-us/blog/what-is-microsoft-power-fx/)

Lindhorst 指出，在低代码端，“目标是将开发者需要理解的概念数量保持在最低限度，理想情况下不超过 Excel 用户已经知道的数量”，为此，Power Fx 的行为很像 Excel，因为编码者不需要关心程序如何运行。相反，它的行为很像 Excel，每当代码或数据发生变化时都要重新计算。在 pro 代码方面，Lindhorst 指出了将 canvas 应用程序解包为组成部分的能力，这些组成部分可以用 Visual Studio 代码或 Visual Studio 进行编辑，用 GitHub 或 Azure DevOps 置于源代码控制之下，以及创建纯用户定义的函数以供重用的能力，就像使用任何常规语言一样。

如果你发现自己带着怀疑和疑问看着这条新闻，当然，你并不孤单。要找到一些关于低代码的承诺如何让最有经验的开发团队陷入泥沼的抱怨，一如既往，只需前往黑客新闻并仔细阅读[评论](https://news.ycombinator.com/item?id=26324347)。对 whit 说:“我们最近试图构建一个相对简单的 PowerApps 应用程序——假设它会比生成一个 React 样板表单节省时间。再也不会了。”

类似地，几本关于电子表格的书的作者和 iProgrammer 的作者 Janet Swift 对 Power Fx 提出了一些[的问题，她写道“我真的不认为 Power Fx 会成为语言领域的一大优势——以前已经有人这样做过了。如果幸运的话，它可能会持续几年，然后当时尚改变时，它就会被拔掉。[……]就我个人而言，我希望看到微软给 VBA 一些爱——它并不完美，但它使用的对象模型仍然是最新的。为什么他们放弃了他们几乎优秀的胶水语言，并一直试图取代它。对我来说是个谜。”](https://www.i-programmer.info/news/98-languages/14392-microsofts-new-language-power-fx.html)

最终，可能不是 Power Fx 能否成为各种语言中的佼佼者，而是它能否实现这一介于两者之间的目的，将无代码和低级代码与 pro 代码连接起来，这将决定它是否能继续存在。当然，得到微软的支持是这个方向上的一个论点，该团队目前表示，他们的目标是“从 Power Apps canvas 中提取语言和文档，并将其推广到其他上下文”，所以这可能很快就会在其他上下文中看到。

## 本周的节目中

*   **Visual Studio Code 增加了对 M1 的支持:**Visual Studio Code 的二月发布已经到来，加入了许多其他软件，增加了对[苹果芯片构建](https://code.visualstudio.com/updates/v1_54#_apple-silicon)以及许多其他功能的支持。M1 支持意味着那些足够幸运拥有快速的新苹果芯片的人将能够使用 VS 代码，而不用与 Rosetta 进行仿真。流行的代码编辑器还添加了一些[可访问性](https://code.visualstudio.com/updates/v1_54#_accessibility)和[时间线视图](https://code.visualstudio.com/updates/v1_54#_timeline-view)的改进，以及添加了[持久终端进程](https://code.visualstudio.com/updates/v1_54#_retain-terminal-processes-on-window-reload)、[括号扩展](https://code.visualstudio.com/updates/v1_54#_brackets)，以及我们上周讨论的[扩展二分工具](https://code.visualstudio.com/updates/v1_54#_troubleshooting-extensions-blog-post)，这使得更容易找出导致一切陷入困境的错误扩展。如果你想了解这个最新版本的更多信息，因为这些只是最新特性的一部分，VS 代码团队还将在 3 月 11 日星期四上午 8 点(太平洋时间)举办一场[直播](https://code.visualstudio.com/livestream)。

*   为了不与 Visual Studio 代码混淆，Visual Studio IDE 已经发布了 [v16.9 和 v16.10 预览版 1](https://devblogs.microsoft.com/visualstudio/vs2019-v16-9-and-v16-10-preview-1/) ，其中有几个关于 C++的特性。NET Productivity、地址清除器、XAML 工具和 IntelliCode 团队。该版本被设定为下一个长期[服务版本](https://docs.microsoft.com/visualstudio/productinfo/vs-servicing-vs)，这意味着在下一个服务基线发布后的一年内，16.9 版本将支持修复和安全更新。至于那些新功能，它们包括 C++一致性、C++智能感知改进和 C++地址杀毒器，以及改进的堆栈溢出场景的调用堆栈处理，更不用说他们所谓的“[无摩擦重复编辑](https://devblogs.microsoft.com/visualstudio/repeated-edits-intellicode-suggestions-completion-list/)”这最后一个功能得到了自己的博客帖子，但 TLDR；IntelliCode 现在可以检测何时需要进行重复的代码更改并为您完成，这样您就不必停下手头的工作来查找所有需要更改的位置。

*   **Flutter 2 承诺平台不可知论:**谷歌已经放弃了 [Flutter 2](https://developers.googleblog.com/2021/03/announcing-flutter-2.html) ，称之为框架的“重大升级”，现在称之为“可移植框架”而不是“移动框架”。这一变化不仅可以为 iOS 和 Android 提供原生应用，还可以为 Windows、macOS 和 Linux 以及多种浏览器提供原生应用，甚至可以为汽车、电视和其他智能设备提供嵌入式应用。他们写道:“我们的目标是从根本上改变开发者构建应用的方式，不是从你的目标平台开始，而是从你想要创造的体验开始。”他们说，这次发布的最大新闻是“对网络的生产质量支持”，这是由谷歌的 Dart 编程语言实现的。他们指出，Dart 还将发布 Dart 2.12，这是该语言“自 2.0 以来最大的版本，支持声音无效安全”虽然宣布 Flutter 2 的博客文章足够长，但谷歌表示，他们甚至可以包括更多内容，所以如果你仍然感兴趣，他们还提供了一个关于 Flutter 2 的单独技术博客[以了解更多细节。](https://medium.com/flutter/whats-new-in-flutter-2-0-fe8e95ecc65)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>