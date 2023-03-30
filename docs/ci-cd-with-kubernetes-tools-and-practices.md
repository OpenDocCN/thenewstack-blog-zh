# Kubernetes 的 CI/CD:工具和实践

> 原文：<https://thenewstack.io/ci-cd-with-kubernetes-tools-and-practices/>

[](https://www.reactiveops.com/)

 [罗布·斯科特

罗布·斯科特在查塔努加的家中工作，是 ReactiveOps 的一名现场可靠性工程师。他帮助为多个客户构建和维护高度可扩展的、基于 Kubernetes 的基础设施。自 2016 年以来，他一直与 Kubernetes 合作，一路为官方文档做出贡献。当他不建设世界一流的基础设施时，Rob 喜欢与家人共度时光，探索户外，并就 Kubernetes 的所有事情发表演讲。](https://www.reactiveops.com/) [](https://www.reactiveops.com/)

在 Kubernetes 之上建立 CI/CD 管道将会加速您的发布生命周期——使您能够一天发布多次——并使敏捷的团队能够快速迭代。Kubernetes 有许多特性使其成为 CI/CD 的理想选择。有了 Kubernetes，构建变得更快。您的构建过程快速、轻量且简单，而不是构建全新的服务器。

当您不必担心为了更新所有东西而构建和部署一个整体时，开发速度就会加快。通过将一个整体分割成多个微服务，你可以更新这些服务。一个好的 CI/CD 工作流程的一部分还应该包括一个强大的测试套件。虽然不是 Kubernetes 独有的，但是容器化的方法可以使测试运行起来更加简单。如果您的应用程序测试依赖于其他服务，您可以针对这些容器运行您的测试，从而简化测试过程。更新 Kubernetes 部署通常只需要一行命令。

## Kubernetes 简化了 CI/CD

在 CI/CD 工作流中，理想情况下，您会运行许多测试。如果这些测试失败，您的映像将永远无法构建，并且您将永远无法部署该容器。但是，如果测试未能发现问题，Kubernetes 会提供更好的保护，因为 Kubernetes 简化了零停机部署。长期以来，部署意味着停机。运营团队过去常常手动或通过脚本来处理部署工作，这是一个实时过程，可能需要几个小时，甚至通宵。因此，CI/CD 的一个担心是部署会中断，站点会关闭。

Kubernetes 的零停机部署能力减轻了对维护窗口的担忧，使计划延迟和停机成为过去，并在此过程中节省了资金。它还让每个人都参与进来，同时满足开发、运营和业务团队的需求。革命性的 Kubernetes 部署对象具有内置特性，可以自动完成这一操作。

[cyclone slider id = " kubernetes-series-book-3-赞助商"]

特别是，前面提到的测试和健康检查可以防止坏代码进入生产环境。作为滚动更新的一部分，Kubernetes 会在旧的应用程序仍在运行的情况下，旋转出单独的新 pods 来运行您的应用程序。当新豆荚健康时，Kubernetes 就把旧豆荚扔掉。这是一个聪明、简单的概念，而且在您的 CI/CD 工作流程中，您不必为每个应用程序担心太多。

## 补充工具

作为 Kubernetes 所看到的不可思议的发展势头的一部分，出现了许多 DevOps 工具，它们对使用 Kubernetes 开发 CI/CD 工作流特别有帮助。请记住，随着 Kubernetes 上云原生部署的出现，CI/CD 工具和实践仍在不断发展。从构建到部署和持续交付，还没有一个工具能够为管理云原生应用提供完美的解决方案。尽管这里有太多的工具需要提及，但还是有必要强调几个专门为云原生应用程序构建的 DevOps 工具:

*   **草稿**:微软的这款工具面向开发者工作流。只需几个简单的命令，Draft 就可以将应用程序封装并部署到 Kubernetes。这里应用程序的自动化容器化非常强大。Draft 使用流行框架和语言的最佳实践来构建图像和 Kubernetes 配置，这将在大多数情况下工作。
*   **Helm:** 这个框架被称为 Kubernetes 包管理器，它简化了向 Kubernetes 部署应用程序。许多流行项目的部署配置在维护良好的“图表”中可用这意味着 helm install Prometheus 是让像 Prometheus 这样的项目在您的集群中运行所需要的全部。Helm 在部署您自己的定制应用程序时也可以提供同样的便利。
*   **Skaffold:** 类似于 Draft，这是谷歌的一个新工具，可以实现令人兴奋的新开发工作流。除了支持更标准的 CI/CD 工作流之外，每当代码在本地发生变化时，它还可以选择将代码构建和部署到 Kubernetes 开发环境中。这个工具是高度可配置的，甚至支持使用 Helm 进行部署。
*   **Spinnaker** :这个开源的连续交付平台是由网飞开发的，用于通过其云网络处理大规模的 CD 操作。它是一个云原生管道管理工具，支持集成到所有主要的云提供商:AWS、Azure、Google 云平台和 OpenStack。它本身支持 Kubernetes 部署，但是它的范围远远超出了 Kubernetes。

如今，越来越多的组织选择使用 Kubernetes，而不是其他编排工具。越来越多的组织认识到容器提供了比他们一直使用的更传统的工具更好的解决方案，Kubernetes 是可用的最好的容器部署和管理解决方案。本系列的下一篇文章将更详细地研究 Kubernetes 的 CI/CD。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>