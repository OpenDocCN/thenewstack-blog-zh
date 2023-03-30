# 为什么 Kubernetes 需要为 DevOps 降级

> 原文：<https://thenewstack.io/why-kubernetes-needs-to-be-dumbed-down-for-devops/>

一个组织向云原生环境的转变必然会涉及到控制平面、数据平面和许多其他特定于 Kubernetes 和微服务的平台和工具的采用，以帮助管理 Kubernetes 的“平行宇宙”此外，许多 DevOps 团队成员，包括开发人员，将需要采用新的技能来完成这一转变。

在本期[新堆栈制造商](/podcasts/makers)播客中，[TNS 创始人兼发行人阿历克斯·威廉姆斯](/author/alex/)与分析师[贾纳基拉姆·MSV](https://www.linkedin.com/in/janakiramm/)谈论了库本内特平行宇宙的背景。他们还讨论了开发人员体验、 [GitOps](/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 如何帮助填补一些空白和集群蔓延的想法，以及它与多云环境的关系。

[为什么 Kubernetes 需要降级为 DevOps](https://thenewstack.simplecast.com/episodes/why-kubernetes-needs-to-be-dumbed-down-for-devops)

新书库最近出版了 MSV 合著的最新版本的电子书《库伯内特生态系统的现状》，该书也可以作为指南。电子书的第二章提供了云就绪和云原生世界的详细概述。这一章“描绘”了“呈指数增长”的新生态系统。

与此同时，关于云原生对开发人员体验和持续集成(CI)意味着什么的问题仍然存在。首先，MSV 解释说，Kubernetes 仍然“对不同的人有不同的意义”。开发人员必须对 Kubernetes 内部发生的事情有很多了解，而管理员必须对服务有很多了解，包括微服务。

“开发者、平台和操作体验之间的界限正在变得完全模糊，”MSV 说。"每个人都必须了解库伯内特的一切."

不幸的是，开发人员必须获得关于 Kubernetes 的知识，这超出了他们开发代码的主要职责。如今，云原生部署的开发人员通常会构建一个 Docker 映像，创建一个注册，然后依靠[入口](https://kubernetes.io/docs/concepts/services-networking/ingress/)来帮助管理 Kubernetes 集群。

MSV 说，为开发者简化这一过程代表着“生态系统中仍然存在的巨大机会”。"开发者体验将允许开发者带着源代码和一个 URL 离开."

然而，由于开发人员和 DevOps 团队成员能够移植到 Kubernetes 和 cloud native universes 并在其中进行管理，许多流程都得到了改进。GitOps 在版本控制方面的改进就是一个很好的例子。但仍有许多工作要做。

“我是 GitOps 的忠实粉丝。我认为这将成为基于 Kubernetes 的部署和管理所需状态配置的事实，”MSV 说。“但不幸的是，即使我是一名熟悉 Git 分类的开发人员，我仍然需要处理 YAML 文件和舵图，因为 GitOps 没有抽象出 Kubernetes 向开发人员公开的方式。”

[https://www.youtube.com/embed/pH352KoeX4I?feature=oembed](https://www.youtube.com/embed/pH352KoeX4I?feature=oembed)

视频

最终，GitOps 最终应该能够进一步帮助开发人员以及所有 DevOps 团队创建体验，这将提高云原生部署和管理的可管理性。但是，至少在短期内，在 Kubernetes 的平行宇宙中，获得管理云本地世界的专业知识仍然是一个挑战。

“我的解决方案是这样的:对于有抱负的 Kubernetes 专业人士——我不称他们为管理员或开发人员，因为这是一个非常令人困惑的职能——但如果你试图在 Kubernetes 建立职业生涯，学习基础知识并了解大局，”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>