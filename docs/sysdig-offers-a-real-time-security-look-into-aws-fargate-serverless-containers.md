# Sysdig 提供了对 AWS 的 Fargate 无服务器容器的实时安全观察

> 原文：<https://thenewstack.io/sysdig-offers-a-real-time-security-look-into-aws-fargate-serverless-containers/>

亚马逊网络服务的 Fargate 是 T2 非常受欢迎的用于容器的无服务器计算引擎。部分原因是它隐藏了 [Kubernetes](https://kubernetes.io/) 如何与[亚马逊弹性容器服务(ECS)](https://aws.amazon.com/ecs/) 和[亚马逊弹性 Kubernetes 服务(EKS)](https://aws.amazon.com/eks/) 一起工作的复杂性。这意味着 Fargate 使您能够运行容器，而不必管理运行这些集群的主机或为它们提供动力的容器引擎。这是好消息。

坏消息是你对集装箱下面的安全性毫无头绪。这就是 Sysdig 为 AWS Fargate 提供的新的运行时安全检测和响应服务的用武之地。

这不是一件小事。正如[Rendition InfoSec](https://www.sans.org/profiles/jake-williams/)创始人兼总裁[和](https://www.renditioninfosec.com/) [SANS Institute](https://www.sans.org/) 讲师 Jacob Williams 在一份声明中所说，“没有威胁检测和访问详细的调查审计跟踪，公司就无法知道到底发生了什么，谁在访问他们的数据。”

Sysdig Secure DevOps 软件即服务(SaaS)平台[的新增功能](https://sysdig.com/secure-devops-platform/)为 Fargate 提供运行时安全检测和响应。它还为系统管理员和安全人员提供详细的审核日志，以便他们可以跟踪和响应事件。

该公司上周在[kube con+CloudNativeCon EU 2021](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)上宣布了这项新技术。

它还附带了 Sysdig 声称的第一个文件完整性监控(FIM)功能。如果您使用容器来处理使用[支付卡行业数据安全标准(PCI DSS)](https://www.pcisecuritystandards.org/pci_security/) 的信用卡和现金卡支付，那么您必须拥有这个。将所有这些放在一起，您将获得一个跨 Fargate、ECS 和 EKS 的统一视图，因此您可以发现错误配置、漏洞和运行时威胁。

具体来说，Sysdig 使用 Linux `syscall`数据为 AWS Fargate 提供了深入的运行时可见性。无论您的应用程序是用什么语言编写的，这种方法都有效。c，走，锈，随便，无所谓。该服务在较低的级别寻找问题。

其次，Fargate 的事件响应依赖于详细的审计跟踪和取证数据。因此，Sysdig 捕获并记录您所有的 Fargate 活动并将其与 AWS 和 Kubernetes 数据关联起来是很有帮助的。当然，您可以使用这些数据来了解发生了什么并采取行动。它还可以作为符合审计要求的证明。

最后，该服务还提供了 Fargate 的统一视图。这让您可以看到整个攻击链。为了保护您的工作负载，它会识别潜在的映像漏洞、可疑的文件活动、错误配置和可疑的配置更改，例如删除 [CloudTrail](https://aws.amazon.com/cloudtrail/) 日志或更改对敏感数据的访问权限。您还可以根据严重程度对事件进行分类，并跟踪特定用户。

所有这些功能都基于 Sysdig 的开源运行时安全程序 [Falco](https://falco.org/) 。这个[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)项目是 Kubernetes 事实上的 Kubernetes 威胁检测引擎。它通过使用自己的内核模块 Sysdig 内核和流行的[扩展 BPF (eBPF)](https://lwn.net/Articles/599755/) 来“发现”威胁。所有的 Sysdig 组件，以及更多的组件，最近都捐赠给了 CNCF。

Falco 通过搜索应用程序中的异常活动来工作。Falco 通过在 Linux 内核层进行审计来做到这一点。此外，它还收集容器运行时和 Kubernetes 指标。在其商业版本中，Sysdig 与 AWS 合作，对 AWS Fargate 容器进行了全面的研究。

[AWS 无服务器容器总经理 Fernando Zandona](https://www.linkedin.com/in/fzandona/) 解释说:“开源 Falco 势头强劲，其 syscall 方法旨在提供全面的 AWS Fargate 威胁检测。我们与 Sysdig 合作进行这一集成，最终目标是让 AWS Fargate 用户更深入地了解风险管理。”

简而言之，AWS 认为 Sysdig Secure DevOps 相当不错。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>