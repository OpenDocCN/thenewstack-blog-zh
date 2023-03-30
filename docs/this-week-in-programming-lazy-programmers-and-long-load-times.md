# 本周编程:懒惰的程序员和长加载时间

> 原文：<https://thenewstack.io/this-week-in-programming-lazy-programmers-and-long-load-times/>

上周，我重新点燃了我最长的、正在进行的自由网页设计工作之一——为我父亲的企业处理任何突发奇想的代码。至少从我的 LinkedIn 上看，我从 2001 年就开始这么做了，那时拨号上网还统治着刚刚起步的网络。这一次，我们把复杂的 CNC 机械图纸转化成——是的，我承认——图像地图。基本上，每幅画都有大约 90 多个部分，我能想到的将它们连接到单个部分的最简单快捷的方法就是回到这个公认的过时技术。在这个过程中，我们不得不扫描这些来自 20 世纪 80 年代机器手册的旧图纸，这一段对话在我的脑海中留下了深刻的印象:

我父亲:“好的，这是扫描结果。是不是太大了？”他一边问，一边给我发送了近兆字节大小的 pdf 文件。

我:“不，没关系。不管怎样，它们可能有高速连接，”我开玩笑地说，我把这些图像转换成 JPEG 格式，完全不在乎大小——把滑块推到 90°，并在那里放一些 JavaScript 代码，至少尝试让这些图像地图有反应。

这与 18 年前我开始从事网页设计时的做法截然相反，当时我知道任何页面的加载时间都不应超过三秒，要仔细计算每一千字节，并在每一页上运行代码优化器。但是事情变了，对吧？我是标题所指的懒惰的程序员。

然后，本周我偶然看到两篇文章，它们真正突出了这整个交流，以及我对速度和效率的自由放任态度，现在我把它们作为思考的食粮呈现给你们。

