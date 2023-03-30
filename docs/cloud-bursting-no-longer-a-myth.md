# 云爆:不再是神话

> 原文：<https://thenewstack.io/cloud-bursting-no-longer-a-myth/>

[](https://www.linkedin.com/in/kltownsend/)

 [基思·汤森

Keith Townsend 是 CTO Advisor LLC 的负责人，拥有 20 多年设计、实施和管理数据中心技术的相关经验。他的专业领域包括为财富 500 强企业提供虚拟化、网络和存储解决方案。](https://www.linkedin.com/in/kltownsend/) [](https://www.linkedin.com/in/kltownsend/)

多年来，使用公共云作为数据中心容量溢出的概念仍然停留在理论上。由于新冠肺炎，2020 年被证明是云爆发的一年。

[据微软](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/30/2-years-digital-transformation-2-months/)称，疫情让他们的许多客户将两年的数字化转型压缩到了两个月。世界目睹了服务提供方式的巨大变化。总的来说，我们的数字体验已经改变。曾经被认为只是亲身体验的服务，现在有了虚拟互动。神秘的云爆发用例为这种能力提供了部分动力。云爆发的概念是，当应用达到私有数据中心的容量限制时，运营商可以通过公共云扩展容量。

有一些关于通过在现有 IT 运营中采用公共云来提高敏捷性和能力的引人注目的故事。没有比远程学习和远程工作领域更好的例子了。出于需要，这些方法的采用在 2020 年加速。

2021 年初，是回顾快速采用云技术的影响以及这种采用对混合基础架构运营的影响的好时机。

## 2020 年是虚拟桌面基础架构之年吗？

疫情迫使公司加快或采用以前不存在的工作场所政策。 [VMware 最近宣布](https://www.vmware.com/company/news/updates/2020/envisioning-future-of-work.html)在家工作是如此受欢迎和有效，以至于该公司现在允许其所有 33，000 名有能力这样做的员工继续在家工作。VMware 表示，“COVID 带来了全新的视角”。然而，支持这种转移的技术能力需要在短时间内付出大量努力。

“[插入年份]是虚拟桌面基础架构(VDI)之年”一直是企业 IT 基础架构专业人士的一个笑话，因为 Citrix 在多年前就已经成熟了该平台。这些年来，我已经部署了几个 VDI 环境。在评估支持 VDI 的基础架构时，我会寻找一些标准功能。下面是一个简化的列表:

1.  承载应用程序/桌面映像的服务器容量。
2.  支持目标用户数量的互联网带宽。
3.  用于访问 VDI 会话的软件许可。
4.  VDI 实例相对于所访问数据的位置。

当扩展 VDI 环境以满足不断增长的需求时，我会考虑所列资源的采购时间。在传统的 IT 环境中，我考虑的时间框架是几个月，而不是公共云的几天甚至几分钟。

那么，如果您是英特尔的首席信息官，并且您的 IT 组织必须[将 100，000 多名](https://itpeernetwork.intel.com/how-intel-it-transitioned-to-supporting-100000-remote-workers/#gs.q0bs3m?cid=spon&campid=2021_q1_dcg_us_dcgitt3_dcghc_KT-DCS-2&content=)知识型员工转移到远程访问，您会怎么做？采购足够的硬件来提供 VPN 容量是一个困难的挑战，更不用说提供带宽了。因此，[英特尔转向公有云](https://www.intel.com/content/www/us/en/it-management/intel-it-best-practices/instant-vpn-scaling-during-crisis-paper.html?cid=spon&campid=2021_q1_dcg_us_dcgitt3_dcghc_KT-DCS-1&content=)及其网络技术来快速扩展 VPN。

## 职业启动器

教育是 2020 年的另一大变革领域。世界各地的学校系统从现场学习转向了远程学习。当你需要在同一个平台上从 1500 名成人学生发展到超过 15 万名 K-12 学生时会发生什么？

总部位于印度的[职业启动平台](https://www.intel.com/content/www/us/en/corporate-responsibility/covid-19-aws-career-launcher-article.html)与 AWS 合作，提供了一个可以为 165，000 名学生服务的平台。想想如果公司需要采购硬件，Career Launcher 会面临怎样的挑战。在疫情启动期间，企业客户很难获得足够的硬件来处理远程用户的涌入。Career Launcher 用例是一个团队如何利用现有应用程序并利用公共云的弹性的示例。但是职业启动器的例子虽然令人印象深刻，但更多的是一个传统的云故事。

## 多云朵

云爆发的概念引出了多云的问题。在 Career Launcher 用例中，组织将一个现有的应用程序迁移到公共云中。英特尔将其 VPN 基础设施扩展至公共云。CTO 顾问团队进行了一项研究，我们在多个公共云提供商中部署了 VMware 的 VDI 解决方案。

我们学到了什么？事实证明，在运行于 AWS、Google Compute 和 Oracle 中的 VMware vSphere 之上部署 VMware 的 VDI 解决方案 VMware Horizon 是公共云提供商的一种常见体验。我们体验了许多与职业启动程序相同的优势。我们成倍增加了我们的 VDI 容量，并发现我们可以在几个小时内部署支持数万名 VDI 用户的能力。

然而，如果我们想在所有三种云上运行该解决方案会怎么样呢？我们发现公共云提供商之间的运营差异足以让 it 获得可疑的回报。网络是一个材料差异的例子。对于 VMware VDI，您必须通过公共 IP 地址公开门户。每个云提供商都有不同的方式为 vSphere 托管的虚拟机分配公共 IP 地址。

我们在安全模型中发现了类似的挑战。AWS 上的 VMware Cloud 拥有独立于 AWS 门户的访问控制系统。账单也不一样。Oracle 要求签订年度合同，而 VMware Cloud on AWS 和 Google VMware Cloud Engine 则允许签订按小时付费的合同。基于 AWS 的 VMware 云需要额外的供应商关系，因为该解决方案是由 VMware 直接交付的。这些挑战越积越多，大到无法找到足够的价值来维持与每个公共云提供商的连接。

毫无疑问，将您现有的数据中心向公众扩展以应对疫情带来的容量挑战的能力代表了容量的巨大变化。Cloud Launcher 和英特尔都展示了如何利用公共云快速扩展容量，而无需应用程序重新架构或运营模式的重大改变。然而，CTO 顾问认为没有足够的价值来采用多云运营模式。

通过关注 thectoadvisor.com，您可以了解更多关于运行混合基础设施的信息。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>