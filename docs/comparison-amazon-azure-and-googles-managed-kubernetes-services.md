# 对比:亚马逊、Azure 和谷歌的托管 Kubernetes 服务

> 原文：<https://thenewstack.io/comparison-amazon-azure-and-googles-managed-kubernetes-services/>

[](https://www.stackrox.com/)

 [凯伦·布鲁纳

凯伦·布鲁纳是 StackRox 的首席开发工程师，她在那里推动自动化并倡导产品的可操作化。此前，Karen 曾在 Clari、Ooyala、LinkedIn 和 Yahoo 担任开发运维及站点可靠性工程职位。她在好莱坞的数字特效行业开始了她的职业生涯，并在《互联网大盗》中出演了电影《宝贝》。她用业余时间渲染纱线中的双关语，学习晦涩的纤维工艺，以及被猫绊倒。](https://www.stackrox.com/) [](https://www.stackrox.com/)

组织使用 Kubernetes 的方式迅速发展，许多用户放弃了自我管理的安装，转而青睐公共云提供商提供的托管 Kubernetes 服务，包括微软的 [Azure Kubernetes 服务](https://azure.microsoft.com/en-us/services/kubernetes-service/?&ef_id=EAIaIQobChMIgZTDu5yY6AIVBG6GCh1KFQXAEAAYASAAEgJHQfD_BwE:G:s&OCID=AID2000586_SEM_EAIaIQobChMIgZTDu5yY6AIVBG6GCh1KFQXAEAAYASAAEgJHQfD_BwE:G:s) (AKS)、[亚马逊弹性 Kubernetes 服务](https://aws.amazon.com/eks/) (EKS)和[谷歌 Kubernetes 引擎](https://cloud.google.com/kubernetes-engine) (GKE)。

传统上，自我管理的 Kubernetes 一直是容器编排的最主要方法，但它现在落后于 EKS 的使用。StackRox 的[集装箱状态和 Kubernetes 安全报告，2020 年冬季](https://www.stackrox.com/kubernetes-adoption-and-security-trends-and-market-share-for-containers/)中的发现表明，EKS 的使用率在过去六个月中增长了 37%,而 AKS 的使用率也增长了 31%。GKE 经历了更大的增长，在这六个月中使用量增长了 75%。

所有主要的云服务提供商都提供托管 Kubernetes 服务，因此用户了解它们之间的差异非常重要。该指南可以帮助您找出最能满足您需求的服务。

## 总体比较

三家云提供商目前提供的 Kubernetes 版本可能会有很大差异。这三家公司目前都使用 Kubernetes 的默认版本，不再接受官方更新。然而，AKS 在增加新的 Kubernetes 版本的预览访问和促进新版本的普遍可用性方面越来越领先。

所有这三个提供商在最近增加的 Kubernetes 特性上是可比较的，比如 Windows 容器和 GPU。主要的区别在于各自提供的管理服务。GKE 通常率先为主节点和节点提供自动升级，同时还支持自动检测和修复不健康节点。

AKS 和 EKS 都需要某种程度的手动工作(或客户编程的自动化)来进行更新。这两家提供商都不提供专门的节点健康监控或修复。虽然 AWS 客户可以为某种级别的运行状况监控创建自定义运行状况检查，并为 EKS 集群创建客户自动更换，但 AKS 不提供任何类似的功能。

> Amazon Elastic Kubernetes 服务提供了其他 Kubernetes 提供商所没有的东西——财政支持的服务级别协议

Kubernetes 主控制平面的服务级别协议的差异是另一个需要比较的方面。EKS 是唯一对其主机收费的提供商(0.10 美元/集群/小时)，尽管谷歌云已经宣布将于 6 月开始对控制平面收费，与 EKS 的收费率相同。

虽然这些成本对于除了最小的集群之外的所有集群来说都可以忽略不计，但 EKS 提供了其他提供商所没有的东西——有财务支持的服务级别协议(SLA)。SLA 罚款的退款很少能与停机造成的潜在生产力或收入损失相比，但提供公布的罚款可以让用户对提供商对可靠性和正常运行时间的承诺更有信心。

另一个有趣的区别是 AKS 主组件的高可用性。Azure 文档没有指定 AKS 是否使用内置冗余的集群控制平面。对于托管在 AKS 上的应用程序，拥有自己的 SLA 的客户通常需要确认他们所依赖的服务和云基础架构已经过设计，具有相似的可靠性级别。虽然在 Kubernetes 集群中运行的 pod 和节点可以在控制平面及其组件中断的情况下继续运行，但是对于某些工作负载来说，即使是短暂的中断也会造成问题。

## 服务限制

值得注意的是，不同提供商对服务限制的处理方式不同——使用 EKS 的每个帐户、使用 AKS 的每个订阅或使用 GKE 的每个项目都有限制。EKS 为每个地区、每个客户提供 100 个集群。类似地，AKS 为每个订阅提供 100 个集群，GKE 为每个区域提供 50 个集群，外加 50 个区域集群。

虽然大多数服务限制相当简单，但有些却不是。例如，在 AKS 中，一个集群可以拥有的最大节点数量取决于几个变量——节点是在 VM 状态集中还是在可用性集中，以及集群网络是使用 kubenet 还是 Azure CNI。即便如此，对于某些配置，哪个数字优先仍然不清楚。另一方面，在 EKS 中，您可以计划可以在一个 Linux 节点上调度的最大数量的 pod，但是这种方法需要一些研究和数学计算，因为它随节点的 EC2 实例类型而变化。GKE 允许每个节点 110 个机架。

## 网络和安全性

Kubernetes 集群的网络和安全特性和配置经常紧密交织在一起，这就是我们一起讨论这些概念的原因。总体而言，EKS 使 Kubernetes 安全控制成为每个集群的标准，从而简化了安全流程。相反，AKS 要求在集群创建时启用 RBAC 和网络策略，这使得安全管理更加复杂。现在，所有三个提供商都默认启用了 Kubernetes RBAC，EKS 甚至强制要求安装 RBAC。

另一方面，默认情况下，目前没有一个提供商启用网络策略支持。EKS 要求客户自己安装和管理印花布 CNI 的升级。根据群集网络类型，AKS 为网络策略支持提供了两个选项，但只允许在群集创建时启用支持。

所有三个云提供商都提供了一些选项来限制对集群的 Kubernetes API 端点的网络访问。即使有了 Kubernetes RBAC 和为集群启用的安全认证方法，让 API 服务器对世界开放仍会使其无法抵御未发现或未来的漏洞，最近出现在现已修补的[Billion laughts 漏洞](https://hub.packtpub.com/an-unpatched-security-issue-in-the-kubernetes-api-is-vulnerable-to-a-billion-laughs-attack/)中，该漏洞为未经认证的用户造成了拒绝服务攻击的可能性。

## 容器图像服务

所有三个提供商都提供类似的容器映像注册服务。Azure Container Registry (ACR)中对图像签名的支持允许用户建立和确认其图像的真实性和完整性。类似地，在弹性容器注册中心(ECR)中对不可变图像标签的支持帮助其用户相信使用相同的**图像:标签**将导致每次部署相同构建的容器图像。

所有这三个注册中心服务都允许某种程度的访问控制，但是它们之间的控制程度各不相同。ECR 和 ACR 都支持存储库级别的范围访问控制，但 GCR 不支持。此外，由于对 GCR 注册中心的访问控制直接取决于支持该注册中心的 Google 云存储桶的权限，因此通过使用服务边界来限制对存储桶的访问可能会中断对其他 GCP 项目中 GCS 桶的访问，还会产生其他副作用。

理解 [Kubernetes](/category/kubernetes/) 服务变化迅速至关重要，即使敏锐地理解了公共云提供商提供的服务的核心差异，您也应该在投资托管 Kubernetes 服务之前，始终运行测试来比较每个提供商的各种计算、存储和网络选项。比较相关成本也很重要。资源的定价，即使是对单个提供商而言，也可能因地区而异，并且对于每种配置都是独特的。在您自己的应用程序堆栈中测试每项服务的特性和功能，最终将为您的需求提供最准确的价格和性能数据。

欲了解更多信息，并看到详细的对比图表，[见这个技术职位](https://www.stackrox.com/post/2020/02/eks-vs-gke-vs-aks/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>