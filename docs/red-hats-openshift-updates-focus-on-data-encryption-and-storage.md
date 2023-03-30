# 红帽的 OpenShift 更新侧重于数据加密和存储

> 原文：<https://thenewstack.io/red-hats-openshift-updates-focus-on-data-encryption-and-storage/>

本周， [Red Hat](https://www.redhat.com/en) 推出了其企业 Kubernetes 平台的最新版本 [OpenShift 4.3](https://blog.openshift.com/introducing-red-hat-openshift-4-3-to-enhance-kubernetes-security/) ，以及[open shift Container Storage 4.2](https://blog.openshift.com/introducing-openshift-container-storage-4-2/)，从而实现了该公司 2018 年对云数据管理提供商 NooBaa 的收购。

在这两个版本之间，焦点完全落在数据上——从 OpenShift 的角度来看，这些功能解决了数据安全问题，增加了符合联邦信息处理标准(FIPS)的加密和对 etcd 加密的支持，以及其他企业安全功能，而 OpenShift Container Storage 4.2 通过 NooBaa 引入了多云网关，提供了单个亚马逊网络服务的简单存储服务(S3)端点。

“我们试图做的是真正解决一系列类似的挑战——实际上，我们为客户解决的是便携性、简单性、安全性和可扩展性。Red Hat Storage 产品营销总监[伊尔沙德·雷汉](https://www.linkedin.com/in/irshadraihan)在接受采访时表示:“对于部署应用程序和容器的客户，以及采用混合云、OpenShift 和 OpenShift 容器存储的客户来说，这些都是挑战。“我们试图使其尽可能无缝，因此 OpenShift 用户不必真的是存储专家也能为他们的应用程序调配和管理存储。传统存储…无法适应云原生现代应用程序的规模和敏捷性，尤其是考虑到移动等因素。”

OpenShift Container Storage 4.2 构建于 Ceph、Rook 和 NooBaa 技术之上，提供单一的 Amazon Web Services 简单存储服务(S3)端点进行编码，使开发人员能够访问文件、数据块和对象存储，初始支持 AWS 和 VMware，包括内部部署和云中。除了 S3 端点，OpenShift 容器存储 4.2 还带来了内置的数据保护功能，如加密、匿名化、密钥分离和擦除编码。

“这是我们能够提供高度可扩展的对象存储的一大优势。在 OpenShift 容器存储的背后，运行的是 Ceph 技术，”Raihan 说。 [Ceph](/simplify-storage-for-kubernetes-with-rook-and-ceph/) 已经被部署到一些要求最苛刻的工作负载中，OpenShift 的下一批大规模应用是这些以数据为中心的数据密集型应用。准备好提供他们需要的规模让我们处于非常有利的位置。”

在 OpenShift 4.3 方面，FIPS 的加入意味着处理极其敏感的数据和工作负载的企业和政府组织现在可以使用 OpenShift 并遵守法规，但这不是最新版本中唯一的安全功能:对 OpenShift 使用的 [etcd 数据存储库](/the-etcd-database-joins-the-cloud-native-computing-foundation/)的加密支持将有助于更好地保护静态存储在 ectd 中的机密和配置映射，网络绑定数据加密可用于远程启用加密卷，以防止主机存储被物理窃取。

此外，Red Hat 还开放了 OpertorHub.io 来托管私人运营商。以前，运营商需要通过某些要求，很像一个应用程序被提交到应用程序商店，但现在私有运营商可以在内部共享，这将对安装有空气间隙的客户有用。OpenShift 4.3 基于 Kubernetes 1.16，并在试用版和正式版中提供了许多功能，最值得注意的是增加了 Prometheus 的应用程序监控功能，该功能在此版本中首次试用。

最后，OpenShift 容器存储的首席产品营销经理 [Karena Angell](https://www.linkedin.com/in/karenaangell) 说，这次发布的重点是让开发者更容易，特别是在处理持久存储时。

“我们真的试图简化它。在此 4.2 版本中，重点实际上是简化存储，这在过去一直是个问题，同时为现有存储提供抽象层。有了这个 API，我们就可以不用将 S3 API 硬编码到配置文件中，而是将它保留在配置文件之外。Angell 说:“当您在内部部署它或将其保存在云中或迁移到云提供商时，您不必担心它，不必经过这些环节，您只需编写一个 API。

亚马逊网络服务、Red Hat 和 VMware 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>