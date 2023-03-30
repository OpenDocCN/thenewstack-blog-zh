# 借助您的混合云基础架构，从这里到任何地方

> 原文：<https://thenewstack.io/get-from-here-to-anywhere-with-your-hybrid-cloud-infrastructure/>

[NetApp](https://www.netapp.com/us/solutions/devops/index.aspx) 赞助了这篇文章。

 [艾伦·考尔斯

Alan 是 NetApp 的解决方案架构师。](https://www.linkedin.com/in/alanvcowles/) 

“从这里，任何地方”是[红帽峰会 2020 虚拟体验](https://www.redhat.com/en/summit)的主题。这是一个相当吸引人的标语，但它确实让你想知道它的意思。我和我的 NetApp 同事急于找到答案，所以我们注册了 4 月 28 日和 29 日举行的免费虚拟活动。参加了几次会议后，我对它的含义有了更好的理解。

我们都在旅行。我们都有一个起点:我们现在的基础设施状况。我们都有一个目的地，我们希望我们的基础设施所在的地方——一个基础设施转型，如果你愿意的话。许多这样的变革之旅正在 IT 领域发生。我们行业中的许多人在过去几年中经历的一次旅程的起点是传统的内部基础架构，终点是公共云。

## 简化之旅中的挑战

现场基础架构通常包括计算、网络、存储和虚拟化，全部由现场管理团队管理。相反，公共云提供作为服务交付的基础架构，这简化了资源调配、部署和管理。这种放手的方法已经成为许多公司消费基础设施的关键。虽然这些公司可能仍然在内部托管他们的一些服务，但他们最终的目标是简单。

考虑到简单性，现场数据中心的融合和超融合基础设施的部署有所增加。超融合解决方案允许部署任意数量的类似服务器，传统的网络和存储角色由虚拟机管理程序虚拟化。为了易于使用，管理采用简单的用户界面，就像公共云中可用的用户界面一样。

然而，这些解决方案仍然存在挑战。为了获得简单性，通常需要进行权衡。在许多情况下，您受限于供应商为其平台选择的特定虚拟机管理程序。通常，关键服务(如存储)的虚拟化会导致额外的开销和系统资源利用率。由于整个部署需要相似或相同的节点，您会发现自己不得不扩展整个基础架构来满足特定的资源需求。例如，如果您需要额外的存储，那么您还必须扩展您的计算空间并向基础架构添加更多虚拟机管理程序，因为这两种服务是一体的。

## 选择更好的道路:分解和自动化

为了帮助您解决这些问题，NetApp HCI 被设计为一种分解的基础架构。您可以独立扩展计算和存储节点。您还可以通过 NetApp 部署引擎(NDE)简化部署和管理。您可以使用 NDE 部署带有默认虚拟机管理程序的默认配置。

然而，使 NetApp HCI 真正具有创新性的是基础架构由独立的存储和计算资源组成这一事实。因此，您可以在没有任何特定依赖关系的情况下部署您选择的虚拟机管理程序。尽管这一过程不是自动化的，但仍通过详细的设计和部署文档(以 NetApp 认证架构(NVA)文档的形式)得到了极大的简化。这些文档详细描述了由 NetApp 工程师执行的设置和配置过程。我们的团队采用这种方法，将 [NetApp HCI 用于带有 Red Hat](https://www.netapp.com/us/media/nva-1133-deploy.pdf) 的私有云。我们与 NetApp 和 Red Hat 的主题专家合作，基于 Red Hat OpenStack Platform 13 和 OpenShift Container Platform 3.11，在 NetApp HCI 上为虚拟化和容器化应用程序部署私有云环境。

现在，为了满足对简单性和灵活性的更高要求，NetApp 和 Red Hat 宣布了一个新的联合解决方案:**NetApp HCI for Red Hat open shift on Red Hat virtual ization**。NetApp 希望通过其混合云基础架构提供更高的简单性、更多选项和更大的选择自由度。所以我们选择和红帽再次合作。这种新的解决方案支持 OpenShift 容器平台 4.4，它作为托管在 Red Hat Virtualization 4.4 上的虚拟化基础架构运行。它安装在 NetApp HCI 计算节点上，并且具有运行 NetApp Element 12 软件的存储节点。

Red Hat 虚拟化是一种企业级虚拟化数据中心技术，基于 Red Hat Enterprise Linux，构建在基于内核的虚拟机(KVM)管理程序的基础上。通过 Red Hat Virtualization Manager，您可以获得现代虚拟数据中心的所有功能，如共享存储、实时迁移、高可用性和集中管理。

借助 Red Hat 虚拟化，Red Hat OpenShift 4.4 引入了全自动安装体验。通过 Red Hat 虚拟化上的安装程序提供的基础架构方法和用于容器化应用程序的资源管理模型，您可以简化部署。只需使用 openshift-install 二进制文件，并提供一些关于部署在 NetApp HCI 上的 Red Hat 虚拟化环境的信息。然后，无需交互或管理员操作，就可以为您部署一个全功能的 OpenShift 集群。全栈自动化部署促进了无故障部署，使您的开发运维工作流能够轻松跟上速度。

整个 NetApp 和 Red Hat 解决方案使用基于 NetApp 元素的存储系统来提供 iSCSI 存储卷，您可以将其用作 Red Hat 虚拟化中的共享存储域。您还可以在 OpenShift 中获得容器化应用程序的持久卷，这些卷是使用 NetApp Trident storage orchestrator 动态配置的。

## 观看课程并参加大师班

如果您对 NetApp 和 Red Hat 如何合作为混合云和容器创建最佳基础架构解决方案感兴趣，您可以点播观看来自 [Red Hat 虚拟峰会](https://www.redhat.com/en/summit)的几场会议。此外，请务必参加专门针对该解决方案的特别[大师班网络研讨会](https://netapp.io/event/devops-master-class-special-edition-with-red-hat/)，该研讨会将于 5 月 19 日现场直播。本次网络研讨会是一次深入探索联合解决方案的机会，来自 NetApp 和 Red Hat 的工程师将展示 NetApp HCI、Red Hat 虚拟化和 OpenShift 容器平台。在[网络研讨会](https://netapp.io/event/devops-master-class-special-edition-with-red-hat/)期间，您还将有机会观看该解决方案的简短演示。网上研讨会将以现场问答环节结束。我将作为 NetApp 的主题专家出席，安德鲁·苏利文将作为 Red Hat 的主题专家出席。

我们真诚希望您能参加我们 5 月 19 日的现场[网络研讨会](https://netapp.io/event/devops-master-class-special-edition-with-red-hat/)。这只是我们继续从这里到任何地方的 It 基础架构之旅的下一步。

*[注册](https://netapp.io/event/devops-master-class-special-edition-with-red-hat/)devo PS 大师班特别版:NetApp HCI 上的红帽，太平洋时间 2020 年 5 月 19 日上午 9:30。*

*在大师班之后，您将有机会与 NetApp 技术专家进行一对一的交流，讨论您面临的独特挑战。*

Red Hat OpenShift 是新堆栈的赞助商。

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>