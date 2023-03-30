# Kubermatic 承担更多的 Kubernetes-管理重任

> 原文：<https://thenewstack.io/kubermatic-assumes-more-kubernetes-management-heavy-lifting/>

最近正式发布的 [KubeOne 1.4](https://github.com/kubermatic/kubeone) 和[Kubermatic Kubernetes Platform(KKP)2.19](https://www.kubermatic.com/blog/kubermatic-kubernetes-platform-2-19-is-ga/)反映了 Kubermatic 的持续推动——主要基于开源社区的反馈——通过扩展 Kubernetes 集群管理的自动化来继续支持 DevOps 团队。

Kubermatic 最初称为 Loodse，直到该公司在 2020 年更改了名称，它一直试图为 DevOps 团队提供一种集中和简化的方式来创建和管理 Kubernetes 集群，尤其是在大规模的情况下。旨在管理 Kubernetes 部署和管理的许多极其复杂的任务，运行在引擎盖下的自动化是一个关键组件。Kubermatic 平台和工具承担了许多复杂的命令和过程，否则 DevOps 团队可能不得不自己进行配置。

Kubermatic KubeOne 旨在通过跨云、内部、边缘和物联网环境的 API 实现集群运营管理的自动化。KubeOne 1.4 引入了一个新的 KubeOneCluster API 版本。Kubermatic 的代表描述了前一版本如何为用户提供新的插件 API、对加密提供商的托管支持以及自动化的 Docker-to-containerd 迁移。

## KubeOne 1.4

KubeOne 1.4 提供了一个新版本的 KubeOneCluster API，解决了用户在集群配置管理方面遇到的许多问题，[Kubermatic 的软件工程师 Marko mud rini](https://www.linkedin.com/in/xmudrii/)告诉新堆栈。其中一个问题是用户需要一个 ContainerRuntime 特性来配置注册表镜像、私有注册表和其他用户以前必须手动运行的配置任务。

Mudrini 告诉新的堆栈，用户经常表示需要这些 ContainerRuntime 功能“开箱即用，这在以前是不可能的”。

开源社区为开发 CNI 纤毛对 KubeOne 1.4 版本的支持提供了大量的投入。作为 CNCF(云本地计算基金会)在云本地环境中容器工作负载之间的网络连接的孵化项目，Cilium 已经与 KubeOne 集成，因此用户可以利用构建在 Cilium 之上的 [Hubble 插件](https://docs.cilium.io/en/v1.8/intro/#:~:text=Hubble%20is%20a%20fully%20distributed,in%20a%20completely%20transparent%20manner.)。Hubble 通过仪表板为 KubeOne 用户提供 Cilium 的网络和安全可观察性，实现“以完全透明的方式深入了解服务的通信和行为以及网络基础设施；”根据哈勃附加文件。

KubeOne 1.4 提供的其他新功能包括:

*   通过对用于创建和管理 Kubernetes 集群中工作节点配置的操作系统管理器(OSM)的“实验性”支持，更好地控制混合和边缘部署。
*   增加了对外部云控制器管理器(CCM)和 CSI 驱动程序的支持。

## KKP 2.19

Kubermatic Kubernetes Platform(KKP)2.19 版本专门针对 KKP 的边缘和混合云功能以及网络性能进行了改进。

Kubermatic 的产品经理[塔米·巴塔查里亚](https://www.linkedin.com/in/mita-bhattacharya-aa0375176?originalSubdomain=in)告诉新的堆栈:“这一版本专注于改善用户体验，提高网络性能，并为边缘用例的高需求空气间隙环境铺平道路。”Bhattacharya 说:“已经运行了几个分布式 Kubernetes 部署的组织需要访问多个仪表板，以获得全面的状态概述。为了帮助这些组织简化他们的 Kubernetes 操作，而不必放弃现有的集群，KKP 用户可以直接从 KKP 仪表板管理和升级外部集群。"

在 2.19 版本中，Bhattacharya 说现在可以导入现有的 AK、EKS 和 GKE 集群，并使用 KKP 仪表板管理它们的生命周期。Bhattacharya 说:“这仅仅是通过使用 API 实现的。“此外，我们现在为操作系统管理器(OSM)提供实验性支持，使用户能够在混合云和边缘环境中更好地控制他们的操作系统。我们将在即将到来的空气间隙环境中利用这一点，这些环境对高级边缘用例有很高的需求。”

像 KubeOne 1.4，有很多强调纤毛 CNI 支持。Bhattacharya 说，KKP 用户现在可以“在两个最受欢迎的 CNIs Canal 和 Cilium 之间选择，或者简单地添加和管理他们选择的 CNIs 不管它是否受 KKP 支持。

“通过增加对 CNI 纤毛的支持，我们不仅为用户提供了两个 CNI 最佳选项，还为他们提供了选择他们喜欢的选项。例如，KKP 用户可以从用户界面中选择默认的 CNI，”Bhattacharya 说。“我们提供了运河和纤毛的选择，或者他们可以选择自带 CNI。未来，我们的目标将是继续为我们的所有功能提供这种灵活性。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>