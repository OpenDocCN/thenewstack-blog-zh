# 5 对边缘数据的要求

> 原文：<https://thenewstack.io/5-requirements-for-data-at-the-edge/>

[MayaData](https://mayadata.io/) 赞助本帖。

 [穆拉特·卡尔斯利奥格鲁

Murat 是一名基础架构架构师，拥有存储、分布式系统和企业基础架构开发方面的经验。他是 MayaData 的产品副总裁，也是 CNCF 项目 *OpenEBS* 的维护者之一，还是*Kubernetes——devo PS 食谱大全*的作者。](https://www.linkedin.com/in/muratkarslioglu/) 

在 KubeCon+CloudNativeCon NA 2020 大会上，云计算原生计算基金会技术运营委员会主席 Liz Rice[将](https://youtu.be/bESogtuHwX0?t=322) *edge* 命名为[2021](https://twitter.com/CloudNativeFdn/status/1329863326428499971)第二大领先趋势。

虽然我们没有关于广泛部署的 OpenEBS 部署在哪里的具体数据，但由于其开源性质，调查和我们的商业业务表明会有更多的边缘部署。最近在多架构映像方面的贡献也表明 OpenEBS 正越来越多地用于基于 ARM 的集群。此外，专注于边缘的云提供商 Volterra 选择了[open EBS Mayastor](https://github.com/openebs/Mayastor)；另一家专注于边缘的托管服务提供商 Platform 9 也是如此。我们还与一些大型系统集成商合作，帮助服务提供商和零售商构建他们始终基于 Kubernetes 的边缘部署。

简而言之，我们每天都听到 Kubernetes 上关于边缘数据的需求。在这篇文章中，我们分享了一些我们所听到的。

## 边缘要求

我们看到了边缘数据管理的五个主要要求:

1.  **Kubernetes native** :既然 Kubernetes 是控制层，任何与 Kubernetes 行为不同的解决方案对我们合作的用户来说都有些可疑。从美国空军到美国电话电报公司，再到世界上最大的实体零售商，每个人都将 Kubernetes 视为他们的控制平台。这类用户希望看到 Kubernetes 根据需要用操作符、CRD 和容器进行扩展；大概就是这样。如果它不符合他们的工具链和专业知识，它就是可疑的。
2.  **可用的超融合架构**:在边缘，空间、电源和管理功能非常重要。与连接 CEPH 群集或其他横向扩展存储系统或阵列相比，使用由容器连接存储扩展的本地连接存储可以显著减少占用空间。与简单使用本地磁盘相比，高性能容器连接存储提高了可能的密度，因为与将整个主机专用于特定工作负载(通过使用直连存储)相比，它可以更轻松地运行和存储多个工作负载。
3.  **社区和开源**:这类似于关于成为 Kubernetes 原生用户的第一点——用户不希望被任何供应商的专有解决方案所束缚。他们希望并期望找到一个活跃的社区，独立于任何一家供应商。我发现具有讽刺意味的是，虽然像微软和 AWS 这样的大公司越来越多地拥抱开源——例如，最近的一个例子是 [AWS 开源](https://aws.amazon.com/about-aws/whats-new/2020/12/introducing-amazon-eks-distro/)他们在 EKS 使用的 Kubernetes 配置——但在存储、网络和安全领域仍然有一种趋势，试图出售专有的盒子和软件系统。当用户看到一个边缘架构时，它将在多年内涉及成千上万个位置，他们似乎对遗留的业务模型特别紧张。毕竟，对 Kubernetes 本身的需求(至少部分)是由组织内的高管层推动的，他们希望限制或消除云以及供应商锁定。
4.  **性能**:一方面，边缘的许多工作负载对性能并不敏感。另一方面，某些工作负载(如视频分析)肯定会浪费热量、空间和资金，如上文第二点所述，由底层硬件启用且未通过存储的每个 I/O 都会浪费热量、空间和资金。
5.  **企业级支持和解决方案工程**:最后，构建和运行分布式应用程序是很困难的，没有多少用户对他们现有的构建和运行大型分布式系统(包括边缘位置)的专业水平感到满意。像 Volterra、Mavenir 和 Platform 9 这样的公司——至少是我们所知道的全球系统集成商的一部分——似乎正在蓬勃发展。他们有不同的业务和技术，但他们的共同点是在构建和帮助运营基于 Kubernetes 的边缘系统方面的经验证的专业知识。

## 结论

正如你可能想象的那样，我们认为我们的软件非常符合上述趋势。最近的 [CNCF 调查](https://www.cncf.io/wp-content/uploads/2020/11/CNCF_Survey_Report_2020.pdf)也支持我们在 OpenEBS 采用和趋势方面的发现。OpenEBS 本身是一个 CNCF 项目，我们围绕它包装我们的支持和其他开源软件，为 edge 和其他用例进行产品化。

请试用并与我们分享您的反馈。你现在可以申请获得 Kubera Propel 的免费试用许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>