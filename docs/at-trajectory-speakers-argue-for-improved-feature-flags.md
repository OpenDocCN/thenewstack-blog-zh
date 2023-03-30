# 在 Trajectory，发言人主张改进特征标志

> 原文：<https://thenewstack.io/at-trajectory-speakers-argue-for-improved-feature-flags/>

功能标志提供的众多好处已经存在多年了。然而，随着与发布软件相关的新挑战的出现，今天的 DevOps 团队要求功能标志比过去有更大的影响力。

简而言之，根据周二和周三在[launch Daryl](https://launchdarkly.com/?utm_content=inline-mention)的年度用户大会、 [Trajectory](https://launchdarkly.com/trajectory-2021/) 上几位发言人的说法，功能标志需要认真改进。

随着跨多云和内部环境大规模部署应用变得越来越普遍，相关的复杂性和提高发布节奏的压力只是当今挑战的两个例子。

大规模部署，尤其是那些支持大型迁移的部署，也意味着部署失败的后果可能会大得多。这种背景为更多的恐惧和害怕创造了条件，因为发布可能会出现可怕的错误。

## 团队希望对特性标志进行更严格的控制

今天，Trajectory 的几位演讲者强调，功能标志必须为开发运维团队提供更紧密、更直接的控制，包括如何分阶段激活、停用和发布应用功能。

LaunchDarkly 的代表阐明了在[轨迹](https://launchdarkly.com/trajectory-2021/)中的利害关系，作为领先的特征标志提供商，LaunchDarkly 在这些工具的使用中有明显的既得利益。

launch crystally 的首席执行官兼联合创始人 Edith Harbaugh 在她的会议发言中，讨论了 Gartner 的一份报告，该报告显示了绝大多数部署是如何失败的，以及为什么不一定是这样。正如她在演讲中所描述的那样，能够更好地适应当今多云发布挑战的功能标志已经被证明可以显著降低发布失败率。

Harbaugh 说:“在云时代，基础设施与提供一流的客户体验紧密结合，我们可以开始将应用程序的所有组件都视为功能。

“我们的最终目标是以更有效的方式向用户传递价值。无论是[针对 UI]还是后端数据库，特性管理都可以帮助我们实现这一目标。因此，当我们考虑逐步发布一项功能时，可以将其视为一系列阶段。”

## 采用功能标志的主要原因

风险缓解和部署稳定性是 DevOps 团队使用功能标志的首要原因，根据 11 月初与 Wakefield Research 联合发布的一份报告[的结果:](https://launchdarkly.com/state-of-feature-management/)

*   对于参与调查的 LaunchDarkly 客户来说，采用功能标志的三大原因(按顺序)是风险缓解、部署稳定性和测试程序管理。
*   非 LaunchDarkly 用户表示，他们标记的最大原因是(按顺序)部署稳定性、风险缓解以及运行 A/B 测试和衡量用户接受度之间的联系。

作为 LaunchDarkly 自我报告的“每天 20 万亿个标志”的用户之一，非结构化数据 SaaS 提供商相对论最近升级了为其开发客户提供的软件平台的功能标志。Relativity 的客户包括律师事务所和全球公司，他们有与法律合规性和隐私相关的非结构化数据问题，该公司的技术架构师和软件工程师 Dan Wells 在他的会议发言中说。

威尔斯说，相对论五年多前开始提供的功能标志已经升级，以满足今天的复杂需求。“我们基于自主开发的 SQL 数据库建立了一个功能系统，”他说。“它对我们来说工作了很长时间，但我们想要更复杂的东西。”

Wells 说，相对论采用的 LaunchDarkly 的功能标志功能帮助该组织安全地完成了一次重大迁移。

“我们知道我们不能进行大规模迁移，中断团队，被客户干扰——我们需要非常渐进地进行，”他说。“我们需要安全地进行，这样我们就可以在出现问题时拥有回滚功能。我们需要真正出色的可见性和控制跟踪，因为我们有 80 个应用程序和 50 个团队需要协调。”

## 特征标志和可观察性

![](img/0dd85fbafc21d0ef231a34b03dd4cfc6.png)

蜂巢的 Liz Fong-Jones 在她的轨迹演讲中。

三年前，领先的可观察性平台提供商 [Honeycomb.io](https://www.honeycomb.io/?utm_content=inline-mention) 的联合创始人兼首席技术官 [Charity Majors](https://www.linkedin.com/in/charity-majors) 表示，特性标志允许 DevOps 团队[不“在我同意之前，不要派任何人去写这段代码。”](https://thenewstack.io/launchdarkly-providing-a-control-switch-for-features/)

让我们回到本周的会议上，她的 Honeycomb 同事 Liz Fong-Jones 在她的演讲中描述了 Honeycomb 如何“每天”使用 Flash 来分离软件的部署和发布。

Honeycomb 的首席开发人员 Fong-Jones 表示:“我们有一个 pull request 模板部分，其中包括我们正在使用的功能标志以及我们的可观察性计划。

## 消除部署恐惧

与此同时，功能标志的使用是帮助消除发布软件时非常普遍的失败恐惧的一种方式，特别是在主要版本中，传奇书籍[《凤凰计划:一部关于它的小说，DevOps，并帮助你的企业获胜》](https://www.librarything.com/work/13405936/reviews/194038609)的作者 [Gene Kim](https://www.linkedin.com/in/realgenekim/) 说。

Kim 将特性标记描述为“一个架构上的突破”，提供了 DevOps 团队可以使用正确工具的方法，例如特性标记，来帮助在软件发布之前消除对失败的恐惧。

“我的建议是去寻找人们害怕部署的地方，并真正理解为什么，”金说。“我认为它会带你去很棒的地方，让一大群人说，‘谢谢你让我们拿着你的啤酒。’"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>