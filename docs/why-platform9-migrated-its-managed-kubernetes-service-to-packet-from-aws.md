# 为什么 Platform9 将其托管的 Kubernetes 服务从 AWS 迁移到 Packet

> 原文：<https://thenewstack.io/why-platform9-migrated-its-managed-kubernetes-service-to-packet-from-aws/>

编者按:TNS 出版商亚历克斯·威廉姆斯对本文有贡献。

有一个核心经济理论叫做“规模经济”一个组织越大，它生产小部件的成本就越低，这意味着它可以在价格上削弱较小的竞争对手。

然而，在构建云应用的背景下，托管的 Kubernetes 提供商 [Platform9](https://platform9.com/) 发现这个基本的经济解释并不成立。2017 年，受管理的 Kubernetes 供应商开始脱离[亚马逊网络服务](https://aws.amazon.com/)，转而从小得多的[包](https://www.packet.com/)中购买裸机。最大的动力是成本。

## **成本的重要性**

无论是存储的[成本](/wasting-money-on-public-cloud-storage/)、运行 Kubernetes 的[成本](/replex-sheds-light-on-kubernetes-costs/)还是无服务器的[成本](/how-to-avoid-cost-pitfalls-by-monitoring-apis-in-aws-lambda/)，云成本几乎是所有在公共云中运行的公司的主要关注点，尤其是像 Platform9 这样的托管服务提供商。AWS 的成本结构也非常复杂。

“我们对 AWS 作为产品和服务感到满意。Platform9 首席执行官 Sirish Raghuram 解释说:“AWS 的主要问题是成本。“有无数的杠杆可以用来优化成本，我们花了太多的时间来管理和优化成本。”Platform9 达到了一个不可避免的投资点:要么以控制 AWS 成本的方式，要么转向另一个可以降低成本的解决方案。

鉴于 Platform9 有另外两个令人信服的理由放弃 AWS，投资一个能带来长期低成本的解决方案似乎是最好的选择。

众所周知，许多公司，尤其是零售商，将 AWS 视为死敌。Platform9 的潜在客户表示，他们无法使用 AWS 上托管的任何服务。转向非亚马逊解决方案意味着 Platform9 可以与这些客户合作。

放弃 AWS IaaS 产品的第三个原因是让 Platform9 使用自己的平台。这对于客户来说并不明显，但是给了 Platform9 团队使用他们自己的产品的满足感，并且感觉他们真的在“行走”为了实现这一点，Platform9 需要转向裸机。

### **为什么分封？**

基础设施服务提供商 Packet 是一家相对较小的裸机提供商，主要与拥有 100 至 500 名员工的初创公司合作。根据 Packet 收入营销总监[克里斯·赖特](https://www.packet.com/about/team/chris-wright/)的说法，Packet 的主要价值主张之一是降低基础设施成本:“我们往往从这些超高速增长的初创公司那里听到他们的公司每年增长 2 到 3 倍，但他们的云基础设施成本增长了 5 到 10 倍。”

事实上，AWS 确实有一项裸机服务，可以让 Platform9 整合自己的平台——但据 Platform9 的技术总监科迪·希尔(Cody Hill)称，这项服务的成本是 Packet 同类硬件的两倍多。

数据包并不是平台考虑的唯一选择。2017 年末，当项目开始时，让 Packet 与众不同的是一切的 API 驱动性质。“我们可以利用他们的 API 来访问裸机基础设施，并使用我们的产品来提供云服务，”Raghuram 解释道。

> “有无数的杠杆可以用来优化成本，我们花了太多的时间来管理和优化成本。”西里什·拉古拉姆。

“你不必放入服务票，你不必等待，”希尔解释说。从配置网络到获取 IP 地址，一切都是自动化完成的。有了 Packet 作为可编程基础设施层，Platform9 作为云服务，该团队拥有了 AWS 的完整替代方案。

嗯，差不多了。

在不同环境之间进行迁移——尤其是在考虑生产客户和 SLA 的情况下——总是一项复杂的任务。只有一个令人不快的惊喜:存储。AWS 有一个完整的解决方案，包括强大的(虽然有时很贵)存储选项。随着平台 9 和数据包的结合，存储是唯一缺少的东西。

用 Raghuram 的话说，Packet 使用的第一个第三方存储解决方案平台 9 是“火车残骸”挑战不仅仅在于存储解决方案，还在于将一切整合在一起——现在有三个移动部分，而不是一个，并且三者之间的集成并不总是完美的。

在转变之初，Platform9 使用蓝绿色部署模式从 Amazon 转移到 Packet。起初，只有基于虚拟机的工作负载被转移，而 RDS 数据库留在 Amazon 上，这意味着 Platform9 必须连接 Amazon 和数据包工作负载，以使虚拟机能够访问数据库。

Platform9 已经转移到托管数据库，不再使用 RDS。事实上，Platform9 现在只使用 AWS 进行灾难恢复，以防 Packet 完全离线——主要站点根本不使用亚马逊的服务。

### **外卖**

自从转向分组业务以来，Platform9 还签下了一家将亚马逊视为竞争对手的大客户。Raghuram 相信，如果 Platform9 仍然在 AWS 上，该合同就不会发生。

从基础设施到基础设施的角度来看，与 AWS 相比，Platform9 节省了约 63%的成本。这个数字没有考虑到管理集成所需的一些额外投资，但即使考虑到增加的工程人员，节省仍在 45%左右。

“我想说，数据库服务和存储服务是我们努力争取的两个领域，最终不得不投入相当多的时间来找到替代品，”Raghuram 说。这些是他希望看到其他公司介入的领域，提供最后一块拼图，使其在未来更容易取代亚马逊的全套解决方案。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>