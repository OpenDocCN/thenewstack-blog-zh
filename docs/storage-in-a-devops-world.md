# DevOps 世界中的存储

> 原文：<https://thenewstack.io/storage-in-a-devops-world/>

云原生应用程序开发带来的向 DevOps 过渡的一部分是存储责任的转移，从专门的专家转移到开发人员，他们越来越多地负责为他们构建的应用程序调配存储。

“人们不希望存储成为一项复杂的任务，”NetApp 首席技术专家 Chris Merz 说。“这是一项基础设施。它应该是简单的，应该是可扩展的，应该是自我修复的。它们应该遵循与 DevOps 实践者和云原生架构师每天构建的系统相同的模式。”

[存储在 DevOps 世界](https://thenewstack.simplecast.com/episodes/storage-in-a-devops-world)

在 Kubernetes 出现之前，构建和运行基于容器的应用程序是一项繁重的任务，包括手动处理 DNS 管理、负载平衡、扩展和资源监控等任务。Merz 说，现在 Kubernetes 生态系统处理所有这些，但需要一种方法来获得相同水平的存储自动化。

## 一个用于容器的开源存储编排器

[Trident](https://github.com/NetApp/trident) 是一个由 NetApp 开发和维护的开源项目，它充当了一个存储协调器，从寻求配置存储的开发人员那里抽象出一些复杂性(和决策)。开发人员不必担心存储如何工作的细节，Trident 将 Kubernetes 与 NetApp 的内部和基于云的存储产品相集成。

“你可以把 Trident 看作是集装箱和 Kubernetes 的存储管理员，”Merz 说。你什么都不用担心，门房会处理好的。

使用集成到 Kubernetes 中的云本机存储协调器解决了应用程序生命周期中最棘手的问题。它使持久性供应变得更加容易和快速，而且还使正确设置持久层以便在应用程序在生产环境中运行时进行监控和观察变得更加容易。这对任何应用程序都很重要，对有状态的应用程序更是如此。

Merz 说:“有状态的应用程序倾向于记录系统或对应用程序框架更为核心的东西。鉴于有效的企业级监控涉及数以千计的指标，您需要在每次配置带有存储的容器时自动遥测您的持久层。

Merz 说，无论应用程序架构如何，挑战本质上都是一样的:规模和控制。当我们谈论企业规模的公司时，可伸缩性是必不可少的。安全性、可观察性和数据管理形式的控制也至关重要。完全有可能在云原生应用中获得与企业级存储相同的可扩展性和控制力。它只需要使用不同的工具，并确保现在负责调配存储的开发人员拥有做出正确选择和正确设置存储的知识和工具。

### 在这个版本中:

[2:42:](https://thenewstack.simplecast.com/episodes/storage-in-a-devops-world?t=2:42) 默茨踏上 DevOps 变革之旅
[4:30:](https://thenewstack.simplecast.com/episodes/storage-in-a-devops-world?t=4:30) 在这个由容器和不可改变的基础设施组成的新世界中，你认为有哪些经验教训？
[14:27:](https://thenewstack.simplecast.com/episodes/storage-in-a-devops-world?t=14:27) 你对团队、工作流和 CI/CD 有什么看法，以及它们是如何结合在一起的？
[17:09:](https://thenewstack.simplecast.com/episodes/storage-in-a-devops-world?t=17:09) 随着开发人员越来越多地扮演运营角色，工作流对他们来说会有很大的改变吗，或者改变很小？
[19:15:](https://thenewstack.simplecast.com/episodes/storage-in-a-devops-world?t=19:15) 这对于设计在容器和 Kubernetes 上运行的有状态应用程序有多重要？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>