首先，一篇来自前端开发者和设计师尼克·赫尔的博客文章，他称之为“[扯淡网站”。请注意，这是典型的胡说八道。在这篇文章中，他谈到在 1998 年的时候，所有的东西都加载得如此之慢，当他使用 56k 调制解调器时，这看起来很自然。当然，然而，随着时间的推移和互联网连接以指数速度增长，一切都会加载得更快，对不对？不对。](https://pxlnv.com/blog/bullshit-web/)

“那么，随着互联网连接速度超过我在 20 世纪 90 年代末的想象，现在的比分是多少？”赫尔问道。《山巅之城》的故事花了 9 秒多才载入；在政治，十七秒；在 CNN，超过三十秒。这是狗屁网站。[……]美国的平均互联网连接速度大约是十年前的六倍，但我们没有让浏览同类网站更快，而是用更多的*内容*占用了额外的带宽

其余的内容值得一读，但出于我们的目的，我们将继续下一篇文章，它着眼于一个类似的高度相关的主题——[2018 年 JavaScript 的成本](https://medium.com/@addyosmani/the-cost-of-javascript-in-2018-7d8950fbb5d4)。在这篇文章中，[谷歌人 Addy Osmani](https://medium.com/@addyosmani) 写道,“构建[交互式](https://philipwalton.com/articles/why-web-developers-need-to-care-about-interactivity/)网站需要向你的用户发送 JavaScript。通常，太多了。”他马上提供了一张图表，显示虽然最新的 iPhone 8 处理 CNN 的速度可能足够快，但普通手机处理同一页面的时间要多 9 秒。与此同时，一部更便宜的手机加载时间超过 30 秒。你明白要点了。Osmani 然后用他精彩详细的文章的剩余部分来检查问题和探索解决方案，但是我们会让你去读，因为我们自己也在继续。为了简洁起见，以下是他关于同一主题的讲话:

[https://www.youtube.com/embed/63I-mEuSvGA?feature=oembed](https://www.youtube.com/embed/63I-mEuSvGA?feature=oembed)

视频

## 本周的节目中

*   **看看 F# 4.5 上的开源大炮:**没错，微软正在通过[F # 4.5](https://blogs.msdn.microsoft.com/dotnet/2018/07/26/announcing-f-4-5-preview/)的最终预览版来宣传其开源证书，它称之为“非常非常稳定”，实际上，只是名义上的预览版。正如[应用开发者时报写的](https://adtmag.com/articles/2018/08/01/fsharp-preview.aspx)的版本，“微软拥抱开源并转向互操作性和协作，这一趋势在 F#的新预览版中得到了体现。”微软的声明将大量时间集中在 F# 4.5 的开发方式上，这是“完全通过开放的 RFC(征求意见)过程，社区做出了重大贡献，特别是在功能讨论和演示用例方面。”至于特性本身，包括对语义版本化的[改变](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1004-versioning-plan.md)，以及“与中新的 [Span 特性一致的特性集。NET Core 2.1](https://msdn.microsoft.com/en-us/magazine/mt814808.aspx/) …允许以非常严格的方式安全使用面向性能的结构。”
*   **TypeScript 3.0 增加了未知类型和项目引用:**在其他微软语言新闻中，TypeScript 3.0 也在本周[发布](https://blogs.msdn.microsoft.com/typescript/2018/07/30/announcing-typescript-3-0/)，它继 2.8 的条件类型和 2.9 的通用键之后，更容易用未知类型导入类型，以及其他功能。JAXEnter 写道,[未知类型](https://jaxenter.com/typescript-version-3-0-147394.html)做了任何类型都做不到的事情。如果你想描述最无能的类型，现在你可以了！”更具体地说，“和任何一样，任何值都可以赋给未知数；然而，与任何类型不同的是，在没有类型断言的情况下，unknown 几乎不能赋给任何其他类型。您也不能访问未知的任何属性，也不能调用/构造它们。”除了未知类型，3.0 还[引入了项目引用](https://sdtimes.com/msft/microsoft-introduces-project-references-in-typescript-3-0/)，“该版本最大的改进之一，通过允许 tsconfig.json 文件相互引用，使开发人员更容易共享多个 TypeScript 项目之间的依赖关系。”

*   **Atlassian Cloud For Gmail Add-On 带来 BitBucket 集成:**对于你的 BitBucket 用户来说，上周在 Google Next 发布的[Atlassian Cloud For Gmail Add-On](https://www.atlassian.com/blog/add-ons/announcing-the-new-atlassian-cloud-for-gmail)看起来像是一个必须拥有的东西，因为它允许你[从收件箱中做更多事情](https://blog.bitbucket.org/2018/07/30/inbox-atlassian-cloud-gmail/)。根据公告，该插件使您能够“在不离开收件箱的情况下采取行动，并获得关于您的拉式请求、问题和管道构建的上下文信息。”具体来说，您可以阅读和发布关于位桶问题和拉取请求的评论，合并拉取请求，重新运行管道构建，甚至可以查看谁批准了或没有批准拉取请求。此外，Atlassian 应用程序还集成了吉拉。
*   **你的 IntelliJ IDEA 中的谷歌云服务:**另一个谷歌云公告，尽管这一个似乎是在大会之后发布的——你现在可以[直接从 IntelliJ IDEA](http://cloudplatform.googleblog.com/2018/07/access-google-cloud-services-right-from-intellij-idea.html) 访问谷歌云服务。IntelliJ 插件的[云工具](https://cloud.google.com/intellij/)允许您发现和使用 API，并在本地测试它们，就在 ide 内部。该插件还允许您启用 Google Cloud APIs，为本地开发创建服务帐户，将相应的 Java 客户端库添加到您的构建中，以及检测和修复潜在的错误配置。该插件还包括对 Google App Engine、Stackdriver 调试器、云存储库和云存储的支持。顺便说一句，如果你还没看过，几周前另一个关于 IntelliJ IDEA 及其与谷歌关系的伟大故事在这里出现，问“[JetBrains 的 IntelliJ 是真正的 Android 垄断吗？](https://thenewstack.io/is-the-jetbrains-intellij-the-real-android-monopoly/)“值得一读。

*   **脸书应用编程接口打破了所有的东西:**你有没有注意到，也许所有的脸书应用程序都不再工作了？或许最明显的变化是 [Twitter 不再能交叉发布到脸书](https://www.programmableweb.com/news/facebook-breaks-twitter-feature-changing-its-api/2018/08/01)？嗯，那是因为脸书[更新了应用审查流程](https://newsroom.fb.com/news/2018/07/update-on-app-review/)，8 月 1 日是最后期限。其要点是，所有使用 Facebook 平台 API 的应用程序都需要经过“更全面的审查，以更好地保护人们的脸书信息”(再次感谢剑桥分析公司)，并且“因此，(脸书)切断了数十万未提交我们应用程序审查流程的不活跃应用程序的 API 访问权限。”
*   GitHub Desktop 1.3 增加了一些方便的通知: GitHub Desktop 1.3 于[本周](https://blog.github.com/2018-07-30-github-desktop-1.3/)发布，它的主要特点是当你的分支偏离你的库的默认分支时，它会通知你，这听起来相当有用。除此之外，这个版本还向您显示了“哪些存储库有最近的活动、未提交的变更和未推送的变更，而不必点击每一个。”

谷歌和微软是新堆栈的赞助商。

特征图像[通过](https://nos.twnsnd.co/)新老库存。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>