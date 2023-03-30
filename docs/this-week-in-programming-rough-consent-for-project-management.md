# 本周节目:项目管理的“粗略同意”

> 原文：<https://thenewstack.io/this-week-in-programming-rough-consent-for-project-management/>

在过去的几年里，我们已经在本专栏中多次讨论了新编程语言开发过程中出现的问题。例如，随着时间的推移，在 Go 中继续使用模块的决定上出现了一点混乱。同样，我们研究了 Rust 团队经历的一些[斗争，这些斗争导致 Rust 团队的](/this-week-in-programming-a-peek-into-the-rust-rfc-sausage-factory/)[现前](https://blog.rust-lang.org/2019/02/22/Core-team-changes.html)核心成员之一 [Aaron Turon](https://github.com/aturon) 写了一系列关于决策和前进中使用的方法的博客文章。在他的帖子中，Turon 注意到“不信任的迹象越来越多，‘我们对他们’的思维，人们觉得他们必须大声喊叫才能被倾听”，并就如何修复 Rust RFC 流程提出了几个建议。

本周，又是一个 Twitter 帖子让我思考了一下项目治理模型，以及当人们聚在一起试图创造一些东西时所面临的困难。我相信你很清楚，这并不容易，但是 Node.js 社区的核心成员 James Snell 提供了一个简单的建议:

斯内尔继续解释说，通过要求反对而不是同意，“提出反对的人不能只是说不就走了，”相反，他们必须实际捍卫自己的观点。

上周，我们看到了一种编程语言[的死亡](https://thenewstack.io/this-week-in-programming-requiem-for-a-programming-language/)，这种编程语言可能提供了唯一的另一种选择，让每个人都同意——或者更确切地说，不是不同意——这种选择就是，简单地不要有一个大团队，你不会以一种饱受争议和功能蔓延困扰的语言而告终。

当然，斯内尔同意，没有什么过程是完美的，但他认为这种模式(其中一个回复等同于“[粗略同意](https://tools.ietf.org/html/rfc7282)”，另一个等同于“[懒惰共识](https://community.apache.org/committers/lazyConsensus.html)”)是一种平等对待所有声音的前进方式，只要他们愿意捍卫自己的想法。

## 本周的节目中

*   Git 在 2.21 版本中增加了人类可读时间:[Git 的 2.21 版本](https://github.blog/2019-02-24-highlights-from-git-2-21/)是 GitHub 和 Bitbucket 等流行工具背后的免费开源版本控制系统，于本周发布，有 60 多个贡献者提供了功能和错误修复。新特性中最突出的特点是使用–date = human 命令添加了人类可读的日期。正如公告中所指出的那样，有时您不需要精确到秒的时间戳，例如“星期二 Feb 12 09:00:33 2019 -0800 ”,并且想要更具可读性和相关性的内容。–date = human 命令提供了比–date = relative 更具体的内容，并且根据上下文的不同而不同。此外，新功能还提供了自动切换功能，具体取决于输出写入的位置。除了日期之外，新的 Git 还包括检测不区分大小写的路径冲突的能力，并提供了一些性能改进和其他功能。如需完整的细节，一如既往，请查看[发布说明](https://github.com/git/git/blob/v2.21.0/Documentation/RelNotes/2.21.0.txt)。
*   **Visual Studio 2019 RC&GitHub 更新:**本周有几个来自 Visual Studio 世界的花絮——首先， [Visual Studio 2019 发布候选](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-release-candidate-rc-now-available/)现在可以在 4 月 2 日的[虚拟发布活动](https://launch.visualstudio.com/)上正式发布之前[下载。其次，GitHub](https://visualstudio.microsoft.com/downloads/)[详细介绍了最新发布的](https://github.blog/2019-02-26-get-even-more-detail-in-pull-requests/) [GitHub for Visual Studio](https://visualstudio.github.com/) 的新特性，其中包括“查看对话的能力，拉请求列表中的新状态圈，以及围绕打开和克隆存储库的改进体验。”

*   **Go 1.12 准备模块支持:**没错， [Go 1.12 发布](https://blog.golang.org/go1.12)并可供[下载](https://golang.org/dl/)，这一最新版本包括[选择加入支持 TLS 1.3](https://golang.org/doc/go1.12#tls_1_3) 、[改进模块支持](https://golang.org/doc/go1.12#modules)(准备[成为 Go 1.13](https://blog.golang.org/modules2019) 中的默认)、支持 windows/arm、[改进 macOS & iOS 前向兼容性。](https://golang.org/doc/go1.12#darwin)“根据[发布说明](https://golang.org/doc/go1.12)，这个最新版本(在 Go 1.11 之后 6 个月发布)主要涉及“工具链、运行时和库的实现”的变化，应该是完全向后兼容的。
*   **Flutter 1.2 和 Dart 2.2:** 说到谷歌支持的语言之类的东西，该公司本周在世界移动通信大会上发布了 [Flutter 1.2，也就是一年前首次推出 Flutter 测试版的地方。最新版本的标准努力提高了稳定性和性能，但也致力于“改善现有小部件的视觉效果和功能”，并为开发人员构建 Flutter 应用程序添加了新的基于网络的工具。ProgrammableWeb 写道](https://developers.googleblog.com/2019/02/launching-flutter-12-at-mobile-world.html) [Flutter 1.2 专注于改进](https://www.programmableweb.com/news/flutter-12-focuses-refinements/2019/02/26-0)，并指出“这个搜索巨头如此快速地迭代 Flutter 是个好兆头。”随着声明的发布，谷歌表示开发者可以期待大约每月一次的 1.x 更新(包括测试版),并为那些有兴趣了解 Flutter 最新消息的人提供了一个专门的 YouTube 频道。在撰写公告时，Techcrunch 重点关注了 Flutter 的[基于网络的开发工具](https://techcrunch.com/2019/02/26/googles-flutter-toolkit-will-get-web-based-dev-tooling/)，其中他们写道“值得注意的是，谷歌已经在 Android Studio 中内置了 Flutter 支持，并为微软越来越受欢迎的 Visual Studio 代码添加了工具。现在，它还在开发新的基于网络的编程工具 Dart DevTools。它们在本地运行，包括一个小部件检查器、一个时间线视图、一个源代码级调试器和一个日志视图。”最后，Google 还宣布“Flutter 1.2 包括 Dart 2.2 SDK，这是一个更新，它为编译的代码带来了显著的性能改进，并为初始化集合提供了新的语言支持。”
*   **谷歌云物联网设备 SDK:** 在 Google-y 新闻中，ProgrammableWeb 为我们带来了[谷歌云物联网设备 SDK](https://www.programmableweb.com/news/google-introduces-cloud-to-iot-device-sdk/brief/2019/02/26) 的新闻，开发人员可以使用它“将微控制器类设备直接连接到谷歌云物联网平台”，许多物联网相关平台都支持开箱即用。谷歌在其[博客公告](https://cloud.google.com/blog/products/iot-devices/introducing-cloud-iot-device-sdk-a-new-way-for-embedded-iot-devices-to-connect-to-google-cloud-iot-core)中提供了全部细节，并指出 SDK 可在其 [GitHub 资源库](https://github.com/GoogleCloudPlatform/iot-device-sdk-embedded-c)中获得。
*   **脸书开发者，启动你的引擎:**脸书刚刚宣布 [F8 2019 注册现已开放](https://code.fb.com/ai-research/f8-2019/)，会议将于 2019 年 4 月 30 日和 5 月 1 日在加利福尼亚州圣何塞举行。时间表的[预览可用，](http://www.f8.com/schedule)[流媒体](http://www.f8.com/watch)也可用于那些不能按时到达的人。在其他脸书开发者的新闻中，该公司已经发布了 React 16.8 的钩子，它称之为“一种强大的编写组件和在组件之间重用代码的新方法”该公司写道，钩子是完全向后兼容的，可以与你现有的代码一起工作，并且不会遭受 mixins 的缺点。更多细节，请查看 GitHub 上的[文档](https://reactjs.org/docs/hooks-intro.html)或[挂钩。](https://github.com/facebook/react/)
*   **开源的持续发展:**最后，如果你最近一直关注的话，开源世界中有一些[的争议](https://thenewstack.io/this-week-in-programming-open-source-or-merely-ajar/)关于像亚马逊这样的大玩家接受开源项目并以他们认为不公平的方式与小玩家竞争。嗯，这并没有平息任何事情，ZDNet 报道了 [MariaDB 首席执行官指责大型云供应商“露天开采”开源](https://www.zdnet.com/article/mariadb-ceo-accuses-large-cloud-vendors-of-strip-mining-open-source/)的故事。请继续阅读。

专题图片:“[韦尔切莱战役](https://www.metmuseum.org/art/collection/search/437794?searchField=All&amp;sortBy=Relevance&amp;ft=Battle&amp;offset=0&amp;rpp=80&amp;pos=3)”(细节)，乔凡尼·巴蒂斯塔·提埃坡罗，1725–29；纽约大都会艺术博物馆。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>