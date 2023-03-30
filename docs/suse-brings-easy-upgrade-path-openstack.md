# SUSE 现在为 OpenStack 提供无中断升级

> 原文：<https://thenewstack.io/suse-brings-easy-upgrade-path-openstack/>

SUSE 刚刚使该公司的 OpenStack 发行版 SUSE OpenStack Cloud 6 (SOC 6)的升级变得更加容易。

“如果企业客户希望迁移到新版本的 OpenStack，他们不必更换和重建；他们现在可以从旧版本的 OpenStack cloud 正常升级到新版本，”SUSE 首席执行官 Nils Brauckmann 说。“这意味着他们可以轻松地利用 OpenStack 创新。”

企业进一步采用 OpenStack 的一大症结是升级过程，这是一项繁重的工作。Brauckmann 说，在这个版本中，“SUSE 是第一个也是唯一一个提供不间断升级到新版本的提供商，从 SUSE OpenStack Cloud 6 开始。”

该版本基于 OpenStack Liberty，构建于 SUSE Linux Enterprise(SLE)Server 12 SP1(顶级 SLE 的最新版本)之上。这意味着 SUSE 可以为整个堆栈提供支持，包括主机 Linux 和客户操作系统。

SUSE 已经为这个版本工作了一段时间，去年发布了一个测试版。该公司经历了一些紧缩，尽管在 2014 年被微焦点收购后[，SUSE 一直在恢复实力；Brauckmann 说，该公司现在正在大力投资创新，这反映在 OpenStack 等产品上。](http://www.pcworld.com/article/2684352/micro-focus-buying-novell-suse-linux-owner-for-12-billion.html)

在此版本中，SUSE 为未来的 OpenStack 版本带来了无中断升级功能。该公司还致力于更面向业务的发布周期，以简化迁移过程，减少对生产环境的干扰。

SUSE 云基础设施高级产品经理 Pete Chadwick 写道:“现在，客户正在将 OpenStack 用于越来越多的生产工作负载，满足企业 SLAs 服务水平协议]成为一个重要的考虑因素。

Chadwick 解释说，SUSE 通常优先考虑构建部署框架，以最大限度地延长正常运行时间，并最大限度地减少迁移和升级周期中的中断。该公司在其 Linux 发行版 SUSE Linux Enterprise Server 中内置了高可用性扩展和实时内核补丁功能。

Chadwick 说，SUSE OpenStack Cloud 6 利用了这些关键的高可用性功能，并提供了支持未来版本无中断升级的架构。

但是在 OpenStack 中升级有真正的挑战吗？来自 OpenStack 基金会的[非常受欢迎的视频](https://www.youtube.com/watch?v=SnpeXLKfxco)怎么样，显示工程师在 10 分钟内升级 OpenStack 系统。的确，根据组织、基础架构和其他因素的不同，所有更新都不尽相同。

当我与 SUSE 全球产品和解决方案经理查德威克和马克·史密斯谈到 OpenStack 升级的现有挑战时，他们指出:视频中的升级展示了一个专为单一客户环境设计的流程。

SUSE 经理解释说，与单一客户 OpenStack 环境相反，SUSE 需要定义一个可用于更广泛的客户部署场景的流程，其中包括 OpenStack、合作伙伴驱动程序以及底层操作系统和虚拟机管理程序。

他们还指出，该视频并不是真正无干扰的；OpenStack 控制面板的停机时间(最短)。

“OpenStack 在部署、配置和利用方面具有很大的灵活性。在预定义的场景中可以做出许多配置假设，但这些假设在现实安装中并不适用。

一个可以更新单个定义良好的 OpenStack 安装的流程与为我们的客户解决升级问题的流程之间存在巨大差异，”Smith 说。

除此之外，10 分钟的升级视频不包括 Neutron、OpenStack 网络组件。当有虚拟机网络流量通过 Neutron 运行时，关闭 Neutron 等同于关闭数据平面。在这种情况下，OpenStack 控件和数据平面都需要脱机才能升级 OpenStack 实例。

“由于大多数客户都在使用 Neutron，无中断升级必须消除停机时间，即使是控制面板也是如此，”Smith 说。

的确，有人可能会说，无法启动或停止虚拟机 10 分钟并不是一个大问题。然而，任何停机时间都可能随着云的规模而增加。SUSE 的经理指出，如果这个时间大幅增加，比如说 30 分钟，对大多数客户来说可能是个问题。

Smith 指出，即使控制平面中断 10 分钟，也存在这样的风险，即如果发生变化，即服务器停机，调度程序通信的缺失将导致即时问题。因此，工作负载不会迁移，或者在控制平面重启后可能会出现其他问题，例如 NOVA 将工作负载调度到离线的服务器。

通过良好的设计可以消除服务停机，但是将节点(虚拟或物理)从控制群集中取出并正常放回是一项挑战。随着工作负载开始利用 Heat 和 Ceilometer 等高级协调功能，这些挑战可能会变得更加复杂。

更复杂的升级场景也需要超越 OpenStack 层。它需要包括升级部署框架，以便用户可以继续使用部署工具来进一步更改他们的设置。数据平面还有一个额外的挑战升级计算节点上的操作系统和虚拟机管理程序带来了确保数据平面持续完整性的新挑战。

根据 Smith 和 Chadwick 的说法，SUSE 在升级过程中解决了以下一些问题:

控制平面:在不中断虚拟机运行或防止控制平面状态丢失的情况下升级服务。

数据平面(或计算集群):实时迁移虚拟机，以疏散计算节点，从而全面升级整个计算体系，包括操作系统、虚拟机管理程序和 OpenStack 组件。

数据库:模式更新和数据迁移。

部署框架:部署框架包含物理集群的状态，包括部署服务的位置。这需要升级以包括新的 OpenStack 服务。与 OpenStack 数据库的迁移类似，这种升级必须在不丢失状态的情况下完成。在 SUSE OpenStack Cloud 6 中，对框架进行了更改，支持在不中断云的情况下升级框架。一旦升级了框架，它就会自动执行云的升级过程。

Chadwick 和 Smith 解释说，部署框架的目的是提供一个使用一组预定义的脚本和描述符文件安装 OpenStack 的结构化流程，该流程通过一个明确定义的可重复流程执行完整的部署。默认选项被假定为最小化选项，尽管该包仍然提供了处理各种场景的灵活性。

## 还有什么新鲜的？

SUSE OpenStack Cloud 6 现在支持针对计算节点的 IBM z/VM。SUSE 表示，这是对客户要求将他们的大型机整合到 OpenStack 云中的直接响应。在虚拟机管理程序方面，SUSE OpenStack Cloud 已经支持 KVM、Xen、Microsoft Hyper-V、VMware vCenter 以及现在的 IBM z/VM。

自从 SUSE OpenStack cloud 的第一个版本发布以来，SUSE 就一直支持 Linux 容器，在这个版本中，他们为 Docker 容器和工作负载添加了部署功能。

该公司还推出了新的基于网络的安装框架和基于角色的管理，以改善用户体验。它还支持云中的共享文件即服务，称为 Manila。

NetApp 云解决方案组高级总监 Jeff O'Neal 表示:“我们对在马尼拉支持下发布 SUSE OpenStack Cloud 6 感到非常兴奋。“作为马尼拉项目的创始人和 OpenStack 基金会的创始成员，我们贡献了深厚的专业知识和技术，将为我们的 Data ONTAP 客户实现公共云和私有云之间的共享卷，这是许多企业一直在寻求的功能，以加快他们的云采用。”

SUSE OpenStack 6 立即[可用](https://www.suse.com/products/suse-openstack-cloud/how-to-buy/)。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>