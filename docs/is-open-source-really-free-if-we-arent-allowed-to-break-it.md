# 如果不允许我们破坏开源，开源真的是免费的吗？

> 原文：<https://thenewstack.io/is-open-source-really-free-if-we-arent-allowed-to-break-it/>

过去的一周是开源软件世界中有趣的一周。现在你可能已经听说了，两个流行的开源库 colors.js 和 faker.js 的作者 Marak Squires 故意破坏了这两个库 T1，部分是以 T2 的名义对抗 T3(也就是“财富 500 强”)，部分是为了让人们意识到他自己最喜欢的阴谋论。

在破坏这两个库的过程中，开发者有效地破坏了依赖它们的数千个项目，这两个库总共占了超过 2000 万的周下载量和数千个依赖项目。虽然结果可能是一场浩劫，但一个卑微的开源开发者反抗利用他的大而富有的公司的象征却引起了许多人的共鸣。然而，正是对这些行动的回应引起了一些争论。

作为对受损库的回应，微软迅速暂停了他对 GitHub 的访问，并恢复了 npm 上的项目。GitHub 发言人向 actions 提供了以下声明:

“GitHub 致力于确保国家预防机制登记处的健康和安全。我们根据 npm 关于恶意软件的可接受使用政策，删除了恶意软件包并暂停了用户帐户，正如我们的开源条款所概述的那样。我们也在这里发布了一条安全公告:【https://github.com/advisories/GHSA-5rqg-jm4f-cqx7

虽然这对于一些人来说似乎是一目了然的事情——开发者犯下了恶意代码，GitHub 和 npm 做了它必须做的事情来保护它的用户——但一场围绕开发者对他们的代码做他们想做的事情的权利的辩论爆发了，不管它可能有多少项目和依赖关系。

iprogramer 上的一篇[文章进一步概述了这个看似清晰的案例中存在的困境:“如果你认为回购中的代码属于[它的]创作者/维护者，任何暂停似乎都是不合理的。是的，它是开源的，因为你可以派生它，也可以为它做出贡献，但这是否意味着 GitHub 有理由拒绝你改变甚至破坏自己代码的权利？”](https://www.i-programmer.info/news/136-open-source/15140-developer-sabotages-own-code.html)

然而，截至昨晚，整个事件似乎只是一场智力辩论，因为 GitHub 确实实现了一些人可能认为的交易的结局:开发者的账户是活跃的，他被允许删除他在 GitHub 上的 faker.js 库(尽管可能有所依赖)，并且自[以来提供了一个更新](https://github.com/Marak/colors.js/issues/285#issuecomment-1012604165)说他“没有驴脑子”。

在智力辩论中，开源开发者是否应该能够写一个库，在麻省理工学院的许可下提供给大众，依赖它，然后最终取出代码，看起来他们确实能够这样做。

在我们离开这个现在已经不是问题的话题之前，还有一个关于整个事件的观点——再次关注开源中的资金——我们认为值得向读者指出:[依赖风险和资金](http://lucumr.pocoo.org/2022/1/10/dependency-risk-and-funding)。一句或许能激起你阅读欲望的话:

“由单个未经审查的开发人员通过诸如 npm、cargo、pypi 等包管理器安装的小型、更常用的依赖项所带来的风险很高。然而，当那里出现问题时，每个人都会立即注意到，人们会很快呼吁提供资金。然而，这些并不是真正支撑我们经济的依赖。这些依赖中的许多成为了基础，不是因为它们解决了一个困难的问题，而是因为我们集体开始拥抱懒惰胜过一切。当我们将我们的资金讨论集中在这些类型的依赖上时，我们也含蓄地将焦点从实际上重要的包上移开了。”

## 本周的节目中

*   所以你想 DIY Docker 桌面？回到去年 8 月，Docker [宣布改变其定价结构](https://thenewstack.io/this-week-in-programming-docker-and-the-internet-of-entitlement/)，这将使 Docker Desktop 成为员工超过 250 人或年收入超过 1000 万美元的公司的付费订阅。现在，当我们发现自己处于 1 月中旬时，转换的最后期限(1 月 31 日)正在迅速临近。对许多公司来说，这是决定生死的时刻，他们要弄清楚是否要放下现金，或者尝试走自己的路。我们之前已经探索了作为潜在替代品的 [Rancher Desktop](https://thenewstack.io/this-week-in-programming-ranchers-docker-desktop-replacement/) 和 [Podman](https://thenewstack.io/this-week-in-programming-the-docker-dogpile-continues/) ，但本周 Docker 本身也加入了[的游戏，思考 Docker Desktop 和 DIY 解决方案](https://www.docker.com/blog/guest-blog-deciding-between-docker-desktop-and-a-diy-solution/)之间的权衡。正如你可能想象的那样，这篇博客文章似乎最终会倾向于坚持使用 Docker Desktop，而不是 DIY 路线，客座作者写道，“虽然有些人更喜欢 DIY Docker 的灵活性和控制，但 Docker Desktop 需要较少的设置工作和维护，为每个人从开发到 QA 提供了更温和的学习曲线。”然而，如果你仍然犹豫不决，这篇文章，以及我们过去讨论过的其他思考，可能值得一读。

*   **Docker Business 获得单点登录:**在 Docker 的另一个快速新闻中，Docker 已经[正式宣布为其 Docker Business 客户](https://www.docker.com/blog/introducing-sso-for-docker-business/)提供单点登录(SSO)，这是一项功能[上个月](https://thenewstack.io/the-foreseeable-future-ends-with-knatives-cncf-application/)当一篇预览该功能的博客帖子意外发布时，我们让您了解了这项功能。Docker Business 是上述企业继续使用 Docker Desktop 所需的订阅层，现在将允许用户使用 SAML 2.0 和 Azure Active Directory 身份提供者登录，关于如何开始的所有细节都在博客帖子中。看起来 Docker 还有另一个胡萝卜在他们潜在的付费客户面前晃来晃去。

*   **AngularJS 的长期支持结束:** AngularJS，谷歌早在 2010 年首次推出的 JavaScript 框架，已经走到了穷途末路，[的长期支持终于结束](https://blog.angular.io/discontinued-long-term-support-for-angularjs-cc066b82e65a)。不要将与随后的 Angular 2 和 Angular 4 JavaScript 框架混淆，AngularJS 是在四年前走上这条道路的，由于疫情，它甚至享受了一年的长期支持，但现在该团队已经正式宣布结束，并建议[将](https://blog.angular.io/finding-a-path-forward-with-angularjs-7e186fdd4429)过渡到 [Angular](https://angular.io/) 。虽然 CDN 链接将保持活动状态，并且[AngularJS.org](http://angularjs.org/)将保持在线，但是 GitHub repos 将变为只读状态，AngularJS npm 包将保留，但将被标记为已弃用。
*   **张开嘴，插入脚:**本周，我们留给你一篇有趣而简短的短文，讲述每个开发人员在其职业生涯中都曾说过一次(如果不是无数次的话)的四个词— [这是谁写的？伴随着意识到我们每一个人都是作为回应说出的名字。](https://www.heltweg.org/posts/who-wrote-this-shit/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>