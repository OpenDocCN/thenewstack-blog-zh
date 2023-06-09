# 专家对现场可靠性工程的状态进行评估

> 原文：<https://thenewstack.io/experts-weigh-in-on-the-state-of-site-reliability-engineering/>

在当今世界，软件和系统的可用性、性能和容量对于交付客户体验和创造收入至关重要。研究表明，仅仅一次糟糕的客户体验就可能导致客户流失。因此，组织正迅速雇用现场可靠性工程师(SRE)来支持运营和推进 SRE 流程。

任何人都可以从谷歌阅读 SRE 的经典著作，从理论上理解它，但是一个高绩效的 SRE 团队在实践中是什么样子的呢？在最近一次名为“[SRE 状态](https://www.youtube.com/watch?v=FI1ArDxAsnE)”的[Techstrong DevOps.com](https://www.youtube.com/watch?v=FI1ArDxAsnE)圆桌会议期间，Chronosphere 的高级软件工程师、【优步】和 Tumblr 的前 SREMatt Schallert 解释说，有效的[站点可靠性工程](https://thenewstack.io/devops-institute-checks-the-pulse-of-sre/)需要对两个方面做出承诺，人和实践

“你需要从整体上考虑系统的人，例如如何维持正常运行时间和衡量服务水平目标(SLO)，特别是在日益复杂的环境中，”他说。“你还需要公司入股。”这意味着承认组织可以在管理风险和正常运行时间目标方面做得更好，甚至愿意停止推出新功能。一项艰巨的任务。

Schallert 加入了 Techstrong Group 的主持人 Michael Vizard，就现场可靠性工程如何从一个时髦词汇变成一个令人垂涎的职位，以及可观察性在 SRE 的日常生活中所扮演的角色进行了热烈的讨论。参与讨论的其他人包括 Harness 的混沌工程负责人[乌玛·穆卡拉](https://www.linkedin.com/in/uma-mukkara/)、strongDM 的客户工程经理[约翰·特纳](https://www.linkedin.com/in/john-turner-12176926/)和 Fairwinds 的客户可靠性工程师 SRE[农·比德尔。](https://www.linkedin.com/in/nungbedell/)

[https://www.youtube.com/embed/FI1ArDxAsnE?feature=oembed](https://www.youtube.com/embed/FI1ArDxAsnE?feature=oembed)

视频

## **SRE 的演变**

谷歌高级副总裁本·特雷诺·斯洛斯因在 2003 年建立了第一个 SRE 团队来应对一些挑战而广受赞誉:

*   网络级的可靠性需求，几乎没有停机时间或延迟
*   大规模分布式基础架构(在公共云普及之前)
*   缺乏代码驱动可靠性管理的开发运维

从那以后，复杂性加速了。云计算、微服务、持续交付渠道和自动化是保持商业竞争优势的核心。

“维持正常运行时间是一个巨大的需求，”Mukkara 说。“系统变得复杂，因此各种规模的组织都在建立 [SRE 实践](https://thenewstack.io/where-the-site-reliability-engineer-role-overlaps-with-devops/)，并获得 SREs 蓬勃发展所需的东西。”

Mukkara 已经看到许多开发人员试图成为 SREs，他认为这是 SRE 函数创新的一个好迹象。特纳注意到更广泛的兴趣。

他说:“我见过对基础设施感兴趣的优秀开发人员，也见过对基础设施感兴趣的人，包括来自 IT 和运营方面的，对如何部署、如何了解正常运行时间以及衡量 SLA 和 SLO 感兴趣的人。”

他不认为软件工程师必须是优秀的开发人员，因为有很多工具可以提供帮助。相反，他指出，任何有兴趣成为 SRE 的人都必须对事物如何工作、事物如何连接在一起有兴趣，并对技术有普遍兴趣。

因为这份工作的旅程有些独特，圆桌会议的参与者都认为没有必要获得特定的 SRE 认证。然而，他们承认，增加关于调试和处理人为失败的面试问题可以提高招聘成功率。

Schallert 说，“这绝对是一个先有鸡还是先有蛋的问题——你通过看到它来获得体验，但你必须先迈出第一步才能看到它。”

专家们希望有更多的人，包括妇女和代表性不足的少数民族，能够应用可转移的技能。

“多样性将继续拓展我们的思维，”特纳说。Schallert 补充说，“作为一个行业和一个角色，我们有责任抓住这个机会，帮助人们提高水平。这是应该做的事情，对每个人都有好处，而不是排斥他人。”

## **建立 SRE 函数**

谷歌 SRE 图书定义是流行的，但大多数组织没有谷歌大小的问题，所以他们不需要复制谷歌 SRE 功能。

“这实际上是一件好事，”Schallert 说。“组织正在意识到如何将 SRE 实践应用到他们自己的业务和组织需求中，以了解这对他们意味着什么。”

该小组就 SRE 职能是否存在最佳模式、如何吸引工程师以及自动化和工具如何适应等问题发表了见解。

“有不同的模式——嵌入式 SREs 和专用的独立功能,”Schallert 说。“当我还是优步的 SRE 时，我看到了两者的结合。在所有情况下，推动 [SRE 成为开发团队和 SRE 团队或嵌入式 SRE 之间的合作伙伴](https://thenewstack.io/todays-site-reliability-engineers-are-more-healers-than-fire-fighters/)非常重要。”

如果没有这种负责任的伙伴关系，人们可能会把软件扔到墙外，让另一个团队拥有部署、可靠性和一切。

“鱼和熊掌兼得的方法是让这些团队成为合作伙伴，并就他们的运营模式达成一致，”Schallert 说，他建议 SREs 应该帮助团队前进，而不是在某个时候取得所有权。

“让两个团队都参与到管理软件的整个端到端生命周期中来，”他说。

穆卡拉表示同意。“你一开始是一个独立的职能部门(工程团队和 sre)，但最终，成功将真正取决于责任是否分散到所有团队，”他说。

特纳说，当“我们有 DevOps，然后我们有 SRE，他们执行两种不同的功能，但有很多交叉时，他看到了重叠。我认为他们将慢慢开始分离，但随后会弄清楚中间那块在哪里，以及谁拥有什么。”

像敏捷开发实现一样，很少有组织会有相同的 SRE 实践或过程。根据专家的说法，团队必须找出最适合他们的方法。就 SRE 愿景达成一致，然后记录或编纂，是一个良好的开端，这包括定义服务级别指标(sli)和 SLO。

## **工具呢？**

圆桌会议参与者一致认为，工具支持团队责任。

“建立共享文化的一些方法是团队使用相同的工具，”Schallert 说。

例如，您的 SRE 团队可以开发开发人员和 sre 都使用的部署软件。或者，他们可以合作开发警报，积累监控系统方面的经验。由于每个人都使用相同的工具，并以相似的方式与应用程序交互，该工具集也有助于建立分担责任的文化。

“有许多内部工具是由开发团队和 SRE 团队创建的，”比德尔说。“这些公司还发布了大量开源工具，让整个技术社区受益。”

专家们提到[可观察性](https://chronosphere.io/platform/)和开放式遥测工具在支持目标和推动 SRE 实践走向成功方面非常有用。

“可观测性平台已经改善了很多，”穆卡拉说。“有很多关注点。过去几年，为了将可观测性提高到一个新的水平，已经进行了大量投资。”

就事件响应而言，自动化是关键。

“SRE 的功能是确保你做更少的手工工作，最终做大量的自动化工作，”Mukkara 说。

他鼓励团队实践混沌工程——一个涉及故意造成故障的概念，以确保分布式系统的设计能够保持高水平的可用性。

## **待命服务**

在许多公司，轮流值班是 SRE 的一个典型特征。Schallert 警告说，这并不意味着 SREs 应该回复每一页。

“如果 SREs 对每一页都有反应，他们就会成为专业的消防员，”他说，再次倡导分担责任。“这对他们或组织来说都不是好事，这也是为什么在过去几年中，开发人员也在转变为自己的服务。”

例如，他说，“如果有人正在部署一个新的版本或他们为之工作的某个功能，而该功能在推出时被破坏了，那么从事该功能的人更适合调试它，并参与到该事件中，而不是将其扔到墙上，让其他人来解决它。”

Turner 补充道，“在这种共同责任模式下，当你有了团队之间的理解、沟通和合作，你也会发现解决事故的时间更短。”

## **如何避免 SRE 倦怠**

SRE 团队可以负责解决大大小小的问题，排除重大事故的故障，并执行日常操作任务。因为可靠性对许多公司来说是一个高风险的问题，而且 SRE 有承担大量随叫随到工作的趋势，所以 SRE 是工程组织中最容易倦怠的职位之一。圆桌会议参与者认为，避免 SRE 倦怠的关键包括:

*   基于业务影响有效地理解和评估风险。
*   围绕 SLA 建立明确的目标和认同。
*   对问题进行优先排序，并决定哪些问题需要立即解决。
*   授权 sre 推迟时间表和优先级。
*   拥有一个人员充足的团队——而不是一个人独自承担责任。
*   合作解决问题。

Schallert 认为，组织开始量化对业务的影响是很重要的，因为它“使其他团队花时间解决这些问题变得非常容易。”

“你必须抑制住把所有事情都归类为热门、高优先级的冲动。比德尔说:“当每个问题都是你的问题时，你很快就会精疲力尽。

观察平台也可以帮助减少 SRE 的压力和倦怠。专家们一致认为，当事情失败或没有正确地从管道中出来时，日志记录、指标、警报和消息传递非常重要。

为了呼应它的重要性，Schallert 引用了一个真实世界的例子:“我们发现在 Chronosphere 中真正有用的一个模型是在整个管道中有相同的信号。在提交进入生产环境的过程中，它会经过一些环境，在这些环境中，我们拥有与生产环境中相同的警报和 SLO 监控。如果出现问题，它不会呼叫人，但它会告诉发布工具停止让该构建通过管道，直到修复被添加。”

工具可以让 sre 更好地了解、分类和理解问题。

“监控和可观察性的区别在于，”Schallert 说，“帮助您越来越多地缩小到问题的根本原因，并向您展示涉及哪些组件，而不是仅仅知道有问题。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>