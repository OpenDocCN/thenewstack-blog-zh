# KubeEdge 及其在多接入边缘计算中的作用

> 原文：<https://thenewstack.io/kubeedge-and-its-role-in-multi-access-edge-computing/>

[Futurewei](https://www.futurewei.com/) 赞助本帖。

 [安妮·赖

安妮领导 Futurewei 开源项目的开源运营和营销，涵盖 Kubernetes、Cloud Native、Cloud-Edge、OpenStack、开放存储和 AI/深度学习。她之前在 OpenStack 基金会董事会任职，目前在 CNCF 和 OCI 董事会任职。](https://www.linkedin.com/in/annilai/) 

[KubeEdge](https://kubeedge.io/en/) ，云本地计算基金会(CNCF)沙盒项目，旨在将 Kubernetes 从云扩展到边缘。它为在边缘节点上部署和编排云原生服务以及与云进行元数据同步提供了基础架构支持。

KubeEdge 旨在应对边缘计算领域的以下三大挑战:

*   云和边缘之间的网络可靠性。
*   边缘节点上的资源约束。
*   边缘架构的高度分布式和可扩展性挑战。

KubeEdge 在云端有一个控制平面，在边缘端有工作节点。本机容器应用程序可以从云到边缘进行编排。云和边缘节点是松散耦合的，因此在云和边缘之间的网络连接失败的情况下，边缘的代理可以自主管理边缘的服务和物联网设备。一旦云和边缘之间的网络连接恢复，元数据可以重新同步以确保持久性。 [KubeEdge 1.2](https://kubeedge.io/en/blog/release-v1.2/) 包括额外的网络增强功能，以确保云和边缘之间更可靠的消息传递和数据传输。

## **相同的 Kubernetes 在云和边缘的用户体验**

KubeEdge 基于 Kubernetes 构建，遵循相同的开放和可扩展架构:

*   边缘的模块化计算平台。Beehive 被用作基于 go-channels 的消息传递框架，用于 KubeEdge 模块之间的通信。EdgeMesh 在边缘提供 ServiceMesh，使服务能够在不同的 pod、节点和位置上运行。
*   KubeEdge 已经与 Kubernetes CRI、CSI、CNI 接口集成，连接到运行时、存储和网络资源。此外，KubeEdge 还开放了与其他 CNCF 项目的集成，如 Envoy、Prometheus 和 etcd。
*   [KubeEdge 1.3](https://kubeedge.io/en/blog/release-v1.3/) ，最近于 2020 年 5 月发布，增加了更多功能，以改善 pod 日志记录、监控、管理和云边缘节点的可维护性。
*   KubeEdge 解决的一个关键挑战是管理地理上分散的边缘节点。KubeEdge 支持对远程边缘节点和在其上运行的应用程序进行“集中管理”。这是一个主要的远程管理功能。
*   展望未来，KubeEdge 项目团队将包括新功能，如边缘到边缘的通信和边缘上的数据分析框架。

## **面向物联网和边缘的可扩展基础设施**

基于 Kubernetes，KubeEdge 是高度广泛的。在运行时，边缘上的当前代理内存占用大约为 10MB。边缘硬件可以小到树莓派，也可以大到多核服务器或集群。KubeEdge 使用实现 MQTT 协议的 Eclipse Mosquitto 消息代理，这使得它适用于物联网消息传递(如低功耗传感器)或移动设备(如电话、嵌入式计算机或微控制器)。

## **MEC**

多接入边缘计算(MEC)，以前称为移动边缘计算，由欧洲电信标准协会(ETSI)定义。它是一个网络架构概念，使云计算和 It 功能能够在网络边缘运行。运行在边缘节点(更接近终端用户)而不是云上的应用或服务可以享受更低延迟和增强终端用户体验的好处。MEC 有大量潜在的垂直和水平用例，如自动驾驶汽车(AV)、增强现实(AR)和虚拟现实(VR)、游戏、人工智能(AI)、机器学习(ML)和深度学习(DL)支持的应用，如自主导航、使用自然语言处理(NLP)或面部识别的远程监控、视频分析等。

MEC 为无线接入网(RAN)提供实时、低延迟的接入，这为电信公司向新的生态系统和价值链开放其网络和区域数据中心资源提供了一个绝佳的机会。在过去几年中，超大规模云提供商通过将其云功能和服务扩展到边缘(通过网关和本地服务器/数据中心边缘)甚至设备边缘(运行具有一些应用逻辑的物联网设备的受限设备边缘或智能设备边缘)，超越了他们的公共云。例子包括微软 Azure 物联网 Edge 和 AWS 物联网 Greengrass。最近，我们看到超大规模云提供商和电信公司结成合作伙伴关系，抓住来自 MEC 的机遇。例如，谷歌和美国电话电报公司，微软和美国电话电报公司，AWS 和威瑞森。

虽然所有这些超大规模专有公共云都在利用 MEC 提供的机会，但 KubeEdge 提供了一种可行的开源边缘解决方案来支持 MEC。

## **MEC 是 KubeEdge** 的一个很好的用例

[Akraino](https://www.lfedge.org/projects/akraino/) 是 Linux Foundation Edge 项目，旨在为各种用户案例(如 5G、AI、Edge IaaS/PaaS 和面向提供商和企业边缘领域的物联网)创建和发布“经过充分测试”的开源电信边缘堆栈。这是通过社区贡献和测试的蓝图来实现的，随后由 AkrainoAPI 分委员会发布 API 白皮书和测试的蓝图以供行业采用。

2020 年 4 月，一个由 Arm、中国移动、Futurewei 和 Signalogic 的成员组成的工作团队提出了“Akraino KubeEdge Edge 服务家族(类型 1: ML 推理卸载)”蓝图，以展示在 MEC 环境中利用 KubeEdge 的端到端 ML 推理卸载解决方案堆栈(支持英特尔 X86 和 Arm 架构)，该蓝图被成功接受为 Akraino 孵化项目。

## **用例**

Akraino KubeEdge Edge 服务可以部署在企业边缘，或者作为云边缘扩展与核心电信网络接口。它支持以下使用案例:

*   用于手机图像识别推理和训练的最大似然卸载
*   自动语音识别(ASR)现场操作
*   制造生产线缺陷检查

[蓝图](https://wiki.akraino.org/display/AK/KubeEdge+Edge+Service+Blueprint)将提出端到端边缘堆栈解决方案，并解决以下 MEC 挑战:

*   边缘上的有限内存占用—随着更多业务逻辑在边缘上运行，大量数据将在边缘上生成。
*   云和边缘之间的网络可靠性
*   具有上下文转移需求的边缘应用移动性
*   边缘和云之间的数据隐私
*   整体效率和可扩展性

这个蓝图项目还在早期，欢迎大家的支持和参与。它的目标是创建一个开放源代码的 MEC 解决方案，供所有人使用。

关于这个蓝图的更多细节，请参考[的网页](https://wiki.akraino.org/display/AK/KubeEdge+Edge+Service+Blueprint)。

有关 KubeEdge 的更多详情，请参考[其网站](https://kubeedge.io)和 [GitHub 简介](https://github.com/kubeedge/kubeedge)。

亚马逊网络服务、云本地计算基金会和 Linux 基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>