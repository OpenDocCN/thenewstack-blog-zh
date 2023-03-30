# 现场可靠性工程在微服务中的作用

> 原文：<https://thenewstack.io/the-role-of-site-reliability-engineering-in-microservices/>

你总能发现技术领域的热门职位:它们是 10 年前不存在的。虽然网站可靠性工程师(sre)在十年前确实存在，但他们大多在谷歌和少数其他硅谷创新者中。然而今天，SRE 的角色无处不在，从优步到高盛，每个人都在从事保持网站在线和稳定的业务。

虽然 sre 是行业中的热门人物，但他们在微服务环境中的角色不仅仅是像花生酱和果冻一样的天然搭配。相反，尽管 SREs 和微服务在全球软件公司内部并行发展，但前者实际上让后者的日子要艰难得多。

这是因为 sre 的生死取决于他们维护和优化的整个系统的完整堆栈视图。该角色将开发人员的技能与管理员的技能结合在一起，当事情完全失控时，产生一个能够在生产环境中调试应用程序的员工。

由于谷歌工程师基本上发明了这个角色，该公司提供了大量关于他们如何管理每天处理多达[1000 亿次请求的系统的见解。他们将可靠性归结为一个基本要素，与速度和创新同样重要。](https://cloudplatform.googleblog.com/2016/04/lessons-from-a-Google-App-Engine-SRE-on-how-to-serve-over-100-billion-requests-per-day.html)

“第一步是认真对待可靠性和可管理性的重要性。谷歌 SRE 主管[托德·安德伍德](https://www.linkedin.com/in/todd-underwood-501a02/)说:“我与之交谈的人花了很多时间考虑功能和速度，但他们没有花时间考虑可靠性这一特性。

安德伍德说，可靠性和可用性应该在项目的每一个层面上加以考虑。他举了一个例子，Gmail 失败的原因是退回到纯粹的 HTML 体验，而不是完全停止。“我就拿难看的 HTML[版本]吧，不过可以看邮件。可用性是一个特性，也是最重要的特性。如果你没空，就没有用户来评价你的其他特点。组织需要选择优先考虑可靠性。”

安德伍德指出，每个组织都是不同的，谷歌遇到的一些问题并不典型。但是他提倡一些更全面的实践。

“对于分布式应用，我们运行某种类型的 [Paxos](http://www.cs.yale.edu/homes/aspnes/pinewiki/Paxos.html) 一致系统。我们有一整个[章节](https://landing.google.com/sre/book/chapters/managing-critical-state.html)关于分布式共识。安德伍德说:“这看起来像是一门计算机科学，但实际上，如果你想拥有流程并知道哪些流程在哪里，没有 Paxos 是不可能的。Paxos 是分布式共识收集算法，通常用于解决分布式系统中可能出现的不一致问题。

然而，安德伍德强调了 SRE 工作的另一个重要方面:能见度。当微服务在基于云的服务器、容器和数据库的不断变化的生态系统中扔出数十亿个数据包时，找出哪里出了问题对于解决任何类型的问题都至关重要。这就是 SRE 工作的所有方面发挥作用的地方。

谷歌最近推出了一些专门针对这类工作的工具。

过去几年来，整个市场一直在有意转向微服务。我们从 Kubernetes 和 Istio 以及从数据中心向云的总体迁移中看到了这一点。前进的道路上有一些挑战。如果你有 100 个容器，像在一个整体上做堆栈跟踪这样的事情就变得非常困难。谷歌云平台产品经理[摩根·麦克林](https://www.linkedin.com/in/morganmclean/)说。

> “要了解整个应用的健康状况，并了解交易如何流经所有这些不同的微服务，您必须有一个系统来帮助您导航。你需要的是能够从交易角度思考的东西，”AppDynamics 的 Matt Chotin 说

为了补救这一点，谷歌最近发布了 [Stackdriver Trace](https://cloud.google.com/trace/) 、 [Stackdriver 调试器](https://cloud.google.com/debugger/)和 [Stackdriver 剖析器](https://cloud.google.com/profiler/)。这些工具听起来像传统企业供应商的老派测试和操作工具，这是有原因的:它们执行开发人员和操作人员习惯的更传统的故障排除任务，但重点是微服务和在云中执行这些任务。

Stackdriver Profiler 处于测试阶段，但允许对运行在云内部的应用程序进行直接的 CPU 利用率监控，而 Stackdriver Debugger 提供了一种在基于云的微服务应用程序中插入断点的方法，Stackdriver Trace 提供了 McLean 提到的全栈跟踪功能。

Stacktrace Profiler 的 McLean 说:“这对于总体性能的提高和成本的降低都是非常有效的。“Snapchat 进行了测试，在收集数据的一天内，他们意识到一段非常小的代码(我认为是正则表达式)实际上消耗了大量的 CPU，这段代码甚至不应该出现在 Profiler 中。这可能发生在任何人身上。谷歌就是这样。Snapchat 的演示很好地展示了这种分析技术的威力。”

“没有这样的工具，这通常是不可能的。追踪正在成为一种普遍的行业做法。在我们的产品中，性能分析和产品调试更加独特，”McLean 说。

## 新思维

[AppDynamics](https://www.appdynamics.com/) 的技术推广高级主管 [Matt Chotin](https://www.linkedin.com/in/mchotin/) 也关注新型工具。他说，一旦从整体应用转移到微服务，团队需要重新思考他们确定整个应用健康状况的方式。

“你们有无数的系统。微服务的乐趣在于，您可以选择适合特定产品的堆栈。每样东西都可能有自己的监控方式，自己的衡量标准，等等。为了了解整个应用的健康状况，并了解事务如何流经所有这些不同的微服务，您必须有一个系统来帮助您导航。你想要的东西会从交易的角度来考虑，”乔丁说。

Chotin 说，工程师不应该考虑服务是上升还是下降。“您的 DevOps 团队关心查看服务以了解总体可用性，但至于您是否正确地为业务提供服务，您需要能够贯穿整个生态系统的监控，从应用程序代码到基础架构代码，”Chotin 说。

谷歌的安德伍德说，SRE 在公司内部的总体目标是限制他们的增长，同时促进谷歌的增长。这意味着，正如 Underwood 所说，“对我们来说，SREs 与 Google 的次线性增长是非常重要的。我们希望继续提高效率。”

他说，为此，谷歌特别关注他们的应用程序。“我们专注于我们所从事的特定服务的深层次。从事谷歌文档的团队，从事广告服务的团队；每个团队都非常关注这些服务的细节。与此同时，我们的 SRE 团队构建了供所有 SRE 团队使用的通用基础架构。”

[AppDynamics](https://www.appdynamics.com/) 和[谷歌](https://cloud.google.com/kubernetes-engine)是新堆栈的赞助商。

Eberhard Grossgasteiger 在 [Unsplash 上拍摄的特写图片。](https://unsplash.com/search/photos/layer?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>