# Kubernetes 现在使用 Kubeadm 进行自托管

> 原文：<https://thenewstack.io/kubernetes-now-does-self-hosting-with-kubeadm/>

Kubernetes 现在可以建立自己的集群。

Kubernetes 容器编排软件的最新版本，本月早些时候发布的，由于 [kubeadm](https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/) 的正式发布，带来了[引导其自身部署的能力](https://kubernetes.io/blog/2018/12/04/production-ready-kubernetes-cluster-creation-with-kubeadm/)。

Kubeadm 可以通过一个命令启动 Kubernetes 集群。集群的设置由最佳实践默认设置定义，并完全符合经[认证的 Kubernetes](https://github.com/cncf/k8s-conformance/blob/master/terms-conditions/Certified_Kubernetes_Terms.md) 指南。

“您可以使用它来引导任何硬件上的任何集群。它可以在任何地方运行。“这只是引导 Kubernetes，获得二进制文件并把东西拼接在一起，”开发人员 Lucas kld strm 说，他是云原生计算基金会的大使，与 CNCF 开发人员 Luc Perkins 一起开发了这款软件。本月早些时候，在西雅图举行的 KubeCon + CloudNativeCon 大会上，kld strm 谈到了这款新堆栈。

Kubeadm 在部署 Kubernetes 集群的过程中自动化了一些棘手的步骤，包括每个节点的安全证书的颁发和协调，以及为系统的基于角色的访问控制(RBAC)理顺必要的权限。除了在集群上安装 Kubernetes 之外，kubeadm 还可以升级 Kubernetes 集群，或者只是在安装过程中执行一些操作，称为阶段。

对于想第一次尝试 Kubernetes 的人，以及想在裸机系统上部署 Kubernetes 的管理员来说，Kubeadm 可以节省时间。对于那些从云中获得 Kubernetes 的人来说，kubeadm 提供了一种简单的方式来定制运行云产品的 Kubernetes，如[亚马逊 EKS](https://aws.amazon.com/eks/) 和[谷歌 Kubernetes 引擎](https://cloud.google.com/kubernetes-engine/)，以满足他们自己的需求。

由于其有意限制的范围，kubeadm 可能更适合作为一个更大的部署系统的组件，该系统负责 Kubernetes 部署的其他方面，比如网络。它并不意味着是一个全栈 Kubernetes 安装工具，比如 [Kops](https://github.com/kubernetes/kops) ，它也包括其他软件，比如 network overlay。然而，Kubeadm 可以使 Kops 维护者的事情变得更简单，因为它标准化了这部分堆栈的安装过程和接口。

[用于 Mac 或 Windows 工作站的 Minikube](https://github.com/kubernetes/minikube) 使用 kubeadm 作为基础。它与[集群 API](https://github.com/kubernetes-sigs/cluster-api) 配合得很好，后者是一个 Kubernetes，提供一组声明性的、Kubernetes 风格的 API 来创建、配置和管理集群。

要运行 kubeadm，现有集群硬件或虚拟机必须已经启动并运行。Kubeadm 对于网络基础设施是不可知的，并且与符合[容器网络接口](https://github.com/containernetworking/cni)的覆盖网络配合良好。通过在一台机器上运行 [kubeadm init](https://kubernetes.io/docs/reference/setup-tools/kubeadm/kubeadm-init/) 命令，创建一个新的控制平面和 Kubernetes 实例。该流程还使用[kube ADM _ join](https://kubernetes.io/docs/reference/setup-tools/kubeadm/kubeadm-join/)command 为其他节点生成登录令牌。

kld strm 还希望这项工作将阻止 Kubernetes 分销商之间任何可能的分裂，否则他们将制定自己的部署方案，这些方案可能互不兼容。

“我们不希望 10 年后出现这种情况，你有三个不同的阵营，你不能在它们之间切换，”他说。“我们真的试图让这一层的东西尽可能通用，并对每个人开放。”

[https://www.youtube.com/embed/YCOWQIFVAbg?feature=oembed](https://www.youtube.com/embed/YCOWQIFVAbg?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>