# 本周编程:是时候关注 WebAssembly 了

> 原文：<https://thenewstack.io/this-week-in-programming-the-time-has-come-to-pay-attention-to-webassembly/>

我不知道你是怎么想的，但是仅仅听到“组装”这个词就能让我血压升高，脉搏加快。光是这个词就让人想起了使用一种看似完全无法理解的语言的经历，如果使用不当(似乎大多数时候都是这样)，这种语言可能会很快覆盖您的引导区，使您的计算机无法使用，或者通常会造成某种程度的伤害，而使用 ol' BASIC 则不太可能。(是的，这是我在 80 年代做的事情。)

如果你碰巧也有这些焦虑，不要为网络大会(WASM)而烦恼。WebAssembly [没有带来覆盖引导扇区的可能性，而是提供了](https://thenewstack.io/ready-web-assembly-revolution/)将高级语言，如 C、C++和 Rust 引入[浏览器](https://webassembly.org/docs/web/)，以及浏览器之外的[的能力。简而言之，webAssembly 是基于堆栈的虚拟机的二进制指令格式，本周，万维网联盟(W3C)](https://webassembly.org/docs/non-web/) [将其称为官方 Web 标准](https://www.w3.org/2019/12/pressrelease-wasm-rec.html.en)和第四种允许代码在浏览器中运行的 Web 语言，加入了 HTML、CSS 和 JavaScript。

根据 W3C 的声明，WebAssembly 的要点是它带来了高性能的应用程序，如图像和视频编辑、游戏、流媒体音乐，以及许多其他用例，“通过作为虚拟机和执行环境，使加载的页面能够作为本机编译的代码运行”，并提供“接近本机的性能、优化的加载时间，或许最重要的是，现有代码库的编译目标”。

至于 WebAssembly 与其同名产品的初步比较，这里的主要区别是 WASM 运行在虚拟机中，这意味着它本质上是沙箱化的，可以被阻止进行内核调用(或覆盖您的引导扇区)。

根据本周的消息，WebAssembly 已经正式达到 1.0 版本，并在 Firefox、Chrome、Safari 和 Internet Explorer 的浏览器引擎中得到支持，字节码联盟[上个月推出了](https://hacks.mozilla.org/2019/11/announcing-the-bytecode-alliance/)，以帮助确保“一个默认情况下安全的 WebAssembly 生态系统”，并将 WebAssembly 带到前面提到的浏览器外使用。

当然，并非一切都是 100%美好的。正如[在 Register](https://www.theregister.co.uk/2019/12/06/webassembly_w3c_standard/) 上的一篇文章所指出的，WebAssembly 也带来了对正在发生的事情的更高层次的混淆，给了它执行一些秘密行动的更大能力。例如，他们引用了一项[研究](https://www.sec.cs.tu-bs.de/pubs/2019a-dimva.pdf)“发现超过 50%使用 WebAssembly 的网站将其用于恶意行为，如[加密]挖掘和混淆。”尽管如此，随着 WebAssembly 获得 W3C 的这一称号，确实是时候更加关注新提名的 Web 语言标准了。

## 本周的节目中

*   **然后就是 KotlinConf:** 当 AWS 忙于[从房间里吸走所有众所周知的空气](/this-week-in-programming-aws-reinvent-for-developers/)参加上周的 re:Invent 会议时，Kotlin 的用户和建造者都在忙于哥本哈根的 [KotlinConf](https://kotlinconf.com/) 。为了简要回顾过去一年 Kotlin 世界发生的事情，你可以看看谷歌最近关于 Android 对 Kotlin 的承诺的博客文章。可以说，Android 将 Kotlin 声明为受支持的语言有助于它的流行，谷歌宣称“前 1000 个 Android 应用程序中有近 60%包含 Kotlin 代码。”如果你是一个展望未来而不是过去的人，那么也许可以看看 Kotlin 的创造者 JetBrain 在[上的博客文章，看看 Kotlin 1.4 和以后的](https://blog.jetbrains.com/kotlin/2019/12/what-to-expect-in-kotlin-1-4-and-beyond/)会有什么。要点是这样的:Kotlin 1.4 预计在 2020 年春天发布，主要是性能和质量上的改进，而不是大的语言变化。当然，你宁愿看而不是读，你也可以看看 KotlinConf 的主题演讲。

[https://www.youtube.com/embed/0xKTM0A8gdI?feature=oembed](https://www.youtube.com/embed/0xKTM0A8gdI?feature=oembed)

视频

*   **JetBrains 的主要 IntelliJ 更新:** JetBrains 发布了其 IntelliJ IDEA Java IDE 的最终更新，SDTimes 称其为[的主要更新](https://adtmag.com/articles/2019/12/11/intellij-idea-update.aspx)，并指出该版本“更快的 IDE 启动，更好的 UI 响应，更少的 UI 和编辑器冻结，更少的内存消耗(特别是在 Gradle 项目上)，以及一系列错误修复。”据 JetBrains [博客文章](https://blog.jetbrains.com/idea/2019/11/intellij-idea-2019-3-better-performance-and-quality/)称，此次发布之前的开发周期见证了“超过 1600 个问题，在我们的问题跟踪器中总共收到了超过 3900 张投票。”
*   **现在是谷歌的代码之夏:**很明显，对于我们这些北半球的人来说，这不是夏天，但更确切地说，是谷歌[宣布其 2020 年](http://opensource.googleblog.com/2019/12/announcing-google-summer-of-code-2020.html)谷歌代码之夏的时候了，这将是第 16 个为学生开发人员和开源项目提供暑期实习的夏季。根据博客帖子，该项目在过去 15 年中为来自 109 个国家的 1.5 万名大学生提供了这一机会，今年的申请将于 3 月 25 日开放，项目将于 2020 年 1 月 14 日开始。所以，如果你知道一个初出茅庐的开发人员正在寻找实践经验，这可能是一条出路。

*   **Flutter 的目标是“环境计算”:**谷歌本周举办了 [Flutter Interact](https://developers.google.com/events/flutter-interact) ，发布了一些公告，也提出了环境计算的想法，写道 Flutter 是[第一个为环境计算设计的 UI 平台](https://developers.googleblog.com/2019/12/flutter-ui-ambient-computing.html)。你可能会问，“环境计算”到底是什么？“我们中的许多人每天都在多种设备之间转换，”他们写道，“在这个新兴的世界，人们的注意力开始从任何单个设备转移到一个环境，在这个环境中，您的服务和软件可以在您需要的任何地方使用。”这就是环境计算——一个设备无关紧要的世界。Flutter 是为了帮助构建 iOS 和 Android 应用程序而开发的，现在谷歌表示，它希望让 Flutter 成为“一个便携式工具包，无论你想在屏幕上绘制像素，都可以构建美丽的体验。”除了概念，谷歌还宣布了 Flutter 1.12，改进了对 macOS 的 Flutter 桌面支持，以及 web 支持，使“构建和使用 web 插件成为可能，使 Flutter 应用程序能够利用 Dart 组件的不断增长的生态系统，从 Firebase 到最新的 web APIs。”说到 Dart，[2.7 版本于本周](https://medium.com/dartlang/dart-2-7-a3710ec54e97)发布，增加了对扩展方法的支持，以及一个处理特殊字符字符串的新包。
*   **咖啡杯和阻止数据传输的 USB 加密狗:**最后，我们离消费主义、赠送礼物的假期只有几个星期了，StackOverflow 为你生活中的程序员准备了一份不错的清单[最后一刻的礼物想法](https://stackoverflow.blog/2019/12/12/last-minute-gift-ideas-for-the-programmer-in-your-life/)，我认为这可能是一个有用的链接，以防你陷入困境。也就是说，你是程序员，所以这可能只是你自己的购物清单。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>