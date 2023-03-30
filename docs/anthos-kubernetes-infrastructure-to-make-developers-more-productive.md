# Anthos: Kubernetes 基础设施让开发者更有效率

> 原文：<https://thenewstack.io/anthos-kubernetes-infrastructure-to-make-developers-more-productive/>

这是一个内部版本的云平台，突然被视为谷歌云的核心。谷歌最早的员工之一，负责技术基础设施的高级副总裁 Urs hlz le 称之为“云的未来”，使“混合和多云成为新常态”。谷歌库伯内特和 GKE 产品团队的负责人阿帕娜·辛哈(Aparna Sinha )没有将 GCloud 称为“为库伯内特打造的云”，而是告诉新的堆栈它现在是“为 Anthos 打造的云”

但是什么是 [Anthos](https://cloud.google.com/anthos/docs/concepts/anthos-overview) 以及为什么谷歌要进入内部硬件？

## Kubernetes 很难

无论是连接不可用的站点的边缘计算，还是监管问题或在自己的服务器上保持特定工作负载的庞大数据量，许多组织都将继续运行自己的硬件。混合云旨在通过减少或消除基础架构管理工作来获得公共云的优势。

将 Kubernetes、Istio 和 Knative 放在来自使用 VMware 和 vSphere 的熟悉服务器供应商的英特尔硬件上的一个堆栈中，这是谷歌试图打造一个以开发人员为先的混合云的方式，该混合云可以扩展到其他云，其一致性水平取决于他们对谷歌技术选择的坚持程度。

市场上已经有许多超融合和混合云选项，但它们通常是基础架构优先的方法。谷歌开发者关系副总裁[亚当·塞利格曼](https://twitter.com/adamse)向新堆栈解释说，与 Anthos(谷歌云服务平台的新名称)的不同之处在于，它同样注重提高开发者的生产力。像 [Cloud Run](/how-google-cloud-run-combines-serverless-and-on-demand-kubernetes/) 和 Cloud Code 一样，谷歌本周在 Google Next 上推出的另外两项新服务，是关于通过照顾基础设施需求，让它们回到开发的有趣部分。“Anthos 是关于提高公司开发环境的水位线，这样开发者可以在更高的水平上漂浮他们的船，”他说。

## 完整的 Kubernetes 堆栈

虽然谷歌可能会在未来打包一些云服务在 Anthos 上运行，但目前 Anthos 正在提供一个既可移植又与谷歌云深度集成的 Kubernetes 堆栈。这是与 Azure Stack 不同的方法，Azure Stack 将 IaaS 和 PaaS 服务从 Azure 放到数据中心的硬件上。

与 Azure Stack 一样，IT 团队可以从他们已经打交道的供应商(如 HPE、戴尔、EMC 和联想)那里购买超融合 Anthos 硬件，他们可以自己运行或为他们管理，也可以使用他们已经拥有的硬件。他们获得了与 VMware 和 Cisco 管理工具的集成，熟悉的系统集成商可以帮助他们设置 Anthos 并将其与现有基础架构集成。

一旦他们获得所有这些，他们就会获得一个软件堆栈，相当于他们自己硬件上的 GKE，他们通过 GKE 像他们的 Kubernetes 云集群一样管理它，并使用他们用于部署到 GKE 的相同工具进行部署。例如，如果你使用谷歌的云构建 CI/CD 系统，新的定制工人允许你使用 GitHub Enterprise、BitBucket、Artifactory 或 GitLab 在 Anthos 中创建管道，以在你自己的硬件上部署，就像在 GKE 一样。

组成 Anthos 的部分是 GKE 或 GKE 本地的 Anthos 配置管理，用于管理 Kubernetes 和 Istio 策略，如名称空间、资源配额和 RBAC，以及 GCP 市场，在那里你可以找到在 GKE 运行的相同的 Kubernetes 应用程序，如 Jenkins 或 WordPress——并且你通过与 GKE 相同的谷歌云账单付费。市场上还有一个测试版的私有目录，你可以在那里提供自己的内部解决方案。

[![](img/057cbb73839d837af96851bd5d94d427.png)](https://cdn.thenewstack.io/media/2019/04/fffd6d46-anthos-arch.svg)

所有这些都是从 GKE 管理的，因此您不必考虑操作和升级 Anthos、维护基本操作系统映像、部署安全补丁或获得正确的配置；运营和升级 Kubernetes 仍然是一个巨大的负担。但是企业很可能也必须做一些与他们自己的基础设施的集成工作。您需要 VMware vCenter 6.5 来创建运行集群的虚拟机，并需要 F5 BIG-IP 负载平衡器来实现第 4 层负载平衡。

谷歌还宣布了一项服务的测试版，该服务可以在不重构应用程序的情况下将其容器化。

Sinha 向我们解释说:“Anthos Migrate 是一种将单片遗留应用程序迁移到 GKE 的方法。这带来了与将应用程序迁移到任何云 Kubernetes 服务中作为实现 it 现代化的第一步相同的优势。“您可以打包，获得更高的利用率和更低的成本，获得类似 DevOps 的工作流，因此您可以在这些应用程序上启用服务管理，摆脱操作系统修补和管理虚拟机，因为您在一个容器中。”

测试服务只包括将那些容器化的应用程序转移到 GKE，但将来会有更多的选择。“从内部虚拟机迁移到云上的 GKE，或者从虚拟机中的 AWS 迁移到 GKE，这是一个一步到位的简化流程；我们的路线图是迁移到 GKE 本地，以及迁移到 Windows 等等。”

## 连接但便携

有许多不同风格的 Kubernetes 可用，从您自己部署的开源 Kubernetes，到托管的 Kubernetes 服务，如 GKE 和 Azure Kubernetes 服务，到打包的产品，如 RedHat Open Shift 和 VMware PKS。Redmonk 创始人 [James Governor](https://twitter.com/monkchips) 建议将 Anthos 视为类似谷歌版本的 Open Shift。这是一个完整的 Kubernetes 堆栈，即使在其他云上也可以管理任何 Kubernetes 集群，尽管集成程度较低。

正如混合云平台 [CloudBolt](https://www.cloudbolt.io/) 首席执行官[布莱恩·凯利](https://www.linkedin.com/in/bkelly-cloudbolt)所说，与 GKE 和其他谷歌云服务的深度整合意味着“最终结果当然是为谷歌的云解决方案带来更多业务。”

除了向谷歌云平台控制台注册您的 GKE 本地集群，以便您可以使用 GKE 作为管理和控制平面，同时还有 Prometheus 和 Grafana 集成以及 Elastic search、Fluentd 和 Kibana 附加组件，Anthos 系统级组件监控必须连接到 Stackdriver 进行监控和警报。

Anthos 使用 Istio service mesh 进行流量管理、呼叫服务的身份和访问控制、服务之间的身份验证和 mTLS 加密、用于监控的遥测和可观测性以及生成审计线索，这些都由云服务 mesh 组件管理。对于本地认证，GKE 本地与 OIDC 提供商合作，这可能是谷歌云身份平台，也可能是活动目录。

但是，应用程序和工作负载的可移植性并不局限于仅在本地使用 GKE 的情况下使用完整的 Anthos 堆栈。Sinha 告诉新的堆栈，根据你需要的一致性和连贯性的级别，你可以使用任何 Kubernetes 发行版和任何云，并使用 Anthos 来管理它们。

“这很像‘我想对冲我的赌注，我不想冒被锁定在一个云中的风险，通常这就是 AWS。“我希望分散风险，我希望能够跨云获得可靠性，我希望能够选择在某些地区运行，我希望拥有更高的可用性，并且更接近我的客户，我希望能够利用不同云中可用的创新服务，”Anthos 允许您这样做。这是一种工作负载的可移植性，是通过利用跨环境运行的一致平台实现的应用程序的可移植性，而 Kubernetes 就是这种基础，这种一致的平台。”

Anthos 配置管理是 Kubernetes API 的扩展，所以你可以在任何地方的任何集群上部署它，她解释道。“它提供了根据策略设置您希望在该群集中拥有的命名空间、您希望创建的 RBAC 角色、您希望拥有的权限、您希望拥有的配额策略的能力，并且可以跨您的多个群集分层设置，而不管它们在何处运行。您可以保留该定义，并将其存储在类似 gitops 的工作流中。系统会将您的更改自动部署到所有已注册的集群，集群会在本地执行策略。”

您甚至可以将 Anthos 与其他 Kubernetes 管理工具结合使用。“如果您正在使用 Heptio，这意味着您正在使用开源的 Kubernetes，您仍然可以向 Anthos 注册该集群，Anthos 将在更高的级别上工作，允许您进行工作负载分配、策略分配和多集群管理。或者，你可以决定使用定制管理功能，这样你就不会使用 Heptio，而会从谷歌获得更多管理功能——但这是你的选择。”

如果这仍然有点混乱，那是因为这是一个具有多种选择的非常雄心勃勃的提议，因为谷歌正试图与整个 Kubernetes 生态系统集成，作为其赢得企业的途径。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>