# Kubernetes 如何成为分布式应用程序的通用控制平面

> 原文：<https://thenewstack.io/how-kubernetes-is-becoming-the-universal-control-plane-for-distributed-applications/>

Kubernetes 正在成为现代应用和基础设施环境中最好的控制平面之一。这个强大的调度程序最初是为了处理在适当的节点上放置 pod 而设计的，具有很强的可扩展性。它可以解决传统分布式系统中存在的许多问题。

Kubernetes 正迅速成为高度分布式环境中调度和管理作业的首选控制平面。这些工作可能包括在物理主机上部署虚拟机，在边缘设备上放置容器，甚至将控制平面扩展到其他调度器，如无服务器环境。

从裸机服务器到虚拟机，再到物联网(IoT)设备，再到托管云服务，Kubernetes 已经超越了容器和容器，以应对多种供应和调度挑战。

下面是这种模式的几个例子:

## 交叉平面

[Crossplane](https://crossplane.io/) 旨在使用由 Kubernetes 首创的以 API 为中心的声明式配置和自动化方法来标准化基础设施和应用管理。它是一个统一的控制平面，可与现有工具和系统无缝集成，并可轻松设置策略、配额和跟踪报告。

Crossplane 充当 Kubernetes 和传统工作负载(如数据库，甚至是公共云中的托管服务)之间的桥梁。DevOps 可以使用相同的 YAML 规范声明外部资源，以及本地 Kubernetes 应用程序。这种方法通过将版本控制、持续集成和部署扩展到非 Kubernetes 资源，鼓励将配置作为代码。

## K3s

【Rancher 的 K3s 是经过认证的 Kubernetes 发行版，专为在高度受限的环境中运行的生产工作负载而设计，如物联网和边缘计算部署。

K3s 可以部署在公有云中最多的虚拟机上，甚至可以部署在树莓派设备上。其架构在保持与云本地计算基金会(CNCF) Kubernetes 一致性测试完全兼容和合规的同时，针对资源受限设备上的无人值守远程部署进行了高度优化。

K3s 通过使 Kubernetes 可访问和轻量级，将它带到了边缘计算层。

## 库比奇

在西雅图举行的 KubeCon+CloudNativeCon 2018 上，华为展示了 [KubeEdge](https://kubeedge.io/en/) ，这是一个将 Kubernetes 的力量推向边缘的官方项目。

KubeEdge 基于华为智能边缘架构(IEF)——一个基于华为物联网 PaaS 的商用物联网边缘平台。IEF 的很大一部分已经被修改并为 KubeEdge 开源。KubeEdge 在 1.3 版本中可用，非常稳定，解决了与物联网和边缘相关的关键用例。它可以安装在受支持的 Linux 发行版和像 Raspberry Pi 这样的 ARM 设备上。

KubeEdge 项目也是 CNCF 沙盒的一部分。

## 库伯维特

Kubernetes 的虚拟机管理插件 KubeVirt ，旨在允许用户在他们的 Kubernetes 或 OpenShift 集群中的容器旁边运行虚拟机。它通过 Kubernetes 的自定义资源定义(CRD) API 为虚拟机和虚拟机集添加资源类型，从而扩展了 Kubernetes。KubeVirt 虚拟机在常规的 Kubernetes pods 中运行，它们可以访问标准的 pod 网络和存储，并且可以使用 Kubernetes 的标准工具(如 kubectl)进行管理。

KubeVirt 是 CNCF 沙盒的一部分。

## 虚拟库伯勒

微软的[虚拟 Kubelet](https://virtual-kubelet.io/) 项目是 Kubelet 代理和 Kubernetes API 最有趣的扩展。虚拟 Kubelet 是一个在外部环境中运行的代理，它注册为 Kubernetes 集群中的一个节点。代理通过 Kubernetes API 创建一个节点资源。通过利用污染和容忍的概念，它通过调用其本机 API 在外部环境中调度 pod。

虚拟 Kubelet 与 [Azure 容器实例](https://azure.microsoft.com/en-us/services/container-instances/)、 [Azure IoT Edge](https://azure.microsoft.com/en-us/services/iot-edge/) 和 [AWS Fargate](https://aws.amazon.com/fargate/) 控制平面一起工作。

虽然 Kubernetes 在容器编排方面有一个卑微的开端，但它很快发展成为云和边缘的操作系统。Kubernetes 是跨越数据中心、混合云、公共云和多云环境的现代基础设施的基础。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>