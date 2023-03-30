# 本周编程:这就是 C 语言的做法

> 原文：<https://thenewstack.io/this-week-in-programming-thats-how-c-does-it/>

本周我有远大的抱负。我看到了一些深入研究编程语言历史、实践和其他基于互联网的趣闻的文章。我考虑过一个简洁的标题，比如“如果！我翻遍了我的原始资料寻找证据，但结果有点空手而归。最后，在一篇有趣的文章的结尾，人们发现了真正总结本周主题的一句话:为什么“=”意味着分配？

“我不知道这是否给谈话增添了什么。我只是喜欢软件历史。”

考虑到这一点，我们将从这里开始，有趣地看看“=”的起源，它是一种变量值赋值的工具，而不是(或者除此之外，而是)求值的工具。

“对命令式编程的一个常见的 FP 评论是这样的:‘A 怎么能= a + 1？这就好比说 1 = 2。可变赋值毫无意义。这是一个符号不匹配:“equals”应该表示“equality”，而实际上它表示“assign”。我同意这种批评，认为这是糟糕的记谱法。但是我也知道有些语言不写 a = a + 1，而是写 a := a + 1。为什么这不是常态？"

虽然简单的答案可能是“C 就是这样做的”，但是作者更深入地探究了实践是如何发展的。但是，我们真的学到了不要重复的教训吗？不尽然，只是觉得有趣。

