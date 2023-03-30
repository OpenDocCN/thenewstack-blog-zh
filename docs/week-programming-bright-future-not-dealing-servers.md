# 本周编程:不与服务器打交道的光明未来

> 原文：<https://thenewstack.io/week-programming-bright-future-not-dealing-servers/>

本周是奥斯汀的 KubeCon，我花了几分钟时间在展厅停留，在那里我看到了几个精彩的例子，这些例子都是我不想真正处理的东西。也就是说，易于使用的基于 Web 的界面可以处理大部分细节——部署容器、安装语言、编译器和依赖项、启动服务器，以及快速获得在线和运行的代码——甚至没有一个错误代码兔子洞搜索或本地安装。这一切都伴随着容器带来的那些你已经听过很多的额外好处——可伸缩性、代码重用和共享、平台独立性、容易捆绑的依赖性，等等。

本周早些时候，我向一些程序员朋友提到了 KubeCon 和 [Kubernetes](/category/kubernetes/) ，他们的反应是“这太新了，没用”和“谁会用它？”我理解这一点，特别是对于为一家公司工作并有一个团队处理操作方面的事情的开发人员来说，但是我无法告诉你现在我已经多少次去学习新的编程知识并遇到相同的障碍——日复一日地处理安装期间迟钝的操作系统错误、缺少依赖项等等。通常，这些障碍是如此之大，以至于当我处理完它们时，我已经失去了继续我最初灵感的热情。

