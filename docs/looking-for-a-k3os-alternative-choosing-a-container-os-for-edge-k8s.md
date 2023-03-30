# 寻找 k3OS 替代品？为 Edge K8s 选择容器操作系统

> 原文：<https://thenewstack.io/looking-for-a-k3os-alternative-choosing-a-container-os-for-edge-k8s/>

作为一名系统管理员，您知道部署和维护 Linux 发行版是很痛苦的。

即使出现了基础设施即代码(IaC)范例，如 Terraform，由于增量更新，Linux 系统也经常处于不同的状态(“雪花”)。

## 容器 OS:为容器和 Kubernetes 构建

今天，我们需要使用 Kubernetes 针对容器化的云原生工作负载优化我们的 Linux 发行版。这意味着保持基础操作系统的稳定性和可预测性，以便顶层的集群能够以相同的可靠性、性能和安全性运行，并使用 K8s 需要的依赖项和服务来优化内核。

如果您改为采用针对 Kubernetes 优化的容器操作系统，就可以避免这种努力。容器操作系统通常在资源有限时部署，尤其是在边缘计算环境中。这就是为什么它们通常是轻量级的，并与轻量级(100 兆以下)Kubernetes 发行版如 [K3S](https://docs.k3s.io/quick-start) 搭配使用。

## 让我们比较六个主要的容器操作系统

在本文中，我们将帮助您找到最适合 Kubernetes 的操作系统。我们将涵盖:

*   CoreOS，先锋云原生操作系统
*   Flatcar 容器 Linux，后继者
*   K3OS，轻量级
*   波特洛克特，亚马逊人
*   Talos，CNCF 认证的安装程序
*   凯罗斯，工厂

## CoreOS，先锋云原生操作系统

可以说第一个容器操作系统是 T2 的 core OS T3。CoreOS 团队在 2013 年发布了第一个版本，甚至在 Kubernetes 创建之前。CoreOS Linux 内置了许多安全特性，比如自动更新和只读文件系统。这种类型的操作系统被认为是“不可变的”CoreOS 还包括一个漏洞扫描器和一个容器防火墙。

2018 年，红帽收购 CoreOS，带领 [Kinvolk](https://kinvolk.io/about/) 团队打造了 [Flatcar](https://www.flatcar.org/docs/latest) Container Linux，作为嵌入式开源替代。

## Flatcar 容器 Linux，后继者

和 CoreOS Linux 一样，Flatcar 是不可变的。它在初始引导过程中是可配置的，任何进一步的修改都不是持久的。只有特定目录中的用户数据会在重新启动后保留。

除了不可变和易于使用之外，Flatcar 还具有令人兴奋的特性，如自动系统更新和主动/被动分区功能，使可伸缩性变得容易。

值得一提的是，当部署到裸机服务器时，ISO 映像是可下载的，这使得 Flatcar 非常适合 Kubernetes edge 用例。

然而，它缺少构建 Kubernetes 集群的现成自动化，并且不提供任何 Kubernetes 本地框架来管理集群生命周期。在我们看来，它属于 DIY 范畴，其中包含了对容器 OS 的管理，但 Kubernetes 层是完全断开的。

对于任何想要管理 Kubernetes 部署的人来说，我们需要继续寻找。

## K3OS，轻量级

K3OS 是由 Rancher Labs 专门为 K3S 集群设计的轻量级不可变操作系统。它只包含驱动 Kubernetes 集群的基本组件。k3OS 和 K3S 的轻量级带来了许多好处，例如减少了攻击面、缩短了启动时间和更精简的文件系统，这使其成为边缘用例的候选。

### 库伯内特土著

此外，一旦集群开始运行，您可以使用 Kubernetes API 轻松地对其进行升级。事实上，k3OS 与 Rancher 系统升级控制器的集成提供了一个 Kubernetes 本地解决方案，通过扩展 Kubernetes API 来升级节点。它使 k3OS 节点能够利用自己的 Kubernetes 集群功能，从最新的 GitHub 版本自动升级。这使得它成为一个真正的 Kubernetes 本地过程。

然而，定制 k3OS 映像并将其配置与 Kubernetes 集群部署一起自动化是复杂的。此外，没有 Kubernetes-native 的方法来生成这些图像或轻松地将它们部署到公共云。

### 一个夭折的项目？

虽然这些功能可能是该项目的一些有趣的后续步骤，但最新的 k3OS [版本](https://github.com/rancher/k3os/releases)于 2021 年 10 月发布，GitHub 问题尚未得到解决。随着 k3OS 的发展显然已经死亡，用户现在正在寻找其他替代方案(其他评论的例子[在这里](https://github.com/rancher/k3os/issues/846))，很难推荐在今天的任何生产环境中使用 k3OS。

下一步是什么？

## 波特洛克特，亚马逊人

Bottlerocket 是另一个基于 Linux 的开源操作系统，专门为在 Kubernetes 集群上安全运行容器化的工作负载而设计。

### 伟大的 AWS 忠诚者

亚马逊网络服务(AWS)在 2020 年创建了 Bottlerocket，它已经集成了各种各样的 AWS 服务，如弹性 Kubernetes 服务(EKS)、弹性容器服务(ECS)、Fargate、EC2 实例、Graviton2 和亚马逊检查员。因此，虽然您可以在各种环境中运行 Bottlerocket，但它主要针对 AWS 公共云。

虽然在 AWS 云或 VMware vSphere 中部署很容易，但在裸机服务器或边缘环境中配置 Bottlerocket 要困难得多。(你可以在这里找到完整的指南)。在 VMware vSphere 中，Bottlerocket 只能作为工作节点运行，这也是一个不便之处。这意味着必须已经有一个现有的控制平面节点，您必须单独进行配置。

该系统只能通过 API 进行配置，采用安全的带外访问方法。Bottlerocket guest 只能通过管理或控制容器来访问，这些容器是额外的组件，必须安装在单独的容器实例中。没有 SSH 服务器，甚至没有 shell。

### 库贝土著

Bottlerocket Kubernetes 运营商负责系统更新，而图像由 TUF(更新框架)保护。这是一个完全 Kubernetes 本地工作流，遵循与 Rancher 系统升级控制器相同的原则。新的映像将替换现有的映像，并且如果在引导过程中出现故障，它将具有回滚功能。

此外，Bottlerocket 支持多个“变体”，对应于一组受支持的集成和功能，如 Kubernetes、ECS、Nvidia GPU 等等。

也可以从策划的变体中构建自己的 Bottlerocket 映像，而不是直接下载工件。这需要 Rust 和 Docker BuildKit。最后，值得注意的是，在撰写本文时没有包含 K3S 的变体。

## Talos，CNCF 认证的安装程序

Talos 是一个极简主义的 Linux 发行版，是为运行 Kubernetes 而从头设计的。

它的主要目的是将 Kubernetes 原则带到操作系统层。它引入了一种声明式的方法来管理操作系统和 Kubernetes 的本地组件，允许以一种简化且高效的方式处理操作，并在整个系统的生命周期中导航。它由 [Sidero Labs](https://www.siderolabs.com/platform/talos-os-for-kubernetes/) 于 2018 年发布(预发布)，并且完全开源。

### CAPI 友好的容器操作系统

Talos 完全移除了 SSH 和控制台访问，支持 API 管理。您可以在裸机服务器和虚拟化系统上的任何超大规模云中部署 Talos。该工具还提供了一种通过执行命令`talosctl cluster create`使用 Docker 运行时部署本地 Talos 集群的简单方法。

它还包括一个集群 API (CAPI)提供者，集群 API 引导提供者 Talos 或 CABPT。它的作用是为机器生成引导配置，并将更新后的资源与 CAPI 进行协调。控制平面配置有一个单独的提供者，即集群 API 控制平面提供者 Talos (CACPPT)。

### 用于生命周期管理的强大 CLI

`talostctl`命令行界面允许您与 Talos 节点和 Kubernetes 集群进行交互，而不需要任何终端或 ssh 连接。它利用了 API 和 Kubernetes CRDs。这使得所有 Kubernetes 基础设施组件的无摩擦生命周期管理成为可能。

Talos 通过`talosctl` CLI 结合声明性输入为您提供了一系列操作。例如，您可以通过运行`talosctl upgrade-k8s --to 1.26.1`以协调的方式升级您的整个集群，其中 1.26.1 是更新的 Kubernetes 版本。

### 强大的安全功能

Talos 在瞬间构建安全的 Kubernetes 集群方面非常高效。Talos 支持磁盘加密、NVIDIA GPU 和 Fabric Manager，并允许您管理您的公钥基础设施(PKI)的生命周期。在边缘运行 Talos 时，磁盘加密非常有用。它可以在磁盘丢失或被盗的情况下保护数据。但是，它的设计并不是为了防止对机器(包括驱动器)进行物理访问的攻击。

它还提供了内置的管理功能来促进集群生命周期管理。

例如，它通过依靠浮动虚拟 IP 部署高度可用的 Kubernetes 集群，无需任何外部负载平衡器，并允许通过公共互联网上的 Wireguard 对等发现进行安全连接。如果一个节点出现故障，剩余的控制平面节点之一将接管 VIP 的所有权。

此外，集群会在集群初始化期间自动引导，并且控制平面的缩放也很容易。

### 轻量级，但固执己见

系统占用空间非常小，只有 80MB SquashFS 图像大小。这大大减少了集群的攻击面。然而，Talos 固执己见的方法也意味着它有一些缺点和局限性:

*   它不支持 K3S，尽管减小的操作系统大小补偿了总的占用空间差异。
*   映像定制仅限于内核模块和根文件系统内容。
*   随着内核占用空间的减少，支持的硬件和特定内核功能的列表也会减少。
*   系统管理的某些方面比传统的 Kubernetes 环境更复杂。

因此，Talos 非常适合特定的场景，在这些场景中，灵活性和安全的现成分发之间的权衡是可以接受的。

## 凯罗斯，工厂

在过去的几年里，Kubernetes 出现了一个有趣的模式。它需要使用 Kubernetes 作为一个可扩展的 API 来添加自动化功能。

例如，Cluster API 通过使集群逻辑组件成为 Kubernetes 中的一等公民，允许部署 Kubernetes 集群。因此，从现有的 Kubernetes 集群中，您可以引导一个新的 Kubernetes 集群，并在部署后委派其管理。

凯罗斯的运作原理相同。它允许您通过扩展 Kubernetes API 来构建和定制不可变的操作系统映像和 Kubernetes 集群。它通过一个监视 Kairos 自定义资源的自定义控制器来提供这些功能。控制器根据在这些资源上执行的 CRUD 操作采取适当的行动。

### 构建您选择的操作系统的工厂

Kairos 提供的不仅仅是一个容器专用的操作系统。Kairos 充当 Kubernetes 的“工厂”,生产由您选择的不可变操作系统支持的 K3S 集群。与之前描述的其他解决方案不同，Kairos 是一个元发行版，这意味着它有能力将任何现有的 Linux 发行版转换成一个不可变的操作系统。

与其固执己见，不如灵活地使用你选择的操作系统。一旦您选择了发行版，Kairos 就会发布一个不可变的工件，您可以将其部署为一个完整的操作系统来支持 Kubernetes 集群。

### OCI 注册中心简化 ISO 映像构建

唯一的要求是该系统符合 OCI 标准的容器映像。Kairos 依靠开放容器倡议(OCI)容器注册中心从容器映像构建成熟的操作系统。这简化了 OS 构建和更新过程，因为这是通过使用 Dockerfiles 和容器运行时来实现的。或者，Kairos 也为每个版本提供预构建的图像。

Kairos 通过一个 ISO 映像交付最终的工件，该映像是通过多个选项制作的:Kubernetes 自定义资源定义(CRDs)、预启动执行环境(PXE)启动，或者通过在目标服务器上手动安装 ISO 映像。

凯罗斯的另一个关键特征是[极光启动](https://github.com/kairos-io/AuroraBoot)。它允许您通过与动态主机配置协议(DHCP)服务器合作，直接从网络引导 Kairos 映像。目前，Aurora 作为 Docker 容器运行，但很快将作为 Kubernetes pod 提供。使用 Aurora，您所需要的只是一个配置文件，它指定了您想要部署为 Kubernetes 集群操作系统的容器映像，以及 cloud-init 配置。

### 自协调集群引导

Kairos 天生支持 Kubernetes。更具体地说，它提供 K3S 集群，使其成为 Kubernetes edge 用例的完美选择。

在这种情况下，Kairos 还能够自我协调 Kubernetes 集群的引导，而不需要任何中央服务器。这意味着它可以按需部署高可用性(HA) Kubernetes 集群，除了所需的控制平面节点数量和 kube-vip 使用的虚拟 IP 之外，不需要任何其他设置。将这种方法与 Aurora 结合起来，您可以通过网络在瞬间自动部署一个 HA 集群。选举过程定义了每个节点的角色，并通过共享的分类帐完全分布。

因此，无论您是希望部署单节点群集，还是具有多个控制平面节点的大型 HA 群集，过程都是相同的。因此，它大大减少了集群的构建，同时还允许更好的可伸缩性。

### 高度安全

在安全性方面，Kairos 可选择使用本地可信平台模块(TPM)芯片提供磁盘加密。支持多种场景:

*   加密密钥可以存储在 TPM 芯片中
*   使用 TPM 密钥对加密后，可以使用外部服务器来存储用户数据分区的加密密码
*   密钥管理(KMS)服务器可用于存储密码，并在 TPM 质询后将其返回给节点。

最后，Kairos 使用与 cloud-init 兼容的云配置格式简化了功能配置。它为动态配置提供了模板化功能，简化了自动化以及与 CI/CD 管道的集成。

Kairos 最初是为 Kubernetes edge operations 创建的，但它也是在数据中心的裸机或虚拟服务器上运行 Kubernetes 集群的一个很好的替代方案。

它的多功能性和对基本 Linux 发行版的选择使 Kairos 成为企业客户的理想解决方案，这些客户受到某些供应商和操作系统的限制，但仍然希望利用容器专用操作系统、不变性和大规模自动化。

## 为什么需要容器操作系统

Kubernetes 是一个复杂的分布式系统，您不能在一个糟糕的基础上构建您的集群。尽管 Kubernetes 经常被认为是“云操作系统”，但它本身并不是一个操作系统。它需要一个通过不变性和专门化提供强大和稳定支持的操作系统。

不变性加强了声明性驱动的状态，这种状态支持所有现代基础设施工具，消除了雪花现象，带来了更好的性能可预测性和更高的可伸缩性。

对于边缘使用案例，大多数操作都是远程执行的，本地很少或没有合格的员工。因此，像原子更新、轻松回滚、有限的可写文件系统和额外的安全性等特性是关键。通过采用不可变的容器操作系统，这一切都成为可能。

## 操作系统的选择对您来说重要吗？

在本文中我们比较的解决方案中，只有 Kairos 允许您将任何 Linux 操作系统转变为不可变的 os。如果您想继续使用您最喜欢的发行版，这可能是首选。

或者，您可以从一些提供开箱即用不变性的精选操作系统中进行选择。我们描述的大多数解决方案都是固执己见的，各有利弊。

## 不要忘记大规模多集群的管理平台

专用于容器的不可变操作系统只是拼图的一部分。当您在不同位置部署多个集群时，尤其是在边缘位置，您还需要一个中央管理平台来帮助实现标准化、简化部署和操作。

Spectro Cloud 的 Palette Edge 基于 Kairos 构建，增加了集中管理功能。它为集群配置文件提供了一个额外的抽象层，允许您创建标准化的 Kubernetes 集群配置，并在关联所需的边缘机器时部署到任何地方。

但是不要相信我的话！你可以[免费试用 Palette Edge】并将其与本文中提到的其他解决方案进行比较，或者](https://www.spectrocloud.com/free-tier/)[查看文档](https://docs.spectrocloud.com/clusters/edge/native)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>