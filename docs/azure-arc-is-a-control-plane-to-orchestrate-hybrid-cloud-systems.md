# Azure Arc 是协调混合云系统的控制平面

> 原文：<https://thenewstack.io/azure-arc-is-a-control-plane-to-orchestrate-hybrid-cloud-systems/>

根据 [Flexera 2020 年云状态报告](https://info.flexera.com/SLO-CM-REPORT-State-of-the-Cloud-2020)，87%的企业正在使用混合云，高于之前研究中的 75%。尽管混合云可能几乎无处不在，但人们在做什么却各不相同，这就是为什么微软有越来越多的混合云产品，从运行在类似云的硬件上的 Azure Stack Hub 到小到可以放入背包或安装在工厂生产线上的 Azure Stack Edge。

[Azure Arc](https://thenewstack.io/azure-arc-is-developing-into-a-full-hybrid-infrastructure-system) 使 Azure Resource Manager 模板成为控制平面，用于以一致的方式管理和应用治理到您的所有基础架构——虚拟机、Kubernetes 或数据库，在 Azure 上，在您自己的硬件上和在其他云中——使用 GitOps 并将 Azure 服务的子集引入该基础架构(从数据库服务开始)。

但是 Arc 也作为一种伞状技术出现，将这些不同的混合解决方案更紧密地联系在一起。

## **随处可见的花纹**

很少有组织决定将所有东西都转移到云上，微软 Azure 营销高级总监 Talal Alqinawi 告诉新堆栈。

“有些 IT 资源，无论是物理硬件、虚拟机、Kubernetes 集群还是数据库，都会在一段时间内或永远留在您的数据中心或边缘，如果这是数据监管的事情。有了 Azure Arc，我们让您能够在 Azure 门户的一个控制平面下集中管理这两者。在控制平面之下，您可以使用 Arc 以混合方式向您的边缘或数据中心提供服务。”

通过 Arc，企业可以将内部基础设施连接到云并自动管理它，或者通过 Azure 支持的数据服务将云服务引入现有基础设施。

第一步是通过安装 Arc 代理为基础架构启用 Arc，无论是虚拟机、裸机还是 Kubernetes。这将它们投射到 Azure 门户中，并提供一种一致的方式来管理所有环境，无论这些环境多么不同，并对它们应用相同的策略、安全性和监控。支持 Arc 的基础设施与实际上是 Azure 一部分的基础设施一起出现在 Azure 门户中。

像任何其他虚拟机一样，在 VMware 上运行的虚拟机可以启用 Arc 目前，它们需要单独启用，但微软在最近的 Ignite 会议上表示，它正在考虑为 VMware 客户启用 Arc 虚拟机管理程序。

支持 Arc 的服务器现在通常可用于 Linux 和 Windows 上的生产工作负载，而支持 Arc 的 Kubernetes(包括使用 GitOps 的配置管理)正在公开预览中。此外，在 public preview 中，针对虚拟机和 Kubernetes 集群使用 Azure 服务来监控并确保新资源以批准的配置加入:Azure 策略(用于标记服务器或集群，以层次结构组织它们并设置配置控制，如密码策略)，Azure Monitor，Azure Sentinel(微软的云 SIEM)，Azure Defender(反恶意软件和威胁分析)，更新管理(显示服务器可用的更新并安排何时应用它们)和所需的状态配置。支持任何云本地计算基金会(CNCF)认证的 Kubernetes 发行版。

Arc 还可以将现有的 SQL Server 实例带到云中；支持 Arc 的 SQL Server 允许您跟踪运行在 Windows 或 Linux 上的 SQL Server 2012 或更高版本、本地、Azure 和 Azure Portal 中的其他云，并使用 Azure 安全中心查看这些实例中的任何漏洞，并获得数据库和操作系统的实时安全警报。这也是在公共预览中，并使用连接的机器代理，微软监控代理扩展和 Azure 日志分析。

Arc 还可以将 Azure 服务的子集带到任何基础设施(包括其他云)。最初，这是支持 Arc 的数据服务，从 Azure SQL 托管实例和 Azure Database for PostgreSQL Hyperscale(它使用 Citus 对 Postgres 的扩展使其成为分布式数据库)开始，运行在任何经认证的 Kubernetes 发行版的 Linux 上。

官方方面，微软表示支持 AKS、Stack HCI 上的 AKS、EKS GKE Azure Stack Hub 上的 AKS，以及开源的 Kubernetes (kubeadm)、OpenShift 容器平台(OCP)和 Azure Red Hat OpenShift。一名微软工程师在最近的 Ignite 会议上表示，“我们已经在其他平台上进行了测试，并发现在其他 CNCF 认证的 Kubernetes 发行版和服务上运行正常。”

Arc 数据服务依赖于运行在 Azure 中的资源提供者和 Arc 数据控制器；这是部署在您的 Kubernetes 集群(在任何位置)上的一组 Kubernetes pods，它们提供控制器服务或运行数据库服务和一个 API，加上用于本地监控数据可视化的 Kibana 和 Grafana 仪表板(尽管您也可以选择导出它并在 Azure 门户中查看它)。

同样，这种间接连接模式目前处于公开预览阶段，在这种模式下，所有管理功能—监控、备份、恢复、日志分析和自助服务配置都是本地的，使用 Kubernetes 进行身份验证和授权；未来，还会有一种直接连接模式，但微软尚未透露更多细节。

支持 Arc 的 SQL Server 和 Arc 数据服务之间的区别不仅仅是更多的数据库选择；Azure 通过数据服务来处理更新、部署、备份/恢复、监控、安全和弹性扩展，所以就像在云中一样，你会得到一个永远最新和受支持的常青树数据库服务。

微软预计每月发布更新，管理员将控制这些更新的应用时间(通过在维护窗口中安排更新或手动触发更新)，但更新的部署将完全自动化。

类似地，缩放是自动化的。比如 PostgreSQL 超大规模需要两个 worker 节点；Arc 确保 Kubernetes 将这些节点安排在两个不同的 Kubernetes 节点上进行横向扩展，如果您添加更多的工作节点，这些节点也将被放置在不同的 Kubernetes 节点上。运营团队可以使用 GitOps 和 Azure CLI 进行扩展和重新平衡，而数据库管理员可以继续使用熟悉的工具，如 Azure Data Studio。

## **挑选并混合硬件和支持**

Arc 的要点是，它可以与您已经拥有的硬件(或云提供商)一起工作，但适用于那些需要经过认证的硬件来支持 Arc 的数据服务的客户。微软正在与 OEM 合作伙伴建立一个项目。

但是 Arc 也可以在微软的 Azure Stack 硬件上管理一些工作负载。这不仅包括虚拟机和 Kubernetes 集群，还包括 [Azure Stack HCI 服务](https://aka.ms/AKS-HCI)上的新 AK(也在公开预览中)。

Azure Stack HCI 是一种云服务，它将运行在认证硬件上的超融合 Windows 服务器集群转变为运行云服务的基础设施。那些基于 Windows Server 重构版本的服务，您只需在使用时付费(不需要 Windows 许可证)，通过与您在其上(或 Azure 上)运行的服务相同的 Azure 订阅，并通过 Azure 门户进行管理。

Azure Stack 上的 AKS HCI 将微软的托管 Azure Kubernetes 运行时放在完全支持运行 Windows 或 Linux 容器的堆栈上，再次使用 Arc 作为管理平面。一旦部署了 AKS，您还可以在其上运行支持 Arc 的数据服务。

" AKS-HCI 正在 Azure Stack HCI 群集上的虚拟机上运行；然而，我们将这种复杂性抽象出来，使 IT 和开发人员能够拥有一个简化、高效和快速的部署流程，并在部署后获得与 Azure 一致的使用体验，”[平台虚拟化团队的微软首席项目经理 Ben Armstrong](https://twitter.com/vBenArmstrong/) 告诉我们。

当您在 Azure Stack HCI 上设置 AKS 并部署 Kubernetes 集群时，它们会自动与 Arc 一起设置并连接到 Azure，以获得与 Azure 服务集成的好处(尽管客户可以选择不使用 Arc 来部署 AKS，使用 Windows 管理中心或 PowerShell，并使用他们选择的 Kubernetes 工具来监视它)。由于 Azure Stack 上的 AKS，HCI 可能需要定期连接到 Azure(可能一周一次或一个月一次)。

除了作为 AKS 下的基础设施的控制平面，Arc 还可以通过 GitOps 管理 Kubernetes 工作负载和集群配置，就像在任何其他 Kubernetes 集群上一样。

Armstrong 说，Azure Stack HCI 上的 AKS 与云 AKS 服务共享上游代码回购，以实现应用程序兼容性和提供一致的用户体验。

“通过简化部署体验，最终结果与您在 AKS 等 Kubernetes 云服务中的预期非常相似，特别是开发人员和 IT 人员能够专注于他们的工作负载，以及一种 GUI/编程方式来快速建立新的工作负载集群以满足他们的应用需求，而无需关注幕后的管道，”Armstrong 说。

## **云服务，云定价**

Arc 正在像云服务一样开发，在私有和公共预览版中有不同的部分，并正在向全面可用的方向发展。

由于某些功能仍处于预览阶段，因此 Arc 的所有功能都无法定价。Arc 的板载服务器没有任何成本，门户和 CLI 工具使用 Azure 资源图为您提供了库存、RBAC 和搜索等工具，没有任何额外成本，但在支持 Arc 的基础设施上使用 Azure 服务会产生成本，微软称这与直接在 Azure 上使用它们是一致的。Azure Stack HCI 上的 Arc 数据服务和 AKS 被定价为按需付费的云服务(对于基于数据库实例消耗的核心数量的数据服务)。

Arc 数据服务没有数据输入/输出成本，但如果您在有输入/输出成本的托管服务上运行该服务，提供商可能会向您收取进出数据库实例和 Arc 数据控制器的数据费用；只有少量的流量进出数据控制器，但如果你添加 Azure Monitor、Log Analytics 或 Azure Backup 等 Azure 服务，这可能意味着发送更大量的数据。当然，任何多云系统都是如此。

通过 Arc，微软正在开发一种一致的方法，将各种各样的基础设施引入其管理平面。虽然过去四年对混合云的关注是其他云提供商必须赶上的，但负责企业研究的副总裁 [Nicholas McQuire](https://www.linkedin.com/in/nicholasmcquire/) 向新的堆栈建议，Arc 将需要更强的多云支持——这是 IBM 和谷歌云比微软更关注的领域。

“现在扩展 Azure 控制面板的一个重要组成部分是其他云。Ignite 上的 Arc 公告增加了一些关键部分，特别是在服务器和托管数据库支持方面，我们预计未来会看到更多 Arc 服务扩展到 AWS 和 GCP 环境，并与公共云服务市场保持一致。”

McQuire 建议，到目前为止，Arc 一直专注于主流基础设施和数据库工作负载，但微软需要将 Arc 保护伞扩展到更多的数据服务，如分析、机器学习甚至 5G 边缘计算。

云计算原生计算基金会是新堆栈的赞助商。

来自 Pixabay 的 JacLou DL 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>