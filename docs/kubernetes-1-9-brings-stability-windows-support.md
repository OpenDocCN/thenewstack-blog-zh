# Kubernetes 1.9 带来了稳定性和 Windows 支持

> 原文：<https://thenewstack.io/kubernetes-1-9-brings-stability-windows-support/>

Kubernetes 的下一个版本是 1.9，预计将于周五晚些时候发布，将支持 Windows 容器，以及一个新容器存储 API 的 alpha 版本。

它还在稳定性方面进行了一系列全面的改进，包括针对工作负载的稳定 API，据[云原生计算基金会](https://www.cncf.io/)和 Kubernetes 1.9 发布功能负责人[的开发者倡导者 Ihor Dvoretskyi](https://github.com/idvoretskyi) 称，这是去年 12 月首次推出的伞状功能。

总的来说，有四种 API 已正式上市:

*   **部署:**描述正在运行的应用程序的期望状态的基本方式，包括副本集。
*   **ReplicaSet:** 根据部署的配置，这可以确保应用程序有足够的运行容器实例(“副本”)来满足其定义。
*   **Daemonset:** 持续运行的应用程序的部署，不管其他应用程序可能正在运行什么，例如日志或监控解决方案。
*   **StatefulSet:** 适用于即使容器被终止并重新启动也需要持久状态的工作负载。StatefulSets 还为容器的网络标识或容器启动和停止的顺序等提供持久性。

转向 stable 意味着用户不再需要担心将它们用于任务关键型工作负载，因为他们知道 API 接口不会变成他们需要重新编码自己的应用程序才能继续使用的东西。

“如果你在为 Kubernetes 写东西，用简化的 API 会容易得多，”他说。

对 Windows Server 的支持已被广泛期待。微软在 10 月份将其 Azure 容器服务平台的缩写从 ACS 改为 AKS，以反映其对 Kubernetes 的关注。

在最近的 KubeCon 活动上，微软宣布了 [Virtual Kubelet](https://azure.microsoft.com/en-us/blog/azure-brings-new-serverless-and-devops-capabilities-to-the-kubernetes-community/) ，一个允许用户瞄准[Azure Container Instances(ACI)](http://www.eweek.com/cloud/microsoft-introduces-rapid-cloud-container-deployment-service)的连接器，一个加速 Azure 上容器的创建和部署的服务，以及对 [Heptio 的](https://techcrunch.com/2017/12/07/heptio-teams-up-with-microsoft-to-build-a-better-kubernetes-disaster-recovery-solution/) Ark backup and recovery utility 和 [Tigera 的](https://www.dailyhostnews.com/microsoft-teams-heptio-tigera-better-kubernetes-support-azure-windows-server-containers/) Calico 网络安全策略*的支持。*

Dvoretskyi 说，虽然 Windows 服务器支持已经进入测试阶段，但还不能用于生产环境。

“同时，beta 意味着它很快就会稳定下来。如果您计划在 Windows 环境下用 Kubernetes 构建一些东西，现在是开始使用它的好时机。一旦它达到稳定状态，你就会有一些使用它的经验，”他说。它将允许您使用 Windows 服务器向 Kubernetes 集群添加节点，并且 Windows 工作负载将在 Windows 机器上本地运行。

开发人员仍然有一个 Linux 控制平面来管理 Kubernetes 集群中的 Windows pods，但是那些想要编写针对 Windows 环境的应用程序的人将能够。

Cloudbase、Apprenda 和 [Red Hat](https://www.openshift.com/) 已经宣布在 Kubernetes 1.9 中支持 Windows Server Containers。

Dvoretskyi 说，[容器存储接口](https://github.com/container-storage-interface/spec) (CSI)，一个跨行业标准倡议，是对存储供应商对 Kubernetes 兴趣的回应。这是一个 alpha 特性，意味着不建议在生产中使用，必须显式启用。

容器存储接口将使用户能够插入和交换 Kubernetes 集群的存储。

“以前，如果您想在 Kubernetes 集群中使用其他存储解决方案，您必须确保它们在 Kubernetes 的代码库中默认可用。这也给想要为 Kubernetes 提供存储解决方案的存储供应商带来了困难。这使得供应商更容易为 Kubernetes 提供存储选项，”Dvoretskyi 说。

其他新功能:

*   硬件加速的 alpha 版本，允许使用 GPU 作为机器学习工作负载的资源。
*   IPv6 寻址的 Alpha 支持。
*   更快地验证[自定义资源定义](https://kubernetes.io/docs/concepts/api-extension/custom-resources/) (CRD)数据。CRDs 允许管理员定制和扩展 Kubernetes 的安装，而不会损害与新版本 Kubernetes 的兼容性。

此外，CNCF 宣布了[认证的 Kubernetes 一致性计划](https://www.cncf.io/certification/software-conformance/)，该计划验证在任何认证的 Kubernetes 发行版或平台上运行的工作负载将在其他认证的 Kubernetes 发行版或平台上正确工作，现在[包括](http://blog.kubernetes.io/2017/11/certified-kubernetes-conformance.html?utm_source=blog&utm_medium=referral)40 多个项目。

网络、存储和运行时接口标准的出现，以及一致性计划和服务网格项目(如 Istio)的相关可扩展性机制，是 Kubernetes 成熟的标志， [Google](https://cloud.google.com/kubernetes-engine) 的 Kubernetes 集团项目经理 [Aparna Sinha](https://www.linkedin.com/in/apsinha) 在 Kubernetes 与 KubeCon 新堆栈的[播客](https://thenewstack.io/where-is-kubernetes-headed-in-2018-and-beyond/)中说道。

[2018 年及以后，Kubernetes 向何处去？](https://thenewstack.simplecast.com/episodes/where-is-kubernetes-headed-in-2018-and-beyond)

“服务代理是成熟的标志，因为我们正在向上层移动，”她说。“这不仅仅是网络、操作系统和容器运行时的问题，这些都正在标准化，现在我们正在向上移动，并考虑如何确保服务得到认证和保护。”

她预测 2018 年将是集装箱和 Kubernetes 空间的安全年。

在 CoreOS 的博客中，Eric Chiang 阐述了该项目的目标，即将 Kubernetes 的整体存储库分割成更小、更易消耗的项目。

“从 1.9 开始，许多功能都是为此目的而设计的。Kubernetes 对[容器网络接口](https://github.com/containernetworking/cni) (CNI)的使用实现了一个丰富的网络选项生态系统。[自定义资源定义(CRDs)](https://coreos.com/blog/custom-resource-kubernetes-v17) 和聚合 API 服务器允许用户扩展 API，同时为自定义控制器和操作员保留熟悉的工作流程。用于身份验证和授权的 Webhook 插件允许与各种身份提供者和策略引擎集成。他说:[这个名单还在继续。](https://kubernetes.io/docs/concepts/overview/extending/)

他说，需要转移到外部项目的组件包括云控制器管理器、用于外部存储的 CSI 以及将 kubeadm 转移到自己的回购协议的长期目标，但这些都需要时间。

然而，另一个新功能 devstats.k8s.io 收集 Kubernetes 组织下 GitHub repos 的指标。它可以用于创建个人或公司贡献的摘要，以提供对项目整体进度的洞察。

[云本地计算基金会](https://www.cncf.io/)、 [CoreOS](https://coreos.com/) 和 [Red Hat](https://www.openshift.com/) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>