然而，这些天来，我开始看到曙光，它看起来很像 Kubernetes(和其他容器平台)以及构建在其上的各种系统——从 [OpenShift](https://www.openshift.com/) 到 [Glitch](https://glitch.com/) 到 [CodeAnywhere](https://codeanywhere.com/) 。我的意思是，对你们中的许多人来说，这已经是令人眼花缭乱的白天了，但对我来说，太阳看起来就要升起了——对于个人开发者来说，这整个云原生的事情看起来越来越好了。虽然我理解这种兴奋感大多来自企业、底线和效率方面，但这也让我对那些只想做东西而不想陷入其他复杂问题的人感到兴奋。

如果这些听起来很吸引人，你可能想看看我们对上周在 KubeCon 发生的一切的报道，我们将在未来几天继续更新。现在，让我们来看看在过去的一周里，在编程语言和一切与开发者相关的事物中还发生了什么。

## 本周的节目新闻中

*   Android Things Developer Preview 6:好吧，我们承认，上周在最后我们错过了它，但我们本周将它包括在内，因为它似乎值得一提——谷歌发布了其[Android Things Developer Preview 6](https://android-developers.googleblog.com/2017/11/android-things-developer-preview-6.html)。如果你不熟悉，Android Things 是谷歌为 Android 开发者提供的 IOT 平台，它提供了使用 [TensorFlow](https://www.tensorflow.org/) 或视频和音频处理的机载机器学习等功能。最新的更新在[发行说明](https://developer.android.com/things/preview/releases.html)中有详细介绍，但[的亮点](https://sdtimes.com/google-announces-android-things-developer-preview-6/)包括“一个新的物联网启动器，用于提供设备状态和更改设置的可见性，一个新的命令行闪烁工具，用于闪烁设备映像，以及一个外设命令行工具，用于访问外设 API，以及 Android Things 控制台更新。”
*   **说到 TensorFlow…:** Google 还[宣布了 TensorFlow Lite](http://developers.googleblog.com/2017/12/announcing-core-ml-support.html) 中的核心 ML 支持，这是一款面向移动和嵌入式设备的轻量级 ML 解决方案。CoreML 是一个面向 iOS 的机器学习框架，随着这一声明,“iOS 开发者可以利用 Core ML 的优势来部署 TensorFlow 模型。”
*   **Visual Studio 更新:**[最新的 Visual Studio 版本](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-mac-relnotes)据说将大型 C#和 VB 项目的下载时间减少了一半，并带来了一系列其他功能，从分步调试到帮助识别和管理数据库连接字符串和 web 服务密钥等秘密的功能。此外，新的 Visual Studio for Mac 推出了自动 iOS 应用程序签名、VTest 支持以及其他新功能。查看博客文章了解 Visual Studio 2017 版本 15.5 更新的冗长列表。
*   **PHP 7.2:** 对于那些不太讨厌 PHP 的人来说，你可能会有兴趣知道，该语言自 2015 年以来已经在[进行了首次更新，其中包括多项安全改进和几项新的增强的编程功能，据 InfoWorld 报道。另外，请看](https://www.infoworld.com/article/3239299/web-development/whats-new-in-php-72-better-security-code-handling.html)[官方公告](http://php.net/releases/7_2_0.php)。
*   **C++17 获得官方:**c++ 17 的最终标准已经[在 ISO.org](https://www.iso.org/standard/68564.html)上发布 [Fossbytes 注释](https://fossbytes.com/c17-final-standard-official/)“c++ 17 已经成为一个主要标准，就像 C++11 和 C++98 一样”。看起来[维基百科](https://en.wikipedia.org/wiki/C%2B%2B17)和这个 [Reddit 评论](https://www.reddit.com/r/programming/comments/7hnnc6/c17_standard_is_now_official/dqskkdb/)可能有这个新标准突出的最好的特性列表。
*   **Angular 5.1:** 对于小点版本来说，这似乎是一个重要的一周，Angular 正在通过 [Angular 5.1](https://blog.angular.io/angular-5-1-more-now-available-27d372f5eb4e) 加入这场游戏，它称之为“包含几个较小功能和错误修复的小版本”功能包括 Angular Material 和 CDK 稳定版本、CLI 中的服务人员支持、CLI 中改进的 universal 和 AppShell 支持、改进的 decorator 错误消息和 TypeScript 2.5 支持。
*   Django 2.0: 最后，为了完成 dot 的发布， [Django 2.0](https://docs.djangoproject.com/en/2.0/releases/2.0/) ，这个自封的“有期限的完美主义者的 web 框架”，已经用一些[新特性](https://docs.djangoproject.com/en/2.0/releases/2.0/#whats-new-2-0)，一些[废弃的特性](https://docs.djangoproject.com/en/2.0/releases/2.0/#removed-features-2-0)，和一些[向后不兼容的变化](https://docs.djangoproject.com/en/2.0/releases/2.0/#backwards-incompatible-2-0)在 web 的普通街道上运行。最值得注意的是，该项目放弃了对 Python 2 的支持，引入了简化的 URL 路由语法，改变了“url(r'^articles/(”。P <年>【0-9】{ 4 })/$ '，views.year_archive)、“到”路径(' articles/ < int:year > /'，views.year_archive)。现在，难道不喜欢尼斯吗？
*   **Atlassian 开发者路线图:** Atlassian 在 Trello 上发布了一份[的完整路线图，](https://trello.com/b/8XBuIeIu/atlassian-platform-for-developers-roadmap)[称](https://developer.atlassian.com/blog/2017/12/announcing-atlassian-platform-developers-roadmap/)展示了从过去版本到未来考虑的一切。该公司指出，新的路线图允许开发者对未来的功能进行投票，让他们在最重要的事情上有一些发言权。干净利落。
*   **赶上 Kotlin:** 我们上个月为 KotlinConf 进行了[全面的 Kotlin](https://thenewstack.io/week-programming-kotlin-eats-lunch/) ，现在该公司发布了全套 [KotlinConf 2017 会议录音和照片](https://blog.jetbrains.com/kotlin/2017/12/kotlinconf-2017-session-recordings-and-photos-are-here/)，所以如果你觉得你错过了什么，就去看看吧。除此之外，JetBrains 团队还在过去的一周[在 Reddit 上举办了一场 AMA](https://www.reddit.com/r/Kotlin/comments/7hoytl/kotlin_team_ama_ask_us_anything/) ，他们谈到了考虑将 Kotlin/Native 引入 IntelliJ IDEA 或 Android Studio 并在欧洲举办 KotlinConf 的计划。

## 本周在编程数字和思想中

*   **2018 据 GitHub 报道:**又到了一年中的这个时候——让预言的冲击开始吧！本周我们将从 GitHub 提供的 2018 年技术预测开始。我个人最喜欢的是“基础设施将有它的 Ruby on Rails 时刻”——我在简介中写的全部内容——“减轻开发人员的一些基础设施负担，他们将自由地专注于他们最关心的事情——构建、发展和改进他们的项目和产品。”其他预测，如数据很重要和安全性受到关注，似乎，嗯…过时了。
*   谁真正从这些学习中受益了？根据本周的一段对话，不是学生。这篇文章[对学习编程热潮](https://theconversation.com/taking-a-second-look-at-the-learn-to-code-craze-86597)进行了第二次审视，研究了“他们的主要受益者不一定是学生或工人，而是最初[推广这些项目](https://www.recode.net/2017/9/26/16364662/amazon-facebook-google-tech-300-million-donald-trump-ivanka-computer-science)的[有影响力的科技公司](https://blogs.microsoft.com/on-the-issues/2016/01/30/microsoft-supports-white-house-initiative-to-expand-access-to-computer-science/)这篇文章指出，这并不新鲜，可以追溯到 80 年代初的倡议，以及“里根时代的担忧，即美国人在‘新经济’中落后于全球竞争对手。”“他们争论的真正结果是什么？大公司的廉价劳动力。万岁。

谷歌[和微软](https://cloud.google.com/kubernetes-engine)[是新堆栈的赞助商。](https://azure.microsoft.com/en-us/?v=17.14)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>