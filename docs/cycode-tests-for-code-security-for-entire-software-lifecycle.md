# Cycode 测试整个软件生命周期的代码安全性

> 原文：<https://thenewstack.io/cycode-tests-for-code-security-for-entire-software-lifecycle/>

过去几年中一连串与源代码相关的安全事件为 [Cycode](https://cycode.com/) 联合创始人 [Lior Levy](https://www.linkedin.com/in/lior-levy-ba076689/) 和 [Ronen Slavin](https://www.linkedin.com/in/ronen-slavin-26281411/?originalSubdomain=il) 提供了一个“啊哈时刻”。

像 NSO 集团这样的公司，一名前雇员被指控从公司窃取源代码，并试图在黑暗网络上出售。各大杀毒公司的源代码被泄露到网上。

“与代码相关的事件有所增加，我们发现这是一种未得到满足的需求。我和 Lior 都有开发背景，所以我们知道这是一个需要额外关注的领域，以前没有给予足够的重视，”Slavin 说。

这一切都发生在最近的网络安全管理软件产品事件之前，在该事件中，黑客将恶意代码插入影响包括微软和顶级政府机构在内的大公司的软件中。

以色列国防军的前安全研究人员 Levy 在 2019 年离开了赛门铁克和 Slavin Reasons 网络安全公司，成立了 Cycode。

它最初的方向是保护源代码和代码库，如 GitHub、 [GitLab](https://about.gitlab.com/?utm_content=inline-mention) 和 Bitbucket。然后，通过与潜在客户和客户合作并观察市场趋势，他们发现许多控制开发运维流程的配置正在转向代码。

“我们知道，如今代码库正成为一个更大的目标，并成为整个开发操作的这种单一来源。所以[我们决定]这是我们应该关注的。这是我们应该保护的，”斯拉文说。

## 秘密，泄露，IAC

该技术与 GitHub、GitLab 和 Bitbucket 等基于 Git 的存储库相连，以检查访问配置等内容，以及组织是否在其系统中强制实施双因素身份认证。它还查看单个用户的权限和实际活动，检查这些权限是否合适。

它还检查一般配置，如存储库是否从私有变为公共，以及更复杂的设置，如存储库是否有分支保护。这种品牌保护有类似提交签名、保护存储库不被重写的策略吗？这些分支保护措施实际上得到执行了吗？

然后团队开始寻找秘密。

“如今，我们可以在许多代码库中找到秘密。它可能在提交历史中；它可以在实际代码中，也可以在实时活动中。也可能是开发商的公共贡献，”斯拉文说。

“所以我们建立了一个秘密检测机制，允许我们检测这些类型的秘密。最近，我们开始将其扩展到 DevOps 管道的其他部分，例如，寻找 Kubernetes 中存储错误的秘密，或构建中的秘密，或类似的事情。”

他们还建造了一个泄漏检测引擎。

“这是一种可能发生在整个管道中的事情:它可能发生在代码库本身，它可能发生在错误配置的构建中，它可能发生在云中的各种配置中，”他说。

该技术还扫描存储库中 IAC 文件中的错误配置，寻找任何违反安全建议最佳实践的情况，然后在云中检查该技术。

最后，我们有平台的审计部分，查看这些工具中发生的事件。并且某种程度上汇总了这种审计活动。然后，我们获取所有这些数据，并获取我们在连接的提炼系统中找到的所有资产。我们把它收集在图表中。还有不同资产之间的关系以及系统之间的连接。我们有检查图形中各种配置和设置的策略，允许我们检测工作站之间发生的冲突配置或不安全问题。

本月早些时候，该公司公布了其知识图技术。这款无代理工具可聚合来自 DevOps 工具、基础设施和安全扫描器的数据，以提供上下文和安全洞察，并帮助安全团队更好地处理他们收到的大量警报。

“Cycode 为我们节省了大量时间来强化我们的源代码控制管理系统，加强安全配置并防止秘密进入我们的代码。此外，通过无缝插入我们开发人员的工作流程，我们的团队立即采用了 Cycode，”系统渗透测试服务公司[钴](https://cobalt.io/)的首席信息安全官[雷·埃斯皮诺萨](https://twitter.com/rayespinozasec?lang=en)说。

## 检查多个工具

Open Web Application Security Project(OWASP)[post](https://owasp.org/www-community/Source_Code_Analysis_Tools)指出，市场上有太多的源代码分析工具，同时还列举了其中相当多的工具。它们的优点之一是伸缩性好，并且为开发人员突出显示了精确的源文件、行号，甚至是受影响的行的子部分。然而，它列出的弱点是配置问题和检测安全漏洞的问题，包括身份验证、访问控制和其他方面。

“目前的技术水平只允许这些工具自动发现相对较小比例的应用程序安全缺陷。然而，这类工具正变得越来越好，”它总结道。

虽然市场上有许多竞争对手，但该公司坚持认为，它的价值在于保护公司可能拥有的每个存储库实例，如 GitHub 或 GitLab(大型企业可能有多个),以及保护多个供应商的源代码。

“GitHub 永远不会做的一件事是构建在 Bitbucket 中工作的治理工具。因此，为了解决企业用例，你必须考虑不一定来自同一个供应商的多个实例，”Cycode 营销副总裁[安德鲁·法伊夫](https://www.linkedin.com/in/andrewfife/)说。

“谁知道你的 M&A(并购)部门下周会带来什么。他们将收购会影响收入的软件公司；他们不会买那些必须有干净的安全实践的软件公司。

“另一件事是，我们不再只是谈论 SCMs(供应链管理)系统，我们谈论的是所有的基础设施，你的构建系统，你的工件树，你的云环境。”Fife 坚持认为，这些领域中的本地供应商没有一个拥有跨软件开发生命周期的所有阶段管理代码的本地工具。

## 新资金

同样在这个月，这家总部位于特拉维夫的公司宣布了由 Insight Partners 领投的 2000 万美元 A 轮融资。

Insight Partners 的负责人乔恩·罗森鲍姆(Jon Rosenbaum)将加入 Cycode 的董事会，他说:“保护像 GitHub、Jenkins 和[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)这样的 CI/CD 工具的问题实际上是每个企业的一个缺口。“Cycode 以优雅、以开发人员为中心的方式保护 CI/CD 管道。这使该公司成为新一代应用安全公司中的领导者，这些公司正在快速扩大市场，其解决方案可以在不牺牲速度的情况下保护每个版本。”

除了计划扩大其集成的系统范围，它还在考虑保护许多企业仍在使用的非基于 Git 的代码库。这是为了防止类似去年年底对 Accel lion T1 的传统文件传输平台 FTA 的攻击。

它还希望更深入地研究现有的用例，检测它所连接的每个系统周围的更多问题。并创建更多基于知识图的策略。

“SDLC 的现代化创造了新的安全漏洞，攻击者很容易利用，”Slavin 在资金宣布时表示。“最近像网络安全管理软件产品和 Codecov 这样的供应链攻击，来自[微软](https://www.zdnet.com/article/windows-xp-leak-confirmed-after-user-compiles-the-leaked-code-into-a-working-os/)和[日产](https://www.zdnet.com/article/nissan-source-code-leaked-online-after-git-repo-misconfiguration/)的主要源代码泄露，以及针对像 [Sawfish](https://cycode.com/blog/a-unique-supply-chain-attack-the-2020-sawfish/) 和 [XcodeSpy](https://nakedsecurity.sophos.com/2021/03/19/serious-security-mac-supply-chain-backdoor-takes-aim-at-xcode-devs/) 这样的开发人员的攻击，表明战场已经在转移。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>