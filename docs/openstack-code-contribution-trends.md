# OpenStack 的代码贡献分析及其揭示的趋势

> 原文：<https://thenewstack.io/openstack-code-contribution-trends/>

编者按:New Stack 创始人亚历克斯·威廉姆斯(Alex Williams)将于 5 月 29 日参加由 Pivotal 和 Greylock Ventures 主办的炉边聊天。

[Registration](http://play.gopivotal.com/Pivotal-Presents-Fireside-Chat-Greylock.html?mkt_tok=3RkMMJWWfF9wsRokuK7JZKXonjHpfsX56O8pXaSwiokz2EFye%2BLIHETpodcMT8JqMa%2BTFAwTG5toziV8R7bHKc1pz98QWxHr)

现已开放。他计划将 OpenStack 报告作为讨论的一部分，讨论将涵盖与开源和企业相关的各种主题。对报告及其背后的数据感兴趣？请联系我们进行咨询。

有超过 100 家公司为 OpenStack 贡献代码，看到他们贡献方式的趋势是很有趣的。关于提交的指标已经被跟踪了一段时间，并且[stack alitics](http://www.stackalytics.com)有很好的可视化效果。我们开始在跨多个项目的多个发布中寻找代码贡献的趋势。

我们分析了来自 Github、 [Stackalytics](http://www.stackalytics.com/) 的数据，并采访了来自不同公司的许多开发者。我们跟踪了 OpenStack 过去 4 个[版本](https://wiki.openstack.org/wiki/Releases)(*Folsom*(2012 年 9 月)、*Grizzly*(2013 年 4 月)、*Havana*(2013 年 10 月)以及最近的*ice house*(2014 年 4 月))的总体贡献趋势。请注意，这里的“整体”包括所有项目 [OpenStack Gihub](https://github.com/openstack/) ，但不包括 [OpenStack Infra](https://github.com/openstack-infra) 项目。我们还钻取了 OpenStack 的以下项目中的贡献趋势: [*Nova*](http://www.openstack.org/software/openstack-compute/) (计算) [*Swift*](http://www.openstack.org/software/openstack-storage/) (对象存储) [*煤渣*](http://www.openstack.org/software/openstack-storage/) (块存储) [*中子*](http://www.openstack.org/software/openstack-networking/) (联网) [*地平线*](http://www.openstack.org/software/openstack-dashboard/) (仪表盘) [*热度*](http://www.openstack.org/software/openstack-shared-services/) (编排)

我们在周二的新堆栈分析师[展示](https://thenewstack.io/the-new-stack-analysts-inaugural-show-today-at-11-a-m-pst-data-research-about-openstacks-developer-community/)中展示了我们的发现。以下是我们观察到的一些趋势。虽然有些和预期的一样，但也有一些有趣的异常值。

## 标准趋势

### 前 5 名贡献者

在过去的两个版本中，贡献最大的是[红帽](http://www.redhat.com)、[惠普](http://www.hp.com)、 [IBM](http://www.ibm.com) 、 [Rackspace](http://www.rackspace.com) 和[米兰蒂斯](http:/www.mirantis.com)。除了 IBM 之外，他们也被开发人员视为最大的贡献者。几乎所有非 IBM(甚至是 IBM)开发人员都将 Rackspace 或 Mirantis 列为前三名，但 IBM 没有。这可能与他们和其他人相比保持低调有关。从他们的总体贡献来看，我们也感觉到他们即将发布自己的 OpenStack 发行版。

在不到两年的时间里，在 Folsom 发布期间，观察 Mirantis 从 28 名进入前 5 名也是非常有趣的。

### 代码=承诺

OpenStack 社区是一个开发者驱动的社区。只有代码在内部说话。很明显，如果一个人需要被重视，他就需要编码。正如参与公司的贡献趋势所反映的那样，它们对此非常理解。

在 [Red Hat](http://www.redhat.com) 加入 OpenStack 社区后不久，他们一直在稳步增加其参与度。在过去的 4 个版本中，他们一直是第一贡献者，并在下一个版本中继续保持这一趋势。这种模式在 [Mirantis](http://www.mirantis.com) (#5)和 eNovance (#8)中也有所体现。SIs 的宠儿 Mirantis 一直被视为 OpenStack 专家。随着他们对代码贡献的增加，他们现在已经是全面的专家了(我们也想知道为什么大玩家还没有获得他们:)。

### 小众玩家

每个项目都有在该项目中占主导地位的利基参与者，但在其他项目中可能几乎不为人知。创业公司展现了这种趋势，比如 Swift 的 [SwiftStack](http://www.swiftstack.com) ，Neutron 的[大开关网络](http://www.bigswitch.com/)，Cinder 的 [SolidFire](http://www.solidfire.com/) 。

### 缩小差距

我们跟踪了提交的总数，并计算了每个公司在总体上以及在这些单独的项目中所占的百分比。#1 和#2 贡献者之间的百分比差距总体上在下降(中子和 Keystone 项目除外)。例如，在《新星》中，哈瓦那的上映率是 8%，而冰室的上映率只有 6%。在加热阶段，这种模式更加突出，同期的差距从 49%下降到 24%。

另一个有趣的趋势是，贡献前 80%的贡献者的数量也增加了(从 Folsom 的 3 个增加到 Icehouse 的 8 个)，贡献者的长尾也在增加。

## 极端值

两个在总贡献排名中迅速上升的局外人是[华为](http://www.huawei.com/us/index.htm)(从灰熊的第 69 位到哈瓦那的第 18 位到冰室的第 12 位)，[三星](http://www.samsung.com/us/)(从哈瓦那的第 102 位到冰室的第 13 位)。对华为来说，这主要归功于他们在 APAC 的快速增长。对于三星来说，这可能与 Nova 上的 ARM 相关移植工作有关。几乎所有的开发人员都没有看到这一点，直到我们向他们展示数据，但一旦数据出现，他们就能够关联起来。

我们观察到的另一个独特趋势是[英特尔](http://www.intel.com)，他们从未进入前 3，也从未低于前 15。他们一直致力于对其具有战略重要性的功能(如 Nova 中更智能的调度、减少 Swift 中的存储空间等)。虽然它们总体上趋向于上升，但在两次发布之间会上下波动。

## 流行趋势

几乎每个项目都有独特的玩家，大多反映了他们的产品策略或服务。比如在《中子》中，[大开关网络](http://www.bigswitch.com)已经从 Grizzly 的#14 上升到 Icehouse 的#6。在 Keystone 中，[元云](http://www.metacloud.com)在同一时期从非贡献者飙升至第四。

## 低骑手

我们也有贡献者倾向于低。当我们分析它们的模式时，我们发现贡献减少的趋势是三倍的:

### 其他贡献者大幅增加

一些公司表现出这种持续贡献的趋势，但其他公司的贡献显著增加。DreamHost 是这种趋势的一个很好的例子。虽然他们的代码贡献总的来说总是在 2-3%之间，但是他们的排名已经明显下降了(从 Folsom 的第 5 位下降到 IceHouse 的第 15 位)

### **产品完成/产品变更**

典型的小公司表现出这种模式。当他们实现了他们想要做的目标，或者如果他们的产品策略发生了变化，他们的贡献趋势会急剧逆转。例如， [Nexenta](http://www.nexenta.com) 在 Havana 发布之后，一旦与他们的产品相关的代码完成，就停止了对 Swift 的贡献。[墨水瓶](http://www.inktank.com)在哈瓦那之后的煤渣中展出了同样的东西。更有趣的是，Nebula 曾经是 Folsom 和 Grizzly 的 Horizon 的最大贡献者，在哈瓦那之后，一旦他们决定使用他们自己的产品仪表板，就逐渐减少了。

### **贡献递减**

一些公司确实减少了他们的代码贡献，我们还没有找到合理的理由。例如， [Canonical](http://www.canonical.com) 的贡献越来越小，从 Folsom 的 1.8%到 Icehouse 的 0.5%。 [Rackspace](http://www.rackspace.com) 在我们跟踪的项目中呈下降趋势，但在其他更新的项目、手册和基础设施相关项目中也有所上升。SUSE 热度持续走低，Yahoo 热度持续走低。

关于作者: Sriram 是云咨询公司 Cloud Don LLC 的创始人和云专家。他是一名 [OpenStack](http://www.openstack.org/) 爱好者，是 [OpenStack 基金会](http://www.openstack.org/foundation) 的个人成员，对 OpenStack 的整体成功充满热情，尤其是在印度。在 Cloud Don 之前，他是 [ComputeNext](http://www.computenext.com/) 的首席开发人员，构建了一个联合云市场，在那里他获得了包括 OpenStack 在内的多个云平台的专业知识。在 ComputeNext 之前，他曾供职于微软、英特尔、日立等多家公司，从事云计算、虚拟化、编译器和低功耗设计等广泛的技术研究。他对云计算、绿色/清洁技术和整体生活充满热情。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>