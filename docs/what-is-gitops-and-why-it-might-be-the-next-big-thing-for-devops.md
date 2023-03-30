# 什么是 GitOps，为什么它可能是 DevOps 的下一件大事

> 原文：<https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/>

容器带来了商业世界中前所未有的敏捷性。在几秒钟内，管理员就可以部署多种服务。当这些企业需要扩展这些容器时，他们可以转向 Docker Swarm 或 Kubernetes。

但是，当一个标准的容器工作流都跟不上不断增长的业务需求时，会发生什么呢？您很难找到比 Kubernetes 更有效的部署和扩展容器集群的方法。虽然这很可能是真的，但这并不意味着开发周期不能改进。

GitOps 是一种工作流方法，GitLab 的技术宣传主管 Priyanka Sharma 说，GitOps 的概念是“每个成功地将基础设施作为代码的人都是 git ops 概念的真正创造者”。

## 输入 GitOps

但是 GitOps 到底是什么？从表面上看，这很简单。GitOps 的核心是使用一个版本控制系统(比如 Git)来存放 Kubernetes 部署的所有信息、文档和代码，然后使用自动化控制器将更改部署到集群。然而，一旦你深入了解表面，你会发现事情远比这复杂得多。

Sharma 说，GitOps 为开发人员提供了一种管理运营工作流的方法，特别是对于 Kubernetes，使用 Git 和他们自己的版本控制系统。他们使用 pull 请求或 merge 请求合并代码的相同过程可以用于部署到 Kubernetes。

“对于那些做 [DevOps](/tag/DevOps) 的商店来说，这种方法可能很有吸引力，因为它使工作流程更接近开发者，”Sharma 说。

她解释说，这种方法有一些关键的好处。开发人员可以使用他们熟悉的工具将代码投入生产。她解释道:“生产力大幅提升，T4 开发真的发生了。”她补充道，“这是 GitLab 的核心理念，一切以先生为先。”

Sharma 说，因为所有的东西都要通过版本控制系统，所以所有的人都可以看到。“从软件开发和基础设施的角度来看，有一个审计跟踪、恢复有问题的更改的能力，以及最终系统中正在发生的事情的单一真实来源。”

在其核心，GitOps 是 Kubernetes 和其他云技术的运营模式。与其他模型不同的是，它集中了流程的每个方面，因此您有一条管理运营和开发的单一途径。

“GitOps 最重要的功能之一是使一组系统更改能够正确应用，然后由*验证*,[Alexis Richardson](https://twitter.com/monadic)说， [Weaveworks](https://www.weave.works/) 的首席执行官和创始人[因创造了术语“GitOps”](https://thenewstack.io/gitops-git-push-all-the-things/)而广受赞誉。之后，如果任何系统偏离了正确的状态，GitOps 应该能够通知(警告)用户和指挥者，以便它可以收敛到正确的期望状态(在 Git 中)。所以在 GitOps 中，我们必须使用持续的观察和验证，来启用 app &集群管理。”

[什么是 GitOps，为什么它可能是下一件大事](https://thenewstack.simplecast.com/episodes/what-is-gitops-and-why-it-might-be-the-next-big-thing)

## GitOps 是如何工作的？

很复杂。但是让我们简化一下。

想象一下，在一个 Git 存储库中包含了所有的文档、所有的 YAML 文件和 Kubernetes 所需的所有代码。在一些自动化工具的帮助下，任何负责管理 Kubernetes 部署的人都可以发出一个 pull 请求，编辑代码，然后向 Git 存储库发出一个 merge 请求。

“如果你没有很好地理解为什么 Kubernetes 是优先的，为什么它是异步的，为什么它是一个均匀的流……如果你不理解所有这些，只看 GitOps 的定义，看起来这有点神奇，”Weaveworks 工程师 Stefan Prodan 说。

一旦合并请求完成，自动化的 GitOps 操作符就会检测到一些变化，另一个自动化器(如 Flagger)会声明这些变化是可操作的，然后这些变化会自动部署到集群中。这里有一个例子来说明它是如何工作的:

*   Jenkins(一个开源自动化服务器)将一个带标签的图片推送到 Quay(一个应用注册表)。
*   Jenkins 将配置和 Helm (Kubernetes 管理器)图表推送到主 Git 存储桶。
*   一个自动化的云功能将配置和舵图从主 Git 存储桶复制到主 Git 存储库。
*   弗拉格确保变革是可行的。
*   GitOps 操作员更新集群。

在这个工作流程中，自动化是至关重要的，因此要保持一切以纯手动管理无法比拟的效率水平运行。

## 为什么应该使用 GitOps？

首先，GitOps 使您的工作流程更加高效。最重要的是，使用 GitOps 使通过 SOC 2 合规性更具成本效益。关于省钱的话题，Weaveworks 的理查森说:

想象一下这样一个世界:每次部署都是正确的。如果不正确，那么部署会彻底失败，所以您可以再试一次或做出其他明智的决定。想象它是正确的，想象你知道它是正确的，想象你可以回家，然后被告知是否出了问题。这是一个不可思议的运营成本节约。从不安全、半可靠的系统转移到一个基本上更健壮的系统。"

最后，GitOps 提供了:

*   通过持续的部署自动化提高工作效率。
*   通过推送代码而不是容器，增强了开发人员的体验。
*   由于所有集群更改的自动审计日志，提高了稳定性。
*   更高的可靠性来自 Git 内置的 revert/rollback 和 fork 以及单一的真实来源。
*   端到端工作流的一致性和标准化。
*   更强的安全性，因为 Git 具有很强的正确性以及用于跟踪和管理变更的加密技术。
*   更低的停机时间和大幅提高的生产率带来的成本效益。

关于 GitOps 的更多信息，请听我们对 Weaveworks 的 Alexis Richardson 和 Stefan Prodan 的播客采访。

[什么是 GitOps，为什么它可能是下一个大事件](https://thenewstack.simplecast.com/episodes/what-is-gitops-and-why-it-might-be-the-next-big-thing)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>