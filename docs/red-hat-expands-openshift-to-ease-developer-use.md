# Red Hat 扩展 OpenShift 以方便开发者使用

> 原文：<https://thenewstack.io/red-hat-expands-openshift-to-ease-developer-use/>

Red Hat 已经更新了其[open shift](https://www.openshift.com/)enterprise Kubernetes 平台，使其更容易为两类不同的用户使用——管理员和开发人员。混合云应用平台的 4.4 版本在本周虚拟举行的红帽峰会上亮相。

“当谈到 OpenShift 时，实际上有两种角色，”Core Cloud Platforms 的副总裁[Red Hat](https://www.redhat.com/)Joe Fernandes 在一次采访中解释道。他解释说:“有管理员，负责安装 Kubernetes、管理集群、管理对容器映像等内容的访问，还有最终用户，通常是开发人员，他们负责构建和部署应用程序。

“作为管理员，您可以看到 Kubernetes 的所有内部功能以及集群的所有配置和管理。当你是一个开发者时，你不会想看到这些。你只是想看到你的应用程序，并能够将它们与其他服务集成，部署它们等等。”

管理员将喜欢 4.4 中的新指标仪表板，这将把监控扩展到 Red Hat 运营商，并提供成本管理功能，在单个位置提供工作负载和云计算支出的综合视图。管理员可以期待的 OpenShift 4.4 的另一个功能是 Kubernetes 的高级集群管理，这使他们能够跨混合云环境一致地运行和管理 Kubernetes，并从单个控制点管理多个集群和应用程序。该功能基于 IBM 的[Cloud Pak for multi Cloud Management](https://www.ibm.com/cloud/cloud-pak-for-management)，将于 5 月在技术预览版中推出，并于 2020 年夏季正式上市。

除了这些针对管理员的核心改进，Fernandes 解释说，OpenShift 4.4 旨在增强开发人员的能力，为他们提供新的指标和监控工具，并将其重点扩展到传统的主要用户群 Kubernetes 管理员之外。

例如， [OpenShift 无服务器](https://www.openshift.com/learn/topics/serverless)的全面上市，这是一款基于 Knative 的无服务器产品，也是去年在 preview 中推出的。该特性允许开发人员使用任何语言或运行时来构建他们的应用程序，然后将它们打包到标准容器中，并在任何混合基础设施上的普通 Kubernetes pods 中启动。

这一最新版本与 Kubernetes 保持同步，使对 [Kubernetes 1.17](https://kubernetes.io/blog/2019/12/09/kubernetes-1-17-release-announcement/) 的支持成为一项核心功能，因为企业产品仅落后于上游 Kubernetes 一个版本，以确保该平台经过企业用户的实战测试。

该版本升级了入口控制器实现，以使用 HAProxy 2.0，提供更高性能的入口、端到端 HTTP/2 支持、可扩展的多线程以及改进的安全性和整体性能。在存储方面，它引入了具有持久卷(PV) [调整大小、快照、恢复和克隆](https://docs.openshift.com/container-platform/4.4/storage/expanding-persistent-volumes.html)功能的存储增强功能，它在一篇博客文章中表示，这些功能“对于开发有状态应用程序的开发人员和管理生产部署的管理员来说非常重要”

最后，OpenShift 4.4 还看到许多新功能进入预览版，同时支持 Helm 3，该公司表示，这解决了以前版本 Helm 的潜在安全问题，并使 Helm 图表在 OpenShift 控制台的开发者目录中可见和可用。例如，OpenShift Pipelines 是一个基于 Tekton 的 CI/CD 插件，它“提供了一种 Kubernetes 原生的方式来创建可跨 Kubernetes 平台移植并在容器中按需运行的 CI/CD 管道”，它已经进入了 Tech Preview。

同样，OpenShift Builds 允许开发人员使用许多 Kubernetes 工具(如 Source-2-Image、Buildah、Cloud Native Buildpacks 等)从应用程序源代码和二进制文件中构建精益映像。)”，也将进入开发者预览版。

红帽是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>