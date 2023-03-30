# 微软终于把基于 ARM 的虚拟机带到了 Azure

> 原文：<https://thenewstack.io/microsoft-finally-brings-arm-based-vms-to-azure/>

嗯，那花了点时间。在亚马逊网络服务公司(Amazon Web Services)和 T2 甲骨文公司(Oracle)购买 ARM 处理器用于云计算的几年后，微软终于冒险让 T4 将 ARM 芯片引入 Azure。

微软的新产品现在处于预览阶段，其特点是 Azure 虚拟机(VM)运行在基于 Ampere Altra Arm 的处理器上。这些新虚拟机旨在高效运行横向扩展工作负载、web 服务器、应用服务器、开源数据库、云原生。NET 应用程序、Java 应用程序、游戏服务器、媒体服务器等等。简而言之，所有东西和厨房水槽。

## 最适合 CI/CD

就我个人而言，我不确定所有应用程序清单都能在 ARM 虚拟机上很好地运行。正如 [Ed Vielmetti](https://www.linkedin.com/in/edwardvielmetti/) 、 [Equinix Metal](https://metal.equinix.com/?utm_content=inline-mention) 高级生态系统工程师(他喜欢云上的 ARM)所观察到的， [ARM 在 CI/CD 构建操作](https://metal.equinix.com/blog/cloud-native-arm-servers-mainstream/)等任务上表现最佳；高内存应用程序和需要快速扩展的程序。

为什么？因为它们都可以利用 ARM 的固有优势，即拥有比 x86 竞争对手多得多的内核。例如，Azure 正在部署的 Ampere 高性能云原生处理器可以包含多达 128 个内核。顶级英特尔云 CPU[英特尔至强白金 8380 处理器](https://www.intel.com/content/www/us/en/products/sku/212287/intel-xeon-platinum-8380-processor-60m-cache-2-30-ghz/specifications.html)，最大 40 核。当然，内核并不是一切，但它是 ARM 在处理云级应用时的王牌之一。

至于 Azure 的现有产品，微软声称其新的 ARM 虚拟机系列包括通用 Dpsv5 和内存优化的 Epsv5 虚拟机，与可比的基于 x86 的虚拟机相比，其性价比最高可提高 50%。您可以通过填写[这张表格](https://aka.ms/arm64vmspreview)来请求访问预览。

Dpsv5 和 Epsv5 Azure VM 系列采用基于 Ampere Altra Arm 的处理器，工作频率高达 3.0GHz。新 VM 提供多达 64 个 vCPU，包括每个 vCPU 2gb、4gb 和 8gb 内存配置的 VM 大小、高达 40 Gbps 的网络和可选的高性能本地 SSD 存储。

Dpsv5 虚拟机运行典型的 Linux 企业工作负载。这包括 web 服务器、应用服务器、开源数据库。NET 应用程序、Java 应用程序、游戏服务器、媒体服务器等等。Dpldsv5 VM 系列为每个 vCPU 提供 2gb 的容量。它提供了各种 vCPU、内存和本地存储组合，能够经济高效地运行每个 vCPU 需要少量 RAM 的工作负载。

您还可以以较低的价格获得不带临时存储的 Dpsv5、Dplsv5 和 Epsv5 VM 系列。您还可以将标准固态硬盘、标准硬盘和高级固态硬盘连接到当前 preview 中的任何虚拟机，Ultra Disk 存储支持即将推出。也支持虚拟机规模集。

现场虚拟机可用。然而，在 ARM 虚拟机普遍可用之前，Azure 保留虚拟机实例定价将不可用。和往常一样，价格因地区而异。

目前，你可以在 ARM 虚拟机上运行 [Canonical](https://canonical.com/) Ubuntu Linux、CentOS 和 Windows 11 专业版和企业版。对 AlmaLinux 的支持即将到来，CentOS 克隆；Debian 红帽企业 Linux(RHEL)；SUSE Linux 企业服务器(SLES)；和 Flatcar 容器 Linux。

## 为什么是手臂？

那么，你为什么想试试 ARM 呢？[Canonical 公共云副总裁亚历山大·加拉格尔](https://www.linkedin.com/in/alexander-gallagher-a997a513/)说这很简单。“我们看到许多公司使用基于 ARM 的架构来降低成本和能耗。对于那些希望在 Azure 上使用 Linux 进行开发的人来说，这是一个巨大的进步，我们很高兴与微软合作提供 Ubuntu 图像。”

[红帽](https://www.openshift.com/try?utm_content=inline-mention)同意。看到了吗？Canonical 和 Red Hat 可以在一个问题上站在同一边！Red Hat 的云合作伙伴副总裁 Maryam Zand 多年来一直致力于 ARM in 服务器。他们是 ARM 的先驱之一。对于 Red Hat 来说，这为他们的“客户提供了广泛的选择，以满足他们独特的企业计算需求，这扩展到了内部和公共云中的架构选择。”

最后，SUSE 首席技术官托马斯·迪·吉亚科莫博士也加入了进来。“SUSE 在 Arm 生态系统中扮演着重要而积极的角色，支持 Arm 64 位架构和 Ampere Altra 服务器实例。SUSE 很高兴能与 Microsoft Azure 合作，在我们即将发布的 SLES 15 SP4 版本中支持基于 Ampere Altra Arm 的服务器实例的 Dpsv5 和 Epsv5 Azure VM 系列。

简而言之，无论什么 Linux 发行版支持你的业务，它都可以在 Azure 的 ARM 产品上使用。

## AK 和更多

除了简单地运行 Linux 虚拟机和 [Windows 365 云 PC](https://www.microsoft.com/en-us/windows-365) 实例，Azure 还使其客户能够通过 [Azure Kubernetes 服务(AKS)](https://azure.microsoft.com/en-us/services/kubernetes-service/) 部署、运行和管理容器化的应用。你为什么要这么做？微软 AKS 集团产品经理 Sean McKenna 表示，这是因为 ARM 处理器将提供更好的性价比，尤其是当你扩大云足迹的时候。

至于您的应用程序，您将能够运行。Linux 上的. NET 5 和 6 程序。这意味着你可以在这个平台上构建 C# 10 和 F# 6 应用程序。很快，你也可以。Windows 11 上的. NET Framework 4.8.1。两者目前都在预览中。此外，在 preview 中，最新的 Microsoft Visual C++工具将使您不仅可以运行您的应用程序，还可以在 ARM 上为 ARM 进行本机构建。

当然，由于微软最近对 OpenJDK 的贡献，你可以用 OpenJDK 的微软版本来构建和运行 Java 应用程序。微软在兼容的 Arm 硬件上为 Java 11 和 Java 17 提供了 Windows、Linux 和 macOS 的二进制文件。轻量级的免费 [Visual Studio 代码](https://code.visualstudio.com/)编辑器也可以在 ARM 上本地运行。

了解关于新 Azure 虚拟机的更多信息，并[请求访问预览版](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRyMSy8VejZVEo6yZykiPSHpURFRIQVY1QTcyWTlJNURUS1pNTktOUTUxVi4u)。

最初，ARM 预览版将仅在美国西部 2、美国中西部和西欧 Azure 地区提供。想知道更多吗？太平洋时间 4 月 27 日(星期三)上午 10-11 点，将有一场[网络研讨会](https://info.microsoft.com/ww-landing-new-innovations-with-azure-core-compute.html?lcid=en-us)。“看”你那里。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>