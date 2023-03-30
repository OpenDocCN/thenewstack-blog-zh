# 本周编程:隐私问题围绕着谷歌的 GoLang 代理调用

> 原文：<https://thenewstack.io/this-week-in-programming-privacy-issues-around-googles-golang-proxy-calls/>

go 1.13 已经在过去的一周里[在互联网](https://blog.golang.org/go1.13)的普通街道上发布，该团队强调了一些功能，如对数字文字、[错误包装](https://golang.org/doc/go1.13#error_wrapping)和 [TLS 1.3 默认开启](https://golang.org/doc/go1.13#tls_1_3)，并且很快注意到 Go 命令现在使用 Go 模块镜像和 Go 校验和数据库默认下载和验证模块。

虽然是一个相对较小的版本，但最后一点引起了 Go 开发者 Matt Farina 的注意，他写道“这可能会给专有软件带来问题。尤其是那些为谷歌开发有竞争力的解决方案，但却没有关注的公司。”

那么，到底发生了什么？

Farina 写道，Go 的最新版本是这样的“GOPROXY 默认为 https://proxy.golang.org，direct”意味着“go get 和 go build 等命令将试图从 Go Proxy 中获取模块，Go Proxy 由谷歌运营，受谷歌隐私政策管辖。”

https://Twitter . com/trans _ disaster/status/1163503264698130434

法里纳认为，从本质上讲，像谷歌这样的公司可以窥探一个项目引入了哪些包，并推断出一些关于潜在竞争对手等的有趣信息。

“想象一下人们可以用这种信息拼凑出的细节。您知道一个或一组 IP 正在拉动某一组模块。有些是公开的，你知道细节，有些是私人的，但是名字会泄露一些。从这个信息中可以推测出什么？尤其是如果他们有来自其他数据源的其他数据要与此合并。”

虽然 Go 提供了 GOPRIVATE 和 GONOPROXY 环境变量来解决这一问题，但 Farina 认为这一切都是默认的，他写道，“如果大多数使用 Go 的开发人员没有意识到这一变化正在发生，我不会感到惊讶，它会悄悄地对他们生效。”

现在，在 HackerNews 上围绕这个话题的[对话](https://news.ycombinator.com/item?id=20869324)很活跃，当然，[的一位评论者](https://news.ycombinator.com/item?id=20871731)似乎认为这不是问题，指出 Node.js、Perl、Python 和 Rust 都“有一个包的中央注册表，它可以像 go 代理一样收集元数据的详细程度。”

法里纳在评论中称，当然，区别在于谷歌。

“npm、Perl 以及其他提到的和 Go 之间是有区别的。Go 是拥有多样化产品和服务的谷歌。许多使用 Go 的人建立了对谷歌有竞争力的服务。哪家公司在使用 python 并构建一些东西来与 python 软件基金会竞争？还是给其他人的？这种差异值得考虑。如果 Go 是 Python 这样的软件基础的一部分，情况就会不同了。”

对于关心的人来说，这个问题并没有完全被 Go 团队忽视——围绕这个问题已经产生了一个[问题](https://github.com/golang/go/issues/33985),许多人认为默认代理是这里的真正问题。一如既往，一些人说，最好选择加入，而不是被要求选择退出。正如一位对此问题的评论者简洁地指出的那样[认为](https://github.com/golang/go/issues/33985#issuecomment-526811187)，“如果信息不是太多而是导入路径，那么默认情况下不应该是‘将信息暴露给第三方公司/公共代理’事件。”

## 本周的节目中

*   **迎来黑暗模式——又名 Android 10:** 没有什么比黑暗主题更能尖叫“开发者为开发者打造的功能”了，amirite？本周，Android 10 在[发布，它以黑暗主题为特色，对你的 Android 开发者来说还有更多。除了黑暗主题支持，Android 10 还为开发者提供了可折叠支持、](http://android-developers.googleblog.com/2019/09/welcoming-android-10.html)[可选的](https://developer.android.com/guide/topics/media/playback-capture#allowing_playback_capture)直播字幕功能、5G 支持、提供“智能回复”的能力以及手势导航。当然，这只是表面现象——谷歌提供了一份关于 Android 10 需要了解的 10 件事的清单，这份清单更深入地探讨了最新 Android 操作系统的隐私和安全特性。说到这里，谷歌已经向 [Android 开源项目(AOSP)](https://source.android.com/) 发布了 Android 10 源代码，并与更大的生态系统分享了一些功劳，指出“超过 20 万人在 26 种不同的测试设备上测试了早期版本，报告了 2 万个独特的问题。”

*   **将 Perl 从 Perl 6 中取出:**几年前，我们看了一下[重命名 Perl 6 的想法，以避免它最终不受欢迎](https://thenewstack.io/week-programming-renaming-perl-save-terminal-unpopularity/)。这个想法已经重生了，正如 Perl 开发人员 Ovid 在这篇博客中所总结的，他问道:[Perl 6 会被重命名吗？](http://blogs.perl.org/users/ovid/2019/08/is-perl-6-being-renamed.html)这场争论因 Github 问题[而再起波澜](https://github.com/perl6/problem-solving/issues/81)“Perl 6”名称中的“Perl”令人困惑和愤怒，它是由核心 Perl 6 开发者之一 Elizabeth (Liz) Mattijsen 创建的。Ovid 总结了“过于简单的背景故事:Perl 6 社区似乎分成了两派，一派认为 Perl 6 是 Perl 5 的姐妹语言，另一派认为 Perl 6 是 Perl 5 的继承者。与此同时，Perl 5 社区分为‘操你妈的耶’和‘操你妈的’。”然而，最近的这个请求，似乎在这个重命名努力的背后有一些魅力，我们可能会看到 Perl 6 完全放弃了 Perl 这个名字，以便最终将自己与一种主要在名称上而不是在功能上与之相关的语言拉开距离。或者，正如这篇文章再次总结的那样:“两种编程语言差别很大，源代码不兼容，只是版本号不同，这有损于 Perl 5 和 Perl 6 在世界上的形象。”

*   为新手和专业人士在边缘运行人工智能:如果你正试图在边缘实现人工智能，看看[新推出的](https://azure.microsoft.com/blog/microsoft-and-qualcomm-accelerate-ai-with-vision-ai-developer-kit/)[视觉人工智能开发工具包](https://aka.ms/visionaidevkit)，去年由微软和高通首次发布。该套件包括一个摄像头和开发边缘解决方案所需的软件，如“边缘设备上的本地实时图像处理，以及 Azure 上的模型培训和管理。”根据套件的描述，这款相机与 Azure IoT Hub 配合使用，并配有一个默认的视觉人工智能模块，可以识别 183 种不同的物体。根据这篇博文，该工具包实际上是为所有级别设计的，提供了“三个可供开发人员入门的选项，包括不使用定制视觉的代码、 [Azure 认知服务](https://azure.microsoft.com/en-us/services/cognitive-services/custom-vision-service/)、带有 [Azure 机器学习](https://azure.microsoft.com/en-us/services/machine-learning-service/)的定制模型，以及由 [Visual Studio 代码](https://code.visualstudio.com/)提供的完全集成的开发环境。”

*   还记得 Quarkus 吗，我们之前写过的 Kubernetes-native Java？InfoWorld 报道了 Quarkus 是如何准备测试的，“在未来几个月可能作为产品向开发者开放之前。”根据这篇文章，目前的路线图已经在今年完成测试，明年年初全面上市，开发者工具也在路上，开发者预览版也将在明年年初推出。

来自 Pixabay 的 Miranda Bleijenberg 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>