# 本周编程:责怪语言还是程序员？

> 原文：<https://thenewstack.io/this-week-in-programming-blame-the-language-or-the-programmer/>

你知道那些看起来没完没了的 Windows 更新吗——那些你只想关掉电脑回家，就像“不，等等，我有 73 个安全更新要先做，不要走”的更新？根据微软安全工程师 Matt Miller 在本月早些时候的一次安全会议上的发言，大多数漏洞都是内存安全问题，这一点已经在 Twitter 上引起了轩然大波，一些人认为 C 作为一种编程语言有多糟糕……还有一些人认为开发人员应该受到指责。

如果你们感兴趣，这里有一段米勒演讲的视频，从他阐述这一点开始:

[https://www.youtube.com/embed/PjbGojjnBZQ?start=835&feature=oembed](https://www.youtube.com/embed/PjbGojjnBZQ?start=835&feature=oembed)

视频

《T4》在 ZDNet 上的一篇文章首次引起了人们对这一点的关注，从那以后它就一直在流传。该文章解释说，“每年通过安全更新解决的微软产品中大约 70%的漏洞是内存安全问题”，并且“当软件以超出其分配的大小和内存地址的方式意外或有意地访问系统内存时，内存安全错误就会发生。”

文章还指出，“这一高百分比的原因是因为 Windows 主要是用 C 和 C++编写的，这两种‘内存不安全’的编程语言允许开发人员对代码执行的内存地址进行细粒度控制。”

问题很快变成了这是编程语言的错还是程序员的错？

特别是， [Matthew Garrett](https://en.wikipedia.org/wiki/Matthew_Garrett) ，Linux、GNOME、Debian、Ubuntu 和 Red Hat 的主要贡献者，一直在 Twitter 上带头指责 C，并拿起武器反对 C 确实是一种很棒的语言，应该受到指责的是编码人员。

现在 Twitter 帖子值得一看，但是在这里以有意义的方式链接有点困难。相反，让我们看看开发人员 Sean Griffin 的博客文章，标题是“不，问题不在于糟糕的编码人员”。

“让我明确一点，我不同意那种认为程序员本身就可以变得完美的说法。但是，断言我们只需要更好的 C 程序员远远不止这些。这不仅仅是一个人们是否能发现他们编写的代码中的问题的问题。它还期望人们能够在他们交互的任何代码中重新考虑每个不变量的上下文(即使是间接的)。格里芬写道:“它设定了一个预期，即在提出时间代码和合并时间代码之间，不会发生任何变化。”。“这不是对一个人的合理期望。我们需要有护栏的语言来防止这种错误。没有人会争辩说，如果路上有更好的司机，我们就不需要安全带。我们也不应该就软件开发人员和编程语言进行这样的争论。”

那么，亲爱的读者，你怎么看？是时候放弃这些“内存不安全”的语言了吗？还是怪你这个开发商不够细心？

## 本周的节目中

*   这些是谁的东西？根据谷歌的说法，Android 的东西[不再是你的东西](http://android-developers.googleblog.com/2019/02/an-update-on-android-things.html)——也就是说，除非你是它的一个制造智能扬声器或智能显示器的 OEM 合作伙伴。根据公告，“目前将不会通过公共开发者平台提供对基于恩智浦、高通和联发科硬件的生产系统模块(som)的支持。”正如 [Ars Technica](https://arstechnica.com/gadgets/2019/02/android-things-is-no-longer-for-things-focuses-on-smart-speakers-and-displays/) 指出的，“谷歌的精简版 Android 因其专注于‘物联网’(IoT)而得名，现在不再专注于物联网，”称这一举动“非常奇怪”，因为该操作系统“刚刚经历了漫长的初始开发周期[……]，9 个月前才推出 1.0 版本”那么为什么要杀安卓的东西呢？Ars Technica 认为，也许“Android 的东西对于更小的物联网设备来说太重了。”
*   **用谷歌的 Jib 将 Java 容器化:**本周谷歌开发者头条的下一条新闻是，[宣布](https://cloud.google.com/blog/products/application-development/jib-1-0-0-is-ga-building-java-docker-images-has-never-been-easier)其 [Java 容器化工具“Jib”](https://adtmag.com/Articles/2019/02/13/java-jib.aspx?m=1&p=1)正式上市，应用开发者时报将会看到。根据这篇文章，用于容器化 Java 应用程序的开源工具“是一个快速而简单的容器映像构建器，它整合了将应用程序打包到容器映像中所涉及的所有步骤，并允许开发人员使用熟悉的 Java 工具来构建容器。”该工具“通过将 Java 应用程序分成多个层以进行更精细的增量构建，有效地规避了安装 Docker、运行 Docker 守护程序和/或编写 Docker 文件的需求。”对于那些感兴趣的人，Google 提供了“[示例](https://cloudtoolsforjava.page.link/Xwwv)和 Codelabs，用于[将 Spring Boot 应用程序部署到 Kubernetes](https://codelabs.developers.google.com/codelabs/cloud-springboot-kubernetes) 或[将 Micronaut 应用程序部署到 Kubernetes](https://codelabs.developers.google.com/codelabs/cloud-micronaut-kubernetes) 。”
*   **用 Google Docs API 自动完成任务:**谷歌本周最后一次发布，[谷歌文档在去年 4 月进入开发者预览版后，现在有了一个 API](https://techcrunch.com/2019/02/11/google-docs-gets-an-api-for-task-automation/) 。Techcrunch 写道，“[Google Docs 的新 API](https://developers.google.com/docs/api/)将允许开发者自动化许多用户通常手动完成的任务。”该 API 将允许开发人员“在事件发生后设置处理文档的过程[来更新它们，并且该 API 还具有插入、删除、移动](https://developers.google.com/docs/api/reference/rest/v1/documents/batchUpdate)、[合并](https://developers.google.com/docs/api/how-tos/merge)和[格式化](https://developers.google.com/docs/api/how-tos/format-text)文本、插入内嵌图像和[处理列表](https://developers.google.com/docs/api/how-tos/lists)等功能。” [ProgrammableWeb](https://www.programmableweb.com/news/google-opens-api-google-docs/brief/2019/02/12) 也看了新闻，提供了一个全面的摘要，指出谷歌已经发布了一个[快速入门指南](https://developers.google.com/docs/api/quickstart/js)，并提供了一个向导来在谷歌开发者控制台中创建或选择一个项目，称这个过程“简单明了”

[https://www.youtube.com/embed/jeU-tWKeb6g?feature=oembed](https://www.youtube.com/embed/jeU-tWKeb6g?feature=oembed)

视频

*   **Python 3.8 先睹为快& PyPy:** 转到 Python，JAXEnter 在 Python 3.8 的早期[开发者预览版上提供了一个](https://www.python.org/downloads/release/python-380a1/)[第一次从巅峰看 Python 3.8](https://jaxenter.com/first-look-at-python-3-8-155422.html) 。虽然 3.8 仍在开发中，但文章指出“我们知道的几个主要特性将在下一版本中出现”，即赋值表达式和 typed_ast 将合并回 CPython。本周 Python 的第二篇文章，InfoWorld 写道 [PyPy 7 加速了 Python 2.7、Python 3.5 和 Python 3.6](https://www.infoworld.com/article/3339542/python/pypy-7-speeds-pythons-27-35-and-36-alike.html#tk.rss_applicationdevelopment)。Python 运行时“使用即时编译来实现对现有 CPython 发行版的重大性能改进，现在在支持 Python 2.7、Python 3.5 和 Python 3.6 的 7.0 版本中可用。”官方 PyPy 状态博客[上的帖子提供了发布的全部细节。](https://morepypy.blogspot.com/2019/02/pypy-v700-triple-release-of-27-35-and.html)

*   **用草案拉取请求试水:**如果你感到胆怯，GitHub 最近宣布的[草案拉取请求](https://github.blog/2019-02-14-introducing-draft-pull-requests/)可能会很受欢迎，因为新功能将让开发者“在你的出色想法或代码准备就绪时，立即提出拉取请求，与你的合作者展开对话。”该特性消除了拉请求的非黑即白的本质，提供了一点中间性，使其更具协作性。GitHub 写道:“有了草稿拉取请求，你可以清楚地标记你正在编写的作品。”这个新特性还附带了一个[草稿拉取请求 API](https://developer.github.com/changes/2019-02-14-draft-pull-requests/) 。
*   **关于类型的一个例子:**整个引言部分，我们谈到了内存安全等等。这似乎奇怪地让人想起了关于数据类型的辩论，所以我忍不住以这个 Reddit 帖子结束，讨论 Airbnb 的 38%的错误是如何通过使用类型来防止的。也许这也是开发商的错。(我开玩笑！)

https://twitter.com/CarlyRM/status/1095876750763061248

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>