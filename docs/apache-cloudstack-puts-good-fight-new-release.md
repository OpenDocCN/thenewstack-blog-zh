# Apache CloudStack 凭借新版本打了一场漂亮仗

> 原文：<https://thenewstack.io/apache-cloudstack-puts-good-fight-new-release/>

Apache Software Foundation 发布了 Apache CloudStack 的[4.6 版本，该版本被称为“刚刚工作”的云编排平台。](https://blogs.apache.org/foundation/entry/the_apache_software_foundation_announces84)

该项目的副总裁 Sebastien Goasguen 表示，由于新的工作流程使生产就绪的发布分支始终可用，发布将会更快。

除了 200 多个错误修复， [CloudStack v4.6 还反映了许多增强功能](http://docs.cloudstack.apache.org/projects/cloudstack-release-notes/en/4.6.0/index.html):

*   NuageVsp 网络插件
*   与 Globo DNSAPI 绑定集成
*   SAML 2.0 插件
*   KVM 托管存储
*   改进的 CloudByte 存储插件
*   使用 SSH 向虚拟路由器发送命令
*   裸机高级网络支持

CloudStack 支持三个 hypervisor 家族，带 XAPI 的 XenServer，KVM，VMware 的 vSphere 以及裸机主机 RHEL 或 CentOS，v6.2 或 6.3；Fedora 17 和 Ubuntu 12.04。

CouldStack 与 OpenStack 竞争，在很大程度上有被它掩盖的风险。但它有一系列的客户，包括一些大学，如帝国理工学院、墨尔本大学、科隆大学和圣保罗大学。一些电信公司喜欢这款软件，包括 BT Cloud、中国电信、韩国电信，以及 CloudOps、DataCentrix、Datapipe、EVRY、Exaserve、Exoscale 和 IDC Frontier 等服务提供商。

该软件最初由 Cloud.com 开发，Citrix 于 2011 年收购了该公司。Citrix 在 2012 年将该项目移交给了 Apache Software Foundation，今年 4 月，Citrix 宣布它已签约成为 OpenStack 的企业赞助商。OpenStack 也得到惠普、IBM 和 Red Hat 的支持

思杰开源解决方案总监 Mark Hinkle 当时表示,[将继续支持 CloudStack](http://searchcloudcomputing.techtarget.com/news/4500245475/Apache-CloudStack-marches-on-in-OpenStacks-shadow) 及其商业衍生产品思杰 CloudPlatform。

他称这个项目更像是用户驱动的，而不是厂商驱动的——“那些(用户)的声音不像销售 OpenStack 解决方案的人那样响亮。”

当被问及 CloudStack 的定位时，Apache CloudStack 项目管理委员会的 Giles Sirett 回答道:

“Cloudstack 的优势在于它易于部署、经验证且可扩展性强。它有一个严格定义的范围。

“越来越多的服务提供商希望大规模运行 IaaS 环境，而其他组织则希望获得自动化基础架构的优势，同时避免其他技术所带来的时间和成本影响，因此使用这种技术。”

CloudOps 首席执行官 Ian Rae 表示，CloudOps 是一家总部位于蒙特利尔的托管云服务提供商，同时支持 CloudStack 和 OpenStack，但与虚拟机管理程序领域类似，一种解决方案无法满足所有需求。

OpenStack 主要在私有云市场中找到了一席之地，在以成本为中心的企业中与专有的基于 VMware 的虚拟化竞争。他说，对于以利润为中心的服务提供商来说，OpenStack 并不十分成功，他们在很大程度上与构建和运行基于 OpenStack 的云的运营成本和复杂性作斗争。

他说，CloudStack 通常用于构建公共云服务，主要用于区域云，受到许多大规模运营并希望控制成本的软件公司的欢迎，特别是在服务提供商(SaaS 和 IaaS)中，因为它的构建和运行更简单、更便宜。

虽然有更多的 OpenStack 云，但平均而言，CloudStack 云更大，有数万个节点。

“我们看到大量资金投入 OpenStack，这推动了一个充满活力但有些不稳定的生态系统。另一方面，我们看到 CloudStack 产生了更多的钱，但投资却少得多，生态系统虽然小但稳定，”他说。

他说，在技术方面，OpenStack 有一个分布式系统架构，有几十个项目，你可以选择加入或退出。CloudStack 更像是一个分立的产品，它是一个非常完整和紧密集成的产品，但不太容易适应高度定制的用例。

虽然供应商营销使 OpenStack 成为新闻，但 CloudStack 没有营销，并有可能淡出人们的视线。

“我们听说了采用亚马逊、OpenStack 和微软 Azure 的故事。我们很少听说 CloudStack。Kusnetzky Group 的分析师 Dan Kusnetzky 表示:“上一次提到 CloudStack 的采访是在很久以前，至少是一年前。”Kusnetzky Group 不收集市场份额数据，但会与公司的决策者和供应商代表交谈。

“尽管人们可能对这套软件很感兴趣，但我们没有听说过。”

451 Research 的云管理和容器研究经理杰伊·莱曼(Jay Lyman)表示，CloudStack 是 OpenStack 和其他 IaaS 软件的一个可行竞争对手，但随着 OpenStack 的不断成熟和发展，以及亚马逊网络服务和微软 Azure 等非开源公共云的发展，它越来越不受欢迎。

“作为面向企业和服务提供商的云，CloudStack 在许多方面更加成熟、稳定、简单，并且经过了实战考验。然而，我们看到许多组织选择 OpenStack，主要是因为它在开发运维、微服务、移动性和物联网等领域的基本 IaaS 和管理之外的可扩展性，”他说。

*特征图片:* [的](https://www.flickr.com/photos/theaucitron/)[云](https://www.flickr.com/photos/theaucitron/5810163712/in/photolist-9RqBfq-4nvqBz-36sady-7QqEwB-6TBJ8p-eANnTu-p8EBZ2-b6wkkP-7u8sVQ-rEqdKA-wcmDY1-xsLNAU-dbvGNY-oqJqTF-hw4AVc-vk7iEV-yqcg-bzm3vU-9Acp78-p2ZZVZ-5XvvXP-aEheUm-6Xw3vL-oWUqFs-Nx311-oNpBfa-24QLTr-5KM8Ar-p5Siki-6Xs2nz-jtMME6-nXRyaB-2xqic-qAXchw-nmNiF8-74EY4b-7oFU8a-qn52Gu-8MgvTK-qPhha9-foWSfm-8zgx3R-vmqAnC-ehc216-35YkUG-dbvGB6-5Fjyi2-4nXkbg-8yGj8R-uTiMZr)在 **CC BY-SA 2.0** 下授权的、*。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>