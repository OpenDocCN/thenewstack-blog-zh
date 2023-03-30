# 网络功能虚拟化的开源包

> 原文：<https://thenewstack.io/opensource-virtual-network-functions-part3/>

编者按:这是详细介绍网络功能虚拟化的系列文章的第三部分，虚拟化是一组新兴的网络层虚拟化技术。该系列的第一部分，NFV 介绍，可以找到

[here](https://thenewstack.io/de-ossify-the-network-with-function-virtualization/)

第二部分是

[here](https://thenewstack.io/opnfv-operationalizes-network-functions-virtualization/)

.

[](https://thenewstack.io/author/sridharrao/)

 [斯里达尔饶

斯里达尔于 2007 年获得新加坡国立大学计算机科学博士学位；2000 年获得印度苏拉特卡尔 KREC 大学计算机科学硕士学位；并于 1997 年 8 月在印度班加罗尔大学 Tumkur 获得仪器仪表和电子工程学士学位。他在 NEC 印度技术公司担任副总经理；印度 SRM 研究所研究负责人；意大利都灵理工大学微软创新中心博士后研究员；并在新加坡资讯通信研究所(I2R)担任研究员。他从事过各种开发和部署项目，涉及 ZigBee、WiFi 和 WiMax。斯里达尔目前在思必驰通信印度有限公司担任解决方案架构师。](https://thenewstack.io/author/sridharrao/) [](https://thenewstack.io/author/sridharrao/)

在我们的上一篇文章中，我们已经关注了[网络功能虚拟化](https://thenewstack.io/opnfv-operationalizes-network-functions-virtualization/) (OPNFV)的网络平台，主要涵盖了支持[网络功能虚拟化](https://thenewstack.io/de-ossify-the-network-with-function-virtualization/) (NFV)的虚拟基础设施和相应的管理器。在本文中，我们将重点关注可用于构建不同虚拟网络功能的开源选项。

虚拟化网络功能(VNF)是一种能够在 NFV 基础设施(NFVI)上运行并由 NFV 协调器(NFVO)和 VNF 管理器协调的网络功能。除了明确定义的功能行为之外，VNF 还应该支持到其他网络功能、VNF 管理器、其 EMS 和 NFVI 的明确定义的接口。

商用服务器和软件旨在取代的网络设备范围从防火墙和 VPN 网关到交换机和路由器。研究人员认为，几乎任何网络功能都可以虚拟化。

今天市场上的 NFV 焦点包括交换元件、网络设备、网络服务和应用。为 NFV 考虑的典型网络功能是交换元件、电信级 NAT 和路由器、移动网络(回程和接入)节点、家庭/小型办公室路由器中的功能、流量分析元件、IP 多媒体子系统(IMS)、应用级优化功能和安全功能。

## 虚拟 EPC 和 IP 多媒体系统

3GPP 是一个标准开发组织，为移动和融合网络定义网络架构和网络功能规范。LTE 从称为通用移动电信系统(UMTS)的早期 3GPP 系统演进而来，UMTS 又从全球移动通信系统(GSM)演进而来。

当今 LTE 移动网络最常用的架构称为[演进分组核心](http://searchtelecom.techtarget.com/definition/Evolved-Packet-Core-EPC) (EPC)，由 UE、演进通用陆地无线接入网(E-UTRAN)和 EPC 核心(LTE-ARCH = UE + EUTRAN + EPC)组成。E-UTRAN 包括被称为 E nodeb(enb)的基站。EPC 由四个网元组成，即服务网关(SGW)、PDN 网关(PGW)和移动性管理实体(MME) [x1]。移动网络中充斥着各种各样的专有硬件设备。

随着 NFV 和 SDN 在 EPC 中的引入，上面列出的一些组件变得虚拟化，并且在虚拟化元素之间引入了开放 API。

在下表中，我们从最小 EPC 开始，并在随后的行中向最小 EPC 添加越来越多的功能。最后一列显示了每种功能的 3GPP 架构组件:

IP 多媒体子系统(IMS)是用于传送 IP 多媒体服务的架构框架。

大量的开源项目实现了 EPC 架构的各种组件。下表列出了该软件。然而，可以理解的是，没有一个软件可以实现完整的 EPC。为了实现这一点，人们必须使用不同的软件，并开发使这些软件协同工作以实现 EPC 功能的“粘合剂”。

## 虚拟交换和路由

有两个最重要的网络功能是路由和交换。从 NFV 的角度来看，目标是通过在商用硬件上或作为虚拟机运行来支持 BGP & OSPF 等标准协议。下面，我们将寻找一些流行的用于交换和路由的开源软件。

### 切换:

**Linux Bridge** :基于软件交换机，实现了 IEEE 802.1D 标准，作为内核模块随 Linux 发行版一起提供。它包括对 FDB(转发数据库)、STP(生成树)、接收所有数据包的混杂模式以及流量过滤和整形的支持，这使它比硬件网桥更强大。

**OpenVswitch (OVS)** : OVS 可能是最受欢迎、使用最广泛的基于软件的开关。它支持 OpenFlow，也可以用作普通交换机。它包括各种功能，如 VLAN 标记、VXLAN、GRE、绑定、基于流的转发、用户空间控制平面等。

**Lagopus** :又一个 OpenFlow 1.3 投诉软件开关。与 OVS 类似，它也可以与英特尔 DPDK 配合使用。在他们的路线图中，他们计划集成其他控制平面程序，如 Quagga 和 GoBGP，我相信这在开放各种用例方面非常有用。

**Vale/Netmap** :与 Linux Bridge 和 OVS 类似，Vale 互连物理或虚拟网络接口。然而，与其他软件交换机相比，它拥有高性能(高吞吐量和低 CPU 使用率)和可扩展性。更好的性能是通过 netmap APIs 实现的，事实上，Vale 是作为 netmap 发行版的一部分提供的。

### 路由:

Quagga 是一个更小的守护进程的集合，每个守护进程都有一个特定的任务。该任务可能是运行像 OSPF 或 BGP 这样的路由协议。Zebra 守护进程负责与内核交互，并提供一个简单的 API(称为 Zserv)供其他守护进程使用，因此它们不需要直接进行内核调用。其他守护进程运行各自的协议。您可以配置 Quagga，以便所有这些守护程序从同一个地方获取它们的配置，或者单独配置每个守护程序。

BIRD 是布拉格查尔斯大学数学和物理学院的一个学校项目。目前，它由 CZ 开发和支持。NIC 实验室。BIRD 项目旨在开发一个全功能的动态 IP 路由守护进程，主要针对(但不限于)Linux、FreeBSD 和其他类似 UNIX 的系统，并在 GNU 通用公共许可证下发布。IPv4 和 IPv6(配置时使用–enable-IPv6)。它支持多路由表 BGP、RIP、OSPF、静态路由 IPv6 路由器广告等。

**VYoS** : VyOS 是一个基于 Linux 的网络操作系统，提供基于软件的路由功能。它包括 OSPF、BGP 等路由协议以及防火墙和 VPN 支持。VyOS 是 Vyatta 的一个社区分支，被 Brocade Communications 收购。

## 虚拟提供商网络元素(PNEs)

研究人员认为，尽管核心路由器的虚拟化不可行，至少在不久的将来，由于高性能(吞吐量)的要求，提供商边缘(PE)路由器的虚拟化将是一个更可行的选择。

虚拟化后，诸如 L3 IP VPNs(每个 PE 设备就像一组虚拟路由器)、L2 VPN、EVPN 和伪线等虚拟专用网络服务将支持这些功能的灵活性和可扩展性。这将是提供商的主要优势，许多提供商已经考虑通过在他们的云中执行相同的执行来虚拟化这种 PE 功能。

与 PE 路由器类似，宽带远程访问服务器(B-RAS)是提供商网络中的专用服务器，它有助于将多个互联网流量源(如 DSL、电缆、宽带无线和以太网)汇聚到一个网络上，该网络通常包括往返于 DSLAMs 的流量路由。它可以是将分组从核心转发到用户(反之亦然)的简单路由器，也可以是实现(每个用户)IP 策略、QoS、分组操作、限制器等的复杂路由器。BRAS 功能的虚拟化也证明对服务提供商是有益的——在成本和灵活性/可扩展性方面。

### 开源 PNEs

路由下面提到的大部分开源软件，如 Quagga、VyOS、BIRD，都可以用来实现很多 PE 功能。作为标准 Linux 发行版一部分的软件，如 IPtables T1(netfilter)和 T2 Radius 服务器 T3(freeRADIUS)可以分别用于虚拟防火墙和虚拟 AAA。在一些 NFV 部署中， **[snort](http://www.snort.org)** 软件已经用于虚拟入侵检测系统。

此外，其他软件如 **mpls-Linux** 和 **xl2tp-daemon** 也可以用来虚拟化 PE 功能。最近 AT & T 和爱立信联合推出了基于 SDN 的 L3VPN via OpenDaylight Controller。

### 虚拟 CPE

用户驻地设备(CPE)通常位于任何企业或住宅宽带用户的驻地，用于连接到服务提供商的网络。通常，服务提供商提供、配置和管理 CPE，这些 CPE 可能来自不同的硬件供应商、企业客户和住宅用户。

如果没有 CPE 的虚拟化，服务提供商可能会在采用任何新技术、添加新服务或升级安全性、隐私和计量功能时产生大量费用。

借助虚拟 CPE，大部分 CPE 功能将从客户驻地转移到运营商的网络中(可能在数据中心设施中)。这导致了“简化的”CPE，其中 CPE 充当连接到服务提供商网络的简单的第二层转发设备。通常是 DHCP、防火墙、NAT、路由、VPN 等服务。由作为虚拟机(VM)实例运行在提供商数据中心的虚拟网络功能(VNFs)提供。

### 开源 vCPE:

诸如 DHCP、防火墙、NAT、DNS (vDHCP、vFW、vNAT、vDNS)等网络服务在开源实现中可用，并且也作为许多标准 Linux 发行版的一部分分发。比如 DNS 和 DHCP 可以通过 **dnsMasq** 进行部署。鉴于 **IPtables** 用于实现 NAT 和防火墙，还没有一个单独的开源项目以 NFV 为目标，致力于构建虚拟 CPE，如客户路由器、虚拟机顶盒和虚拟家庭路由器。

## 虚拟接入网络元件

驻留在混合光纤 DSL“远程”节点中的接入网络功能，例如通常位于街道或建筑物中的 **FTTcab** 和 **FTTdp** ，正逐渐成为虚拟化的热门候选。为了在经济上可行，这些节点应该是紧凑的，具有非常低的功耗和非常低的维护成本。通过虚拟化某些功能来简化此类远程节点(首先是 OLT、DSLAM、ONU、ONT、MDU 和 DPU ),可以通过将复杂的处理转移到虚拟化环境来帮助实现经济可行性。虚拟化的目标网络功能是。不幸的是，这些虚拟功能都没有开源软件。主要的电信公司，如 AT & T，正在致力于虚拟化这些功能，希望他们在不久的将来也能开源，所以祈祷好运吧！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>