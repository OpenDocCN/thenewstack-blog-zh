# Codefresh 为 Kubernetes 管理添加了一个命令行界面

> 原文：<https://thenewstack.io/codefresh-adds-cli-kubernetes-management/>

包括 [Codefresh](https://codefresh.io/) 的联合创始人兼首席执行官拉结尔·塔比在内的一些人将 2018 年称为 Kubernetes 的[年。](https://thenewstack.io/predictions-2018-rise-kubernetes-platform/)

他表示，2017 年为容器编排市场带来了清晰度，Kubernetes 是容器编排技术的主导者。

这家初创公司一年前发布了基于 Kubernetes 的持续交付平台，[去年 8 月与谷歌](https://thenewstack.io/google-codefresh-collaborate-make-kubernetes-accessible-smaller-organizations-new-users/)合作，让这项技术更容易获得。对于该平台的最新更新，该公司在其软件中添加了命令行界面。

“我们发现，在我们的平台中，要充分释放 Codefresh 和 pipelines 以及复杂的 Kubernetes 部署的力量，有一个明显缺乏的东西，那就是命令行界面(CLI)。这是个人偏好，但是你可以发现社区中有相当一部分人更喜欢命令行界面而不是用户界面。它允许(用户)做他们用 Kubernetes 命令行做不到的事情，”他说。

CLI 包括以下功能:

*   **构建矩阵管道，**在其中你可以用不同的值并行运行相同的管道多次，比如一次为几个不同的架构构建和测试一个发布。
*   **管理来自多个注册表的图像**—CLI 显示每个连接的 Docker 注册表，从而可以添加注释、快速搜索和查看所有图像。
*   **安装和升级舵图。**

他指出了复杂的 Kubernetes 用户，如 GIF 文件数据库 [Giphy](https://giphy.com/) ，它在自动化脚本的开始使用命令行来运行跨不同集群的管道，并测试多个内部服务的代码。

Tabib 说，CLI 是 Codefresh 在过去几个月中的第三次重大改进。12 月，它增加了对舵图作为原生实体的支持。它们允许用户为 Kubernetes 打包微服务和网络组件。

使用 Helm charts，您可以自动化更复杂的流程，例如自动配置应用程序、对其运行集成测试以及进行 canary 部署。Codefresh 用户可以在连续交付管道中使用完整的平台。自动化管道可以按需启动环境并加载测试用的完整应用程序，而不是将软件更改推送到临时服务器并运行测试。

Tabib 说，随着 Docker 映像的构建、测试和部署，Codefresh 正在添加更多的元数据，因此最终 DevOps 中的任何人看到映像在生产中运行，无论它运行得好不好，它都可以一键获得关于这个 Docker 映像经历了什么、它是如何测试的、它是否通过了安全扫描等等的所有信息。

Kubernetes 是发展迅速的开源项目之一。它的社区在 2017 年每个季度都会发布一个版本，最近的一个版本是 12 月的[1.9](https://thenewstack.io/fun-kubernetes-1-9/)。

在去年夏天由 451 Research 发布的对 200 家公司的调查中，71%的公司使用 Kubernetes 来管理他们的集装箱基础设施。

包括 [Mesos](https://thenewstack.io/mesosphere-returns-kubernetes-beta-dcos/) 、Docker、[亚马逊网络服务](https://techcrunch.com/2017/11/29/awss-container-service-gets-support-for-kubernetes/)在内的竞争对手在 2017 年宣布支持 Kubernetes。

然而，Lawrence Hecht 对新堆栈的研究发现，实施和维护的复杂性仍然是采用的主要障碍。12 月份 Kubecon 2017 的一个主要主题是需要让技术变得乏味，确保稳定性和可用性。

除了与现在更愿意选择 Kubernetes 的公司合作，Tabib 还表示 Codefresh 将在 2018 年整合另外两个开源项目:

*   [Istio](https://istio.io/) ，Kubernetes 之上的一个代理和管理层。与舵图一起使用，它将使用户能够轻松地设置部署策略，如金丝雀和蓝/绿。
*   监控解决方案 [Prometheus](https://prometheus.io/) ，允许用户在提高自动化程度的过程中检查应用程序的健康状况。

管理 Kubernetes 的云本地计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>