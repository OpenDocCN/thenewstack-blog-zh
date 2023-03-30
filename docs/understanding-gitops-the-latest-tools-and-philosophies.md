# 理解 GitOps:最新的工具和理念

> 原文：<https://thenewstack.io/understanding-gitops-the-latest-tools-and-philosophies/>

[](https://www.linkedin.com/in/urlichsanais/)

[Anas Urlichs](https://www.linkedin.com/in/urlichsanais/)

[Anas 是 Codefresh 的开发者传道者。当她不提倡 DevOps 最佳实践时，她运行自己的以 Kubernetes 为中心的 YouTube 频道。](https://www.linkedin.com/in/urlichsanais/)

[](https://www.linkedin.com/in/urlichsanais/)[](https://www.linkedin.com/in/urlichsanais/)

GitOps，最简单的形式，就是在 Git 中定义所有资源的原则，Git 是一个免费的开源分布式版本控制系统。这个词是由 [Weaveworks 在 2017 年](https://www.weave.works/blog/gitops-operations-by-pull-request)创造的。然而，从那时起，几个新玩家正在推进游戏:

*   新工装(如 [ArgoCD](https://argoproj.github.io/argo-cd/) 和[Flux](https://fluxcd.io/))；
*   新哲学；
*   新举措。

本文将概述这些开发以及它们如何致力于推进 GitOps。

## **GitOps:原理**

首先也是最重要的， [GitOps](https://github.com/gitops-working-group/gitops-working-group) 是[部署软件](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/)的实践。它指的是 git 在部署中的作用、部署的频率以及人机交互。在实现 GitOps 时，git 被用作所有部署资源的单一事实来源。当向集群部署新的部署时，开发人员将通过 git 与所有资源进行交互。因此，如果您的所有资源都是在 git 中定义的，那么自动化流程和实现工具以获得更高的可观察性会变得更加容易。这反过来允许团队更频繁地部署，并在部署中获得更高的信心。

## **最低可行 GitOps 实施**

在我们开始谈论正在开发并用于实现大规模 GitOps 的新奇平台和工具之前，我们应该看看最起码需要什么才能归入 [GitOps](https://github.com/gitops-working-group/gitops-working-group) :

*   您以声明的方式定义您的资源，在 git 中保持对您的部署的任何更改的不可变记录。
*   您可以随时访问资源的状态。这使得暴露部署的实际状态和期望状态之间的任何差异成为可能。
*   您已经自动将部署交付到运行时环境中；以便自动进行部署，不需要人工干预。

## **开源项目**

到目前为止，GitOps 在很大程度上是由开源项目驱动的，如 ArgoCD 和 Flux。在过去的一年中，更多的项目开始涌现。由于 GitOps 领域仍处于起步阶段，每个项目都采用稍微不同的方法来实现 GitOps。由于 Argo 和 Flux 是最突出的，接下来的两节将仔细研究它们。

### **ArgoCD**

[ArgoCD](https://argoproj.github.io/argo-cd/) 是一个用于 Kubernetes 的声明式 GitOps 连续交付工具。ArgoCD 是 [Argo 项目家族](https://argoproj.github.io/)的一部分，这是一组在[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) ( [CNCF](https://www.cncf.io/) )内孵化的项目。所有 Argo 资源都是 Kubernetes 的定义，因此像其他 Kubernetes 资源一样部署到您的集群中。这使得 Argo 可以直接与您的部署进行交互。CLI 及其 UI 提供了一个全面的工具集，用于将 git 中定义的资源部署到集群中。

### **通量**

[Flux](https://fluxcd.io/) 在成为 CNCF 项目之前，最初是由 Weaveworks 开发的。它是 Kubernetes 的持续交付解决方案。与 ArgoCD 类似，所有部署资源都是在 Git 中定义的。新的部署是基于拉取请求而展开的，而不是与您的 Kubernetes 集群直接交互。Flux 本身是通过一组 Kubernetes 控制器和 API 部署的，也称为 [GitOps Toolkit](https://toolkit.fluxcd.io/components/) 。

## 还有谁参与其中？

除了前面提到的开源工具和平台，我们可以看到更多的商业供应商参与进来。例如，Weaveworks 通过开发 Weave Cloud 和其[企业 Kubernetes 平台](https://www.weave.works/product/enterprise-kubernetes-platform/)提供 GitOps 工具。同时， [Codefresh](https://codefresh.io/?utm_content=inline-mention) 正在与 [ArgoCD 整合，提供先进的 GitOps 工具](https://codefresh.io/gitops/)。这只是几个组织的两个例子，它们参与并为 GitOps 的开发做出了贡献。

## **GitOps:疼痛**

为了获得对 GitOps 的平衡理解，既要看到它的好处，也要看到当前的批评和建议的改进，这一点很重要。Codefresh 发布了一系列的[文章](https://codefresh.io/devops/pains-gitops-1-0/)，提供了 GitOps 中发现的缺点的全面概述，因为它现在已经实现了(我们也在新的 Stack 上发布了关于这个[)。类似的缺点](https://thenewstack.io/the-problems-with-gitops-and-how-to-fix-them/)[已经被云领域的其他组织探索过](https://blog.container-solutions.com/gitops-limitations)。这些对话带来了进一步的改进和合作，例如 GitOps 工作组。

## **GitOps 工作组**

[GitOps 工作组](https://github.com/gitops-working-group/gitops-working-group)由[亚马逊](https://aws.amazon.com/?utm_content=inline-mention)、Codefresh、GitHub、微软和 Weaveworks 于 2020 年 11 月成立。这是一个开放的 CNCF 社区项目，目标是为组织和个人提供实施 GitOps 的资源。

时至今日，这个领域已经围绕 GitOps 开发了不同的定义和实践。GitOps 工作组旨在为定义和标准化这些内容铺平道路，使协作更容易，并推动进一步采用。

## **Codefresh 和 GitOps 2.0**

Codefresh 发布了 GitOps 2.0 的[愿景](https://codefresh.io/devops/vision-gitops-2-0/)以及我们希望改进上述缺点的方向。这些都集中在部署中使用的标准化信息处理方法、更高的部署可观察性，以及工具通过突出正确的信息为 GitOps 提供更多价值的方式。

值得一提的是，GitOps 仍处于非常早期的阶段，需要进行大量的实验和研究，以形成一致的理解。

## GitOps:我从哪里开始？

GitOps 是一个新的范例，所以可能很难找到足够的关于最佳实践和建议的内容。这些资源为更好地理解 GitOps 提供了更多信息:

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>