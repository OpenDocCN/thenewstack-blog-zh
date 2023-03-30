# KubeMove:跨 Kubernetes 集群移动数据，无需专有扩展

> 原文：<https://thenewstack.io/kubemove-move-data-across-kubernetes-clusters-without-proprietary-extensions/>

OpenEBS 背后的人发起了一个新项目，旨在提供一个代码库，允许 Kubernetes 用户在集群之间自由移动数据。 [KubeMove](https://www.kubemove.io/) 包括一个 [Kubernetes 操作符](https://thenewstack.io/databases-operators-bring-stateful-workloads-to-kubernetes/)和 API。

“用户希望简单地将数据从集群 A 转移到集群 B，”负责监管开源 [OpenEBS](https://docs.openebs.io/) 容器存储软件的 [MayaData](https://mayadata.io/) 的首席执行官 [Evan Powell](https://www.linkedin.com/in/epowell/) 说。

上个月，谷歌云推出了 [Anthos](https://cloud.google.com/blog/topics/hybrid-cloud/new-platform-for-managing-applications-in-todays-multi-cloud-world) ，这是一个[托管的 Kubernetes 服务](https://thenewstack.io/anthos-kubernetes-infrastructure-to-make-developers-more-productive/)，包括跨不同集群移动数据的能力。这惊动了鲍威尔和他的同事，促使他们创建了 KubeMove。目前，最初由 Google 创建的 Kubernetes 本身还没有跨不同 Kubernetes 集群迁移数据的机制，尽管这个问题正在由 Kubernetes 联盟项目解决。

Powell 说，随着围绕云原生计算的生态系统变得越来越复杂，Kubernetes 作为一种在没有专有云提供商扩展的情况下在云中运行工作负载的工具的最初吸引力可能会减弱，因为组织转向了 Anthos 等托管服务。

“这很好，这是他们的决定，”鲍威尔在谈到谷歌的 Anthos 时说。“但这有让用户失望的风险。如果他们认为 Kubernetes 是一张出狱卡(来自专有服务)，然后他们发现这些移动数据的部分是专有的。”将这种方法与[容器存储接口](https://github.com/container-storage-interface/spec/blob/master/spec.md) (CSI)进行比较，后者是 Kubernetes 与存储交互的标准化方法，用于提供快照、恢复和整个行业所需的其他功能。

【T2![](img/68769c8c32b528d80931ebe2a5415c6a.png)

KubeMove 的基本功能包括:

*   能够在本地和云之间或云之间移动应用程序。
*   将遗留数据转移到 Kubernetes 集群上。
*   为 Kubernetes 和其他应用程序的升级申请做好准备。

KubeMove 从 kubectl 命令行工作:

```
kubectl km move init  &lt;app&gt;  &lt;kubemove-template.yaml&gt;

```

```
kubectl km status  &lt;movepair-cr&gt;

```

```
kubectl km move switch  &lt;movepair&gt;

```

因为 KubeMove 是一个新项目，鲍威尔希望吸引更多的外部贡献者。到目前为止，该项目已经在 GitHub 上获得了 18 颗星，有两个贡献者提交了 35 个项目。最终，Powell 希望看到 KubeMove 在上游的 Kubernetes 代码库中被接受，这样它将成为一个标准的 Kubernetes 命令。KubeMove 是在 Apache 2.0 许可下发布的。

## 存储虚拟化

上周，云原生计算基金会接受了 MayaData 的 OpenEBS 作为[云原生沙盒项目](https://www.cncf.io/sandbox-projects/)。MayaData 将 OpenEBS 描述为“容器附加存储”，能够为基于容器的操作提供有状态存储。

有了 OpenEBS，每个容器都有一个专用的存储控制器，它执行粒度存储策略和隔离。根据文档，OpenEBS 运行在用户空间，没有任何 Linux 内核模块依赖关系。

OpenEBS 通常与 Kubernetes 部署结合使用，被 Adobe、Cisco、IBM、NuoDB、ActivEngage、Streetline 等公司使用。Wirpo 使用该软件作为其宣布的多云管理解决方案的一部分，正如 Red Hat for RedHat OpenShift 一样。

KubeCon + CoudNativeCon Europe 的与会者有关这两个项目的更多信息，请参观 KubeCon 展馆的 SE41 展位。该公司还将展示其即将发布的 MayaData OpenEBS Enterprise，其中包括对 TCP 上的 NVMe 的支持。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>