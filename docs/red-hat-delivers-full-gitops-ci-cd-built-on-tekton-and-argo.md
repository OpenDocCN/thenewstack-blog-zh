# Red Hat 提供基于 Tekton 和 Argo 的完整 GitOps CI/CD

> 原文：<https://thenewstack.io/red-hat-delivers-full-gitops-ci-cd-built-on-tekton-and-argo/>

企业开源软件提供商 [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 本周在[kube con+CloudNativeCon Europe](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)期间发布了其 OpenShift GitOps 和 OpenShift Pipelines 特性，分别基于流行的开源项目 [Argo CD](https://argoproj.github.io/argo-cd/) 和 [Tekton](https://www.tekton.dev) 提供功能，这两个项目共同提供了完整的[持续集成](https://thenewstack.io/category/ci-cd/)和持续交付(CI/CD)解决方案。

该公司首先[于 2020 年 5 月发布 OpenShift Pipelines](https://www.openshift.com/blog/openshift-pipelines-tech-preview-blog) 进行预览，同年晚些时候[讨论了其迈向完整 GitOps 版本的计划](https://developers.redhat.com/blog/2020/09/03/the-present-and-future-of-ci-cd-with-gitops-on-red-hat-openshift/)，注意到其与 Jenkins 等传统 CI 工具的集成，同时也探索了其采用云原生 CI/CD 工具的计划。2021 年 2 月，红帽跟进了 OpenShift GitOps 的[预览，现在该公司表示两者都已准备好黄金时间。](https://www.openshift.com/blog/announcing-openshift-gitops)

Red Hat 产品战略高级总监 Brian Gracely 解释说，全面上市不仅表明产品已准备好投入生产使用，还表明它们与上游项目完全同步，并与 Red Hat 产品组合的其余部分完全集成。此外，优雅地强调，这个特殊的版本强调了该公司最近采取的一个不同的策略，为其用户提供更多的灵活性:模块化。

“这是另一个领域，我们不再需要将 OpenShift 作为所有功能的一部分。Gracely 说:“我们已经开发了 Git Ops、管道、无服务器、服务网格和这些独立的模块化运营商，所以好处是，客户可以以任何速度将这些功能添加到他们想要的任何集群中。“如果我是一个客户，并且我已经对某个版本进行了标准化，那么在过去很多时候，你会说，‘哦，我不能碰那个版本，尽管我想要一些新功能。’因为我们将它们作为模块化组件提供，所以现在它们可以更加灵活地混合和匹配各种功能。"

Gracely 说，在这个版本中，可用的 CI/CD 特性超过了以前提供的与 Jenkins 等工具的集成。例如，OpenShift Pipelines 就是建立在 Tekton 之上的，它利用 Kubernetes 以一种比其前身更加资源敏感的方式来运行进程。

“以前，像 Jenkins 和其他人一样，他们倾向于占用更大的资源块，所以他们会占用整个虚拟机，他们会占用整个机器来运行它，”Gracely 说。“通过在容器中运行，这意味着我们不仅可以限制我们需要多少资源，还可以利用所有的 Kubernetes 部署模型。”

OpenShift Pipelines 在其自己的容器中运行 CI/CD 管道的每一步，允许它们独立扩展并最大限度地减少静默期所需的资源，并且没有要管理的中央 CI/CD 服务器。因此，优雅地解释，管道可以迎合他们的个人需求。例如，如果某个东西总是获得贡献并触发构建，那么该管道可以作为 Kubernetes 守护进程运行，以利用尽可能多的机器。其他作业可能在固定的时间间隔内运行特定的时间长度，并且可以作为批处理作业处理，在不再需要资源时关闭资源。

格雷斯利说:“它真的允许我们说，我们实际上可以变得更细粒度，因为 Kubernetes 内置了不同部署可以有不同外观的想法，而不是让管道成为占用大量资源并对每个管道一视同仁的通用事物。“如果你愿意的话，Tekton 可以让一切都成为工作节点，这样你就不必一直维护这个庞大的有状态资源。”

在 OpenShift GitOps 领域，很少有传统技术可以取代。GitOps 是一种相对较新的实践，它不仅使 Git 存储库成为开发人员，而且也是运营团队及其基础架构配置的单一来源，Argo CD 是 Kubernetes 的声明性 GitOps 操作符，根据 Red Hat 关于该主题的博文[所述，“通过将应用配置同步到目标集群并确保集群处于所需状态，自动将应用部署到多个集群”。](https://developers.redhat.com/blog/2020/09/03/the-present-and-future-of-ci-cd-with-gitops-on-red-hat-openshift/)

“它实际上旨在了解平台团队与应用团队之间发生的真正交集，平台团队需要担心资源、安全性和冲突，而应用团队只需说‘我只想做些事情，给我足够的空间让我在项目中高效工作。’，”优雅地解释道。

Red Hat first [于 2020 年 8 月加入 Argo CD 社区](https://www.redhat.com/en/about/press-releases/red-hat-and-intuit-join-forces-argo-project-extending-gitops-community-innovation-better-manage-multi-cluster-cloud-native-applications-scale)，Gracely 表示，他们对该项目的最初贡献不仅包括将其引入 OpenShift，还包括为该项目提供洞察力。

“我们回馈的很多东西只是客户对使用模式等诸如此类的东西的见解。对我们来说，贡献不仅在于我们对技术有了更深刻的理解，我们可以全力支持它，等等，而且它还让我们在提交者级别上有能力成为我们客户及其使用案例的倡导者，”Gracely 说。

OpenShift GitOps 和 OpenShift Pipelines 都可以在 [OperatorHub](https://operatorhub.io/) 上获得，用于所有受管理的 OpenShift 订户，以及自我管理的 OpenShift 容器平台和[最近发布的 OpenShift 平台 Plus](https://thenewstack.io/red-hat-offers-a-complete-kubernetes-stack-with-openshift-platform-plus/) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>