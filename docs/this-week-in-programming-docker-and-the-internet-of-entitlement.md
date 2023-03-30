# 本周编程:Docker 和自由软件权利的互联网

> 原文：<https://thenewstack.io/this-week-in-programming-docker-and-the-internet-of-entitlement/>

现在，不要误解我的意思——我是一个天生的抱怨者，当谈到不得不在互联网上支付东西时——但是这整个繁琐的程序，人们正在通过开始对 Docker Desktop 收费来呼唤 Docker 拉一个[诱饵和开关](https://twitter.com/jbeda/status/1432803352853684227?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1432803352853684227%7Ctwgr%5E%7Ctwcon%5Es1_&ref_url=https%3A%2F%2Ffeedly.com%2F)？

这看起来有点荒谬，并且指出了我们免费使用软件的权利水平。

毕竟，Docker 本周宣布的[更新定价和订阅](https://www.docker.com/blog/updating-product-subscriptions/)保留了 Docker Desktop 作为一款完全免费的软件，一如既往，面向“员工少于 250 人、年收入少于 1000 万美元”的公司至少在我看来，这是一个完美的举动，可以在公众舆论的法庭上轻松辩护。当你的公司规模如此之大并能赚到这么多钱的时候，谁能反对向拥有这些特殊品质的公司收取每位用户仅仅 5 美元(到 7 美元或 21 美元)的费用呢，对吗？

显然，很多人会争论，正如本周早些时候《新堆栈》撰稿人 [Bruce Gain](https://thenewstack.io/author/bruce-gain/) 所详述的[。众所周知，](https://thenewstack.io/docker-says-some-users-must-pay-but-can-it-make-money/)[有互联网，就会争论](https://idioms.thefreedictionary.com/have+(something)%2C+will+travel#:~:text=A%20phrase%20used%20when%20one,%E2%80%94have%20degree%2C%20will%20travel!)。

[除了抱怨和他们的讽刺之外](https://twitter.com/jbeda/status/1432803352853684227)，Hacker News 上关于新闻的[顶级评论帖子](https://news.ycombinator.com/item?id=28371907)提出了几个关于处理许可证时的开销以及这如何可能足以让企业说“去它的，让我们使用其他东西，”这是我唯一想知道的一点。考虑到费用本身的最低性质，企业会支付每个用户的成本，并处理有关新员工入职和遵守许可的所有复杂问题，还是会认为负担太重而转向其他替代方案？

如果你本周关注黑客新闻和 Twitter，你可以看到许多关于替代方案的讨论，其中大部分是前维护者 Matt Rickard 在他的[概述 Docker 桌面替代方案](https://matt-rickard.com/docker-desktop-alternatives/)中提供的。当然，问题是转移到其他东西——以及转移过程中涉及的所有过程和风险——是否比简单地支付订阅费和帮助 Docker——真正推动整个集装箱化概念的公司——维持运营提供了更好的投资回报。

“我认为对 Docker 决定的愤怒被过分夸大了。如果您是一家大规模使用 Docker 桌面的企业，那么您应该为支持付费。实际上，我对 Docker 的当前方向和团队对开发人员工具的关注感到非常兴奋，”Rickard 恰当地总结道。

## 本周的节目中

*   **TypeScript 4.4 带来新主页:**在 TypeScript 4.3 到来的三个月后，微软[发布了 TypeScript 4.4](https://devblogs.microsoft.com/typescript/announcing-typescript-4-4/) ，这是 JavaScript 超集的最新版本，增加了静态类型的语法。最新版本增加了几个新功能，如[别名条件和判别式的控制流分析](https://devblogs.microsoft.com/typescript/announcing-typescript-4-4/#cfa-aliased-conditions)，这有助于保存类型守卫的结果，在允许代码执行某些操作之前，可以检查变量的类型。其他功能包括[符号和模板字符串模式索引签名](https://devblogs.microsoft.com/typescript/announcing-typescript-4-4/#symbol-template-signatures)、[默认为 Catch 变量中的未知类型](https://devblogs.microsoft.com/typescript/announcing-typescript-4-4/#use-unknown-catch-variables)、 [tsc —帮助更新和改进](https://devblogs.microsoft.com/typescript/announcing-typescript-4-4/#tsc-help)、[性能改进](https://devblogs.microsoft.com/typescript/announcing-typescript-4-4/#perf-improvements)等等，以及一些[突破性的更改](https://devblogs.microsoft.com/typescript/announcing-typescript-4-4/#breaking-changes)。TypeScript 还为 JavaScript 带来了一个新特性，增加了 JavaScript 的[拼写建议，它们是“相同的‘你是说…？’”TypeScript 文件已经有的建议，现在它们以某种形式出现在所有 JavaScript 文件中。“除了最新发布的版本，TypeScript 还有一个新的 TypeScript 主页](https://devblogs.microsoft.com/typescript/announcing-typescript-4-4/#spelling-corrections-js)，继去年 8 月对整个 TypeScript 网站的[重新设计和重新架构](https://devblogs.microsoft.com/typescript/announcing-the-new-typescript-website/)之后。新的 [TypeScript 主页](https://www.typescriptlang.org/)使你更容易更快地到达你要去的地方，同时也减少了页面上的文本，使其更容易扫描，但不要相信我们的话——只要过去看看就行了。

*   **GitHub 反驳“模糊的侵权指控”:** GitHub 最近在联邦上诉法院提交了一份关于 SAS Institute，Inc .诉 World Programming Ltd .一案的“[法庭之友](https://en.wikipedia.org/wiki/Amicus_curiae)”[摘要](https://github.blog/wp-content/uploads/2021/08/2021.08.30.GitHub.Amicus.Brief_.pdf)，并在本周的一篇博客文章中幽默地标题为“[模糊的侵权指控被认为是有害的](https://github.blog/2021-08-31-vague-infringement-allegations-considered-harmful/)”(如果你不熟悉这份参考资料，可以看看这个每周专栏的一个版本，它关注的是考虑计算机世界中有害事物的传统。)在手头的案例中，SAS 提出了“非文字”侵权的索赔，这意味着它不能指出哪些“特定的代码行被逐字复制，而只是使用了其他方面，如代码的整体结构和组织。”在这份简报中，GitHub 辩称，SAS 提出的指控是模糊的，并且“对非文字版权侵权的模糊指控特别创造了 FUD，因为这种指控的接收者经常没有办法评估他们面临的风险。”GitHub 写道，结果可能是软件被移除，没有办法清楚地解决问题或抵制误导的索赔，“当一个严重依赖的软件因侵犯版权的模糊指控而离线时，依赖该软件的整个生态系统都将崩溃”。

*   **GitHub 移除了很少使用的 Git 安全特性:**GitHub 本周又一次快速更新，迁移到[提高 GitHub 上的 Git 协议安全性](https://github.blog/2021-09-01-improving-git-protocol-security-github/)。该公司表示，它正在改变 SSH 支持的密钥，并完全删除未加密的 Git 协议，尽管它预计这些变化将影响一小部分用户。更具体地说，它正在删除对所有 [DSA](https://en.wikipedia.org/wiki/Digital_Signature_Algorithm) 密钥的支持，添加对新添加的 [RSA 密钥](https://en.wikipedia.org/wiki/RSA_(cryptosystem))的要求，删除一些遗留的 SSH 算法，并为 SSH 添加 [ECDSA](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm) 和 [Ed25519](https://en.wikipedia.org/wiki/EdDSA#Ed25519) 主机密钥。“只有通过 SSH 或 git://连接的用户会受到影响，”他们写道。"如果你的 Git 遥控器以 https://开头，这篇文章中的任何内容都不会影响你."如果你碰巧是一个 SSH 用户，就去看看这篇文章，了解预期变化的时间表的全部细节。
*   **AWS 推出针对 Swift 和 Kotlin 的 Alpha SDK:**AWS 本周发布了两款新的 Alpha SDK:针对 Swift 的[AWS SDK](https://aws.amazon.com/blogs/developer/announcing-new-aws-sdk-for-swift-alpha-release/)和针对 Kotlin 的[AWS SDK](https://aws.amazon.com/blogs/developer/aws-sdk-for-kotlin-alpha-release/)。对于 Swift，已经有一个用 Objective C 编写的 iOS SDK，但新的 SDK 将提供一个在“其他平台，如 Linux、macOS、Windows、tvOS、watchOS 等”上运行的原生 Swift SDKSwift SDK 还支持使用其他 AWS 服务，而[路线图](https://github.com/awslabs/aws-sdk-swift/projects/1)“概述了为特定 AWS 服务添加功能和定制以改进功能的计划。”与此同时，[用于 Kotlin](https://github.com/awslabs/aws-sdk-kotlin) 的 AWS SDK“使得使用惯用的 Kotlin APIs 调用 AWS 服务变得容易”并且“使得开发者能够对所有支持的 AWS 服务进行 API 调用”同样，GitHub 上有[公开路线图](https://github.com/awslabs/aws-sdk-kotlin/projects/2)和[入门指南](https://github.com/awslabs/aws-sdk-kotlin/blob/main/docs/GettingStarted.md)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>