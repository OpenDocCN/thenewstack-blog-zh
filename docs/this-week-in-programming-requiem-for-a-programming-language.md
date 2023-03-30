# 本周编程:编程语言的安魂曲

> 原文：<https://thenewstack.io/this-week-in-programming-requiem-for-a-programming-language/>

本周，我们为这些年来为我们服务的语言倒一杯羹，但是[不再为我们服务了](https://www.kidscodecs.com/dead-programming-languages/)。

实际上，那可能有点难找，不是吗？[有语言真的死了吗](https://www.quora.com/What-are-some-truly-dead-programming-languages)？如此多的语言流行了又流行，但是即使那些已经消失的语言仍然在某个地方运行着一些不知名的程序，不是吗？

快速浏览了一下[语言流行指数](https://www.tiobe.com/tiobe-index/programming-languages-definition/) [TIOBE Index](https://www.tiobe.com/tiobe-index/) 追踪的所有语言，我惊讶地发现，即使是那些晦涩难懂、似乎早已消失的昔日语言。事实上，随着年轻的开发人员转向流行的、闪亮的未来新语言，一些语言并没有完全消失，而是仍然在为年老的开发人员服务。

然而，我们知道有一种语言实际上已经过时了，因为在它的一生中，它只被一个小的开发团队和一家公司使用——纽约时报。本周，《纽约时报》的工程副总裁布莱恩·海曼为“[帮助塑造了数字纽约时报](https://open.nytimes.com/remembering-a-programming-language-that-helped-shape-the-digital-new-york-times-cd809d707c74)”的语言写了一篇讣告，这种语言在服务了 17 年后，于 2018 年 3 月咽下了最后一口气。

根据这个故事，这一切都始于一个简单的请求:“Context 于 2001 年诞生于 Scott Meyer 的办公室，当时他是《纽约时报》网站的总经理。梅耶尔希望通过在主页顶部添加读者用户名来使《纽约时报》网站更加个性化。当时，nytimes.com 是一个静态的网站，不能为每个人定制，但梅耶尔希望改变这种情况

https://Twitter . com/tangentialism/status/1098323477709258752

尽管 PHP 和 CGI 是可选的，但该团队怀疑这些语言能否处理快速增长的纽约时报网站和未来的定制需求。因此，相反，“他们创建了 Context，一种轻量级语言，被编译为在《纽约时报》的服务器上运行，并针对速度进行了优化”，获得了“比早期测试中的 CGI 快一百倍的速度。”

接下来你知道，Context 提供个性化的广告，内容分页，做所有我们期望从现代网络中得到的事情。但是，正如海曼指出的，“它从不冒险走出大楼的围墙；它从未开源或出售过。”因此，它保持了 17 年，忠诚的骏马。虽然上下文可能是因为这个原因而真正消亡的少数语言之一，但海曼也指出这是其长寿的基础——也许这是那些正在开发新语言的团队感兴趣的一点。

“但也许这种隔离有助于它存活到去年早些时候。由于只有少数贡献者，这种语言避免了被拉向不同的设计方向。不到十几个工程师知道构建系统是如何工作的。也许有一百名工程师学会了编写上下文代码，”海曼写道。“如果没有一个大型的工程师社区，Context 就不会受到新功能可能给系统带来的拖累，这意味着它在创建后的十年里保持小型、灵活，并能够扩展以满足时代不断增长的流量。”

最终,[用](https://open.nytimes.com/react-relay-and-graphql-under-the-hood-of-the-times-website-redesign-22fb62ea9764)[更新的技术](https://open.nytimes.com/the-new-york-times-now-on-apollo-b9a78a5038c)重写了该网站，包括 React、Relay 和 GraphQL，而 Context 则悄然淡出使用。所以这是给你的，上下文——听起来你很好地服务了你的创造者。

## 本周的节目中

*   去拿你的。这里是开发领域:谷歌目前正在为其[新版本提供早期访问期。dev](https://www.blog.google/technology/developers/hello-dev/) 顶级域名。到本文发布时，你将能够以 350 美元的早期访问费，加上标准的 12 美元/年获得一个域名，或者你可以等到月底，只需支付年费。我想这取决于你认为你的。开发领域是去之前，然后…以及你愿意为此付出多少。一个有趣的事实是——谷歌写道，就像它的“最近为[推出的产品”。app](https://get.app/) 和[。页面](https://get.page/)，默认情况下这个新域是安全的，因为它需要 HTTPS [连接到所有。开发网站](https://security.googleblog.com/2017/09/broadening-hsts-to-secure-more-of-web.html)。要获得您的，请访问 [get.dev](https://get.dev/) 。
*   **在 2019 年保持您的 Android 应用程序 API 合规:** Android 开发者，请注意——谷歌在一篇博文中概述了其 2019 年[扩展的目标 API 级别要求](http://android-developers.googleblog.com/2019/02/expanding-target-api-level-requirements.html)，该博文提供了“关于 2019 年 Google Play 要求的更多信息，并宣布了一些影响通过其他商店分发的应用程序的变化。”该公司自 2018 年 11 月以来一直要求 API 等级为 26，并将于 2019 年 8 月开始要求新应用程序达到 28 级，并于 2019 年 11 月之前要求现有应用程序达到 28 级。帖子还列出了中国和其他地方的应用商店的日期。该公司表示，超过 95%的“我们在 Play Store 之外检测到的间谍软件故意针对 API 级别 22 或更低的 API”，并且“ [Google Play Protect](https://www.android.com/play-protect/) 将警告用户，当他们试图安装来自任何来源的 apk，而不是针对最近的 API 级别。”有关如何更改 API 目标级别的参考，请访问 Google 的[迁移指南](https://developer.android.com/distribute/best-practices/develop/target-sdk)或查看以下视频。

[https://www.youtube.com/embed/YyDnYaFtRS0?feature=oembed](https://www.youtube.com/embed/YyDnYaFtRS0?feature=oembed)

视频

*   **深入探究围棋:**新堆栈的[大卫·卡塞尔](https://thenewstack.io/author/destiny/)继续他的[对围棋](/whats-coming-to-golang-in-2019-modules-generics-better-error-handling/)的深入研究，这一次聚焦于它作为[云端编程语言](https://thenewstack.io/go-the-programming-language-of-the-cloud/)的地位，再次提供采访[史蒂夫·法兰克王国](https://github.com/spf13)的细节，他于 2016 年加入谷歌，成为其围棋产品负责人。采访提供了“ [Go 云开发套件](https://github.com/google/go-cloud)”的新细节，法兰克王国称之为“或多或少的云应用的标准库”除此之外，卡塞尔写道，法兰克王国深入研究了“Go 不仅是云基础设施的语言，它甚至还将成为整个云的语言，”引用法兰克王国的话说，“可以合理地说，现代云是用 Go 编写的。几年前，一位分析师写道，go 是云基础设施的语言，我认为这已经被证明是绝对正确的——大多数云基础设施都是用 Go 编写的。”当你在这里的时候，这是本周 Golang 回合中另一个相当值得阅读的内容——Go 项目成员 [Dave Cheyney](https://dave.cheney.net/about) 为编写可维护的 Go 程序提供了一些[现实世界的建议](https://dave.cheney.net/practical-go/presentations/qcon-china.html)。
*   **GitHub Ups the Bounty:**GitHub 的内容部门一直在做，写关于语言和软件包受欢迎程度的博客，我倾向于觉得这是一本好书，不管是什么主题。你有没有碰巧看到[10 月 21 日的事后分析](https://github.blog/2018-10-30-oct21-post-incident-analysis/)？这是一个激动人心的，如果技术，阅读。本周，GitHub 博客团队回顾了过去五年 GitHub 漏洞奖励计划的情况，除了过去一年发现的大量漏洞之外，更令人激动的一点是，包括未来一年增加的奖励。该公司列出了从 617 美元(这是随机的)到超过 3 万美元的奖励，并将资格扩大到“我们 github.com 域名下托管的所有第一方服务”要了解完整的细节和漂亮的排行榜，请访问 [GitHub Bug Bounty](https://bounty.github.com/) 网站。
*   **谷歌为语音转文本服务的数据提供折扣:**对于那些愿意向谷歌的[数据记录程序](https://cloud.google.com/speech-to-text/docs/data-logging)出售数据的人，根据 TechCrunch 上一篇关于[谷歌云的语音 API](https://techcrunch.com/2019/02/21/google-clouds-speech-apis-gets-cheaper-and-learn-new-languages/)的报道，谷歌现在提供 33%的降价。此外，对其云[语音转文本](https://cloud.google.com/speech-to-text/)和[文本转语音](https://cloud.google.com/text-to-speech/)API 的更新包括“企业用户应该特别感兴趣的新功能，以及改进的语言支持和降价。”除了定价之外，云文本到语音转换“获得了 31 个新 WaveNet 和 24 个新标准语音的重大更新。该服务现在还支持七种新语言:丹麦语、葡萄牙语/葡萄牙语、俄语、波兰语、斯洛伐克语、乌克兰语和挪威语博克马尔语。这些语言目前都处于测试阶段，支持的语言列表已增加到 21 种。”
*   **再见，免费 CodeAnywhere:** 免费层 CodeAnywhere 用户刚刚收到一封电子邮件，称从 3 月 1 日起，免费层将成为免费试用版，并且仅限于 7 天，简单地说，因为“我们的用户群对提升我们的容器服务性能的需求不断增长，迫使我们增加了运行我们服务的运营成本，因此，永远免费的计划不再可行。”该公司为那些现在转为付费账户的人提供 40%的终身折扣。

特征图片:[纸浆管理员](https://twitter.com/PulpLibrarian)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>