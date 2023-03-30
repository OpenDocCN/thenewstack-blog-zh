# 为什么 Packet 要开源其“裸机”培养技术

> 原文：<https://thenewstack.io/why-open-source-matters-more-for-bare-metal/>

[Packet](https://www.packet.com/) 赞助新栈对 [IFX2019](https://www.eventbrite.com/e/ifx-2019-celebrating-the-craft-culture-of-infrastructure-registration-67894681821?aff=eemailordconf&utm_campaign=order_confirm&ref=eemailordconf&utm_medium=email&utm_source=eventbrite&utm_term=viewevent) 的新闻报道。

在当今以云为先的世界中，大多数开发人员将支持其部署的底层基础设施视为达到目的的手段。AWS、GCP 和微软 Azure 的高端服务的爆炸式增长进一步强化了这一点。

然而，随着组织寻求提高性能、降低成本或将公共云风格的体验引入其私有数据中心，管理裸机基础架构变得越来越重要。许多团队面临的挑战包括将公共云中的运营实践扩展到包括物理服务器和网络在内的基础架构堆栈。

Packet 是一家成立五年的公司，由软银、戴尔技术资本和其他公司资助，其核心业务是帮助开发人员主导的公司供应和生命周期物理基础设施。该公司目前提供全球裸机公共云，并帮助 Sprint 等大型组织将相同的体验扩展到内部和边缘环境。

与大型公共云不同，Packet 不提供数据库、Kubernetes 或无服务器等托管服务。相反，他们只关注基础架构即服务(计算、网络和存储构造块)，并依赖不断增长的软件和 DevOps 生态系统来实现高级服务。因此，开源和可移植软件在 Packet 的工作中扮演着关键角色。

虽然 Packet 为开源社区贡献了大量资源(为包括 CNCF、Openstack 和 Kernel.org 在内的数十个著名项目以及像 [Drone.io](https://www.packet.com/blog/a-blank-check-for-open-source/) 和 TravisCI 这样的 CI/CD 平台提供免费基础设施)，但该公司宣布将开放其服务器供应工作流引擎 [Tinkerbell](https://tinkerbell.org/) 。作为 Tinkerbell 项目的一部分，Packet 还将发布各种支持组件，即其元数据服务(Hegel)、内存安装环境(OSIE)和 DHCP & iPXE 服务器(Boots)。

在该公司位于拉斯维加斯市中心的 [IFX2019](https://www.eventbrite.com/e/ifx-2019-celebrating-the-craft-culture-of-infrastructure-registration-67894681821?aff=eemailordconf&utm_campaign=order_confirm&ref=eemailordconf&utm_medium=email&utm_source=eventbrite&utm_term=viewevent) 上，新的 Stack 有机会与 Packet 的首席架构师[内森·古尔丁](https://www.packet.com/about/team/nathan-goulding/)坐在一起。12 月 4 日至 5 日的活动是 Packet 的第二次年度供应商中立基础设施会议，与 [AWS Re:Invent](https://reinvent.awsevents.com/) 同时举办。Goulding 分享了在 Apache 2.0 许可下发布 Tinkerbell 如何反映了与开放源代码和更广泛的软件社区的深化关系。

Tinkerbell 是每月在 Packet 的全球裸机云上部署超过 60，000 次的同一技术，它为开发人员提供了一种一致的方法来配置和生命周期异构物理基础架构。该工具与架构无关(例如 x86 和 Arm)，与硬件无关(OEM、ODM 等)。因为它在硬件层实现了自动化，Tinkerbell 也不知道运行在它上面的软件是什么；Linux、VMware 和 Windows 生态系统同样具有可寻址性。

通过 Tinkerbell，Packet 希望将类似云的体验带到更多环境中。“我们开源 Tinkerbell 的目标是确保用户可以利用自动化裸机作为他们的多、混合和私有云计划的基础，无论这看起来像什么或基础设施位于何处，”Goulding 说。“这种能力传统上只属于最大的公司，所以我们认为向社区开放这种能力将激发许多新的思维。”

Packet 方法的核心是相信基础设施和软件正变得更加多样化。“大多数企业在越来越多的地方利用各种各样的基础设施，包括内部、边缘、区域托管和云中，”Goulding 说。“随着 DevOps 的兴起，无论是企业数据中心的戴尔服务器还是工厂车间基于 Arm 的物联网设备，该基础架构的一致性都至关重要。”

Goulding 说，在没有配置引擎的情况下配置服务器和网络设备是一个缓慢的手动过程，他花了近 20 年的时间来大规模构建基础设施和软件。Goulding 说:“除非你决定拥抱一个单一的供应商，比如在一个超融合模型中，否则你几乎不可能像对待云一样对待物理基础设施。”“除了基本配置之外，调整固件等元素、应用英特尔的微码更新、取消配置时擦除驱动器、检查 BIOS，甚至只是测试新内核，都会非常繁重。”

Packet 与 Tinkerbell 的目标是允许更多的用户以代码的形式与不同的物理基础设施进行交互，从而提供一个零锁定的基础设施基础。有了可扩展的裸机作为基础，组织可以在硬件中采用新的先进技术，同时利用开源和其他软件替代方案(如谷歌保罗·马森在 IFX 的主题演讲中提到的[谷歌 Anthos](https://cloud.google.com/anthos/) )来安全地在云和内部甚至边缘基础设施之间转移工作负载。

“例如，像迪士尼这样的公司可能会说‘我想超越亚马逊，创建流媒体电影的主导平台，但为了做到这一点，我需要在全球范围内部署和运营非常具体的基础设施，’”古尔丁说。“开源软件和标准已经使这在云中成为可能，但在其他环境中，缺少的环节通常在物理服务器或网络交换层。这就是我们认为 Tinkerbell 可以提供帮助的地方，也是我们很高兴加入开源社区并做出贡献的原因。”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>