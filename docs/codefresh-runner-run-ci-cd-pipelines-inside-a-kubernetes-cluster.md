# Codefresh Runner:在 Kubernetes 集群中运行 CI/CD 管道

> 原文：<https://thenewstack.io/codefresh-runner-run-ci-cd-pipelines-inside-a-kubernetes-cluster/>

[](https://twitter.com/codepipes)

[Kostis Kapelonis](https://twitter.com/codepipes)

[Kostis Kapelonis 是 Codefresh 的开发人员，code fresh 是一个为 Kubernetes 和 containers 构建的连续交付平台。Kostis 以前是一名软件工程师，在应用程序容器化、构建 CI/CD 管道和开发 Java 应用程序方面有多年的经验。他住在希腊，喜欢轮滑。](https://twitter.com/codepipes)

[](https://twitter.com/codepipes)[](https://twitter.com/codepipes)

Codefresh 最近开源了 [Codefresh Runner](https://codefresh.io/docs/docs/administration/codefresh-runner/) ，这是一个原生的 Kubernetes 应用程序，用于在任何 Kubernetes 集群内运行 CI/CD 管道，无论是在公共云上还是在私有集群的防火墙后面。

[持续集成/持续交付(CI/CD)](/understanding-the-difference-between-ci-and-cd/) 管道本身就是迁移到 Kubernetes 集群的完美工作负载。在大多数软件组织中，活动管道的数量总是随着时间而变化。例如，就在软件发布之前，活动管道的数量将会激增，因为工程师们正急于实现最后一分钟的功能和修复。

自动扩展工作负载是 Kubernetes 集群的内置特性之一。将 CI/CD 管道放在 Kubernetes 集群中是一个显而易见的选择，因为这将使它们在没有任何其他配置的情况下利用自动伸缩特性。

Codefresh Runner 不仅允许您利用 Kubernetes 对 CI/CD 管道的可伸缩性，还提供了几个优势来处理 CI/CD 管道中使用的数据和服务的安全性和合规性。

## CI/CD 管道中的安全服务

当使用新的软件工具时，有严格安全限制的公司总是面临艰难的选择。通常的选择是在内部安装该工具，并花费大量精力对其进行维护和监控。另一种选择是使用公共云，并接受与之相关的所有风险。

Codefresh Runner 通过实现一个混合的解决方案，实现了两个世界的最佳结合。Runner 本身安装在一个私有的 Kubernetes 集群中。通过这种方式，it 可以访问所有安全的服务，比如 Git 存储库、Docker 注册中心和组织已经维护的其他数据库。

管理跑步者的 Web UI 运行在公共云上，享受着 SaaS 平台的所有好处。需要注意的重要一点是，网络通信只是传出的。Codefresh Runner 正在轮询要执行的管道的云 UI。没有防火墙端口需要开放，使安装变得轻松。

同时，CI/CD 管道中使用的源代码总是位于防火墙之后。数据库、Docker 注册中心和其他安全服务也遵循同样的方法。

最终结果是，使用 Codefresh Runner 的公司可以减少对 SaaS 解决方案的维护(Web UI 由 Codefresh 团队监控和管理)，同时仍然确保公司的知识产权(即源代码和安全数据)在公司防火墙后仍然安全。

## Kubernetes 在 CI/CD 管道中的可扩展性

Kubernetes 集群可以根据工作负载指标以不同的方式进行扩展(例如，增加单元或节点的数量)。这是 Kubernetes 最大的卖点之一，因为它允许管理员以可能的最佳方式利用底层资源。

Codefresh Runner 将自动利用它所运行的集群中的任何自动伸缩功能。这意味着，随着更多管道的启动，运行器将适应增加的负载，而无需任何额外的配置。

随着 CI/CD 管道数量的增加，一个典型的场景是在 sprint 的末尾。开发人员可能会打开大量的拉请求，或者相反，他们会将大量的拉请求合并回主线分支。

使用 Codefresh Runner，所有管道将在排队后立即运行，而不是由于缺乏资源而造成瓶颈。所有 Codefresh 管道还启用了[自动工作空间和 Docker 层缓存](https://codefresh.io/docs/docs/configure-ci-cd-pipeline/pipeline-caching/)，无需任何额外配置。

## 多云 CI/CD 管道

Codefresh Runner 使用的是标准的 Kubernetes API，没有对底层云提供商做任何假设。这意味着 Runner 可以以同样的方式安装在任何兼容的 Kubernetes 发行版中(甚至是运行在您的笔记本电脑上的本地 Kubernetes 集群)。

Codefresh 管道是可组合的(即，您可以从一个管道调用另一个管道)。对于子管道的运行位置没有限制。这个关键特性允许您将运行在完全不同的集群甚至云提供商上的管道连接起来。

例如，您可以运行一个始于公共 Google Cloud 的父管道，它启动另一个运行于 AWS 的管道。或者，一个管道可以在您的内部数据中心内运行，但第二个管道在 Codefresh SaaS 资源上运行。Codefresh Runner 是不可知的，无论它运行在哪个集群上，它的行为方式都是相同的。

管道可以专门针对不同的集群或环境，在运行时环境中的资源约束和安全措施上提供最大的灵活性。

## 为 CI/CD 管道重用 Kubernetes 知识

许多 CI/CD 解决方案传统上很难建立和维护。Codefresh Runner 在安装和维护方面采用了一种新的方法。

首先，虽然您可以通过许多不同的方式安装 Codefresh Runner(例如，使用 Kubernetes 清单或 Helm 图表)，但最快的安装方法是使用友好的命令行向导。

向导会询问一些关于集群的基本问题，然后在一个步骤中下载、安装和设置 Kubernetes 集群中的所有 Runner 资源。

安装完成后，转轮可以自给自足。它将自动查看您的管道队列，并运行分配给相应集群的管道，以及 Docker 注册中心和 Git 提供程序的所有现有集成，这些集成已经在 Codefresh 帐户中设置。Runner 使用 [Docker 映像作为构建工具](https://thenewstack.io/docker-based-dynamic-tooling-a-frequently-overlooked-best-practice/)，这意味着新工具不必安装在 Runner 本身上。

转轮组件都是本地 Kubernetes 资源。这意味着您可以使用集群中已经存在的 Kubernetes 工具来监控 Runner。特别是在大型组织中，这是一个显著的优势，因为它允许运营商重用他们现有的 Kubernetes 知识和对集群监控工具的投资。

## 结论

在 Kubernetes 集群上运行 CI/CD 管道不一定是一个复杂的过程。

使用 Codefresh Runner，您可以:

*   在任何兼容的 Kubernetes 集群上执行管道，而不考虑云提供商
*   在任何 CI/CD 管道中访问防火墙后的安全服务，同时将源代码保留在数据中心/私有云内
*   自动获得 Kubernetes 处理大量管道的可伸缩性优势
*   在多云配置中运行管道，在完全集群和云安装中混合父/子管道
*   像其他 Kubernetes 应用程序一样维护和监控您的 CI/CD 运行时

Codefresh Runner 托管在[GitHub](https://github.com/codefresh-io/cli)(code fresh CLI 的一部分)。关于如何在 Kubernetes 集群上安装它并开始运行 CI/CD 管道的更多细节，请参见[文档页面](https://codefresh.io/docs/docs/administration/codefresh-runner/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>