同样，本周另一个引起我注意的互联网历史是一篇向[提供 JavaScript](https://medium.com/@dhope21/a-brief-history-of-javascript-9067ac4dce40) 简史的帖子。长话短说，JavaScript 和 Java 有关系吗？正如一个卡通广告所指出的，“JavaScript 听起来好像和 Java 有关系。并没有。事实上，Java 对于 JavaScript 就像 Ham 对于仓鼠一样。”

[知道的越多。](https://www.youtube.com/watch?v=GD6qtc2_AQA)

关于早期浏览器战争的有趣故事(你知道“Mozilla”是“马赛克黑仔”的组合词吗？)以及我们今天所知道的无处不在的全栈语言的诞生(当然，可以在评论中自由地表达和/或辩论)，[继续阅读](https://medium.com/@dhope21/a-brief-history-of-javascript-9067ac4dce40)。

此外，在我们自己的页面上，还有对前谷歌遗物“全球目录”50 周年纪念日的庆祝和审查，它提供了一段有趣的历史，涉及塑造了我们所知的互联网的一系列人物。"当时嬉皮士和反文化分子所钟爱的纸质目录，也成为了“整个硅谷革命的核心”，[约翰·佩里·巴洛](https://thenewstack.io/inspiring-life-john-perry-barlow/)曾打趣道."

最后，当我们在这里讨论遗物时，本周有一条新闻，除了怀旧之外，可能几乎没有真正的用处，但微软[已经开源了它在 20 世纪 90 年代的原始文件管理器，所以它可以在 Windows 10](https://www.theverge.com/2018/4/9/17214586/microsoft-windows-file-manager-windows-10-app-download) 上运行。没错，这款已有 28 年历史的软件现在“[在 GitHub](https://github.com/Microsoft/winfile/) 上可用，由微软资深人士 Craig Wittenberg 根据 [MIT](https://github.com/Microsoft/winfile/blob/master/LICENSE) 许可进行维护。

至此，让我们来看看过去一周编程领域的新闻和想法。

## 本周的节目中

*   **。NET Core 2.1 即将发布:**微软已经[宣布了。NET Core 2.1 预览版 2](https://blogs.msdn.microsoft.com/dotnet/2018/04/11/announcing-net-core-2-1-preview-2/) ，可能在未来一两个月正式发布前的最终预览版。预览版中的新特性包括构建性能改进、newSDK 命令、全局工具、新工具参数、自包含应用程序服务等等。
*   **谷歌&网飞发布开源金丝雀分析工具:**如果你以前没有听说过“金丝雀分析工具”，Techcrunch 的弗雷德里克·拉迪诺伊斯[很好地总结了这一点](https://techcrunch.com/2018/04/10/google-and-netflix-team-up-to-launch-a-new-open-source-canary-analysis-tool/):“顾名思义，这是一个早期预警系统，当你推出服务或基础设施的更新时，它可以防止重大问题。当您向新用户(或服务器，或网络的一部分)的子集推出更新时，canary analysis service 会检查新系统的行为是否符合预期，或者至少与旧系统一样好。”[本周宣布](https://cloudplatform.googleblog.com/2018/04/introducing-Kayenta-an-open-automated-canary-analysis-tool-from-Google-and-Netflix.html)，Kayenta“集成到了网飞孵化的 [Spinnaker](https://www.spinnaker.io/) 连续交付平台，该平台几乎可以在所有公共云和私有云上运行。”

[https://www.youtube.com/embed/LqquUa-IT28?feature=oembed](https://www.youtube.com/embed/LqquUa-IT28?feature=oembed)

视频

*   **伯克利的“数据科学基础”课程现已在线免费:**没错，该大学发展最快的课程现已在线免费[通过该校的在线教育中心 edX](http://news.berkeley.edu/2018/03/29/berkeley-offers-its-fastest-growing-course-data-science-online-for-free/)。根据公告，该课程“涵盖了从测试假设、应用统计推断、可视化分布和得出结论的所有内容，同时使用 Python 和真实世界的数据集进行编码。”edX 证书课程是由约翰·德内罗、统计学教授阿尼·阿迪卡里和计算机科学教授戴维·瓦格纳教授讲授的三个为期五周的系列课程，于 4 月 2 日星期一上午 9 点(太平洋时间)开始。课程开始后，报名将继续开放。
*   **Android P 中默认 TLS:**对于 Android 开发者来说，谷歌本周宣布 Android P 将[阻止针对 Android P 的应用默认允许未加密连接](http://android-developers.googleblog.com/2018/04/protecting-users-with-tls-by-default-in.html)，这是一个合理的警告。要了解全部细节，请阅读这篇博客文章，它试图解决如何做、为什么做以及你可能有的任何其他问题。比如你可能会问“TLS 不是很慢吗？”对此谷歌回答道:“[不，不是](https://istlsfastyet.com/)”所以，你有它。
*   面向大众的 Perl 6 IDE:Perl 6 社区似乎对基于 JetBrains IDEA 平台的名为 [Comma](http://www.commaide.com/) 的 Perl 6 IDE[公告](https://twitter.com/jnthnwrthngtn/status/980827338840690692)感到兴奋。IDE 目前处于测试阶段，早期支持者可以付费使用。要查看即将发布的 IDE 的全部细节，请查看其网站的[功能](http://www.commaide.com/features)、[常见问题](http://www.commaide.com/faq)和[路线图](http://www.commaide.com/roadmap)部分。
*   **一个用于 AppCode 的 Kotlin/Native 插件:**说到 IDE 和 Jetbrains，Kotlin 和 IDEA 平台背后的公司宣布了一个用于 AppCode 的 [Kotlin/Native 插件](https://blog.jetbrains.com/kotlin/2018/04/kotlinnative-plugin-for-appcode/)，它是专为 iOS/macOS 开发者设计的 macOS 专用 IDE。据该公司称，自从[宣布](https://blog.jetbrains.com/kotlin/2017/12/kotlinnative-v0-5-released-calling-kotlin-from-swift-and-c-llvm-5-and-more/)Kotlin/Native 与 Objective-C 的互操作性以来，它已经“收到了许多关于 IDE 支持的问题，这些问题将允许在混合 kot Lin/Native 和 Swift/Objective-C 的项目上工作”。要试一试，下载 [AppCode 2018.1.1](https://www.jetbrains.com/objc/) 。

https://twitter.com/caspervonb/status/984101018978758661

这就是我们本周所有的新闻内容，但我们确实看到了一些我们认为值得包含的指导文章…

*   **不要装 Kubernetes！至少，这是来自 [DevOps Zone](https://dzone.com/articles/dont-install-kubernetes) 的一位作者的建议。我们已经多次研究了现代容器工具如何帮助开发人员，但是正如本文所指出的，事实是完全安装这些系统之一可能非常耗时和困难。相反，这里的论点的要点是“大型云平台之间存在军备竞赛，以使 Kubernetes 成为一种交钥匙和自动管理的服务，从非常小的规模到非常大的规模，所以为什么不利用它们呢？”**
*   **管好你的属地！当我们从互联网上获取建议的时候，这里有另一篇文章建议你应该注意你的依赖关系。将依赖分为三类——基础、核心和实用——作者探讨了在构建软件时如何考虑采用不同库、框架或其他技术的风险。他们写道:“在上述三个群体中，我都经历过错误选择的后果。”“对实用程序库的错误选择是可以忽略的，但是对其他两个库的错误选择可能会成为一个严重的负担。”**
*   **保证团队苦难！**最后，如果你发现自己想知道[如何让你的团队痛苦](https://www.reddit.com/r/programming/comments/89an76/how_to_make_your_team_miserable/)，这是一个关于如何做到这一点的精彩大纲。“我对团队和公司中真正聪明、有才华的人无法一起工作的现象很着迷，他们几乎每天的工作都变成了不可避免的失败的又一步，我一直在收集创建痛苦团队的技巧和方法。”仔细阅读，或者大笑，故意呻吟，或者默默忍受未来一周的痛苦。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>