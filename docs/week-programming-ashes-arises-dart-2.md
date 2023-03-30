# 本周节目:Dart 2 浴火重生

> 原文：<https://thenewstack.io/week-programming-ashes-arises-dart-2/>

Dart，Objective-C，CoffeeScript，Lua，Erlang。这个编程语言列表有什么共同点？

如果你的答案是“[2018 年最难学的五种编程语言](https://www.techrepublic.com/article/the-5-worst-programming-languages-to-learn-in-2018/)”，那么你会同意[共同导师](https://www.codementor.io/)发布的一项调查。根据该报告，这些语言“位居开发人员在 2018 年应该避免学习的编码语言之首，因为它们缺乏社区参与、就业和增长。”

即使这不是你的答案，我相信你读了之后会对自己说“是的，听起来很对。”但是，也许本周的一两个其他公告将改变列表中至少一种语言的情况——Dart。

我们已经看到了像谷歌这样的大公司支持一种语言可以为它的受欢迎程度做些什么。本周编程界的新闻有一大堆来自巴塞罗纳[移动世界大会](https://www.mobileworldcongress.com/)，而引领我们的是谷歌[宣布的 Flutter beta 1](https://developers.googleblog.com/2018/02/announcing-flutter-beta-1.html) 。Flutter 是谷歌新的移动用户界面框架，适用于 iOS 和 Android 的原生界面。

[https://www.youtube.com/embed/fq4N0hgOWzU?feature=oembed](https://www.youtube.com/embed/fq4N0hgOWzU?feature=oembed)

视频

你会问，这和 Dart 有什么关系？嗯，Flutter 本身是用 Dart 写的，所有基于 Flutter 的 app 也是。

与此同时，谷歌还宣布了一个 [Dart 2 重启](https://adtmag.com/articles/2018/02/23/dart-2.aspx)，据[应用开发者趋势](https://adtmag.com/Home.aspx)称，谷歌已经通过添加强类型和其他优化“改造”了 Dart。与此同时，Jaxenter 的开发人员表示，他们“一直在急切地等待这个版本中的所有重大变化”，并且“Dart 2 是这种语言的一次重大重启，使它更接近其创造者的初衷。”

因此，尽管 2017 年版的你——三个月前在某项调查中被问到时可能会说不要学习 Dart 的你——可能不会同意，但也许 2018 年版的你终究应该学习 Dart。

## 本周在(谷歌)编程

*   **让 AR 开始:**在谷歌本周发布的众多相关公告中，该公司还[发布了 ARCore 1.0 以及谷歌镜头的更新](https://www.blog.google/products/google-vr/announcing-arcore-10-and-new-updates-google-lens/)，这是谷歌护目镜的替代品。虽然谷歌镜头的更新并不真正属于编程的范畴，但 ARCore 是谷歌为 Android 开发的[增强现实 SDK](https://developers.google.com/ar/) ，让你可以构建类似的应用程序。随着这一版本的发布，ARCore 已经离开了测试版，现在可以投入生产，这意味着您的开发者现在可以将 AR 应用发布到 Google 的 Play Store。该公司表示，ARCore 用于 1 亿部安卓智能手机，包括 13 款，并将很快用于三星、华为、LGE、摩托罗拉、华硕、小米、HMD/诺基亚、中兴、索尼移动和 Vivo 的设备。1.0 版本还包括“改进的环境理解，使用户能够放置虚拟资产”，并在 Android Studio Beta 的[模拟器](https://developers.google.com/ar/develop/java/emulator)中得到支持，允许桌面虚拟环境测试。
*   **谷歌加入聊天机器人军备竞赛:**上周，Atlassian 宣布向开发者开放其 Stride API，现在谷歌也紧随其后，发布了其 [Hangouts 聊天平台和 API](http://gsuite-developers.googleblog.com/2018/02/develop-bot-integrations-with-hangouts.html) 。这一举动已经被期待了一段时间，因为谷歌已经谈论过 [Hangouts Chat，](https://chat.google.com/)它的“网络和移动企业协作的信息平台”然而，正如该公司在公告中指出的那样，“更有趣的是，从今天开始，你将能够使用 [Hangouts 聊天开发平台和 API](https://developers.google.com/hangouts/chat) 来制作自己的机器人集成。”尽管谷歌称 Apps Script 是“创建和部署机器人最简单的方式之一”，但它也将在[谷歌应用引擎](https://cloud.google.com/appengine)或你自己的[谷歌计算引擎](https://cloud.google.com/compute)实例或其他公共或私有云上支持 Python、Java、PHP、Go 等更多语言。
*   **不再有非 SDK 的 Android 界面:**提醒 Android 开发者，谷歌本周还宣布将致力于[通过减少非 SDK 界面的使用来提高稳定性](http://android-developers.googleblog.com/2018/02/improving-stability-by-reducing-usage.html)，因为使用这样的界面“会给用户带来崩溃的风险，也会给开发者带来紧急部署的风险”继 2016 年[对允许的 C/C++符号的限制之后，](https://android-developers.googleblog.com/2016/06/improving-stability-with-private-cc.html)Android 的下一个版本将扩展这些限制，以包括 SDK 的 Java 语言接口。关于这可能如何破坏现有应用程序的完整细节，请确保完整阅读该公告，但谷歌表示，“我们的规划和设计有一个明确的目标，即尊重我们的开发者社区，在解决应用程序稳定性的同时，尽可能减少变化。”简而言之，“如果你的应用目前依赖于非 SDK 接口，你应该开始计划向 SDK 替代品的迁移。”
*   **谷歌动作:**最后，Android 开发者终于可以用 16 种语言构建谷歌的“动作”(想想 Alexa 的“技能”)[，包括印地语、泰语、印尼语、丹麦语、挪威语、瑞典语和荷兰语。此外，actions 现在还可以使用 askForPlace，这是一个新的对话助手，它使用 Google Places API 来理解基于位置的用户对话中的查询。](http://developers.googleblog.com/2018/02/actions-on-google-now-supports-16.html)

## 本周在(GitHub)编程中

*   **Slack 的一款新 GitHub 应用:**如果你不是 IRC 的死忠，你可能会使用 Slack。Ang GitHub。这两家公司已经合作发布了新的 GitHub 和 Slack 应用程序。根据 GitHub 的[公告](https://github.com/blog/2506-slack-and-github-your-ultimate-productivity-pair)，新的应用程序“将 GitHub 活动带入您的空闲频道，以保持您的团队及时更新和高效”，允许您订阅 GitHub 资源库，并自动查看新的拉取请求、问题、代码审查和部署的更新。Slack/GitHub 集成是[开源的](https://github.com/integrations/slack)并且是用公开可用的 API 构建的。如果您想贡献代码、提交功能请求或错误报告，请访问 GitHub 知识库进行集成。
*   **GitHub Desktop 1.1 来了:**在 GitHub 本周发布的一系列较大或较小的公告中，我们有 [GitHub Desktop 1.1](https://github.com/blog/2508-github-desktop-1-1-is-now-available) ，它以[电子应用](https://electronjs.org/)的“全新发布”为特色。GitHub Desktop 1.1 的最新特性包括 diffs 中的语法突出显示、拉请求列表，该列表在当前存储库的分支旁边显示打开的拉请求、[共同创作的提交](https://github.com/blog/2496-commit-together-with-co-authors)，以及查看哪些拉请求通过了[提交状态](https://help.github.com/articles/about-statuses/)检查以及哪些需要更多工作的能力。有关完整的细节，请查看[发行说明](https://desktop.github.com/release-notes/)。
*   **告别弱加密标准:**我们在发布时提到过这一点，所以在此再次重申——[GitHub 将不再支持弱加密标准](https://github.com/blog/2507-weak-cryptographic-standards-removed)。它已经永久删除了对 github.com 和 api.github.com 的 TLSv1/TLSv1.1、diffie-hellman-group1-sha1、diffie-hellman-group14-sha1 的支持。
*   **PHP Pull Requests:** 最后，GitHub 增加了一个特性来[查看 PHP Pull Requests 中已更改的函数](https://github.com/blog/2512-quickly-review-changed-functions-in-your-php-pull-requests)，对文件查找器进行了更改，使您可以导航到 Pull Requests 中已更改的方法和函数。通过在文件查找器中搜索术语 function 或 PHP 文件中已更改函数的名称，您将获得结果的过滤视图，以帮助识别 pull 请求中最有影响的部分。如果这没有意义，请查看文档。

## 本周在(非附属)节目中

*   Ruby 的实时编译器:最新版本的 Ruby，被它的朋友亲切地称为 Ruby 2.6.0-preview1，已经在[发布](https://www.ruby-lang.org/en/news/2018/02/24/ruby-2-6-0-preview1-released/)，并引入了 JIT(实时)编译器的初步实现。JIT 编译器将通过将 C 代码打印到磁盘上并生成通用 C 编译器进程来生成本机代码，从而提高 Ruby 程序的执行性能。目前，这个版本主要是一个检查平台兼容性和确定安全风险的机会——大多数优化还没有实现。有关如何试用预览版的详细信息，请查看公告。
*   **2017 年围棋调查称:**我们在新堆栈这里有我们自己的方式，但[围棋 2017 年调查结果](https://blog.golang.org/survey2017-results)已经出来了，我相信你可能已经听说了。这是他们超快的要点:围棋很受欢迎，人们正在用它赚钱。而用围棋的人，嗯，他们也喜欢围棋。如需完整的细节，请自行查看结果，或查看我们的完整报道。
*   **爪哇 EE 已死——向雅加达 EE 致敬！**最后，本周最大的新闻(我们当然把最好的留到了最后) [Jakarta EE 是 Java EE 的新名字！](https://mmilinkov.wordpress.com/2018/02/26/and-the-name-is/)在不到 7，000 份回复中，近 65%的人毫不意外地选择了“Jakarta EE”而不是“企业简介”“企业简介”听起来像一种语言的名字吗？哦，还有，不要叫它 EE4J，这显然是绝对不允许的。

谷歌是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>