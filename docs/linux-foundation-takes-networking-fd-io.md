# Linux 基金会在 FD.io 的努力下开始联网

> 原文：<https://thenewstack.io/linux-foundation-takes-networking-fd-io/>

Linux 基金会专注于通过其最新的合作项目解决网络挑战，该项目名为 [FD.io](https://fd.io/) (“快速数据”或 Fido)。该小组将致力于为下一波网络和存储软件创建一个 IO 服务框架。

“在过去的 5 到 10 年里，我们已经看到了开源项目在推进流程编排和网络控制器功能方面的发展，如 OpenDaylight 项目、NFV 开放平台(OPNFV)和开放网络操作系统(ONOS)。但需要一个开放的数据 I/O 框架来提供动态数据平面服务，而这正是 FD.io 准备满足的需求，”该基金会战略项目副总裁 Mike Dolan 说。

该项目的创始成员包括 6WIND、Brocade、Cavium、Cisco、Comcast、爱立信、华为、Inocybe Technologies、Intel、Mesosphere、Metaswitch Networks(Project Calico)、PLUMgrid 和 Red Hat。

FD.io 提供模块化、可扩展的用户空间 io 服务框架，支持快速开发高吞吐量、低延迟和资源高效的 IO 服务。它被设计成与硬件、内核和部署(裸机、虚拟机、容器)无关。

FD.io 由一系列子项目组成，共同形成一个更有凝聚力的代码库。以这种方式构建项目可以实现真正开放的基于社区的开发，并带来更高水平的创新。Dolan 说，通过这种方式，FD.io 社区将能够专注于组件能力和互操作性，这最终会带来更多的用户选择和采用水平。

该项目的初始代码来自思科的虚拟交换模块——矢量数据包处理(VPP)。在[的独立测试](http://img.lightreading.com/downloads/Cisco-Validating-NFV-Infrastructure-Pt1-and-2-SH-Edits.pdf)中，欧洲高级网络测试中心 AG (EANTC)报告称，VPP 比基于 DPDK 的开源 Open vSwitch (OVS)“更加一致和可靠”。

它运行在多种架构的用户空间中，包括 x86 服务器和嵌入式设备上的 x86、ARM 和 Power 架构。它从网络 IO 层读取最大的可用数据包向量，然后通过处理图处理数据包向量。

FD.io 网站解释说，VPP 不是一次处理一个包，而是在继续前进到下一个图节点之前，通过一个图节点处理包的整个向量。

它把这个过程比作一堆木材，每块木材都需要切割、打磨和钻孔。更快的方法是完成所有的切割、打磨和钻孔，然后为每块木板选择不同的工具。

FD.io 的初始版本可供下载。它包括一个完整的构建、工具、调试和开发环境；一个 OpenDaylight 管理代理和一个 Honeycomb 代理，用于展示 netconf/yang 模型的数据平面功能，以简化与 OpenDaylight 和其他 SDN 技术的集成。

未来，FD.io 成员希望在防火墙、负载平衡、LISP(定位器/ID 分离协议)、主机堆栈、硬件加速器集成、通过附加管理代理的附加 SDN 协议支持以及其他针对网络和存储流量的关键 io 服务等领域开展工作。

该基金会还宣布了一个持续性能实验室(CPL)作为 FD.io 的一部分，为代码功能和性能的持续验证提供一个完全自动化的测试基础架构框架**。**不同的供应商捐赠了不同的硬件来运行 FD.io 上的性能测试。

这只是来自 Linux 基金会的最新合作项目，该基金会此前推出了[开放 API 倡议](https://thenewstack.io/linux-foundation-sets-stage-easier-sharing-apis/)、Node.js 基金会、云原生计算基金会、[开放大型机项目](https://thenewstack.io/new-linux-collaborative-projects-open-mainframes-universal-io-and-bare-metal-storage/)、IO Visor 项目和 Kinetic 开放存储项目等。

思科、英特尔和红帽是这一新体系的赞助商。

特征图片:[丁卡瑞](https://www.flickr.com/photos/126049139@N03/)的[繁忙交通](https://www.flickr.com/photos/126049139@N03/14432016947/in/photolist-nZiRQp-akn6Nn-oXLXMt-4jvLJD-3eM8td-e5z7Kc-pzc94x-48ofEh-4yWcR5-grVMFM-5eGQeG-ec84tZ-5tdngD-rssoHs-tp8oVr-csLtm5-4coPYG-tiTNk-5x1r1h-6zYZWL-743C4K-h2x1uB-qpWJ4h-5VNqMA-pGdgtS-9Y5Wd5-dCCZrY-92fjHV-asz9FY-dZrHav-MWufN-sCkGxQ-akY1L6-qUibQ8-4jvLuV-3dSkhj-d7ojES-8GhDpe-9Wfv7h-i87i1-toRcdY-3rwfx-9h5hQ-5mPPyf-4URyqA-9pn6xx-9qdw4t-9HKPiG-7YFVPG-dU3WFx)，在 **CC BY-SA 2.0** 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>