# 为什么 Loft Labs 要向 CNCF 捐赠 DevSpace

> 原文：<https://thenewstack.io/why-loft-labs-is-donating-devspace-to-cncf/>

我们很高兴地宣布 [Loft Labs](https://loft.sh/) 正在向云本地计算基金会(CNCF)捐赠 DevSpace。它还不是 CNCF 沙盒的一部分，因为正式验收需要 CNCF 技术监督委员会(TOC)在 12 月 13 日开会时审查和同意。在本帖中，我们将探讨我们做出这一贡献的一些动机，以及我们希望 DevSpace 将为 CNCF 生态系统的发展带来什么。

## **为什么我们要向 CNCF** 捐赠 DevSpace

目前，有数百个组织使用 DevSpace 来构建他们的云原生应用程序。因为如此多的公司日复一日地依赖它，我们觉得它不应该完全掌握在一个小的创业公司手中。我们希望通过将 DevSpace 贡献给 CNCF，我们可以为该项目提供一个中立的家，以接收来自云原生社区的外部贡献。

我们希望成为未来的主要贡献者，并将大力投资于该技术，但治理应该安全地过渡到 [Linux Foundation](https://thenewstack.io/linux-foundation-research-why-open-source-needs-it-now/) 和社区，因为 [DevSpace 对于这一步已经足够成熟](https://thenewstack.io/devspace-designed-to-lower-the-kubernetes-learning-curve/)。

## **为什么 DevSpace 对 CNCF 如此重要**

[云原生计算基金会章程](https://github.com/cncf/foundation/blob/main/charter.md)声明该基金会的使命是“让云原生计算无处不在。”CNCF 在这一使命中的作用是全面管理项目，促进项目的发展和基础技术的推广。

目前，Kubernetes 有超过 50 种开发工具，但其中只有一种，Telepresence，在 CNCF 的沙盒中。通过向 CNCF 贡献 DevSpace，我们希望通过向生态系统添加 Kubernetes 开发者工具的新选项，同时通过 CNCF 的管理和推广，使 DevSpace 项目在沙盒中成长，从而为 CNCF 实现云原生无处不在的目标做出贡献。

## **DevSpace 如何增强开发人员的能力**

[DevSpace](https://www.devspace.sh/) 是一个开源开发者工具，让本地 Kubernetes 开发更快更少痛苦。

您所需要的只是一个本地 Kubernetes 集群和一个描述您的本地设置的`devspace.yaml`。DevSpace 将负责剩下的工作，管理你的应用程序所依赖的所有 Kubernetes 资源和依赖项，这样你就可以专注于最重要的事情:构建出色的产品。

有了热重新加载特性，代码更改将被装载到正在运行的容器中，因此不需要等待重新构建和重新部署。由于 DevSpace 的依赖结构，多个团队可以同时在同一个集群上处理不同的服务，如果他们引入了违反合同的变更，可以收到即时反馈。

最棒的是:您可以在`devspace.yamls`之间分享最佳实践和技巧，并构建自己的 DevSpace 库。

想想像 Docker Compose 这样的 DevSpace，但是对于 Kubernetes，不管它是本地 Minikube 集群还是远程 Amazon Elastic Kubernetes 服务(EKS)集群。DevSpace 可以与任何集群、任何编程语言和任何集成开发环境(IDE)一起工作。

DevSpace 通过热重装、日志和集中部署配置等特性提供了更高效的开发体验。通过热重装，只要您保存了应用程序文件，DevSpace 就会负责重新构建和重新部署您的应用程序。通过利用`devspace log`，开发人员可以在附加到 pod 的同时轻松地打印日志。

虽然其他解决方案依赖复杂的网络代理来模仿 DevSpace 提供的闪电般快速的集群内开发，但 DevSpace 专注于仅通过客户端二进制文件提供更简单、轻量级的执行模型。由于代码更改被热重新加载到正在运行的容器中，这允许开发人员使用云来运行所有工作流，并看到他们的应用程序的更改立即反映在正在运行的容器中，而无需构建映像或重新创建和重新安排容器。这释放了本地工作站的计算能力，并更好地利用云来运行工作负载。

## **DevSpace 使用案例**

[DevSpace](https://loft.sh/blog/devspace-6-announcement/) 使开发团队能够与 Kubernetes 一起工作，而不管他们对 Kubernetes 了解多少。以下是一些使用案例:

1.  集群内发展
2.  标准化 Kubernetes 工作流
3.  CI 管道或部署到暂存环境

## **结论**

希望你现在对我们向 CNCF 捐赠 DevSpace 的原因有了更深的理解。我们很高兴 DevSpace 能采取下一步行动，看看 CNCF 生态系统能为项目的发展做些什么。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>