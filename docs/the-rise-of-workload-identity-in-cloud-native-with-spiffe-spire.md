# 使用 SPIFFE/SPIRE 在原生云中提升工作负载身份

> 原文：<https://thenewstack.io/the-rise-of-workload-identity-in-cloud-native-with-spiffe-spire/>

在当今的云计算世界中，我们的工作负载和计算架构有各种形状和大小。我们今天的架构包含多个平台、区域，甚至跨越多个云提供商。然而，这并没有结束。在一些用例中，如 5G 或边缘计算，无数设备，如树莓 Pi 到 HPC 节点，可以出现在同一架构图上。

在本文中，我们将讨论工作负载身份如何在云原生架构中发挥关键的基础作用。我们将讨论快速发展的云计算原生计算基金会(CNCF)身份识别技术 SPIFFE 和 SPIRE，以及工作负载身份识别的未来前景。

## 工作负载身份的重要性

 [布兰登·卢姆

Brandon 喜欢设计和实现计算机系统，重点是安全性、操作系统和分布式/并行系统。在 IBM Research，Brandon 针对云和安全性的交叉问题进行设计、构建和开发。他从事各种安全领域的工作，例如通过加密和图像签名保护容器内容、身份和技术以减少内核上的攻击面。](https://www.linkedin.com/in/brandon-lum-a7b79418/) 

随着我们的工作负载组合变得越来越复杂，确保每个工作负载或服务能够安全地访问其所需的服务和资源非常重要。比如访问控制和 RPC 授权、相互认证的传输层安全性(mTLS)和秘密分发。我们从各种技术中获得这些功能，如服务网格( [Istio](https://istio.io/) 、 [Linkerd](https://linkerd.io/) )和流量安全代理( [Envoy](https://github.com/envoyproxy/envoy) 、[ghost tunnel](https://github.com/ghostunnel/ghostunnel))。然而，所有这些技术都依赖于一个基本的基础设施属性来实现它们的保证:强加密工作负载身份。

在云原生之前，工作负载的寿命相当长，可以用我们的双手或一个相当易于管理的电子表格来计算。因此，采用一种相对手动的策略是可行的，即操作员分配工作负载身份并向工作负载提供证明该身份的凭证。

然而，在[云原生](https://www.cncf.io/)空间中，工作负载是短暂的，工作负载定义随着 CI/CD 和 GitOps 等概念变得敏捷，因此需要在提供身份的能力方面进行创新。这意味着配置和交付身份，但同样重要的是，确保它们用于正确的工作负载。

## 回车:SPIFFE/SPIRE

 [埃文·吉尔曼

Evan 是一名具有计算机网络背景的工程师。他扎根于学术界，目前正在从事 SPIFFE 项目，在他的整个职业生涯中，他一直在恶劣的环境中构建和操作系统。Evan 是一名开源贡献者、演讲者和作者，他热衷于设计能够与运行的网络保持平衡的系统。](https://www.linkedin.com/in/evan2645/) 

[SPIFFE](https://github.com/spiffe) ，面向所有人的安全生产身份框架，是一套开源标准，用于在动态和异构环境中安全地识别软件系统。采用 SPIFFE 的系统无论在哪里运行，都可以轻松可靠地相互认证。

[SPIRE](https://github.com/spiffe/spire) ，SPIFFE 运行时环境，是一个可扩展的系统，实现了 SPIFFE 标准中包含的原则。SPIRE 管理平台和工作负载证明，提供用于控制证明策略的 API，并协调证书颁发和轮换。

SPIFFE、SPIRE 和 SPIFFE 组织的一系列其他项目是一套项目的一部分，旨在为现代架构提供云原生工作负载身份框架。有关 SPIFFE 和 SPIRE 的更多技术细节，以及如何在零信任的基础上建立工作负载身份的概念，请查看书籍“[解决底层海龟:用通用身份在基础设施中建立信任的 SPIFFE 方法](https://spiffe.io/book/)”。

SPIFFE/SPIRE 的用户包括彭博、优步、GitHub 和字节跳动(抖音的开发者)，谷歌、HPE、VMware、IBM、英特尔和哈希公司等公司使用它来构建更高层的产品和服务。

## 工作负载身份越来越重要

随着组织拥有更成熟的云原生部署和微服务套件，对像 SPIFFE/SPIRE 这样的工作负载身份的需求变得更加突出。让我们用一些最近的数据来验证这一点！我们将看看即将到来的 KubeCon + CloudNativeCon 北美站的一些亮点，以及从 CNCF 收集的数据。

### SPIFFE @ kube con+CloudNativeCon 2021

事实上，SPIFFE 和 SPIRE 的重要性在今年的 KubeCon + CloudNativeCon 北美展会上就可以看到。关于 SPIFFE 和 SPIRE 的讲座约占整个“安全+身份+政策”专题讲座的 20%,其中三个讲座来自不同的组织:

除了这些讲座和两个维护者跟踪讲座之外，还有一个全天的同地活动，[生产身份日](https://events.linuxfoundation.org/production-identity-day-spiffe-spire-north-america/)，与会议一起，提供了一整天关于 SPIFFE 和 SPIRE 的讲座。

### SPIFFE 媒体和速度报告

除了本次 KubeCon 展会上围绕 SPIFFE 和 SPIRE 的活动和讲座之外，人们对社区项目的兴趣也有所增加。以下是来自 [Q2 2021 SPIRE 媒体和速度报告](https://app2.cision.com/report?id=5f0f0a05-cf8c-487a-a117-e9b1ad1d19e7)的几个亮点:

*   Q2 媒体对 SPIRE 的总提及次数达到 271 次，高于 Q1 的 127 次。
*   涵盖 SPIRE 的顶级出版物和网站包括:Help Net Security、SDxCentral。
*   提及 SPIRE 的媒体报道在 Q2 社交媒体渠道上被分享了 357 次，高于 Q1 的 97 次。
*   从 Twitter 的角度来看，术语 SPIRE 在 191 条推文中被提及，高于 Q1 的 69 条。
*   截至 Q2 年底，SPIRE 已有 13 家参与公司和 42 家开发商，而在 Q1 年底，只有 12 家参与公司和 33 家开发商。

## SPIFFE/SPIRE 的最新亮点

随着越来越多的兴趣和贡献者，SPIFFE 和 SPIRE 项目正在加快步伐，导致 SPIRE v1.0 版于今年 7 月早些时候发布。这是 SPIRE 项目的一个巨大里程碑。截止去年 6 月， [SPIFFE 和 SPIRE 是 CNCF 孵化项目](https://www.cncf.io/blog/2020/06/22/toc-approves-spiffe-and-spire-to-incubation/)，距离 CNCF 毕业仅一步之遥。

除此之外，我们还看到了 IBM 向 SPIFFE 家族捐赠了项目 [Tornjak](https://github.com/spiffe/tornjak) 的，该项目为 SPIRE 工作负载的全球可见性和可审计性提供了管理 UI。

[CNCF 安全标签(技术顾问组)](https://github.com/cncf/tag-security)也在研究供应链安全软件工厂参考架构，该架构以 SPIRE 为特色，提供节点和工作负载的证明，并为软件工厂的组件提供身份。

## 结论

从 SPIFFE 在 KubeCon + CloudNativeCon 会议上的压倒性表现、SPIFFE/SPIRE 的采用者数量，到在一个季度内 CNCF 速度指标的两倍到三倍，毫无疑问，工作负载身份的需求和 SPIFFE/SPIRE 项目的重要性日益增长。快来加入不断壮大的 [SPIFFE 社区](http://spiffe.io)并随着[书](https://spiffe.io/book/)深入探究。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>