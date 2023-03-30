# 本周节目:Deno 走向公司

> 原文：<https://thenewstack.io/this-week-in-programming-deno-goes-corporate/>

十多年前，[瑞安·达尔](https://tinyclouds.org/)创建了 [Node.js](https://nodejs.org/) 让 web 开发者能够运行服务器端 JavaScript，从那时起，开源 Javascript 运行时就成为了后端 web 编程的默认。然而，【Dahl 认为 node . js 存在许多弱点，并因此开发了 [Deno](https://deno.land/) ，这是一个“简单、现代和安全的 JavaScript 和 TypeScript 运行时，使用 V8 并内置于 Rust 中，”作为回应。Deno 于三年前推出，吸引了一些网络开发者的兴趣，本周该项目宣布成立 Deno 公司，获得近 500 万美元的资金。

此举是对他们所说的 Node.js 的“适度成功”的直接回应，认为“十年后，我们发现服务器端 JavaScript 无可救药地分散，与糟糕的基础设施密切相关，并且不可逆转地由缺乏创新动力的委员会统治。”他们说，Deno 是他们“为这个生态系统注入新生命的尝试”，他们说这个生态系统已经“停滞不前”

以免你担心 Deno 已经把[卖完了](https://www.youtube.com/watch?v=K_AWQW41Vu8)，他们保证“Deno 将保持 MIT 授权”，因为他们不相信选择向免费或付费用户提供什么功能是正确的前进道路。

你可能会[问](https://news.ycombinator.com/item?id=26620778)，他们打算如何赚钱？

虽然公告没有直接回答这个问题，但它确实说他们已经“暗示这种基础设施的商业应用多年了”，这是他们计划追求的，用 Deno 开源项目构建它，而不是试图直接货币化 Deno。

目前，Deno 网站提供了两个链接——一个链接到 [Deno GitHub 库](https://github.com/denoland/deno)(开源运行时)，另一个链接到 [Deno Deploy](https://deno.com/deploy) ，“一个在全球边缘运行 JavaScript、TypeScript 和 WebAssembly 的分布式系统。”Deno Deploy 目前处于测试阶段，它将允许用户在将 Deno CLI 部署到 Deno Deploy 的托管基础架构之前使用 Deno CLI 进行本地开发，“不到一秒钟，无需进行任何配置。”在测试阶段，这项服务仍然是免费的，随着[价格](https://deno.com/deploy/docs/pricing-and-limits)在全面上市后公布。

事实上，宣布 Deno 公司的博客文章的结尾读起来就像是这种服务的宣言，并且看起来像是一个寻求“服务器端”JavaScript 的公司的显而易见的前进方向，而不像现在许多事情一样，需要服务器本身。

许多人更熟悉 Chrome DevTools 控制台，而不是 Unix 命令行提示符。比 BSD 套接字更熟悉 WebSockets，比手册页更熟悉 MDN。Bash 和 Zsh 脚本调用本机代码永远不会消失。但是调用 WebAssembly 代码的 JavaScript 和 TypeScript 脚本将会越来越普遍。我们认为，许多开发人员更喜欢 web 优先的抽象层。”

事实上，随着一切似乎都朝着无服务器这个、无服务器那个的方向发展，Node.js 的无服务器选项似乎有一定的意义。

## 本周的节目中

*   **FSF 的沉船:**继上周专栏关于[在](https://thenewstack.io/this-week-in-programming-free-software-cant-exist-without-richard-stallman/)[自由软件基金会(FSF)](https://www.fsf.org/) 有争议的[理查德·M·斯托曼](https://en.wikipedia.org/wiki/Richard_Stallman)复职之后，ZDNet 上的一篇文章详细描述了 [FSF 领导人和支持者是如何抛弃这艘沉船](https://www.zdnet.com/article/free-software-foundation-leaders-and-supporters-desert-sinking-ship/)。正如我们当时注意到的，虽然有支持这一问题的两方的信件，一方包括许多著名的名字和组织，而另一方，嗯…没有那么多。从本质上来说，并不是所有的支持都是平等的，事实上，有些支持是有附加条件的。例如，ZDNet 指出“当红帽公司宣布不再资助 FSF 时，他们的话被听到了。”支持的丧失并没有在 Red Hat 结束，这篇文章继续记录了开源行业中的各种声音，这些声音公开呼吁 FSF 做出改变，以回应 RMS 的复职。他们总结道:“内部意见不一，外部批评严厉，财政资源减少，只要斯托曼还在董事会或其他领导职位上，就很难看到 FSF 以任何有意义的方式继续下去。”事实上，虽然请愿和推特风暴是一回事，但资金完全是另一回事。

*   **GitHub 调整移动通知:**当 GitHub 去年年底首次推出其移动应用程序时，我们评论了他们的乌托邦式愿景，即能够“在散步或在阳台上喝咖啡”时进行代码审查(用他们的话来说)，这或许并不像听起来那么美好。虽然我们确信他们没有在听我们说话，但也许其他人也赞同关于工作/生活平衡的相同想法，该公司本周[推出了推送通知、日程安排、发布等新功能](https://github.blog/2021-03-30-new-push-notifications-scheduling-releases-github-mobile/)。虽然该应用程序现在允许用户在您被请求审查拉动请求、分配任务或请求批准受保护环境的[部署](https://docs.github.com/en/actions/managing-workflow-runs/reviewing-deployments)时获得推送通知，但它现在还允许用户设置“工作时间”他们写道:“无论你是在下班后为你的兼职项目设定一些专注时间，还是确保你在实际工作时没有检查工作，这项功能都将允许你指定暂停通知的时间框架。”除了工作时间，用户还可以[为移动设备上的个人存储库定制他们的手表设置](https://docs.github.com/en/github/managing-subscriptions-and-notifications-on-github/viewing-your-subscriptions#configuring-your-watch-settings-for-an-individual-repository)，使他们能够选择接收他们希望接收通知的行动子集。为了喝你的咖啡，在没有通知的宁静中休息一下。
*   **GitHub 桌面出现樱桃采摘:** GitHub 还宣布 [GitHub 桌面现在支持樱桃采摘](https://github.blog/2021-03-30-github-desktop-now-supports-cherry-picking/)，它说这是去年最受欢迎的功能之一。GitHub Desktop 2.7 提供了这个特性，允许用户通过拖放将提交从一个分支复制到另一个分支。除此之外，GitHub 表示“精选带来了一些好处”，包括撤销、执行冲突解决的能力，以及通过菜单而不是拖放进行精选(如果需要的话)。

*   **GitHub 升级其安全游戏:**来自 GitHub 世界的最后一个快速更新:该公司[以新安全概述](https://github.blog/2021-03-30-github-advanced-security-security-overview-beta-secret-scanning-private-repos/)的[测试版的形式提供了 GitHub 高级安全](https://github.blog/2021-03-30-github-advanced-security-security-overview-beta-secret-scanning-private-repos/#security-overview)的两个更新，以及最近宣布的[私人存储库秘密扫描的普遍可用性](https://github.blog/2021-03-30-github-advanced-security-security-overview-beta-secret-scanning-private-repos/#ga-secret-scanning)。正如您所料，该概述给出了“GitHub 组织所面临的应用程序安全风险的高级视图”，而秘密扫描扩展包括另外 35 个合作伙伴。
*   **php 摆脱自己的 Git:** 根据 PHP 维护者 [Nikita Popov](https://twitter.com/nikita_ppv) 给 php.internals 的一条消息，PHP 似乎在过去的一周遭受了供应链攻击，PHP 团队已经“决定维护我们自己的 Git 基础设施是一个不必要的安全风险，我们将停止 git.php.net 服务器”，而不是将一切转移到 GitHub。这一举动对开发者如何为 PHP 做出贡献有一定的影响，Popov 在他的信息中简单地提到了这一点。长话短说，“虽然以前对存储库的写访问是通过我们自己开发的 karma 系统处理的，但现在你需要成为 GitHub 上 php 组织的一员，”Popov 写道，并指出他们还需要启用 2FA。关于这个主题的更多阅读，请查看我们自己对 [PHP 供应链攻击如何展示开源的优点和缺点](https://thenewstack.io/php-supply-chain-attack-shows-open-sources-virtues-and-vices/)的看法。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>