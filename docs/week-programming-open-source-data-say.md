# 本周编程:你需要区块链吗？

> 原文：<https://thenewstack.io/week-programming-open-source-data-say/>

谷歌的 Chrome 开发峰会于本周在旧金山举行，正如你所料，这次峰会制造了一些新闻。如果你错过了，不要担心——YouTube 上有一个超过 20 场演讲的播放列表，本周我们将从上周最受关注的[谷歌](https://cloud.google.com/kubernetes-engine)新闻开始。

然而，除了谷歌之外，我们还将关注 Mozilla 和微软等公司的几项声明，Linux 基金会开源数据的有趣概念，等等。事不宜迟…

https://Twitter . com/johnnyvonrotten/status/923056427853213696

## 本周的谷歌开发者新闻

*   虽然 Android 8.1 要到 12 月才会面向消费者推出，但开发者现在就可以获得测试版，Techcrunch 的 Lucas Matney [写道](https://techcrunch.com/2017/10/25/google-introduces-neural-networks-api-in-developer-preview-of-android-8-1/)“这里最大的亮点是新的[神经网络 API](https://developer.android.com/ndk/guides/neuralnetworks/index.html) 。”根据谷歌的说法，该 API“旨在为移动设备上的机器学习运行计算密集型操作”，并且“旨在由机器学习库、框架和工具调用，让开发人员在设备外训练他们的模型，并将其部署在 Android 设备上。”
*   你知道那个小场景吗，在那里你会觉得自己是一个网络乐善好施者，“通过自动发送使用统计和崩溃报告来帮助谷歌 Chrome 变得更好”？嗯，这就是为什么——谷歌刚刚公布了 [Chrome 用户体验报告](https://developers.google.com/web/tools/chrome-user-experience-report)，Venturebeat 称旨在“帮助开发者改善他们网站的用户体验”该报告“提供了与其他网站的比较以及整个网络的宏观用户体验趋势”，并且“通过查询 [Google BigQuery](https://cloud.google.com/bigquery/) 上的数据集，开发人员可以看到真正的 Chrome 用户如何从各种硬件、软件和网络体验网络。”
*   根据 SDTimes 的一篇文章，本周还宣布了针对开发者的 Gmail 附加组件，该组件“使开发者能够将应用功能直接添加到 Gmail 中，并在网络上和 Android 上运行，很快将支持 iOS”。虽然今年早些时候在 T2 预览了这些插件，但谷歌已经在 T4 将预览版扩展到了所有开发者。
*   本周谷歌的最后一项官方声明为我们带来了 Android Studio 3.0。此次更新带来了许多变化，但谷歌指出了三个最大的变化，即“一套新的应用程序分析工具，用于快速诊断性能问题，支持 Kotlin 编程语言，以及一套新的工具和向导，用于加速您在最新 Android Oreo APIs 上的开发。”不过，从表面上看，这只是冰山一角。查看[视频教程](https://youtu.be/0n9sBgds-Hs)和[博客文章](https://android-developers.googleblog.com/2017/10/android-studio-30.html)以获得特性更新的完整列表。
*   最后，总结一下谷歌新闻，黑客新闻上的一个帖子提到了谷歌“Jupyter 式笔记本”的“软发布”。据一位[受雇于谷歌但不隶属于谷歌的评论者](https://news.ycombinator.com/item?id=15546350)称，虽然这些功能之前已经推出过，但“可能促使我们推出这些功能的是，这是一个我们很多人非常喜欢并经常使用的内部项目，我们认为如果你们也能使用它会很好。就是这样。”他们继续称之为“Jupyter 笔记本的谷歌文档”。

https://twitter.com/josephfcox/status/922792635974209536

## 本周的非谷歌编程新闻

*   首先，Mozilla 已经宣布它正在与 Firebug 说再见，Firefox Quantum 将在下个月结束。然而，不要担心，因为 Firebug 的所有功能现在都出现在当前的 [Firefox 开发工具](https://www.mozilla.org/en-US/firefox/developer/?utm_source=blog&utm_medium=hacks&utm_campaign=switch)中，Infoworld 的保罗·克里尔[看了一下公告](https://www.infoworld.com/article/3234827/web-development/mozilla-squashes-firebug-in-favor-of-native-firefox-debugger.html)，提供了一些如何获得最新版本的指导。
*   TechCrunch 的 Frederic Lardinois 向你介绍了微软的一款名为 Sonar 的新工具，它可以让你检查网站的性能和安全问题。由微软 Edge 浏览器背后的团队制作的开源工具“是一个林挺工具和网站扫描器”，它“既可以作为微软托管的网络服务，也可以作为命令行工具，供那些希望深入挖掘并将其集成到自己的工作流程和规则中的人使用。”正如 Lardinois 指出的，“如果这一切听起来很熟悉，那可能是因为微软[在今年早些时候向 JavaScript 基金会捐赠了 Sonar 项目](https://js.foundation/announcements/2017/06/22/sonar-js-foundation-welcomes-newest-project)。然而，现在你不需要成为一个命令行向导来让它为你工作。只要输入你网站的网址，你就可以开始了。
*   现在，对于你们这些 Python/R 极客和大数据类型的人来说，Anaconda 宣布[发布 Anaconda 发行版 5.0](https://www.anaconda.com/blog/developer-blog/announcing-the-release-of-anaconda-distribution-5-0/) ，该公司称其拥有超过 450 万活跃用户。该发行版包括“1，000 多个 Python 和 R 数据科学包”，最新版本增加了 100 多个包，以及其他新功能。
*   在半相关的新闻中， [SciPy 库](https://www.scipy.org/scipylib/download.html)在短暂的“0.1 版本问世 16 年后”宣布了[1 . 0 . 0 版本](https://github.com/scipy/scipy/releases/tag/v1.0.0)[崔维斯·奥列芬特](https://en.wikipedia.org/wiki/Travis_Oliphant)，SciPy(和 NumPy)的创始人之一，同时也是 Anaconda 的创始人之一，他在发布会上写道，1998 年关于一份电子邮件列表的讨论是如何让他“拖延我的博士学位，花大量时间编写 Python 的扩展模块，这些模块大多包装了经过实战测试的 Fortran 和 C 代码，以供 Python 用户使用。”
*   最后，你听说过开源软件，但你听说过开源数据吗？嗯， [Linux 基金会](https://azure.microsoft.com/en-us/?v=17.14)的目标是[通过宣布](https://www.cdla.io/)[社区数据许可协议](https://www.linuxfoundation.org/press-release/linux-foundation-debuts-community-data-license-agreement/)来改变这种，这是一个“开放数据协议家族”，它称之为“努力定义一个许可框架，以支持围绕监管和共享‘开放’数据建立的协作社区。”LinuxInsider [写道，公告](https://www.linuxinsider.com/story/Linux-Foundation-Launches-Open-Data-Licensing-Agreements-84903.html)“出现在机器学习和人工智能等技术能够以以前不可能的方式分析数据集的时候。”

## 本周的(非)实用编程

*   Java 开发人员 Steve Perkins 在他的博客上写道[使用 Java 9 模块化来发布零依赖性的本地应用](https://steveperkins.com/using-java-9-modularization-to-ship-zero-dependency-native-apps)。“Java 9 中最广为人知的新特性”，[项目 Jigsaw](http://openjdk.java.net/projects/jigsaw/) 隔离代码块和它们的依赖关系，并允许你的应用程序“声明它真正需要标准库的哪些部分，并可能排除所有其他部分”，最终摆脱对 Java 运行时环境的需要，并使 Java 与其他编译语言平起平坐……某种程度上。“公平地说，带有启动脚本的应用程序捆绑包并不像‘仅仅构建一个。Perkins 写道，但是“即使如此，Java 现在已经到了一个地方，你可以发布自包含的、零依赖性的应用程序，其大小可以与其他编译语言相媲美。”
*   说到各种容器化，Jaxenter 写道 [StackFoundation 的沙箱如何自动化你的日常 Docker 杂务](https://jaxenter.com/sandbox-automation-docker-containers-138348.html)，并允许你“设计一个自动化你经常做的任何开发任务的工作流”沙盒是免费的,“你可以把它提交给 Git，让你的工作流程直接在上面运行，不需要任何其他软件。连码头工人都不是！”查看该公司博客上的完整公告。
*   谷歌的 Kelsey Hightower [在推特上发布消息](https://twitter.com/kelseyhightower/status/923459020358389760)说，Go 社区正在解决一个默认的依赖管理系统，即 dep，根据其 Github 页面的说法，[该系统正被设计成适合 Go 工具链。](https://github.com/golang/dep/wiki/Roadmap)
*   最后，HackerNoon 上的一篇文章问[你是否患有学习者综合症](https://hackernoon.com/do-you-have-the-learners-syndrome-169c8158ec16)，作者将其描述为“受影响的人将不断寻求学习，但从未真正应用知识的行为。”他们解释说，在 web 开发的现代世界中，框架的数量近年来呈指数级增长。他们接着描述了现代程序员的一个难题，我相信你们很多人都经历过——期望成为一个所谓的全栈开发人员:“拥有这么多这些技术的最大问题是，要成为一个‘好’的 web 开发人员，你需要知道其中的大部分，包括后端技术。我认为这不公平。几年前，前端开发人员和后端开发人员之间的界限很清楚。今天，不再有真正的界限了。我们称之为“全栈”这听起来像是让一个人做两倍的工作，而不是真正专注于两个领域中的一个。"

[谷歌](https://cloud.google.com/kubernetes-engine)、 [Linux 基金会](https://www.linuxfoundation.org/)和[微软](https://azure.microsoft.com/en-us/?v=17.14)是新堆栈的赞助商。这篇文章的作者以前为 Continuum Analytics，现在的 Anaconda 做公关工作。

特征图片:[16 世纪的修枝工具](https://www.metmuseum.org/art/collection/search/203954?sortBy=Relevance&amp;ft=tools&amp;offset=0&amp;rpp=20&amp;pos=4)。纽约大都会艺术博物馆，公共领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>