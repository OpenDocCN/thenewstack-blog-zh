# Spotify 利用 Snyk 实现安全测试自动化

> 原文：<https://thenewstack.io/spotify-taps-snyk-for-security-testing-automation/>

由于越来越多的网络攻击，音乐流媒体服务 [Spotify](https://open.spotify.com/) 已经将 [Snyk](https://snyk.io/) 安全软件纳入其软件开发生命周期，以自动化安全测试。增强的安全措施有助于防止应用程序和软件资产中的漏洞和流动。

由于这些攻击在软件开发生命周期的所有阶段都很普遍，从设计到交付，安全措施也必须存在于这些阶段。[Spotify 工程经理 Edina Muminovic](https://www.linkedin.com/in/edina-muminovic-56791754/) 最近写了一篇[博文](https://engineering.atspotify.com/2022/08/how-we-maintain-security-testing-within-the-software-development-life-cycle/)，解释了 Spotify 的一些新的网络安全措施。

《福布斯》在今年 6 月发表了一篇文章[详细介绍了最近的网络攻击数据:](https://www.forbes.com/sites/chuckbrooks/2022/06/03/alarming-cyber-statistics-for-mid-year-2022-that-you-need-to-know/?sh=3b982baf7864)

*   2021 年网络攻击和数据泄露的平均数量比上一年增加了 15.1%。
*   [Anchore](https://anchore.com/?utm_content=inline-mention) 最近发布了[一项调查](https://anchore.com/blog/2022-security-trends-software-supply-chain-survey/)显示 2021 年五分之三的公司成为软件供应链攻击的目标。
*   82%的首席信息官认为他们的软件供应链易受攻击。

Spotify 是一款海量应用。它消耗大量的库、服务应用程序和基础设施，所有这些都容易受到供应链攻击。Muminovic 写道，Spotify“希望确保我们可以信任软件来源，反过来，仍然是一个不会向我们的客户提供恶意软件的软件供应商。”

毫不奇怪，Spotify 安全团队在设计他们的网络安全程序时，主要目标是“防止可以针对软件开发生命周期任何阶段的攻击”。当在软件开发生命周期中对安全测试进行分类时，他们关注两个关键领域。

1.  涵盖 Spotify 种类繁多的语言和包管理器。
2.  拥有足够灵活的解决方案来集成到现有的 CI/CD 中。

## **Spotify 安全自动化和 Snyk**

Spotify 使用反应式控制。这些是扫描应用程序并报告任何漏洞的工具集合。Snyk 平台是这个系列的一部分。Snyk 被集成到 Spotify 的构建管道中，并扫描新构建中的漏洞。新的集成分阶段推出，前两个阶段是外围服务和访问敏感数据的服务。

Snyk 的开发者安全平台是为保护代码、依赖项、容器和基础设施而设计的。该软件测试漏洞，并提供内容、优先级和补救措施。Snyk 使用研究团队和机器学习来帮助防范网络攻击。

安全测试自动化之所以重要，有两个原因。自动测试在程序中提供了一个额外的安全层，并保持资产和组件的健康和最新。这有助于 Spotify 快速安全地扩大规模。第二个原因考虑到了数千名 Spotify 开发者。Muminovic 解释说，自动测试允许 Spotify 在实施安全测试时，“将开发人员的需求放在首位，让开发人员专注于他们自己的优先事项”。

Snyk 内置了对 Spotify 所需的大多数语言和框架的支持，这意味着漏洞扫描会自动嵌入到 CI/CD 管道中。Spotify 表示，“这种采用是天衣无缝的，不需要开发者采取任何行动。”

Spotify 证实，Snyk“计划将支持扩展到我们感兴趣的其他领域。”对于 Snyk 自动处理过程之外的语言和框架，Spotify 为开发人员提供了一个简单的指南，使 Snyk 扫描成为他们应用程序的构建步骤。扫描的项目数量持续增加。

一旦发现威胁，Spotify 会采取两种方法来解决。第一种方法是自动生成修复并合并它们，而不需要工程或安全团队的任何干预。Snyk 是该领域的领导者，因为 Spotify 能够通过使用 Snyk 提供的各种 API 来跟踪生命周期漏洞，并将这些数据集成到他们的内部漏洞管理平台中。

第二种方法更加劳动密集型，包括源代码分析、通过自动化进行的全范围升级，以及通过关注开发的每个地方的安全性来防止漏洞的供应链管理。

安全团队的口头禅是“负责任地承担风险，因为攻击媒介的发展与软件行业一样快。重要的是提供一种整体的方法来保护软件开发。”自动化和工具团队为 Spotify 的安全软件开发做出了“强大而有价值的”贡献。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>