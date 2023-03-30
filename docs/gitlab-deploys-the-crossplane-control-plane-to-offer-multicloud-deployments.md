# GitLab 部署交叉平面控制平面以提供多云部署

> 原文：<https://thenewstack.io/gitlab-deploys-the-crossplane-control-plane-to-offer-multicloud-deployments/>

代码库 [GitLab](https://about.gitlab.com/) 正在使用[交叉平面](https://crossplane.io/)通用控制平面为其用户提供一种跨多个云轻松部署其应用代码的方式。

由 [Upbound](https://upbound.io/) 开发的开源多云控制平面旨在允许应用程序通过单一接口直接部署在无状态的多云环境中，以及通过 kubectl 部署在无状态微服务和 Kubernetes 平台上。

虽然 GitLab 已经支持在多个云上运行其容器，但基于 git 的服务发现，Redis 和 Postgres 等有状态服务迫使管理员手动提供这些服务，并在 Kubernetes 之外为每个云管理它们， [Upbound](https://upbound.io) 的首席执行官 Bassam Tabbara 在巴塞罗那举行的[kube con+CloudNativeCon Europe 2019](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2019/)接受采访时表示。

“通过 Crossplane，GitLab 可以以可移植的方式从 Kubernetes API 进行部署和管理，同时仍然可以使用生产就绪的完全托管服务，”Tabbara 说。

Tabbara 说，Crossplane 是唯一一个开源项目，能够以可移植的方式消费来自多个云提供商的完全托管的服务。Tabbara 说:“Crossplane 还支持动态配置，以及开发者和管理员之间关注点的严格分离。

Upbound 和 GitLab 描述了如何通过添加资源声明和资源类来使用 Kubernetes API 部署 GitLab 代码，以支持 Kubernetes 中托管服务依赖的可组合性，类似于持久卷声明和存储类。Tabbara 说，兼容的集群包括 Anthos、GKE 和 OpenShift。

GitLab 和 Upbound 在以下步骤中描述了如何使用 Crossplane 从 GitLab 进行部署:

集群管理员:

*   在您的 Kubernetes 集群上安装交叉面板；
*   设置云提供商凭据；
*   为托管服务提供资源类。

应用程序所有者:

*   为托管服务提供资源声明；
*   将资源声明绑定到导出的 GitLab 舵图中；
*   使用交叉平面托管服务部署 GitLab 应用程序。

在一篇博客文章中，Upbound 的首席产品经理 Phil Prasek 描述了 Crossplane 如何支持将托管服务声明为 Kubernetes 中的资源声明，这些声明使用集群管理员配置的资源类动态绑定到适当的云提供商，以提供托管服务。Prasek 写道:“这提供了一种出色的关注点分离，使应用程序更具可移植性，同时为集群管理员保留了灵活性，以定制他们希望如何在其环境中提供这些托管服务。”。

Crossplane 还旨在适应组织内不同的运营团队，这些团队的任务是确保合规性、设置策略和维护独立云环境中的基础架构任务。虽然通过界面部署的应用程序显然是相同的，但 Crossplane 也有助于满足不同运营商团队的需求。

“我们今天展示了一个多云未来的真实例子，”塔巴拉说。“GitLab 是一个生产应用程序，它使用多个完全托管的服务，因此通过抽象这些服务并将它们与声明性的 Kubernetes API 集成，我们展示了编写一次即可在任何地方运行的能力。”

GitLab 和 KubeCon + CloudNativeCon 是新堆栈的赞助商。

Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>