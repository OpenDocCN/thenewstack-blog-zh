# 集装箱化的云铸造:夸克项目和艾瑞尼项目

> 原文：<https://thenewstack.io/cloud-foundry-containerized-project-quarks-and-project-eirini/>

Cloud Foundry 赞助了这个播客。

Project Eirini 和 Project Quarks 都是在 Cloud Foundry Foundation 中孵化的开源项目，旨在将 Cloud Foundry 与 Kubernetes 集成在一起。

“Cloud Foundry 是一个早于 Kubernetes 的项目，随着容器编排的发展，我们开始看到更多的微服务组件内置到 Cloud Foundry 中，在某种程度上被用作容器化的一种方式。TNS 创始人兼总编辑 Alex Williams 在 Cloud Foundry Summit Europe 录制的一次现场采访中说:“这讲述了 Eirini 项目和 T2 夸克项目的历史。”Pivotal 的软件工程师 Jennifer Spinney 和 SUSE 的 Cloud Foundry 技术主管 Vlad Iovanov 也参加了这次采访。

[夸克 vs 艾瑞尼:有什么区别？](https://thenewstack.simplecast.com/episodes/quarks-vs-eirini-whats-the-difference)

Spinney 继续解释说，“因此，Cloud Foundry 传统上有一个名为 Diego 的组件，它实际上是对过去通过这些 DEAs 在 Cloud Foundry 中运行容器的旧方式的重写。我们用 Diego 取代了它，在这样做的时候，我们在 Cloud Foundry 的 API 和调度容器和调度实际应用工作负载的后端之间引入了这个硬边界。因此，当 Kubernetes 开始加速发展时，因为我们现在在 Cloud Foundry API 和实际调度作业的后端之间有一个硬边界，我们可以考虑用 Kubernetes 替换 Diego，因为它在做同样的事情。当我们开始迭戈的时候，库伯内斯还没有完全成熟，还有很多事情要做。现在我认为我们看到库伯内特斯变得更加成熟，更有可能只是让库伯内特斯代替迭戈。”

Iovanov 随后强调了夸克项目及其历史，并解释说:“夸克项目是将 Cloud Foundry 容器化并使其在 Kubernetes 上自然工作的努力。你可能知道，Cloud Foundry 通常与 BOSH 一起部署。BOSH 是针对 VM(虚拟机)世界的，但是我们注意到随着 Kubernetes 的成熟，它正在成为基础设施的管理者。因此，假设每个人都知道 Kubernetes 并使用它来部署基础架构，问题是我们如何在 Kubernetes 之上提供云铸造，使用 Kubernetes 作为基础架构？夸克项目就是为此所做的努力。”

Spinney 后来继续讨论 Pivotal 如何集成 Eirini 和 Project Quarks，并指出她正在为 Kubernetes 开发一个名为 Pivotal 应用服务的项目，该项目将 Eirini 集成到 Cloud Foundry 的现有 Pivotal 发行版中。她解释说这是一个渐进的变化，补充道，“我们刚刚替换了迭戈，换上了埃里尼。然而，我认为我们有同样的愿望，看看我们可以在哪里使事情更库伯内特本地。如果你只有 Kubernetes 作为你的工具，使用它意味着你不必作为一个操作者学习两种不同的技术。我们仍在评估接下来的步骤，但现在我们对 Eirini 非常感兴趣，我们已经发布了 alpha 版本，将 Eirini 集成到了我们的 Pivotal 应用服务中。”

[https://www.youtube.com/embed/HQZ89YfEDO0?feature=oembed](https://www.youtube.com/embed/HQZ89YfEDO0?feature=oembed)

视频

### 在这个版本中:

[2:01:](https://thenewstack.simplecast.com/episodes/quarks-vs-eirini-whats-the-difference?t=2:01)ei rini 和夸克的定义。
[3:19:](https://thenewstack.simplecast.com/episodes/quarks-vs-eirini-whats-the-difference?t=3:19) 工程夸克。
[9:27:](https://thenewstack.simplecast.com/episodes/quarks-vs-eirini-whats-the-difference?t=9:27) Cloud Foundry 和 Kubernetes。
[13:18:](https://thenewstack.simplecast.com/episodes/quarks-vs-eirini-whats-the-difference?t=13:18) 关于整合 Eirini 和 project 夸克的关键思考。
[15:51:](https://thenewstack.simplecast.com/episodes/quarks-vs-eirini-whats-the-difference?t=15:51) 波什。
[18:04:](https://thenewstack.simplecast.com/episodes/quarks-vs-eirini-whats-the-difference?t=18:04) 云代工厂峰会。

Pivotal 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>