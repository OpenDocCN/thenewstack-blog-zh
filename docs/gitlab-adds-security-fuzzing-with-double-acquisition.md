# GitLab 通过双重采集增加了安全模糊

> 原文：<https://thenewstack.io/gitlab-adds-security-fuzzing-with-double-acquisition/>

为了成为“完整的 DevOps 平台”， [GitLab](https://www.gitlab.com) 收购了两家安全公司——[Peach Tech](https://www.peach.tech/)和[fuzz it](https://fuzzit.dev/)——为其长长的 DevOps 和 DevSecOps 能力列表增加了 fuzzing。Peach Tech 是一家安全软件公司，从事协议模糊测试和动态应用安全测试(DAST) API 测试，而 Fuzzit 则通过覆盖引导的白盒测试提供连续的模糊测试。

通过此次收购，GitLab 将能够向其用户提供全方位的 fuzzing，GitLab 产品总监 David DeSanto 解释说，此次收购超越了知识产权或人才。

“我们不只是在进行收购，我们只是在进行人员或知识产权收购。我们实际上正在收购这些公司。他们将在 GitLab 工作，帮助集成，并继续他们专注的任务，让 fuzzing 成为最容易使用的工具，”DeSanto 在接受采访时说。

Fuzzing 包括向应用程序发送伪随机有效载荷，并监控内存泄漏和崩溃等情况，这可能会提供一种渗透手段。Fuzzing 分为两种一般类型，白盒和黑盒，白盒涉及访问源代码，而黑盒需要将这些有效载荷发送到编译和运行的应用程序。

通过收购，GitLab 将能够提供两种类型的 fuzzing，Fuzzit 提供白盒，而 Peach 提供黑盒，DeSanto 表示，这将使 GitLab 客户能够看到他们以前无法获得的应用程序。

“通过提供这种模糊范式的两个方面，我们将帮助我们的客户比现在更好地发现他们应用程序中的漏洞，”DeSanto 说。“模糊化一直是开发人员面临的挑战之一，因为要想取得成功，你必须成为该工具的专家。这就是 GitLab 改变这种模式的地方。我们将 fuzzing 带给开发者，让它变得易于使用和接近。”

到目前为止，GitLab 用户必须使用第三方集成在其持续集成(CI)管道中运行 fuzzing 工具，但这种集成将把所有东西都集成到一个应用程序中。

“所有的结果仍然在那些第三方工具中，这些工具实际上没有集成到我们的漏洞管理中，因此必须同时使用两种不同的产品。随着这些完全集成，这种需求就消失了。我们将能够在一个单一的环境中工作，就像他们现在可以进行依赖性扫描等一样，”DeSanto 解释道。

DeSanto 说，目前，将这些工具集成到 GitLab 的计划是在 10 月份之前发布“最小版本”,包括 CI 配置、Go fuzzing 和 DAST API 功能。GitLab 从 Go 支持开始，因为该公司遵守 dogfooding 自己的工具，并使用 Go 开发自己的许多应用程序，但这些功能将支持该公司支持的所有 16 种语言。“可行成熟度”版本预计将于明年年初发布，在用户界面中进行配置，而不是 YAML，结果在作为关键功能提供的仪表板中提供，使工具易于使用，并随时可以取代第三方替代品。

总的来说，此次收购是 GitLab 继续推进 DevSecOps 的一部分，DeSanto 将 DevSecOps 设计为简化开发和将安全性融入过程的东西。

“安全是一项团队运动。只有每个人都参与，你才会赢。我们正在帮助将安全性转移给开发人员，并提供他们可以运行的工具，他们可以理解输出，并可以修复问题。这对他们有利，因为他们能够简化他们的开发，而不是等到一个周期结束才得到那些发现。它还使安全团队能够更积极地参与开发过程，因此我们不仅提供开发人员可以理解的工具，还提供安全团队可以理解的工具，然后他们可以一起合作开发更安全的应用程序，”DeSanto 说。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过 Twitter 或脸书访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈:feedback@thenewstack.io.

GitLab 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>