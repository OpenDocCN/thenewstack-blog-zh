# 新的 Microsoft、Oracle 项目将 Kubernetes 与无服务器环境连接起来

> 原文：<https://thenewstack.io/microsoft-oracle-extend-kubernetes-new-serverless-projects/>

上周在奥斯汀举行的 Kubecon 2017 上，[微软](https://azure.microsoft.com/en-us/?v=17.14)和甲骨文都发布了新软件，以进一步将[无服务器](/category/serverless/)功能集成到 [Kubernetes](/category/kubernetes/) 开源容器编排软件中，并管理不需要用户管理的服务器运行的容器操作。

Oracle 已经开源发布了一个安装程序，允许其无服务器软件 Fn 安装在 Kubernetes 上；同样在展会上，微软推出了虚拟 Kubelet，它伪装成 Kubernetes kubelet 节点代理，将 Kubernetes 连接到 K8s 的容器环境之外的 API 服务。

10 月，甲骨文发布了 [Fn 项目](http://fnproject.io/)的源代码，该项目由 [Chad Arimura](https://www.linkedin.com/in/chadarimura/) 和 [Iron.io](https://www.iron.io/) 的其他成员开发，他们是在甲骨文公司被 Xenon Ventures 收购后加入甲骨文[的。从](https://blog.iron.io/full-circle-iron-io/) [IronFunctions](https://github.com/iron-io/functions) 派生而来，Fn 通过将代码放在容器中，提供了一种执行用多种语言编写的函数的方法。该软件具有内置的负载平衡器，并与 AWS Lambda 功能即服务完全兼容。关联软件 Fn 流提供了一种使用开发人员喜欢的语言和开发环境来构建更高级别的工作流和编排的方法。

Arimura 说，与 Kubernetes 的合作在许多方面都是有用的。在微服务环境中， [Kube-DNS](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/dns) 可用于从您的功能中自我发现微服务，反之亦然。Kubernetes 为管理基础设施(包括无服务器部署)提供了一个统一的基础。

该安装程序允许 Kubernetes 网络中的用户，如[Oracle Container Engine Cloud Service](https://cloud.oracle.com/en_US/containers)，使用 Fn 无服务器功能。Fn 安装程序也已经与 [Oracle 容器本地应用开发平台](https://www.zdnet.com/article/oracle-unveils-container-native-application-development-platform/)集成。

微软的工作也借鉴了早期的成果。7 月，该公司为其无服务器容器运行时 [Azure 容器实例](https://azure.microsoft.com/en-us/services/container-instances/) (ACI)发布了自己的 Kubernetes 连接器。该公司扩展了这个连接器的范围，[现在被称为虚拟 Kubelet](https://azure.microsoft.com/en-us/blog/azure-brings-new-serverless-and-devops-capabilities-to-the-kubernetes-community/) ，通过 Kubernetes 原语的可插拔架构来支持其他运行时。

“我们认为 Azure Container 实例是一个低级别的编排，我们希望使用 Kubernetes 作为更高级别的编排，”微软杰出的工程师和 Kubernetes 的创始人之一[布伦丹·伯恩斯](https://www.linkedin.com/in/brendan-burns-487aa590/)说。

虚拟 Kubelet 是一个 Kubernetes [Kubelet](https://kubernetes.io/docs/reference/generated/kubelet/) ，一个运行在每个 Kubernetes 节点上的小代理。这个 Kubelet 提供了一个通向其他 API 主导的服务的网关。“Kubernetes API 在上面，可编程返回”，这是该软件的 [GitHub 页面对它的描述](https://github.com/virtual-kubelet/virtual-kubelet)。

[![](img/49d21129f8b470fc0d2c4e21fc521f80.png)](https://github.com/virtual-kubelet/virtual-kubelet)

Virtual Kubelet 有一个可插入的提供者接口，用于定义将由非容器环境执行的动作，包括“无服务器”服务。这使得通过 Kubernetes API 使用按需和近乎即时的容器计算服务成为可能，而无需管理虚拟机或其他支持这些服务的设备，也无需为此付费。

Kubernetes 能够调度作业，因此可以调用资源，允许用户只为实际用于完成工作的云时间付费。间歇性工作负载，如持续集成和部署开发管道，或批处理作业，将是这种设置的理想选择:“任何你没有东西一直在运行的地方，”微软 Azure 容器运营项目经理 [Gabe Monroy](https://twitter.com/gabrtv) 说。

Kubelet 已经集成到 Azure 命令行界面(CLI)中，允许 Azure 用户非常快速地将 Kubelet 安装到一个 [Azure 容器服务](https://azure.microsoft.com/en-us/services/container-service/) (AKS)集群中。服务提供商 [Hyper](https://thenewstack.io/hyper-sh-mixes-containers-hypervisors-something-called-hypernetes/) 正在为此做出贡献。该公司已经将连接器[分叉为在自己的 Hyper.sh 云上运行安全容器](https://github.com/hyperhq/hyper.sh-connector-k8s#hypersh-container-connector-for-kubernetes-experimental)，包括最近推出的 [Kata 容器](https://katacontainers.io/)。在 KubeCon，Burns 和 Monroy 都与其他供应商进行了交谈，这些供应商也对将 Kubelet 用于他们自己的软件感兴趣。

“仍然有许多有趣的开放式问题有待 Kubernetes 和调度程序解决，但我认为我们会进行这些对话，不是作为‘Azure ’,而是作为一个对无服务器容器感兴趣的群体，”Monroy 说。

管理 Kubernetes 的[云本地计算基金会](https://www.cncf.io/)和[微软](https://azure.microsoft.com/en-us/?v=17.14)是新堆栈的赞助商。

专题图片:甲骨文公司的 Bob Quillin(左)和 Chad Arimura 在 KubeCon 2017 上。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>