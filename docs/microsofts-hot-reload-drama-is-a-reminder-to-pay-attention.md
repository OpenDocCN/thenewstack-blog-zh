# 微软火热的重装大戏，提醒大家注意

> 原文：<https://thenewstack.io/microsofts-hot-reload-drama-is-a-reminder-to-pay-attention/>

上周，有相当多的人谈论微软如何试图在它的产品上耍花招。NET 社区通过逆转过程和删除[“热重装”功能](https://devblogs.microsoft.com/dotnet/introducing-net-hot-reload/)从。NET，取而代之的是[将它的作用域设为可视代码 2022](https://github.com/dotnet/sdk/pull/22217) 。这一举动在互联网上引发了愤怒的回应，一系列看似神秘的推文来自微软内部的斯科特·汉瑟曼和其他人，还有一篇文章问了这样一个问题:我们能相信微软的开源吗？

这篇文章很好地总结了这种情况，问我们是否可以信任微软，或者仅仅是公司内部的一小部分开源倡导者，来预示一个开源项目，例如。走向未来。

“你信任微软的开放源码吗？还是你真的信任像乔恩·加洛韦、斯科特·汉塞尔曼、斯科特·亨特、吉多·范·罗苏姆、大卫·福勒、达米安·爱德华兹、米格尔·德·伊卡萨和其他一些自下而上在内部推广开放源码软件信息的人？如果这些人离开了。网？微软会继续与社区和谐相处吗？”

帖子敦促社区发出自己的声音，它做到了，不仅在社交媒体上，而且在一个 [pull 请求中撤销了收到数百条支持评论并最终被合并的决定](https://github.com/dotnet/sdk/pull/22262#pullrequestreview-786704734)，与[微软发布道歉](https://devblogs.microsoft.com/dotnet/net-hot-reload-support-via-cli/)。

“首先，我们要道歉。我们在执行我们的决定时犯了一个错误，并且花了比预期更长的时间来回应社区。我们已经批准了重新启用此代码路径的请求，它将包含在的 GA 版本中。NET 6 SDK，”写道。网络项目管理总监[斯科特·亨特](https://twitter.com/coolcsh)。

“我们的愿望是为. NET 创建一个开放和充满活力的生态系统。与许多公司一样，我们正在学习平衡 OSS 社区的需求，并成为. NET 的企业赞助商。有时我们做得不对。当我们没有做到时，我们能做的最好的事情就是从错误中吸取教训，更好地前进，”亨特后来继续说道。

现在，虽然你可能会说结局好就一切都好，但你也可以像开发人员和软件架构师亚历山大·特劳齐(Alexander Trauzzi)所说的那样，认为[是时候放弃了。网离开家](https://atrauzzi.github.io/its-time-for-net-to-leave-home)。特劳齐认为，亨特的博客文章“一事无成，更糟的是，加剧了局势；社区肯定需要开始用他们的两面派方式来牵制微软。”

Trauzzi 提出了这样的论点，虽然这可能有简单混淆的表面现象(或解释),但它实际上是微软的开源方法。

“微软支持开源至今仍是一种绥靖行为，而不是悔悟，”Trauzzi 写道，并引用了扩展无法在非微软 Visual Studio 代码构建上工作的例子。他认为，这整个喧嚣并不像亨特在他的博客中所说的那样是一个沟通的问题，而是“一个意图的问题”

“如果开源的微软爱好者从来不说话，事情会变成什么样？微软经常试图侵占多少；如果没有利益相关者准备好迎接道德后果和相应的指责，这些侵犯最终会导致微软回到他们的老路吗？”在最终得出结论之前，特劳齐问道。这个建议就像这篇文章的标题一样简单:是时候了。带着它的希望箱，走向世界。”

无论你是否得出与特劳齐相同的结论，从整个事件中似乎确实有一个不可避免的教训。开源，看起来像[很像民主](https://en.wikipedia.org/wiki/Democracy_Dies_in_Darkness)——在黑暗中死去，所以继续关注让像微软这样的公司负责是明智的，这些公司现在从他们对开源的明显坚持中受益。

## 本周的节目中

*   **GitHub Universe 综述:**本周首先，GitHub 本周举行了年度开发者大会，并好心地提供了一篇博文，重点介绍了[GitHub Universe 2021](https://github.blog/2021-10-27-everything-new-from-universe-2021/)的所有新内容。当然，如果你想要更多的背景资料，你也可以去[看看我们自己对事件](https://thenewstack.io/github-focuses-on-security-cloud-devex-at-universe-event/)的报道。如果你错过了本周的活动，你可以随时回去观看点播的，但这里有一个最简短的回顾。亮点包括向公共测试版开放 GitHub 问题，为 GitHub 讨论引入标签和自动发行说明，改进 GitHub 操作的 CI/CD，用于运行命令和在 GitHub UI 和[拉请求合并队列](https://github.blog/changelog/2021-10-27-pull-request-merge-queue-limited-beta/)的[私有测试版](https://github.com/features/merge-queue/signup)中跨组织、存储库、问题、拉请求导航的“命令面板”,它允许您合并拉请求，而无需在任何时候更新您的拉请求，同时保持分支绿色。说到颜色，显然，用户在关闭问题时对到处都是红色感到不安，所以现在[关闭的问题将改为紫色](https://github.com/github/roadmap/issues/289)。该博客还提到了对 GitHub 代码空间的大量改进，对 Ruby 的代码扫描支持，企业云客户对存储库的新访问角色，以及…
*   **GitHub Copilot 成为 Neovim 和 JetBrains 可用:**你当然记得 [GitHub Copilot](https://copilot.github.com/) 吧？这是该公司的[只是稍微有点争议的](https://thenewstack.io/this-week-in-programming-github-copilot-copyright-infringement-and-open-source-licensing/)“AI 结对程序员”，以前只在 Visual Studio 代码和 GitHub 代码空间中提供代码完成(甚至完整的代码块建议)。现在，Copilot 可用于 [JetBrains 的 IntelliJ 和 PyCharm 版本 2021.2 及更高版本](https://github.com/github/copilot-docs/blob/main/docs/jetbrains/gettingstarted.md#getting-started-with-github-copilot-in-jetbrains)和 [Neovim 0.6 预发行版](https://github.com/github/copilot.vim#getting-started)和 Node.js。根据 [InfoWorld](https://www.infoworld.com/article/3638550/github-copilot-adds-neovim-jetbrains-ide-support.html#jump) 的消息，Copilot 的最新更新还包括增加了 Java、C、C++和 C#的多行代码完成功能。

*   **Rust 1.56.0 带来了对 Rust 2021 的支持:**[Rust 的最新版本已经到来](https://blog.rust-lang.org/2021/10/21/Rust-1.56.0.html)，它也带来了对 Rust 2021 的支持，该“版本”允许选择加入可能会带来向后兼容性风险的更改。Rust 团队写道，“这是一个更小的版本，特别是与 2018 年相比，但仍然有一些很好的生活质量变化，需要选择版本以避免破坏现有代码中的一些角落情况”，并且[版本指南](https://doc.rust-lang.org/stable/edition-guide/editions/index.html)提供了新功能的详细信息以及[如何迁移](https://doc.rust-lang.org/edition-guide/editions/transitioning-an-existing-project-to-a-new-edition.html)。还有一些“生活质量的变化”需要选择加入版本，以避免破坏现有代码中的一些极端情况。如果你想了解更多关于版本，尤其是 Rust 2021 的信息，可以去看看去年五月的一篇博客文章，这篇文章概括了一切。

*   Docker 在 Docker Hub Registry 上增加了对 IPv6 的测试版支持: Docker 表示，随着本周推出的 IPv6 支持的[测试版，Docker Hub Registry 将成为“少数几个支持 IPv6 的容器注册中心之一”。IPv6 支持已经在 Docker 的](https://www.docker.com/blog/beta-ipv6-support-on-docker-hub-registry/)[公共路线图](https://github.com/docker/roadmap/issues)中，随着这一版本的发布，纯 IPv6 网络上的组织现在可以选择直接使用注册表，而无需 NAT64 网关。对于您可能需要知道的所有细节和警告(基本上，如果您仍在使用 IPv4，您不需要做任何事情),请前往查看博客帖子。
*   **Go 2021 年开发者调查:** Go 开发者们，是时候让你们的声音被听到了:Go 团队已经[公布了 2021 年 Go 开发者调查](https://go.dev/blog/survey2021)。该调查面向“所有使用围棋、曾经使用围棋或对使用围棋感兴趣的人”，将用于帮助塑造围棋的未来。自 2016 年以来，Go 团队一直在提供年度调查(请参见[这里的](https://go.dev/blog/survey2020-results)往年结果)，并使用结果来塑造语言的发展。 [2021 Go 开发者调查](https://google.qualtrics.com/jfe/form/SV_0BwHwKSaeE9Cx2S)将开放至 11 月 16 日。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>