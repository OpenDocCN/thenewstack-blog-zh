# Red Hat 的 Quay 3 集装箱支持多种架构

> 原文：<https://thenewstack.io/red-hats-quay-3-container-supports-multiple-architectures/>

[红帽发布了 Quay 3](https://www.redhat.com/en/blog/introducing-red-hat-quay-3-registry-your-linux-and-windows-containers) ，这是它在 2018 年 1 月收购 CoreOS 时获得的集装箱图像注册表。

在最新版本中， [Quay](https://www.redhat.com/en/technologies/cloud-computing/quay) 支持多种架构、Windows 容器映像和基于 RHEL 的映像。

该公司[在第一个私营企业托管的注册表中吹捧](https://blog.openshift.com/introducing-red-hat-quay/) Quay，可追溯到 2013 年(CoreOS 之前)，具有包括映像回滚和零停机垃圾收集在内的创新功能。

对多种架构的新支持意味着用户可以在更多平台和不同系统上运行容器，如 IBM Power LE 和 Z 系统工作负载、基于 Arm 的物联网设备和基于 Windows 的工作负载。

对 Windows 容器映像的支持将它的使用扩展到了那些使用多个云或仅使用 Windows 的商店。

使用基于 Red Hat Enterprise Linux 的映像的能力意味着那些想全程使用 Red Hat 技术的人可以这样做。据该公司称，Quay 为 Red Hat 的完全支持的集装箱部署管道提供了另一个组件，并提供了一个较小的潜在攻击面。

Quay 提供团队和组织映射、CLI 密码加密和细致的事件记录。它包含自动构建和生命周期管理功能，以及通过地理复制和更高可用性进行扩展的能力。

它的其他安全功能包括支持多种认证系统和身份提供商，以及通过与 [Clair 安全扫描仪](https://github.com/coreos/clair)集成进行漏洞扫描。Clair 是一个开源项目，用于静态分析应用程序容器中的漏洞。

Quay 作为企业软件和托管服务在 Quay.io 上提供。

Red Hat OpenShift 的用户必须选择一个图像注册中心来与平台配对。该公司表示，虽然 OpenShift 已经有了一个注册中心，但红帽计划用 Quay 取代它。Red Hat 还表示，它计划在这两种产品之间建立更紧密的集成，以改善用户体验。Quay 的其他功能包括自动镜像名称空间、存储库或多个注册中心之间的子集；增强了对存储后端和其他内容类型的支持；以及与内容治理相关的增强。

红帽将如何整合 CoreOS 资产一直是人们猜测的话题，尤其是围绕 OpenShift 和 CoreOS Kubernetes-平台-服务架构。

红帽是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>