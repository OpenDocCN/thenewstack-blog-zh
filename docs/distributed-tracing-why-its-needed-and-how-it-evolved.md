# 分布式跟踪:为什么需要它以及它是如何发展的

> 原文：<https://thenewstack.io/distributed-tracing-why-its-needed-and-how-it-evolved/>

本系列中关于分布式跟踪的其他文章:

[Lightstep](https://lightstep.com/) 赞助本帖。

 [奥斯汀·帕克

Austin Parker 是 Lightstep 的主要开发人员，也是 OpenTracing 和 OpenTelemetry 项目的维护者。除了他的专业工作之外，他还教授大学课程，谈论 DevOps 和分布式追踪的所有事情，甚至还抽空开了一个播客。Austin 还是 O'Reilly Media 出版的《实践中的*分布式追踪*的合著者。](https://www.linkedin.com/in/austinlparker/) 

当您想到“跟踪”时，您会想到什么？这是软件开发中含义过多的词汇之一。有些人可能会想到“堆栈跟踪”，这是应用程序运行时发出的熟悉的文本块，显示代码中发生异常的位置之前的每个函数调用。其他人可能会更进一步，想到跟踪的*动作*——浏览来自不同服务和计算机的日志，实际上是跟踪请求在系统中移动的路径。非常方便的是，“分布式跟踪”实际上是这两个过程的组合——您可以将其视为分布式系统的“调用堆栈”,一种在单个请求从一台计算机流向另一台计算机时表示该请求的方法。

现在，如果这没有太多的意义，那是正常的——我刚刚给你讲了很多术语！本系列将从基础开始，揭开分布式跟踪的神秘面纱。今天，我要谈谈分布式系统——它们是什么，我们为什么使用它们，以及为什么分布式系统的兴起使跟踪变得如此重要。

所以，我们从头开始:代码。一台没有软件的电脑不能做很多事情——它可以做很多数学运算，非常快，但不能做很多其他的事情。软件只是给计算机的指令，而代码是人类可读的方式来表达这些指令。你可以用很多不同的编程语言编写代码——Java、C#、Go、JavaScript、Ruby 等等——但是你写的所有程序都有共同点。软件需要做一些对人们有用的事情。

20 年前，我们使用软件的方式与今天大不相同。我们没有“云”，互联网本身也是一项新兴技术。也就是说，自 20 世纪 70 年代以来，一种新型的软件系统被开发出来——分布式系统。现在，分布式系统的想法本身并不是新的，但是到了 20 世纪 70 年代，计算机技术已经发展到了可行的程度。在分布式系统中，计算机可以同时充当*客户端*和*服务器*，允许任务在不同的机器上执行。这些系统可以利用规模经济，允许将大量消息或数据存储在中央服务器上，轻量级客户端可以通过网络访问这些服务器。服务器负责处理数据的“重担”,而客户机只是简单地请求它们需要的东西。这一基本思想导致了更加规范化的形式，如三层或七层体系结构，甚至是对等体系结构，其中“应用程序”扩展成更加独立的服务，彼此协同工作以满足用户的请求。

***关于架构、层、层的一个说明:**形式上，“层”和“层”是不可替代的；层是指离散的物理单元，而层是软件组件的逻辑组。也就是说，这两个术语在对话中经常互换使用。*

随着高速互联网接入在美国和世界其他地方变得越来越普遍，软件架构也随之改变。网络浏览器不再是家用电脑上的专用客户端软件，而是开始充当运行在远程数据中心的更复杂的服务器应用程序的接口。反过来，这些服务器应用程序开始努力解决一个问题——扩展。不是那种你试图爬墙的扩展——尽管，我确信许多程序员是被逼到墙上试图让更多容量上线的！根据应用程序的设计方式，在负载下对其进行扩展可能是一项挑战。如果您的应用程序是*有状态的*(就像在中一样，它在内存中维护某种需要长期存在的“用户状态”)，那么增加容量可能会非常困难——尤其是当您需要更多的内存、存储或 CPU，而这些只能通过购买和安装更多的服务器来获得。这些挑战导致了技术的改变:创建无状态的服务，并将它们分解成更小的功能单元。如果你听说过“面向服务的架构”(或 SOA)，这就是它发挥作用的地方——能够将服务分成不同的部分，通过网络相互通信，使得更容易地扩展应用程序以响应需求成为可能。

正是在这个世界中，分布式跟踪找到了它的市场。如果您的应用程序分散在许多单独的服务器上，您需要一种方法来了解整个系统的行为和性能，而不仅仅是它的各个部分。应用程序的故障模式会发生变化——单个服务崩溃可能会导致系统中完全不同的部分出现意外或无法解释的行为。当这些故障发生时，您需要的不仅仅是记录到出错机器上的堆栈跟踪—您需要能够从头到尾看到整个请求。开发人员针对这个问题提出了许多不同的解决方案——集中日志记录、远程调试和各种其他工具来帮助诊断分布式系统的问题。然而，随着时间的推移，这些问题继续恶化。应用程序变得更加复杂，更加分散。新的部署平台和工具——虚拟机、容器、Kubernetes——使得创建更复杂的应用程序变得更加容易，其中包含了更多的活动部件。云使得在全球范围内轻松配置和扩展新的基础设施成为可能，而这一切导致了更多的复杂性和混乱。

让我们更详细地看一下——这些分布式系统会出现什么问题，我们为什么需要这些工具？

*   康威定律指出，不严格地说，一个系统将反映一个组织的结构方式。随着软件组织变得越来越复杂，他们的应用程序自然也会变得越来越复杂。如果你在一家非常大的公司工作，这应该是显而易见的——你可能在一个大得多的系统中工作，这个系统预计将与全国甚至世界各地的开发人员编写的其他服务协同工作。这使得理解您的服务中的故障如何影响其他服务变得很困难——反之亦然。
*   总的来说，开发人员不希望被单一的语言或技术所束缚。其中一部分是组织动态的结果——例如，整合来自被收购公司的团队或产品——另一部分是由于软件行业快速变化的性质。像 Go 和 Rust 这样的新语言继续得到想要编写高性能、可维护代码的开发人员的采用和青睐。Typescript、Python 和其他动态语言为不同的开发人员提供了各自的优势——尤其是那些从事数据科学的开发人员。随着浏览器成为主要的应用程序运行时，Web 开发人员也看到了他们工具复杂性的指数级增长。每个人都有不同的需求，希望使用不同的工具。
*   小团队也感受到了分布式系统的痛苦。即使只有一种语言和一个相对较小的应用程序，旨在构建为一组较小服务的“云原生”软件的兴起也让开发人员陷入了无法知道出了什么问题及其原因的困境，这些服务在功能上严重依赖外部部署系统和 API。小团队的速度加剧了这种情况——如果您正在部署软件的新版本，一天多次，那么您需要即时信息和生产中发生的事情的实时可追溯性。

这种复杂性的一个解决方案是分布式跟踪——具体来说，是为云本地多语言应用程序构建的分布式跟踪。然而，什么是分布式跟踪？我们为什么需要它？这些分布式系统造成的问题到底是什么？在本系列的下一部分中，我将介绍分布式系统可能导致的问题，以及为什么分布式跟踪是理解我们的系统如何工作的基础。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论故事的读者通过[推特](https://twitter.com/thenewstack)或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>