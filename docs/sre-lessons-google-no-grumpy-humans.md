# 没有暴躁的人类和其他来自谷歌的网站可靠性工程的教训

> 原文：<https://thenewstack.io/sre-lessons-google-no-grumpy-humans/>

“这真的是关于沟通、谦逊和信任，”谷歌工程师 [Liz Fong-Jones](https://www.linkedin.com/in/efong/) 在上个月 [New Relic 的](https://newrelic.com/) FutureStack New York 2017 上谈到网站可靠性工程的新兴实践时说。

这是为了建立长期的信誉。这是让 SRE 这个角色成功的基本要素，她在谈论其他人可以从她在谷歌的 SRE 经历中学到什么时告诉新遗迹的[马修·弗莱明](https://www.linkedin.com/in/matthew-flaming-6762b94/)。“如果你走进一个产品开发软件工程团队，然后说，‘你做错了 A、B 和 C，好像你必须解决这个问题似的，你真的不会在那里取得任何进展，”她说。

谷歌写了一本关于 SRE 角色的书。在谷歌的十年里，Fong-Jones 与八个团队合作过，从低级存储和大表到 Google Play Books 等面向客户的产品。她现在是谷歌 SREs 团队的一员。

弗莱明称 SRE 这个角色是“德沃普斯原则在一个特定角色中最纯粹的升华”他说，New Relic 正在努力为内部和客户定义和授权 SREs，谷歌正在推动行业最佳实践的发展。

那么你能从谷歌的 SRE 实践中学到什么呢？

## SRE 基础

技术技能是可以教授的，所以 Fong-Jones 寻找的是那些有能力理解他人并与其他人建立信任的工程师，以及有技术技能和好奇心的工程师。好奇心很难教，她说，但关键是要有对系统如何破坏感到好奇并真正试图理解发生了什么的工程师。

Fong-Jones 说，雇佣合适的人总是很重要的，但重要的不仅仅是简历。雇佣有生产意识的产品开发软件工程师也是关键。她说:“如果你在一个小组织中，并且你想有一个好的开始，你不能让那些违背你的可靠性目标的人把半成品扔到墙上，或者不想把度量标准写入他们正在编写的软件中。”

Fong-Jones 解释说，拥有一群互不关联的团队或单独的个人，以及拥有一个共同努力，在整个平台或公司范围内系统地改善事情的 sre 社区，这两者之间的区别在于，人们非常关心可靠性，并确保相互之间的最佳实践。

## 从一开始就是 SLO

从一开始就定义服务级别目标(SLO)非常重要，这是用于服务级别协议的指标。“因为如果你没有就什么是适当的可靠性水平进行理性的对话，”她说，“随着时间的推移，你会越来越难做到。”

Fong-Jones 说，如果你没有公布明确的 SLOs，那么你的 SLO 就是你的客户习惯看到的东西。这导致对你的架构的错误假设，或者它可能会失败。

她说，她的团队从乐于助人的态度开始。“哎，你已经有风险了，给你列举一下吧。”关注数据的数量在与内部客户的对话中很有帮助。对于那些不愿意定义新的和准确的 SLO 的人，Fong-Jones 有时会故意将他们的服务精确到他们的 SLO。由此导致的失败通常会让他们改邪归正。

她建议从风险矩阵开始。直接找团队的工程师，让他们列举风险。他们可能不喜欢谈论它，但他们知道他们担心什么。“每个人都知道骨骼埋在哪里，”她说。

一旦定义了风险，并设定了 MTTD(平均检测时间)、MTTR(平均恢复时间)、MTBF(平均故障间隔时间)，他们就可以谈论 SRE 的真正业务了。“这种风险是否可以接受？列举这些风险的成本是多少？我们认为适当的可靠性水平是多少？”她问。

她说，团队还需要定义一个服务水平指标，这是一个代表业务某些方面的关键性能指标。例如，在 200 毫秒内成功完成且没有错误的用户查询的比例。

## 没有暴躁的人类

Fong-Jones 承认，在对系统有足够的可见性和警惕疲劳之间取得平衡是很棘手的。“这不仅仅是在可靠性方面，而是对人类有什么影响？人类会因为一夜之间被传呼五次而变得暴躁吗？因为你不能依靠脾气暴躁的人来运行服务。”

为了做到这一点，她建议关闭尽可能多的提醒，把注意力放在经历痛苦的用户身上。她说，有时情况非常糟糕，一个团队可能会经常在 SLO 上失败。在这种情况下，重新评估你的 SLO 可能是合适的。

“你需要决定，‘好吧，这将是一个短期问题，我们知道我们需要做什么，它将在一个月内修复，让我们忽略任何事情，除了灾难性的失败，’”她说。评估什么是可接受的。“如果用户很满意，你的服务有 99%的可用性，而不是 99.9%，也许这就是你应该设置 SLO 的地方。也许您的业务需求在一开始就没有得到准确衡量。”

## 标准化是关键

好吧，废话。但这其中很大一部分是为了解决影子 IT 的问题，在影子 IT 中，工程师决定他们想要使用一个在已批准的软件之外的闪亮的新功能。为了在谷歌内部解决这个问题，他们采用了自下而上的方法。

例如，当他们注意到有六个不同的 API 在做类似的功能时，她会与工程师交谈。“好吧，你们自己讨论，想办法合并。如果你正在开发两个相互竞争的东西，你说，“好吧，让我们把它合并成一个项目，”她说。

她说，谷歌鼓励他们的工程师“向左看，向右看，看看其他人在做什么”。又回到了简单。他们奖励那些关闭项目的人。在谷歌，这不会让你受到惩罚。那是会让你升职的事情。

Fong-Jones 认为奖励从事可靠性工作的人非常重要。奖励将系统作为一个整体来思考的人，并确保你的职位阶梯奖励从可靠性角度来看是什么使产品变得优秀的思考，并有一个实践社区。

“你是在奖励那些制造了一大堆没人能维护的复杂东西的人吗？”她问。“或者你奖励人们做最简单的事情，即使这意味着不写任何新的软件，只是整合现有的东西。这对于软件工程师来说很有价值，但对于网站可靠性工程师来说更有价值。”

她说，如果做得好，会非常有益。就像家得宝的副总裁在感恩节那天给谷歌的客户可靠性工程总监发短信一样。“信息不是，‘哦，我的上帝，一切都着火了。’它说的是，“谢谢你，我们有史以来第一次过了一个安静的感恩节。”。"

谷歌是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>