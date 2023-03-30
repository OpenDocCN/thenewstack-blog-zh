# 本周编程:实时协作编码来到 Atom 和 Visual Studio

> 原文：<https://thenewstack.io/week-programming-real-time-collaborative-coding-comes-atom-visual-studio/>

如今，大多数办公室工作人员都无法想象没有谷歌文档或微软 Office 365 等实时协作工具的现代工作场所。然而，对于许多开发人员来说，实时协作经常以松散、孤立的 ide 和屏幕共享的形式出现。虽然近年来有越来越多的 ide 提供实时协作，但是一些最流行的已经落后了——直到现在。

虽然新版本的语言和功能不断出现，本周也不例外，但这一次编程新闻的亮点可能是 Atom 和 Visual Studio 实时协作的到来。正如 Atom 的博客文章所指出的，“与另一个程序员一起编写代码的后勤工作可能是如此麻烦，以至于许多人都懒得去做。”本周，GitHub 和微软都宣布(同一天，在那！) [Teletype for Atom](https://github.com/blog/2468-introducing-teletype-for-atom-code-collaboratively-in-real-time) 和 [Live Share for Visual Studio 和 Visual Studio Code](https://code.visualstudio.com/blogs/2017/11/15/live-share) 分别为。

Atom 已经是一个流行的开源代码编辑器，今年早些时候发布了全套 IDE 特性。现在，Atom 的 Teletype 提供了“一种新的方式，可以在 Atom 中打开的任何文件上，在自己的编程环境中，通过自己的配置，与远程合作者[……]实时地直接进入代码。”

一切都是免费和开源的，像往常一样，完全加密，所以你的任何文件或编辑都不会与 GitHub 的服务器共享。也许最令人兴奋的是，整个系统是由一个名为 teletype-client 的编辑器无关的库构建的，这将使未来不同文本编辑器之间的互操作成为可能。虽然仍处于测试阶段，但 Atom Teletype 已经可以下载[了](https://teletype.atom.io/)，Atom 博客文章将带您完成安装。

至于 [Visual Studio Live 分享](https://code.visualstudio.com/blogs/2017/11/15/live-share)，实时代码编辑只是个开始。你的队友不仅可以“阅读你共享的代码，而不必克隆一个 repo 或安装你的代码所依赖的任何依赖项”，而且“他们可以使用丰富的语言特性在代码中导航；不仅仅是以文本形式打开其他文件，还可以使用基于语义分析的导航，如转到定义或查看。”除此之外，您甚至可以协作调试代码。遗憾的是，Live Share 尚不可用，但您可以注册先睹为快。在此之前，您还可以观看新功能的视频:

## 本周的节目新闻中

*   **Kotlin/Native v0.4:** 上周，Kotlin 的创建者 JetBrains 宣布将通过下一版本的 Kotlin/Native 支持 iOS。本周，该公司宣布全面发布[科特林/原生 v0.4](https://blog.jetbrains.com/kotlin/2017/11/kotlinnative-v0-4-released-objective-c-interop-webassembly-and-more/) 。该版本的亮点包括支持在 iOS 和 macOS 上访问 Objective-C API，对 [WebAssembly](https://en.wikipedia.org/wiki/WebAssembly) 的实验性支持，以及“使 Kotlin/Native way 中的应用程序开发更容易的重大变化。”关于 Kotlin 上周在大会上发生的一切，请参考本专栏的上周版本，标题为“[本周编程:Kotlin 吃你的午餐](https://thenewstack.io/week-programming-kotlin-eats-lunch/)”
*   **GitHub 安全警报:**GitHub 进一步兑现了上个月做出的承诺，帮助开发者跟踪并修复依赖关系中的已知缺陷，GitHub 已经[宣布了安全警报](https://github.com/blog/2470-introducing-security-alerts-on-github)，它说这将有助于“超过 75%的 GitHub 项目有依赖关系。”该功能依赖于在 GitHub Universe 发布的一个帮助跟踪依赖关系的功能。启用依赖关系图后，GitHub 会在检测到用户依赖关系中的漏洞时通知用户，并提供来自社区的已知修复建议。新功能还将包括具有[CVE id](https://cve.mitre.org/)的漏洞(从[国家漏洞数据库](https://nvd.nist.gov/)公开披露的漏洞)。
*   **TensorFlow Lite:** 谷歌还提供了一些过去承诺的后续措施，如[tensor flow Lite](https://developers.googleblog.com/2017/11/announcing-tensorflow-lite.html)的开发者预览版，它“实现了设备上机器学习模型的低延迟推理”“面向移动和嵌入式设备的轻量级解决方案”在 iOS 和 Android 上都可以运行。TensorFlow Lite 支持 [Android 神经网络 API](https://developer.android.com/ndk/guides/neuralnetworks/index.html) ，以利用“专门构建的定制硬件来更高效地处理 ML 工作负载”，但“当加速器硬件不可用时，会退回到优化的 CPU 执行，从而确保您的模型仍然可以在大量设备上快速运行。”谷歌表示，“展望未来，TensorFlow Lite 应该被视为 TensorFlow Mobile 的发展，随着它的成熟，它将成为在移动和嵌入式设备上部署模型的推荐解决方案。”谷歌研究博客也提供了一些外围见解，查看了使用 TensorFlow Lite 的[设备上对话建模](http://research.googleblog.com/2017/11/on-device-conversational-modeling-with.html)。为了帮助开发者起步，他们发布了一个设备对话模型和一个演示应用。
*   **NumPy 放弃 Python2:** NumPy，Python 的基础科学计算包，宣布了放弃 Python2 支持的时间表。Python2 的官方支持将于 2020 年[结束](https://pythonclock.org/)，NumPy 计划遵循类似的时间表，在 2018 年 12 月 31 日之前完全支持 Python 2 和 Python3。然后，在 2019 年 1 月 1 日，任何新的功能发布将只支持 Python3，对 Python2 的长期支持(LTS)将持续到 2019 年 12 月 31 日。
*   **Fortran 60 岁:**Fortran 于 1957 年首次推出，现在它正在庆祝自己的 60 岁生日。尽管“接近退休年龄”，但这种语言越来越强烈。博文解释道“顾名思义，Fortran 是为了将数学公式翻译成计算机代码而设计的。这解释了它在处理大量数学公式(尤其是偏微分方程等)的领域中的强大存在
*   Go Turns 8: 与此同时，自 Go 作为开源项目发布以来，[已经过去了 8 年，在这么短的时间内，它已经聚集了全球近百万用户，并在 GitHub 的](https://blog.golang.org/8years) [2017 Octoverse](https://octoverse.github.com/) 流行编程语言列表中获得了第 9 名。自最初发布以来，它已经经历了“语言、库和工具的 10 次发布，超过 1680 名贡献者对项目的 34 个存储库进行了超过 50，000 次提交。”

## 本周的语言趋势

*   **戏剧性的技术转变:** Stack Overflow 继续发布一系列数据驱动的博客文章，研究技术的转变领域，这次试图找出[最戏剧性的转变](https://stackoverflow.blog/2017/11/13/cliffs-insanity-dramatic-shifts-technologies-stack-overflow/)。去年的两个佼佼者包括苹果 iOS 应用程序语言 Swift 和谷歌网络框架 Angular。“这两种技术都发展得令人难以置信地快，产生了巨大的影响，”他们推断，“因为它们是现有开发人员社区的自然下一步。”
*   **Java 开发人员喜欢 Kotlin:**SD times 报道称 [Java 开发人员最兴奋与 kot Lin 一起工作](https://sdtimes.com/report-java-developers-excited-work-kotlin/)，引用了 RebelLabs 的一份报告。根据这份调查了 2000 名 Java 开发人员的报告，Kotlin 是“2017 年最令人兴奋的技术，其次是 Docker，Java 9，Spring，Angular，Java EE 8，Spring 5，Java 8，Kubernetes 和 React。”
*   **脚本语言受欢迎程度下降:** InfoWorld 报道[脚本语言受欢迎程度下降](https://www.infoworld.com/article/3237085/javascript/scripting-languages-slip-in-popularity.html)，因为开发人员“选择更安全的语言，尽管像 Perl、PHP 和 Ruby 这样的脚本语言提供了易用性。”根据 TIOBE 指数,“只有 Python 变得强大了”，这种受欢迎程度下降的原因很可能是运行时错误。他们写道:“即使是像 JavaScript 这样在进行 web 编程时不可避免的脚本语言，也被迫发展成一种更安全的语言。”“微软推出了名为 TypeScript 的 JavaScript 类型化版本，并开发了 Angular 和 React 等各种框架来保护这种语言(并添加额外的功能)。”

微软是新堆栈的赞助商。

通过 [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:HELP_ME_(4278905797).jpg) 获得的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>