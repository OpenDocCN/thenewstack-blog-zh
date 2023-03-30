# 采用微服务和容器架构之前要知道的五件事

> 原文：<https://thenewstack.io/5-things-to-know-before-adopting-microservice-and-container-architectures/>

[](https://newrelic.com/)

 [乔纳森·欧文斯，新遗迹的首席现场可靠性工程师

乔纳森·欧文斯是新遗迹的首席现场可靠性工程师和技术产品经理。不管在哪里工作，乔纳森最后似乎总是做运营。你可能会想，在尝试了 12 年不随叫随到而失败后，他意识到了自己的命运。目前，他在容器平台团队的 New Relic 工作，担任产品经理和一般麻烦制造者。](https://newrelic.com/) [](https://newrelic.com/)

作为 New Relic 的 Container Fabric 项目(我们的内部容器编排和运行时平台)的首席站点可靠性工程师(SRE)，我花了大量时间与现有和潜在客户一起回答有关我们如何使用和管理容器来创建由数十个微服务组成的平台的问题。

我们肯定认为自己是容器的早期采用者，几乎在 2014 年夏天 Docker 发布其第一个生产就绪版本时，我们就开始了容器中的打包服务。我交谈过的许多客户刚刚开始——或考虑开始——这样的旅程，他们想知道我们所知道的一切。他们想知道我们是如何让它工作的，以及我们是如何设计它的。但我想强调的是，这个过程的一部分是，他们需要知道我们从一路上的奋斗中学到了什么。

考虑到这一点，我想与所有考虑容器和微服务的人分享以下五个要点:

### 1.永不停止发展

认真对待你的领养项目，像对待产品一样对待它。给它一个名字，甚至一些内部品牌和一个清晰的产品愿景。应该对它进行管理并赋予它生命。

我们当前版本的容器结构并不是我们第一次尝试自制的编排和交付。我们在 2014 年建立了我们的原始版本，一旦我们得到了我们认为需要的东西，我们就停止开发它。我们对开发人员喜欢使用的产品部署平台没有一个完整的愿景，我们构建的东西只能满足我们对一致抽象层的需求。

> 认真对待你的领养项目，像对待产品一样对待它。

因此，两年过去了，我们才开始对我们的容器平台进行再投资。我们的第一个版本并没有停止使用，但是我们没能捕捉到在 Docker 快速开发阶段出现的许多增量改进。

我们的一个长期客户在同一时期经历了类似的容器编排/微服务之旅，他们甚至比我们今天走得更远。当我们问他们进展如何时，他们的回答简单得令人痛苦:“我们从未停止努力。”

### 2.一点一点地构建，从早期采用者开始

当你转向容器时，采用一项新技术(如 [Kubernetes](https://kubernetes.io/) )并不意味着你要一头扎进深水区，将你的整个生产舰队转移到巨大的高可用性集群中。一件一件的造东西不是更容易吗？

当我们开始使用 Container Fabric 时，我们将部署限制在我们可以服务的最简单的用例上:无状态 HTTP 服务——没有持久性，没有非 HTTP 协议，只有一个部署方案。这减少了平台的功能，我们知道我们可以在合理的时间内有效地服务。

这一点很重要，因为集装箱调度平台不能提供一切。我们仍然需要监控平台、部署对平台的更改、处理机密、配置自动负载平衡和捕获日志，所有这些都是丰富的服务平台所带来的。约束目标服务类型使我们更容易推理平台的组件。

因此，如果您确定容器编排是您所需要的，请仔细看看容器平台提供了什么，并考虑缺少什么。为了支持您的特定服务和基础设施环境，您必须在该平台之上构建什么？这将帮助您选择首先关注哪个组件。

此外，了解你的团队的文化和可用性。谁是你公司的早期采用者？哪些团队已经准备好向新范式转变了？哪些团队正在构建适合微服务架构的服务？哪些团队被遗留的巨石所困，需要更多的时间、计划和实验？

### 3.一种尺寸不适合所有人

当涉及到容器和微服务时，有些系统就是不适合这个模型，如果你从一开始就认识到这一点，事情就简单多了。新系统中的技术通常是如此之新，以至于移植旧系统的努力可能会比它的价值更麻烦。

我们的平台继续主要提供 HTTP 服务，但是我们也开始处理更多的流处理服务。我们仍然不做持久存储或数据库。(数据库团队用 Megabase 处理这个问题。)新遗迹平台的一些部分可能需要数年才能移动到集装箱结构上，如果我们曾经移动过它们的话。没关系！容器平台并不垄断良好的部署实践。

最新的技术和架构都是关于快速迭代和分散控制的，所以如果这些东西对您的业务目标不是至关重要的，就让那些旧的遗留系统慢慢退休，直到您有迁移它们的逻辑业务需求。

### 4.技术变革是组织变革

在考虑如何使用一项技术之前，很容易就开始使用这项技术。新的架构通常需要新的架构知识和关于如何部署系统的新想法。微服务模式影响了软件和使用它的组织的架构。

随着 New Relic 团队将其服务转移到 Container Fabric 上，他们的运营工作量通常会下降。在某些情况下，团队摆脱了大量的辛劳，将他们解放出来从事他们发现更有回报的其他项目。这是自动化消除劳动负担的最好例子，我们很高兴看到这一点。已经迁移的团队可以更自由地构建让我们的客户满意的软件

考虑迁移到容器和微服务架构的组织应该问自己以下问题:

*   您的运营团队为开发人员提供什么产品，该产品使用什么抽象层？
*   这是否适合您的业务，或者容器是否更适合？
*   为了使用容器，你愿意改变抽象，从而改变你的操作团队提供的整个产品吗？
*   您准备好创建新角色来管理这一新抽象的规模和可靠性了吗？

没有哪个组织会在一夜之间发生这样的变化。从理想化的新架构到第一次生产部署的旅程需要改变许多想法并创建新的流程，这并不总是有趣的。

### 5.记住，构建软件是一种人类体验

一个丰富、复杂的集装箱调度平台需要数百人一年的经验来构建、维护和扩展。这些平台和架构要求您接受新的环境，并要求您的组织在其设计中接受折衷，因为您要对其进行调整以适应您的用例。采用容器化的微服务架构是一项大工程，可能会改变所有团队的工作平衡；这会影响他们支配时间的方式；有时，这可能会影响他们在工作中感受到的快乐。除非您真正考虑到平台采用的这些人的方面，否则迁移将比它需要的要困难得多。

由于我们的组织结构，我们已经做好了成功迁移的准备。New Relic 中的每项服务都归一个团队所有——他们负责计划、编程、部署和操作。这种结构已经存在很多年了，Container Fabric 平台使得这些完全所有者团队的工作更加简单，让他们能够在操作抽象层上移动，更接近业务目标。

容器的承诺，尤其是它们的调度平台经常被解读为“每个人都应该这样开发软件——这充满了魔力。”这通常是真的——容器平台确实使一些非常强大的功能民主化了，它们值得认真对待。但是记住他们都是用自以为是的方式解决一个平台产品化的问题。如果这些观点也是你自己的，你需要合理化。

[新遗迹](https://newrelic.com/)是新栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>