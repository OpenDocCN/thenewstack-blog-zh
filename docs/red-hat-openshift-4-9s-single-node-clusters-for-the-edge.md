# Red Hat OpenShift 4.9 的边缘单节点集群

> 原文：<https://thenewstack.io/red-hat-openshift-4-9s-single-node-clusters-for-the-edge/>

开源企业软件提供商[红帽](https://www.openshift.com/try?utm_content=inline-mention)在本周的 [KubeCon+CloudNativeCon 北美](https://www.openshift.com/try?utm_content=inline-mention)发布了用于 Kubernetes 2.4 的[红帽 OpenShift 4.9](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/4/html/4.9_release_notes/index) 和[红帽高级集群管理。](https://www.redhat.com/en/technologies/management/advanced-cluster-management)

该公司在一份声明中表示，这两个版本都是“旨在将开放混合云的一致性推向企业网络的最远端”，Red Hat 市场洞察总监 Stu Miniman 也表达了同样的观点，称这一版本是“我们过去两年来为 OpenShift 在边缘所做工作的高潮。”

Red Hat OpenShift 4.9 将 [Kubernetes](https://thenewstack.io/category/kubernetes/) 整合为一个企业平台，不仅带来了 Kubernetes 1.22，还引入了单节点 OpenShift，将控制和工作者功能结合到单个服务器中。单节点服务器是 OpenShift 边缘部署的第三个选项，它加入了过去两年发布的[三节点集群](https://www.openshift.com/blog/delivering-a-three-node-architecture-for-edge-deployments)和[远程工作节点](https://www.redhat.com/en/about/press-releases/red-hat-extends-open-hybrid-cloud-edge)，并为可能会出现连接中断的环境提供了一个选项，因为不需要中央 Kubernetes 控制平面。

Miniman 解释说，每种部署方案与其他方案相比都有利弊。三节点集群提供相对较小但高度可用的空间，而远程工作节点适用于空间更有限的环境，而新的单节点选项最适合连接受限的情况。

虽然单节点方案不提供高可用性，但它确实可以在离线时继续运行，并在再次连接时同步备份。

这些边缘部署的另一个好处是潜在的成本节约，Miniman 强调这是针对边缘端点而不是边缘设备的完全 OpenShift 部署。

“从定价角度来看，当客户大规模这样做时，边缘解决方案会有一些成本影响，我们可以让它更具成本效益，”Miniman 说。“如果您要处理数百或数千个节点，使用的资源将比主部署少得多。”

Red Hat Advanced Cluster Management[在该公司 2020 年 Red Hat 峰会期间](https://thenewstack.io/red-hat-expands-openshift-to-ease-developer-use/)首次发布，然后在去年的 KubeCon Europe 上[全面推出，现在，Red Hat Advanced Cluster Management 2.4(现在管理所有三种类型的 edge OpenShift 部署)引入了几个新功能。](https://thenewstack.io/kubecon-eu-red-hat-expands-openshift-to-the-edge-with-advanced-cluster-management/)

首先，Advance Cluster Management 2.4 将单个集线器上的集群容量从 1，000 个增加到 2，000 个，增加了一倍，并为受管设备群提供了 IPv6 双堆栈支持，这一功能现已在技术预览版中提供。

接下来，高级集群管理 2.4 获得了中心端策略模板，通过将单个策略应用于不同的集群场景，使管理大规模部署变得更加容易。Miniman 解释说，这些被称为[验证设计](http://hybrid-cloud-patterns.io/)，并且“不仅仅是‘这里是一些最佳实践’，它是 GitHub 上可用的代码，允许你使用 GitOps 操作实践来扩展。”

最后，高级集群管理 2.4 增加了零接触配置的技术预览，无需有人打开服务器并手动启动配置过程，即可实现服务器的远程配置。相反，零接触式配置包括远程开机、通过网络引导、下载必要的配置、安装，以及最终向中央管理系统报告服务器在线并准备好工作负载。

虽然 Red Hat 在 Kubecon 期间宣布了这些新平台，但 Red Hat OpenShift 4.9 预计将于本月晚些时候正式上市，而 Advance Cluster Management 2.4 预计将于 11 月上市。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>