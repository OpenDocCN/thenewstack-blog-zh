# 你怎么知道你的待命系统是不是坏了？

> 原文：<https://thenewstack.io/how-can-you-tell-if-your-on-call-system-is-broken/>

俗话说，如果它没坏，就不要修理它。但是，当你与人和过程打交道时，你不知道事情在起作用，直到你问——有时是反复地问。

甚至在技术方面，你真的不知道什么坏了，除非你用监控和可观察性来询问你的系统。这就是我们随叫随到的原因——响应日益不可预测的技术和用户。

随叫随到是软件工程师面临的最可怕的任务之一，但也是了解和改进代码的最佳机会之一。它们可以是摧毁灵魂的睡眠中断器，也可以是增加客户价值的积极体验。这就是为什么这是开发人员在[求职面试中最常问的问题之一。](https://thenewstack.io/how-to-make-tech-interviews-suck-less/)

那么，你如何识别你的随叫随到过程中的缺陷呢？你如何持续改善传呼机值班体验？你如何停止增加[现有的倦怠](https://thenewstack.io/how-to-recognize-recover-from-and-prevent-burnout/)？在今年的 [LeadDev Live](https://leaddev.com/leaddevlive/) 上，一个由站点可靠性和工程领导组成的小组分享了如何打造开发人员真正想要参与的高效随叫随到流程的经验。

## 需要一个良好的反馈回路

最好从“好”的基本定义开始。 [Stevi Deter](https://twitter.com/smd) 是平台即服务 [DexCare](https://www.dexcarehealth.com/) 的首席软件工程师。在多年协调复杂系统集成的全天候支持后，她将一个成功的随叫随到流程定义为一个正反馈循环。她告诉与会者，当随叫随到的流程被孤立时，当页面没有被捕获并纳入整体工程流程和优先级时，流程就会失败。

“这将完全打破你的能力，以捕捉你需要改进你的产品，你的产品实际上在哪里被使用，以及理解你如何影响你的工程师在他们的日常生活中能够支持你的产品的重要性，”Deter 说。

没有什么比那些随叫随到却无能为力的重复页面更令人沮丧的了。

“随叫随到不应该被视为某种惩罚，”她说。“这实际上是成功的优势之一，因为你实际上需要支持你的产品。这确实是找出系统问题的最丰富的来源之一。

“因此，如果你没有抓住这一点，如果你没有一个让随叫随到的工程师感到有能力实际改善整个系统的系统，无论是对他们自己，对他们的其他随叫随到的工程师，还是对整个组织，那么你就错过了。”

[SeatGeek](https://seatgeek.com/) 的高级工程总监菲尔·卡尔卡多同意迪特尔的观点:“认为事情是一样的或者变得更糟的想法是扼杀这样一个过程的原因。”

## 为团队量身定制时间表

为了了解你的随叫随到的反馈回路的质量，你必须首先了解[工程师的工作量](https://thenewstack.io/mary-poppendieck-on-why-you-should-just-burn-your-backlog/)，Rakuten[的现场可靠性工程(SRE)经理](https://rakuten.tv/uk)Ricardo ara vena[认为。他建议在每次换班后进行交接，并询问:](https://twitter.com/raravena80)

*   主要的警报是什么？
*   您以前见过多少次这种特定警报或事件？
*   有什么你能解决的吗？
*   有什么你修不好的吗？

阿拉维纳说，平衡分担的工作量很重要。当然，在一个更大的组织中，你可能有六个或更多的人轮流工作，但是在一个初创公司中，你可能只有两个人。这两者可能更容易沟通，但随着你在国际上的扩张，你更有能力围绕时区来制定随叫随到的流程，甚至允许在合理的八小时轮班中提供 24 小时服务——这意味着没有人会在凌晨 2 点被传呼

> “当你遇到突发事件时……只要确保事情真的会因此而发生。因此，如果你在半夜醒来，发现这是一个重大事件，你会有这种感觉，“好吧，这很糟糕，但现在我们实际上要找出如何不让这种事情再次发生在我们身上。”"

—Stevi Deter，DexCare @smd 首席软件工程师

随叫随到的时间表会随着公司规模的变化而变化。calado 说，在疫情期间，他的现场活动门票零售商雇主不得不减少团队规模，同时仍然为经常不可预测的流量提供随叫随到的支持。

Deter 的团队还必须想办法优先处理随叫随到的工作。今年早些时候，DexCare [作为孵化器](https://www.hcinnovationgroup.com/finance-revenue-cycle/health-it-market/news/21215397/providence-digital-health-spinout-dexcare-announces-20m-in-series-a-funding)从更大的普罗维登斯数字健康公司分离出来。它从三个由六名随叫随到的工程师组成的团队变成了只有一个六人的团队——支持相同数量的软件，用户群不断增长。

“对期望和他们在一定时间内能够实现的目标要现实一些。还要考虑它会如何影响你的整个过程，”她说。

迪特尔鼓励观众提问:“你对一个随叫随到的人有什么期望？你能指望他们也做冲刺工作吗？”

DexCare 减轻三倍工作量的一个方法是让团队专注于偿还技术债务。

他们还意识到，当他们结束周末的轮班时，对周一有一种共同的恐惧。他们尝试在星期五休息。这产生了戏剧性的积极效果，因为队友们在周五中午结束了工作，并在一周的待命后获得了周末的休息时间。

## 为组织量身定制流程

“随叫随到”必须是一个不断发展的过程， [Jaime Woo](https://twitter.com/jaimewoo) 指出，他是网站可靠性教育家、正念教练，也是“[每个 SRE 人都应该知道的 97 件事](https://www.oreilly.com/library/view/97-things-every/9781492081487/)的合著者

“继续改吧。位置很重要。团队规模很重要。需求很重要。我不认为总会有谁会关注它的发展，”他补充道，以确保“你有那种灵活性和凝聚力。”

calado 只在中小型企业工作过，那里的随叫随到流程总是不断变化。他告诉听众，随叫随到流程的事件管理方面可能非常简单，但“随叫随到的部分有点复杂，因为它与人们的个人生活和期望以及公司的幸福有很大关系。”

他警告不要尝试全公司范围的随叫随到策略，而是让团队自己决定。毕竟，他们应该知道每个人的最佳工作时间表。他的许多 SeatGeek 同事都在以色列，那里的周末是周五到周六，这意味着团队提前一天改变了待命轮换。

“你需要灵活，即使是在日常工作中，也要想出对每个团队来说什么是最好的，”calado 建议道。

当然，永远不要呼叫新父母是一个很好的提醒。正如 [Honeycomb](https://www.honeycomb.io/?utm_content=inline-mention) 创始人兼首席技术官 [Charity Majors 所说](https://thenewstack.io/call-rotations-best-wake-devs-middle-night/):“你不应该在半夜被一件以上的事情吵醒。”

## 与事件响应和事后分析同步

没有什么比感觉没有效率更令人沮丧的了。你需要一个计划。对阿拉维纳来说，成功随叫随到的第一步是与你的团队建立沟通渠道。这可以是定期的回顾和移交，以及类似 Slack polling 这样的匿名反馈工具——当然，所有这些都由事件响应经理提供支持。

您需要关注[关键开发运维指标](https://thenewstack.io/googles-formula-for-elite-devops-performance/)，如[平均修复时间(MTTR)](https://www.atlassian.com/incident-management/kpis/common-metrics) 甚至是检测问题的平均时间。领导总是想知道随着时间的推移，这些是变好了还是变坏了。

但你也应该留意模式，比如是否会出现相同类型的警报，或者工程师是否无法解决重复出现的事件。跟踪和避免假阴性对[避免精疲力尽](https://thenewstack.io/this-cant-be-normal-the-tech-industry-after-a-year-of-burnout/)同样重要。

calado 说，汇报和事后分析是必要的，可以让实践成为一种习惯。定期询问队友随叫随到发生了什么，即使没有发生什么大事。您可能需要调整您的警报系统，以确保您没有忽略事故。

他建议你定期创建典型事件的时间表，并尝试观察主题。他指出，这有助于消除问题讨论的个人化，“因此你可以更自由地提出批评，而不是认为你在谈论同事或朋友。”

总是问:在这个过程中你会改变什么？这在一对一的情况下尤其有效，因为每个人都有机会发言。

永远记住，随叫随到的流程有可能增强团队的力量。对吴来说，这一切都取决于你和你的团队选择如何构建你的体验:

“你可以讨厌它——反正你还是得做。或者你可以学会不一定爱它，而是从中学习一些东西。为什么我们会收到这些警报，或者为什么人们会有这种感觉？我认为通过这种好奇心，通过这种谦逊，一些伟大的事情将会发生。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>