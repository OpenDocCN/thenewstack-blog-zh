# Amazon Elastic Kubernetes 服务上网络策略的最佳实践

> 原文：<https://thenewstack.io/best-practices-for-network-policies-on-the-amazon-elastic-kubernetes-service/>

[](https://www.stackrox.com/)

 [凯伦·布鲁纳

凯伦·布鲁纳是 StackRox 的技术布道者，她在那里推动自动化并倡导产品的可操作化。此前，Karen 曾在 Clari、Ooyala、LinkedIn 和 Yahoo 担任开发运维及站点可靠性工程职位。她在好莱坞的数字特效行业开始了她的职业生涯，并在《网络大盗》中出演了电影《宝贝》。她用业余时间渲染纱线中的双关语，学习晦涩的纤维工艺，以及被猫绊倒。](https://www.stackrox.com/) [](https://www.stackrox.com/)

借助像 [Amazon Web Services](https://aws.amazon.com/) 这样的云服务，客户与服务提供商共同承担管理和保护托管虚拟基础设施的责任。这种职责划分被称为共享责任模型，它规定了哪些配置和监督领域属于用户，哪些属于提供者。了解云工作负载的安全性和合规性完全属于客户的责任范围尤其重要，特别是对于托管 Kubernetes 产品，如亚马逊弹性 Kubernetes 服务(EKS)。通过 EKS，AWS 负责保护其基础设施，修补 Kubernetes，并解决其软件中的安全问题。客户必须确保自己的应用程序的安全性，并正确使用云基础架构中的可用控制来保护他们的数据和工作负载，以及他们的云帐户及其资源。

> 云工作负载的安全性和合规性完全属于客户的责任范围。

通过了解适用于 Kubernetes 和亚马逊 EKS 的控制措施以及集群需要采取额外安全措施的地方，客户可以使集群安全的实现和维护变得更加强大和简单。良好的 EKS 安全性始于针对您的 AWS 帐户和 EC2 虚拟私有云(VPC)的强大设计。理解 Kubernetes 网络框架，并对集群的组件和工作负载应用网络保护，提供了 EKS 安全难题的另一部分。

以下是在亚马逊 EKS 有效建立 Kubernetes 网络的最佳实践。

## 使用 Calico 增强集群网络控制

Kubernetes 集群中的默认网络配置允许网络流量在 pod 之间自由移动并离开集群网络。这些相同的设置在亚马逊 EKS 集群中是标准的——pod 可以连接到所有其他 pod。通过创建仅允许所需群集出口和服务到服务连接的限制，您可以减少潜在威胁，并限制不良参与者或错误配置的工作负载利用群集资源的能力。

通过安装 Calico，一个开源的 CNI(容器网络接口),它实现了标准的 Kubernetes 网络策略 API，您可以创建网络策略来将 pod 流量限制在所需的连接上。Calico 还为标准的 Kubernetes 策略类型提供了各种自定义扩展，以提供更好的入口和出口流量控制。在应用网络策略时，用户应该测试创建的策略，以确保它们在允许所需流量的同时阻止任何被认为不必要的流量。

请注意，Calico 和大多数 CNI 提供商目前不支持 Windows 容器。如果您需要对 Windows 工作负载进行网络流量控制，您可能需要创建一个专用的 VPC 子网，并使用 VPC 网络访问控制列表(ACL)来限制节点到节点的流量。但是，只有使用支持集群的解决方案，才可能有效地限制单元到单元的流量。

## 对网络访问关闭 Kubernetes API 端点

亚马逊 EKS 将 Kubernetes API 服务器的端点(集群控制平面的接口)在新的集群中默认暴露于互联网。EKS 集群中的 API 服务器使用`--anonymous-auth=true`标志运行，以允许未经身份验证的连接，而 EKS 没有为用户提供禁用该设置的选项。必须通过将对 API 服务的网络访问仅限于受信任的 IP 地址来保护群集 API 端点。在亚马逊 EKS 中，您有几个选项可以用来保护集群的 API 端点，这些选项可以组合使用，包括:

禁用公共 API 端点，而在集群的 VPC 中使用私有端点，这提供了终极保护。将 CIDR 数据块列入白名单，以限制可以连接到公共端点的 IP 地址。使用网络策略来阻止从集群中的 pod 到 Kubernetes API 端点的流量，只允许来自需要访问的工作负载的连接。

## 启用 Kubernetes API 私有端点

如上所述，默认情况下，亚马逊 EKS 集群有一个可供公共互联网使用的端点。作为这种配置的副产品，API 服务器和集群 VPC 中的节点之间的流量会离开客户的 VPC 专用网络。通过在集群中启用私有端点，您可以将网络流量保持在 VPC 内部。亚马逊 EKS 支持在同一个集群中同时拥有公共和私有端点，因此即使您需要公共集群 API 端点，您仍然可以使用私有端点将集群流量保持在您的私有网络空间中。

## 阻止 Kubelet 访问

kubelet 服务运行在每个节点上以管理 Kubernetes pods 和容器的生命周期，它需要强大的保护，因为它与节点的容器运行时相集成。Amazon EKS 在禁用匿名身份验证的情况下运行 kubelet，并需要来自集群 API 服务器上的 TokenReview API 的授权，这两者都提供了一定程度的安全性。但是，最佳做法是通过阻止从 pod 网络访问 kubelet 网络端口来采取额外的保护措施。为此，请在安装 Calico CNI 后创建一个 GlobalNetworkPolicy，防止所有 pod 连接到 kubelet。

## 保护服务负载平衡器

默认情况下，在亚马逊 EKS 集群中创建负载平衡器类型的 Kubernetes 服务会生成一个面向互联网的 ELB，除了负载平衡器子网的网络访问控制列表(ACL)之外，没有其他防火墙限制。当只有集群 VPC 内部的源需要访问服务的端点时，应该将以下资源注释添加到服务清单中，以指示集群的云控制器创建内部负载平衡器:`service.beta.kubernetes.io/aws-load-balancer-internal: 0.0.0.0/0`。在负载平衡器必须面向互联网，但同时对某些 IP 地址保持关闭的情况下，用户应该向服务对象规范添加字段 loadBalancerSourceRanges 和批准的源地址的白名单。

除了实施亚马逊 EKS 网络策略以实现最佳安全性，您还应该考虑在亚马逊 EKS 上运行工作负载的其他几个最佳实践，以进一步保护集群及其所有工作负载。过度特权的 pod、具有已知漏洞或可利用工具的容器映像，以及错误配置或过度开放的 Kubernetes RBAC 都构成了亚马逊 EKS 用户的额外风险来源。帮助用户锁定亚马逊 EKS 工作负载的其他技术指南可在此获得。

一般来说，亚马逊 EKS 把很多安全责任留给了用户，尤其是在应用更新和升级 Kubernetes 版本的时候。这种责任是福也是祸——鉴于亚马逊 EKS 可以帮助解决的需求范围，开发人员有很大的灵活性，但拥有多个集群的用户可能需要额外的自动化来减轻管理负担，并快速应用关键的安全补丁。额外的监控功能还将提高对集群运行状况的可见性，并有助于检测和预防未经授权的活动和其他安全事件。优先考虑风险管理并对这里概述的政策和任务进行定期审计是获得亚马逊 EKS 的运营优势同时最小化风险的基础。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

亚马逊网络服务是新堆栈的赞助商。

特征图片:法国亨利二世之盾，1555 年，[纽约大都会艺术博物馆](https://www.metmuseum.org/art/collection/search/23948)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>