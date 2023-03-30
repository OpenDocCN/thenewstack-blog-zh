# 嵌套虚拟化为容器提供了虚拟机隔离，而没有开销

> 原文：<https://thenewstack.io/azure-ahead-nested-virtualization/>

在虚拟机中运行虚拟机(VM)听起来可能效率低下，但在最新的 CPU 上运行硬件辅助虚拟化意味着只有适度的性能损失，并且这种嵌套虚拟化为传统应用程序以及混合搭配容器和虚拟机的应用程序打开了许多选项。

[微软 Azure](https://azure.microsoft.com/en-us/?v=17.14) 已经上线了该功能(它是 Azure 运行于其上的 Windows Server 2016 功能集的一部分，可用于所有地区的最新 [VM 实例类型](https://azure.microsoft.com/en-us/blog/introducing-the-new-dv3-and-ev3-vm-sizes/))。[谷歌计算引擎](https://cloud.google.com/kubernetes-engine)最近[发布了 KVM 和 Linux 虚拟机的测试版](https://cloudplatform.googleblog.com/2017/09/introducing-nested-virtualization-for.html)，这些虚拟机运行在使用 [Haswell 或更新的 CPU](https://cloud.google.com/compute/docs/regions-zones/regions-zones#available)的实例上，[亚马逊 Web 服务即将为其 C5](https://www.theregister.co.uk/2017/11/07/aws_writes_new_kvm_based_hypervisor_to_make_its_cloud_go_faster/) 实例从 Xen 切换到 KVM 的原因之一很可能是为了实现嵌套虚拟化(特别是因为亚马逊今年早些时候向 [Linux 内核贡献了一些相关代码](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=e1d39b17e044e8ae819827810d87d809ba5f58c0))。

这个想法并不新鲜；当微软在 2003 年从 Connectix 购买虚拟个人电脑时，它可以运行自己的模拟器。但正是 Hyper-V 容器——它结合了 Docker 容器的优势和虚拟机的隔离——给了 Windows 服务器提供他们十年来一直想创建的功能的动力。

“我们发现这是一个非常方便、有用的工具，特别是对开发人员来说，但嵌套虚拟化的用例爆炸式增长非常快，”微软的泰勒·布朗告诉新堆栈。

## 提升、移位和追加

“我们在 Azure 上的主要堆栈都是虚拟化的，”微软 Azure 计算产品负责人 Corey Sanders 指出。“一些客户需要利用一些虚拟化技术和功能，我们的主机不会直接公开这些技术和功能。”

最明显的用途是用于 QA 和运行培训实验室，在这种情况下，您希望将现有的虚拟化环境迁移到云中，而不做任何更改，这些都是谷歌为嵌套虚拟化提供的相同示例，使用类似[功能化](http://www.functionize.com/)的服务。

但布朗说，生产工作量也是如此。

“我可以将整个环境迁移到 Azure，这是我以前无法做到的。我有一组预配置的虚拟机，我已经对它们进行了验证，它们可以正常工作；现在，我不必担心更改任何东西，我只需提升整个映像并在 Azure 中运行它，所有这些虚拟机将继续像以前一样工作。现在，我可以移动整个应用程序，这些应用程序不容易装箱或搬运；该应用的整个部分只是在一组嵌套的虚拟机中运行，甚至是一对一的。”

例如，与使用 [Oracle 的 Ravello](https://cloud.oracle.com/en_US/ravello) 嵌套虚拟化在 AWS 上运行 VMware 工作负载而不进行更改不同，还有机会扩展应用程序并通过对其进行编码来取代一次性的“雪花”环境。

嵌套虚拟化还为第三方软件供应商提供了一种为云打包现有应用和服务的方式。“我们有一个合作伙伴围绕 Hyper-V Replica 构建了一个解决方案，这是一个 API，使您能够拍摄快照并将 Hyper-V 实时复制到另一个 Hyper-V 实例，”Sanders 证实道。“他们希望在 Azure 中启用该解决方案，通过嵌套虚拟化，他们可以让客户在我们的虚拟机中部署虚拟机，并利用内置于 Hyper-V 中的技术。”

一些客户一直在要求嵌套虚拟化，以便对 Azure 上的虚拟机进行更多控制。“借助嵌套虚拟化，您可以在我们的规模内创建您想要的任何实例规模，甚至可以配置超额订阅，以更高效的方式尝试和利用云硬件。”这需要桑德斯巧妙地称之为“大量的复杂性”，同时也牺牲了云 IaaS 的简单性和敏捷性。

## 隔离虚拟机但没有开销的容器

但 Azure 客户最感兴趣的是嵌套虚拟化可以使用 Hyper-V 容器将容器的低成本和更容易的服务模式与虚拟机的隔离和安全优势结合起来。“嵌套虚拟化的大趋势将是容器，”Sanders 预测道。

“特别是对于那些运行一些面向客户的应用程序的客户，一些多租户解决方案，其中他们的最终客户可以完全访问容器，实现虚拟化保护和隔离层将非常重要，”他说。

布朗解释说，并不是每个人都需要这种保护，但这使集装箱对那些需要的人来说是可行的。“我们看到了 Hyper-V 隔离的充分渗透，很明显，业务和监管需要一个完善的隔离边界。”

“Hyper-V 隔离允许我们在对话中说‘安全边界没有什么不同，它们与物理边界完全相同’，但容器是当今思考问题空间的一种不同方式。虚拟机提供的特性是它们非常安全，这对于一些应用程序来说很有价值，但对于其他应用程序来说确实没有必要。因此，我们可以就“为什么需要有状态层或不需要有状态层”展开对话。为什么那个特定的层级需要那个状态？我们可以为开发人员讨论一些事情，比如检查点；虚拟机提供检查点技术，可以捕获所有内存状态。这是您所需要的，还是您只需要磁盘上的状态；如果您需要的只是磁盘上的状态，那么容器会更适合您吗？"

布朗认为，这种发展反映了向容器的转变及其持续的演变。“虚拟机运行良好。它们解决了我们在云中的很多需求，但是容器为跨云和 DevOps 模型的可移植性提供了更好的体验。它们比抽象层次高了一步，但仍然提供了相同的价值，这也是它们如此吸引人的部分原因。”

随着开发人员开始发现他们可以用容器做什么，需要新的工具。“当我们发现一些领域的答案是‘我们需要这个工作的另一个工具’时，比如有状态性(stateful ness)——这是分离状态——像卷驱动程序和以一种非常容易理解的方式在容器外保存状态的能力。因此，我们获得了由容器和 DevOps 模型提供的更好的密度，但我们仍然可以将它用于一些有状态的应用程序。”在嵌套虚拟化中运行容器填补了另一个空白。

## 特定问题的真实世界解决方案

然而，嵌套虚拟化并不是微软提供其新的 VMware 支持的方式(也不是微软最近宣布的对 Azure 的 SAP HANA 的支持)。“我们在裸机上发布了一系列功能，如 SAP 大型实例和 Cray，”Sanders 解释道。“在所有这些情况下，由于各种原因，裸机支持只能在裸机上进行，无论是网络要求、规模要求，还是 Cray 的实际硬件要求。在 VMware 的案例中，很多都是围绕着交付它所必需的网络要求。”

例如，嵌套虚拟化不支持广播或多播，Brown 告诉我们 Hyper-V 团队希望做更多的工作来“提高内存访问和性能”

在 Azure 和 Windows Server 上使用嵌套虚拟化的 Hyper-V 容器最初只支持 Windows 容器，但[微软也一直在研究运行 Linux 容器的](https://cloudblogs.microsoft.com/hybridcloud/2017/04/18/dockercon-2017-powering-new-linux-innovations-with-hyper-v-isolation-and-windows-server/)(Windows 上 Linux 容器的缩写为 LCOW)。Windows Server 1709 可以运行带有 Hyper-V 隔离的 Linux 容器，虽然 Docker LinuxKit [支持还在预览](https://blog.docker.com/2017/09/preview-linux-containers-on-windows/)，这里有 [Ubuntu 的分步说明](https://tutorials.ubuntu.com/tutorial/tutorial-windows-ubuntu-hyperv-containers#0)；在带有 vCPU 的虚拟机中创建容器，如 Dv3 或 Ev3 实例，它运行嵌套虚拟化。

下一个阶段(仍在合并到 [Docker](https://github.com/moby/moby/pull/34859) 中)是支持同时在同一个 Windows 节点上并行运行 Linux 和 Windows 容器(不仅仅是在同一个集群中混合 Windows 和 Linux 节点，你已经可以这样做了)。这将在容器之间提供更好的延迟，但也允许组织在单个基础设施上运行混合负载，并使开发人员更容易在单个系统上构建混合的 Linux 和 Windows 应用程序。它为受监管行业中希望对 Linux 容器进行虚拟机级隔离的企业提供了传统虚拟化之外的另一种选择。

到目前为止，AWS 和 GCP 只支持 KVM，而且只支持 Linux。虽然桑德斯指出 Hyper-V 是“我们完全理解并完全支持的虚拟机管理程序”，但 Azure 的嵌套虚拟化也适用于其他虚拟机管理程序；Azure 自己的网络团队使用 KVM 的嵌套虚拟化来运行容器化的路由器，并在其 [CrystalNet](https://www.microsoft.com/en-us/research/publication/crystalnet-faithfully-emulating-large-production-networks) 网络仿真工具中与虚拟机一起交换映像——因为一些网络硬件制造商只提供虚拟机形式的映像，而一些只提供容器形式的映像。

随着组织超越将应用程序迁移到云并开始扩展和增强这些应用程序，这种混合和匹配的异构系统可能会变得更加常见。能从零开始，很难得；通常，一个应用程序需要的资源不会以同样干净、整洁、现代的形式存在。

桑德斯说:“几乎世界上的每一个应用程序，如果今天完全重写，都将使用非常不同的技术，但对于几乎每一个客户和应用程序来说，这只是一种不合理或合理的可能性。”

谷歌、[微软](https://azure.microsoft.com/en-us/?v=17.14)和 [VMware](https://www.vmware.com/cloud-solutions/app-modernization/cloud-native-apps.html) 是新堆栈的赞助商。

由 [Kate Remmer](https://unsplash.com/photos/05_sUnshoaE?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash 上拍摄的特征图像。](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>