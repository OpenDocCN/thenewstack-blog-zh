# 用于 ConfigCat 的 Elixir SDK

> 原文：<https://thenewstack.io/elixir-sdk-for-configcat/>

SaaS 应用程序的一大优点是，平台中的用户可以自动获得任何可用的软件更新。然而，测试程序需要一个独立的环境，这给用户和开发团队带来了潜在的挑战。

在这种情况下，拥有一个可以控制特性和标记特定用户的工具是很重要的，因为有时特性太早或者对所有用户都不相关。这就是为什么，去年，我们开始在 InfluxData 使用 ConfigCat 来完成这项工作。

## 什么是 ConfigCat？

 [兰迪·科尔曼

Randy Coulman 是 InfluxData 电子商务团队的技术主管。他在交付高质量、可持续的软件方面有将近 30 年的经验。](https://www.linkedin.com/in/randy-coulman-97088726/) 

[ConfigCat](https://configcat.com/) 是一个托管服务，用于功能标记和配置管理。它使您能够从代码部署中分离出特性发布。ConfigCat 可用于:

*   即使在部署了代码之后，也可以使用 ConfigCat 仪表板打开/关闭您的功能。
*   根据地区、电子邮件、订阅或任何其他自定义用户属性确定目标用户群。

去年，我们开始在 InfluxDB Cloud 中使用 ConfigCat，在整个平台上共享[功能标志](https://martinfowler.com/articles/feature-toggles.html)。在其他功能中，ConfigCat 允许我们全局打开或关闭功能，或者为特定用户或用户组打开功能。我们甚至可以为一定比例的用户打开功能。

为了实现与各种应用程序的轻松集成，ConfigCat 为许多不同的语言提供了 SDK。不幸的是，对于我们的电子商务团队来说，Elixir 不在其中，也不在当前的路线图上。

ConfigCat 有一个有趣的特性标记方法。它提供了一个用于创建和管理特性标志和目标规则的 web 应用程序，但是实际工作是在各种 SDK 中完成的。SDK 定期下载描述特性标志和目标规则的 JSON 负载(配置),然后使用缓存的配置来评估特性标志。这提供了许多好处:

*   **确定特征标志的值:**无需等待 HTTP 往返
*   **不依赖不可靠的网络通信:**对每个特征标志评估进行更有效的通信
*   **更少的网络流量:**应用程序只需根据需要或特定的时间间隔获取更新的配置
*   **敏感用户信息留在本地:**潜在敏感用户信息不通过网络发送；它位于您的应用程序的本地
*   **所需的服务器基础架构更少:**config cat 服务使用更少的服务器基础架构运行，从而降低了客户的成本

缺点是为新语言构建 SDK 需要更多的工作。ConfigCat 的 SDK 都是开源的，所以我们能够审查其中的几个，看看在编写新的 SDK 时可能会涉及到什么。最终，我们决定继续前进。

## 在 InfluxData 上使用 ConfigCat

我们首先在我们的应用程序中构建了一个 ConfigCat SDK，并计划以后提取它并将其开源。这使得迭代更容易，并确保它为我们工作。我们小心翼翼地让代码尽可能独立于应用程序的其他部分。一旦我们让它工作，我们就开始在生产中使用它。不幸的是，其他优先事项优先，我们不能花时间提取 SDK 以供他人使用。

随着十月的临近，我在想今年我想为 [Hacktoberfest](https://hacktoberfest.digitalocean.com/) 做些什么。我决定将我们的 ConfigCat SDK 提取出来，开源并发布到 Elixir 的 [hex.pm 包注册表](https://hex.pm/)。

当我开始的时候，我注意到 ConfigCat 有一个新的 [GitHub 库，用于一个 Elixir SDK](https://github.com/configcat/elixir-sdk) 。我很快意识到那里还没有代码，所以我[开了一个问题](https://github.com/configcat/elixir-sdk/issues/1)问我们是否能帮忙。

另一家公司 [Drover](https://www.joindrover.com/) 也对 ConfigCat 的 Elixir SDK 感兴趣，并愿意做出贡献。经过一些简短的讨论，我们决定使用我们最初的 ConfigCat SDK 作为起点。根据拉霍斯·szőke 和 ConfigCat 团队的反馈，Drover 的伊戈尔·埃斯科瓦尔和我在接下来的几周时间里一直在重复这个项目。我们在 InfluxData 中添加了我们还不需要的功能，进行了重构以使 SDK 与其他语言的 SDK 更加一致，以便于将来的维护，支持我们最初编写客户端时不存在的新设置和选项，并添加了 Elixir 社区期望的文档。

后来，拉霍斯对自己的努力说了这样的话:

“这是 ConfigCat 的第一个完全由社区驱动的 SDK 开发。看到 Igor[来自 Drover]发起关于开发 Elixir SDK 的讨论后，Randy[来自 InfluxData]也加入了讨论，并提出“我们能帮上忙吗？”Github 问题。…不止一个，而是两个客户想帮助我们开发这个 SDK。发展阶段是特殊的。…看到三家完全不同的公司为了这个伟大的目标联合起来，真是太棒了。"

一旦我们都对结果感到满意，我们就把这个包发布到 [hex.pm](https://hex.pm/packages/configcat) ，现在任何人都可以使用它了！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>