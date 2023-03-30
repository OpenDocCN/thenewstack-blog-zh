# 现场可靠性工程的作用，今天和明天

> 原文：<https://thenewstack.io/the-role-of-site-reliability-engineering-today-and-tomorrow/>

[甲骨文今天和明天 SRE 的作用](https://thenewstack.simplecast.com/episodes/oracles-vision-of-the-role-of-an-sre-today-and-tomorrow)

随着软件开发覆盖比过去更多的领域，现场可靠性工程(SRE)在 DevOps 中的作用变得更加重要。自成为 DevOps 的一部分以来，sre 一直被要求在整个生产管道环境以及软件和应用程序部署的后期部署阶段发挥非常积极的作用。当云原生平台和将遗留系统移植到云环境中，或者同时将应用程序部署到内部和云环境中时，SRE 的责任变得更加重要。

在 5 月底在巴塞罗纳举行的 [KubeCon + CloudNativeCon](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2019/) 会议期间，由 New Stack 的编辑总监 Libby Clark 主持的本期 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中，来自软件巨头和服务提供商 Oracle 的三位 SRE 和工程思想领袖显然有很多关于 SRE 的角色和 DevOps 工具的话要说。来自甲骨文的播客嘉宾有:

虽然由一个“运营人员”或团队管理数据中心的日子已经一去不复返了，但 SRE 仍然可以在凌晨 3:00 接到应用程序崩溃的可怕电话或寻呼。但与此同时，许多类似操作的任务应该在不久的将来实现自动化，这样 sre 就可以将更多的时间花在他们通常最喜欢做的事情上:直接从事代码开发。

退一步说，Boxell 提供了一些关于可观察性的上下文和对 SRE 角色有帮助的其他工具，比如提供对日志、跟踪数据和基本指标的洞察的工具。他说，他通过积极确定最佳实践和“同类最佳的开源解决方案”来做到这一点，他的团队在 Oracle 的 Kubernetes 平台上构建了这些解决方案。

“我基本上一直在浏览[云计算原生计算基金会]的产品组合，看看哪些项目是人们最常使用的，从我们的用户那里获得关于他们正在使用哪些项目的反馈，然后只是经历实施它们的过程，”Boxell 说。“我们还确保所有东西都检查通过并正常工作，然后我们试图想出人们可能会在生产中实际使用它们的场景。”

作为一名工程师，Fontaine 说他在系统的可观察性中寻找的是“理解我想要多少信息之间的某种平衡”

“每当出现问题时，我总是希望获得尽可能多的数据。但从环境角度来看，这并不总是可行的，因为存储所有这些信息需要成本，”方丹说。“因此，找到工具的正确平衡，并能够计算出我可以在哪个区域存储多少(这是关键)。此外，我还可以利用其他平台服务来降低成本，但我仍然拥有我想要的可见性。因此，通常，当我为自己构建服务，或就其他团队正在尝试构建的内容提供建议时，我会寻找一些解决方案，这些解决方案允许您在您的环境中的群集上就地运行基数和较低的保留率，然后利用平台服务获得更长的保留率，比如我可能会推出我的日志或我的遥测和对象存储或类似的东西。”

自动化还将继续发挥越来越大的作用，除其他外，通过减轻 SRE 在生产流水线中的角色以及操作任务中的更平凡的任务。Reeve 描述了如何有更多可用的工具集，例如，用于潜在的自动化补救问题。

现在有更多关于“自动化管道和测试，试图预先防止问题”的讨论。我认为像 [Istio](https://istio.io/) 和服务网格跟踪这样的事情很有趣，我们现在有了一种有趣的工具来源。所以还是那句话，一切都是为了应用，对吧？”里夫说。“我们可以了解应用程序的哪些组件在相互通信，我们可以了解哪些容器实际上是应用程序的一部分。因此，我认为我们现在已经有了一组有趣的数据和关系，可以在另一个抽象层次上推动更多的自动化。”

[https://www.youtube.com/embed/-tHzmvmuni0?feature=oembed](https://www.youtube.com/embed/-tHzmvmuni0?feature=oembed)

视频

### 在这个版本中:

[1:01:](https://thenewstack.simplecast.com/episodes/oracles-vision-of-the-role-of-an-sre-today-and-tomorrow?t=1:01)SRE 工作台
[6:39:](https://thenewstack.simplecast.com/episodes/oracles-vision-of-the-role-of-an-sre-today-and-tomorrow?t=6:39) 当前刀具堆栈。
[11:37:](https://thenewstack.simplecast.com/episodes/oracles-vision-of-the-role-of-an-sre-today-and-tomorrow?t=11:37) Istio 进行调试，进行实验。
[14:05:](https://thenewstack.simplecast.com/episodes/oracles-vision-of-the-role-of-an-sre-today-and-tomorrow?t=14:05) 自动化。
[18:28:](https://thenewstack.simplecast.com/episodes/oracles-vision-of-the-role-of-an-sre-today-and-tomorrow?t=18:28) 未来的 SRE。
[23:34:](https://thenewstack.simplecast.com/episodes/oracles-vision-of-the-role-of-an-sre-today-and-tomorrow?t=23:34) 客户反应。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>