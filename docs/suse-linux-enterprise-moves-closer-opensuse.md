# SUSE 调和了 openSUSE 和 SUSE Linux Enterprise

> 原文：<https://thenewstack.io/suse-linux-enterprise-moves-closer-opensuse/>

历史最悠久的 Linux 公司 SUSE 面临着严峻的挑战。

Canonical 有 Ubuntu，任何人都可以在服务器和云上运行，而无需支付一分钱，并且很容易成为 Canonical 的商业支持客户。 [Red Hat](https://www.openshift.com/) 有 CentOS，它与 Red Hat Enterprise Linux 二进制兼容，通过一些工作，确实允许客户从 CentOS“迁移”到 RHEL。

[SUSE](https://www.suse.com/) ，另一方面，有一个巨大的社区驱动的 [openSUSE](https://www.opensuse.org/) 项目，但它不能像竞争对手利用他们自己的项目那样利用它。SUSE 为其商业软件包和 openSUSE 之间的脱节付出了巨大的代价。虽然 SUSE Linux Enterprise (SLE)在欧洲市场占有一席之地，但它在云和数据中心的市场份额不如 CentOS 和 Ubuntu。公司不想使用 openSUSE，因为如果他们需要商业支持，没有明确的途径。开发人员不把 openSUSE 作为目标，因为没有明确的企业工作负载路径。

沉睡的巨人正在苏醒。随着 SUSE 在 2015 年收购了该公司的【Micro Focus 的领导下变得财务稳定，该公司已经开始发展其技术。

2015 年，openSUSE project 对其发行版进行了重组，创建了两个发行版: [Leap](https://en.opensuse.org/Portal:Leap) 和 [Tumbleweed](https://en.opensuse.org/Portal:Tumbleweed) 。风滚草，充分测试滚动释放，成为 SLE 的上游；作为回报，Leap 以 SLE 为基础，并逐步实现与 SLE 的完全兼容。

2016 年，SUSE 宣布推出 SUSE CaaS(容器即服务)平台，以处理容器化的工作负载。2017 年，该公司发布了名为 Kubic 的 [SUSE CaaS 平台的完全开源社区驱动版本。](https://www.suse.com/releasenotes/x86_64/SUSE-CAASP/1.0/)

2018 年对 SUSE 来说意味着什么？SUSE Linux Enterprise 产品管理总监 Matthias Eckermann 表示:“SUSE Linux Enterprise 产品系列在过去几年中有了显著增长。”他指出，该公司还为[高可用性运营](https://www.suse.com/products/highavailability/)、[高性能计算](https://www.suse.com/products/server/hpc/)、[桌面计算](https://www.suse.com/products/desktop/)和 [SAP 部署](https://www.suse.com/products/sles-for-sap/)提供了专门的发行版。

> 这意味着使用 CentOS 或 Ubuntu 来削减成本的公司有了 SUSE world 的另一个企业级选项。

由于这些产品共享相同的代码库，SLE 变得非常模块化，以迎合不同的用例。埃克曼说:“不同的软件包组生命周期是必要的，以便能够满足客户对开源技术的需求，开源技术的发展速度比企业发行版的通常生命周期更快，客户和合作伙伴的需求与其说是长期支持，不如说是相对较新版本技术的支持解决方案。”。快速移动技术的例子包括 PHP、Node.js 甚至 GCC Gnu 编译器集合。

但是 SUSE 需要一种更好的方法来统一这种模块化。“首先为每个产品提供一个安装 ISO 看起来是正确的。然而，考虑到 90%或更多的[变种]是相同的，我们想知道是否有更好的方法来包装我们的产品，”埃克曼说。

SUSE 通过一个统一的安装程序使客户更容易使用这些产品。当 SLE 15 将于 2018 年发布时，它将有一个统一的安装程序，允许客户安装他们想要的任何 SLE 产品，而不是提供不同的独立产品。

“有了统一的安装程序与模块化相结合，我们将能够比过去更快地响应未来的市场需求，并提高可用性，”埃克曼补充说。

随着 SUSE 向模块化和统一安装程序发展，他们必须克服一些挑战。最大的挑战是模块间的依赖性。包级别上存在依赖关系，这种依赖关系跨越一个或多个模块。SUSE 试图在两个层面上规避这个问题。在技术层面，它通过沿着逻辑边界定义模块来解决这个问题。在用户层面，与以前的 SUSE Linux Enterprise 版本相比，通过提高模块的可用性解决了这个问题。

SUSE 的软件包和补丁管理堆栈 ZYpp 现在实现了跨所有模块的统一视图，并提供搜索和查找等可发现性功能，允许用户跨模块工作。今后，这还将包括 [SUSE 软件包中心](https://packagehub.suse.com/)(一个面向 SLE 客户的社区维护的软件包商店)，以便客户和合作伙伴在需要时可以在社区支持下直接添加软件包。

## 给苏斯一美分？

2018 年还有一个更大的故事在等着我们。由于 openSUSE Leap 基于 SLE，LEAP 15 将推动 SUSE 生态系统向类似 Ubuntu 的体验发展。

openSUSE 董事长 Richard Brown 在一次采访中告诉我们，通过 LEAP 15，客户将能够在 SLE 15 和 LEAP 15 之间移动。2018 年，当 SLE 15 和 openSUSE LEAP 15 发布时，付费客户将能够免费迁移到 LEAP 15，它将完全兼容 SLE。同时，LEAP 15 用户将能够迁移到 SLE 15。

这意味着使用 CentOS 或 Ubuntu 来削减成本的公司有了 SUSE world 的另一个企业级选项。用户现在可以在云上的虚拟机中运行数千个 LEAP 实例，无论是 Azure、AWS 还是本地服务器。像 Linode 和 Digital Ocean 这样的虚拟主机公司或 VPS 提供商现在可以使用 LEAP。如果您需要商业支持，您可以非常轻松地将工作负载转移到 SLE。或者，如果您认为您拥有管理 SLE 部署的内部技能，您可以迁移到 openSUSE LEAP。

但是从 CentOS 到 RHEL 的迁移有多大的不同呢？难度有多大？一点都没有。LEAP 和 SLE 都是由风滚草建造的。两者共享相同的代码库。SLE 实际上是 openSUSE 社区代码的子集，所以从技术上讲，从 SUSE Linux Enterprise 到 openSUSE LEAP 应该没有问题。“SUSE 将正式支持就地迁移选项(双向！)通过其更新堆栈和 SUSE 客户中心，”埃克曼说。

因为在 SLE 中没有不在 Tumbleweed 中的东西，所以从 SLE 到 LEAP 没有问题。然而，当用户从 LEAP 转移到 SLE 时，可能会有一些小问题，因为 openSUSE 社区有许多以消费者为中心的包，这些包可能不会在企业空间中使用。从 openSUSE 到 SUSE Linux Enterprise，客户可能会遇到丢失的包，但更新堆栈会对所有看起来可疑的东西发出红色警告。

然而，由于模块化，SUSE 正在慢慢接近填补社区中可用的和企业发行版支持的差距。最重要的是，SLE 有 SUSE Package Hub，它通过 OBS(开放构建服务)获取包，OBS 为 openSUSE 用户服务。Brown 认为，由于它是开源的和社区驱动的，所以为 Package Hub 获得一个包是非常容易的。

有人可能想知道，如果 SLE 和 LEAP 都兼容，是什么阻止了 SUSE 采用 Ubuntu 模型？独立。布朗讨厌只有一种产品同时服务于社区和商业客户的想法。当社区项目和商业产品没有区别的时候，谁买单谁做主。openSUSE 虽然由 SUSE 赞助，但却是一个相对独立的社区。

“社区可以决定我们在 openSUSE 中想要什么。是的，我们的目标是提高与 SLE 的兼容性，以帮助我们的客户，但有些事情我们是按照自己的方式来做的。很高兴看到 SUSE 接受我们的做事方式，而不是相反，我们希望保持这种方式，”Brown 说。“我们对单一产品不感兴趣，我们感兴趣的是风滚草、SLE 和 LEAP 之间的共生关系。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>