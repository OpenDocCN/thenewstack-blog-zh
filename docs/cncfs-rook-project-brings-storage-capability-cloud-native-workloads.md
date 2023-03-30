# CNCF 的 Rook 项目为云原生工作负载带来了存储能力

> 原文：<https://thenewstack.io/cncfs-rook-project-brings-storage-capability-cloud-native-workloads/>

云原生存储软件 storage [Rook](https://rook.io/) 已经被[云原生计算基金会](https://www.cncf.io/kubecon-cloudnativecon-events/) (CNCF)作为初始级项目接受。

“存储是云原生计算最重要的组成部分之一，然而持久存储系统今天通常在云原生环境之外运行，”CNCF 首席运营官[克里斯·阿尼斯奇克](https://twitter.com/cra)在一份声明中说。

Rook 接受了为主要在云环境中运行的应用程序设置存储的挑战，考虑到存储的复杂性和工作负载可以在不同云环境中迁移的容易性，这是一项具有挑战性的任务。Rook 可以在 Kubernetes 集群的权限下统一文件、块和对象存储类型，这可以在存储和需要存储的应用程序之间架起一座桥梁。

Aniszczyk 说:“Rook 是 Kubernetes 运营商模式的早期采用者之一，我们很高兴引入 Rook 作为一个初始级项目，以推进云原生存储的状态。”

基于 Ceph 构建的开源 Rook 提供了可在商用硬件上运行的可轻松扩展的文件、块和对象存储资源。它还附带了额外的数据保护功能，如快照、克隆和版本控制。

 [鲁克，一目了然

*   47 名捐助者
*   1935 颗 GitHub 星星
*   13 个版本
*   1，463 次提交
*   超过 125 万次容器下载](https://rook.io/) 

通过在 Kubernetes 下整合存储，用户可以开发一个完全自给自足且可移植的云原生集群，该集群可以跨多个云服务以及内部部署运行。

Rook 是 CNCF 毕业标准 v1.0 下的初始阶段项目。CNCF 为每个项目提供了一个相关的成熟度等级，即初始、孵化或毕业。要成为一个初始阶段的项目，软件必须增加云本地计算的价值，并且符合 CNCF 章程。

该项目是 CNCF 主办的第 15 个以云为本的项目，其他项目包括 Kubernetes、Prometheus、OpenTracing、Fluentd、Linkerd、gRPC、CoreDNS、containerd、rkt、CNI、Envoy、Jaeger、公证人和 TUF。

Rook 的创建者[Bassam Tabbara](https://github.com/bassam),[Upbound](https://upbound.io)的首席执行官在最近的[软件工程日报](https://softwareengineeringdaily.com/2018/01/18/kubernetes-storage-with-bassam-tabbara/)播客中指出，Rook 本质上是扩展了 Kubernetes 操作模式，以识别存储集群、存储池、对象存储和文件系统。

目前有一个 alpha 版本的[Rook](https://github.com/rook/rook)(0.6 版)，承诺在 2018 年上半年推出量产版。

最近发布的 Kubernetes 1.9 引入了[容器存储接口](https://github.com/container-storage-interface/spec)的 alpha 实现，它有望使安装新的卷插件像部署 pod 一样简单。这为第三方存储提供商支持 Kubernetes 部署开辟了一条道路。

“在 Kubernetes 上运行存储集群是一种天然的选择。将它纳入进来并保持统一的管理界面是非常明智的，”Rook 项目的最初发起人 [Quantum](https://quantum.com) 的高级主管丹·克恩斯在一份声明中说。

[Kubernetes 为容器本地存储做好准备](https://thenewstack.simplecast.com/episodes/kubernetes-sets-the-stage-for-container-native-storage)

通过 Pixabay 的特征图像。

[云计算原生计算基金会](https://www.cncf.io/kubecon-cloudnativecon-events/)是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>