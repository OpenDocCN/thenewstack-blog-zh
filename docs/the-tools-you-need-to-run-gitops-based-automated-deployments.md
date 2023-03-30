# 运行基于 GitOps 的自动化部署所需的工具

> 原文：<https://thenewstack.io/the-tools-you-need-to-run-gitops-based-automated-deployments/>

GitOps 是一种全新的看待运营过程的方式。GitOps 专注于利用版本控制系统(如 Git)来存放 Kubernetes 部署的所有信息、文档和代码，为自动化部署甚至可编程基础设施奠定基础。

这是一个令人难以置信的复杂系统，具有许多企业从未体验过的优势。GitOps 的主要优势包括:

*   通过持续的部署自动化提高工作效率。
*   通过推送代码而不是容器，增强了开发人员的体验。
*   由于所有集群更改的自动审计日志，提高了稳定性。
*   更高的可靠性来自 Git 内置的 revert/rollback 和 fork 以及单一的真实来源。
*   端到端工作流的一致性和标准化。
*   更强的安全性，因为 Git 具有很强的正确性以及用于跟踪和管理变更的加密技术。
*   更低的停机时间和大幅提高的生产率带来的成本效益。

如果你对 GitOps 的想法感兴趣，你的下一个问题将会是实现 GitOps 需要什么工具？毫不奇怪，有许多工具组成了 GitOps 流程。

让我们来看看可用于 GitOps 的一些必要软件，以及每个工具的作用。

## 库伯内特斯

显然，在这个过程的核心没有这个工具，你就不能拥有 GitOps。 [Kubernetes](https://kubernetes.io/) 可能是近年来商业 IT 领域最具影响力的系统之一。没有 Kubernetes 集群的启动和运行，就无法实现 GitOps。对于那些不了解 Kubernetes 的人来说，根据定义，它是一个用于自动化部署、扩展和管理容器化应用程序的开源系统。GitOps 的一切都以 Kubernetes 开始和结束。

## 码头工人

没有[码头工人](https://www.docker.com/)的帮助，Kubernetes 无法运作。事实上，为了在您的服务器上安装 Kubernetes，您必须首先安装 Docker。对于那些从未使用或介绍过 Docker 的人来说，这个工具是一套平台即服务产品，以称为容器的包的形式交付软件。

## 饭桶

Git 作为 GitOps 最重要的工具之一，紧随 Kubernetes 之后。毕竟，没有 git 就不能拼写 GitOps。Git 是 GitOps 的中心枢纽。部署和维护集群生命所需的所有文档、配置和代码都在 Git 中。但是 Git 不仅仅作为指令和代码的存储库，人类使用它来实现 Kubernetes 集群功能。取而代之的是，有一些自动机与 Git 一起工作，使一切无缝和自动化。从 Git 中读取配置，如果发现更改，集群将根据更改进行更新。

## 舵

[Helm](https://github.com/helm/helm) 是管理 Kubernetes 图表的官方工具，这些图表是预先配置的 Kubernetes 资源的包。有了 Helm，安装和管理 Kubernetes 包的过程大大简化了。Helm 可用于查找和使用流行软件(打包为 Helm charts)，共享您的定制应用程序，创建可重现的构建，智能管理您的 Kubernetes 清单文件，以及管理 Helm 包的发布。在某种意义上，Helm 就像是 Kubernetes 的 apt、yum 或 homebrew。

## 野生鸢尾花

[Flagger](https://github.com/weaveworks/flagger) 是一家渐进式交付运营商，它自动推广 canary 部署(一种向用户或服务器子集推出版本的模式)。Flagger 使用 Istio、Linkerd、App Mesh、NGINX 或 Gloo 路由进行流量整形和 Prometheus 指标(用于 canary 分析)。Flagger 测量关键性能指标(如 HTTP 请求的成功率)，同时实施一个控制循环来逐步将流量转移到 canary 部署。关于 GitOps，Flagger 负责确保 Git 存储库中的任何更改对集群都是可行的。

## 普罗米修斯

说到[普罗米修斯](https://prometheus.io/) …这里我们有一个开源监控解决方案，它是 GitOps 警报系统的核心。有了 Prometheus，如果某项更改(由 Flagger 发现)不可行，管理员就会收到实时警报。Prometheus 的加入还允许其他自动机(在 GitOps 流程中)在系统发生变化时通知警报系统。

## 将（行星）地球化（以适合人类居住）

HashiCorp 的 [Terraform](https://www.hashicorp.com/products/terraform/) 是一款开源工具，允许您为任何基础设施提供一致的工作流程。Terraform 通过使用广泛的插件生态系统来实现基础设施的供应。关于 GitOps，您可以在 Git 中编写一个 terraform 文件来提供一个 Kubernetes 集群。Terraform 还使您能够以代码的形式安全、可预测地编写、规划和提供基础设施。对 GitOps 来说，T2 的可预测性是关键。

## 流量

[Flux](https://www.weave.works/oss/flux/) 是 GitOps 领域的关键组件。Flux 是使您的 Kubernetes 集群中的 GitOps 成为可能的中心操作符。有了 Flux，您的集群配置将总是与 Git 存储库中的配置相匹配。Flux 还支持向集群连续交付容器映像。借助版本控制 Flux 可以确保部署是:

*   可再生的
*   可预言的
*   可审计
*   应归还的

只要 Flux 到位，您的团队就可以确信对集群所做的任何更改都可以轻松恢复。

## 詹金斯 X

[Jenkins X](https://jenkins.io/projects/jenkins-x/) 是一个由 CloudBees 管理的开源自动化服务器，有助于您的 Kubernetes 集群的持续集成和交付。Jenkins X 实现了环境管理和环境间新版本升级的自动化。在 GitOps 领域，Jenkins X 用于快速创建集群、快速启动多种编程语言来部署绿地应用程序、导入现有棕地应用程序、自动设置容器化应用程序部署、自动提升和自动回滚。

## 码头

Red Hat 管理的 Quay 是一个图像注册表，允许您轻松管理您的集装箱图像，具有高度的安全性和可靠性。不要依赖 GitHub 之类的东西，您会希望您的 GitOps 工作流使用一个内部的图像注册中心。为此，你最好的赌注是码头。

这些只是组成 GitOps 拼图的一部分。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>