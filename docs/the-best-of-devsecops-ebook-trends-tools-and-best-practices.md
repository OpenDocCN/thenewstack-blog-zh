# DevSecOps 电子书精华:趋势、工具和最佳实践

> 原文：<https://thenewstack.io/the-best-of-devsecops-ebook-trends-tools-and-best-practices/>

DevSecOps 是自始至终使安全性成为整个软件交付过程的一部分的文化和实践——一个与整体弹性和 DevOps 最佳实践越来越相关的规程。

开发运维的先驱们正在优化部署速度。他们必须专注于配置硬件以适应软件架构。在最近的站点可靠性工程(SRE)运动之前，弹性并不是传统的 DevOps 指标，正如在转向 DevSecOps 之前，安全性也不是传统的 DevOps 指标一样。DevOps 作为一种文化运动，专注于效率、速度、功能开发和持续发展。SRE 专注于弹性和在不中断或影响性能的情况下处理使用高峰或云提供商服务中断的能力。

传统上，安全处于外部，在文化、组织和工作流上与开发团队、运营团队、开发运维团队和 SRE 团队隔离。这些团队处理了不同的成功标准和不同的绩效指标。然而，开发运维、SRE 和安全性之间存在明显的重叠，因为应用编程接口(API)端点变得更加脆弱，需要更好的风险管理。这将我们带到了 DevSecOps 的新世界。

现代架构迫使 DevOps 和 SRE 团队之间进行更深层次的整合。同样的强制集成正在扩展到安全团队。这是德夫塞科普斯。

编程基础设施，也称为基础设施即代码，将它们绑定在一起。它提供自动化、度量和分析，以持续发展开发运维、SRE 和开发运维实践。所有三个学科的指标都有重叠。例如，客户票证是 DevOps 中的一个指标。在 DevSecOps 中，客户支持安全票证是一个指标。在减少不同学科中的错误和漏洞数量方面有着共同的利益。

例如，可以通过自动分离那些没有加载到内存中因而不需要修复的漏洞来减少漏洞。自动化漏洞检测只是如何更容易地发现异常的一个例子，使整个基础设施更能抵御攻击。

持续开发团队现在必须从一开始就关注集成安全性的原则。就弹性而言，横向扩展体系结构必须将服务视为拥有自己的保护层，但在松散耦合的环境中仍然相互连接的单元。

在我们的第一个“新堆栈最佳”选集中，我们挑选了过去一年中由新堆栈和我们的贡献者创作的六篇顶级帖子，并将其与我们自己的分析相结合，以提供关于 DevSecOps 和围绕它出现的趋势的更深入的观点。其结果是快速阅读，让您了解 DevOps 和云原生安全趋势的最新想法。在[Best Of DevSecOps:Trends in Cloud Native Security Practices](/ebooks/devsecops/best-of-devsecops-trends-in-cloud-native-security-practices/)电子书中，您可以找到:

*   DevSecOps 的主要和次要影响。
*   向左和向右转移安全性的原因。
*   为什么速度等于自动化。
*   声明式环境如何适用于 DevSecOps。
*   为什么从整体上处理安全问题可以获得更好的弹性。

那么，当我们讨论大规模应用程序开发、部署和管理时，弹性和可靠性指的是什么呢？它如何应用于 DevSecOps？可观测性和混沌工程浮现在脑海中。这两种方法都有助于组织使其服务更具弹性和可靠性。

混沌工程是由网飞边缘工具团队首创的概念。想法是:释放混沌猴子来制造混乱，以测试系统，并在这个过程中，使其更有弹性。可观察性允许 SRE 发现“未知的未知”，从而发现诸如延迟问题之类的问题。安全团队还需要分离信号和噪声的方法，因为更老的实践，如监控，实际上是针对遗留体系结构的，仍然存在。云原生架构采用以容器为中心的方法，需要一种不同的、更复杂的方式来查看分布式环境，包括自动化的安全反馈循环。

安全性和弹性通常是相互关联的，但是这种关系很少被讨论。即使向有成就的技术专家询问安全性，他们也会说安全性和软件开发生命周期(SDLC)是完全分开的。在最近的对话中，不止一位工程高管对新的团队发表了这样的评论。

由于基于容器的互联架构依赖于数据共享，DevSecOps 已经成为一种必然。每个服务都集成到更大的服务中。老式人类形式的通信与服务之间的自动化通信一样重要。

根据 [2019 年 DevOps 状态报告](https://puppet.com/resources/whitepaper/state-of-devops-report)，SDLC 中内置的安全性越高，组织对其安全状况就越有信心。根据[2020](https://puppet.com/resources/report/2020-state-of-devops-report/)[devo PS 报告](https://puppet.com/resources/whitepaper/state-of-devops-report)的状态，当安全被集成时，补救会更快。约 45%已将安全性集成到 SDLC 所有阶段的组织表示，他们可以在 24 小时内修复关键漏洞，而没有集成的组织中只有 25%能够做到这一点。

尽管如此，关于如何最好地将安全性集成到 SDLC 以及使用哪些安全工具的困惑仍然存在，即使在拥有成熟 DevOps 流程的公司中也是如此。许多从业者不确定他们是否应该依赖他们的云服务作为工具，使用第三方工具，开发自己的工具，或者主要依赖开源安全工具。

也许考虑 DevSecOps 的一个更好的方法是从使安全性成为工程师工作的一部分的角度出发。将安全性集成到普通的开发工作流中有其挑战性，但这比处理危机要好得多。平凡的生活是最好的生活。但是实现一个普通的，没有危机的生活需要大量的工作。这意味着坚持常规，建立行为最佳实践，控制你能控制的。

这是一种紧张和焦虑的状态，知道安全性不能作为最后一步被敲进软件开发中。当紧耦合架构被配置时，这可能就是过去的情况，需要花费几天甚至几周的时间来为记录系统的新版本做准备。

事实上，未来就在我们面前，通往真正韧性的道路也在我们面前。基于容器的架构在设计上是有弹性的。不可变的基础设施允许删除容器并用新的替换。这是一个受欢迎的改变，因为旧的方法不容易更换。可编程安全性和附带的 DevOps 实践是这条道路上的下一步。

DevSecOps 可能没有我们想象的那么复杂。它已经以现代建筑的形式存在了。现在，只需定义编排本身，就可以在设计上已经具备弹性的环境中自动化和扩展安全实践。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>