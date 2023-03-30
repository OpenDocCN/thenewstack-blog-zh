# 使用 OpenStack 到达边缘

> 原文：<https://thenewstack.io/arriving-at-the-edge-with-openstack/>

多年来，你已经听到了大数据和物联网的鼓声，但现在，随着越来越多的设备上线，从家中的智能设备到路上的自动驾驶汽车，数据流量和处理数据的需求都在呈指数级增长。随之而来的现实是，现有的基础架构根本无法及时处理所有数据，除非我们将部分处理转移到边缘。

上个月在科罗拉多州丹佛市举行的[开放基础设施峰会](https://www.openstack.org/summit/denver-2019/)上，近 36 场会议讨论了边缘的主题，并且展出了各种用例和技术方法，从[工业物联网和“智能仓库”](https://www.openstack.org/summit/denver-2019/summit-schedule/events/23561/how-to-bring-things-together-to-the-smart-warehouse)到[电信公司如何利用边缘](https://www.openstack.org/summit/denver-2019/summit-schedule/events/23494/highly-efficient-edge-cloud-data-center-for-5g)实现 5G 的低延迟和高带宽。甚至还有关于如何使用 Kata 容器在边缘部署 FaaS 的讨论。

大量的讨论表明，“边缘”不再是一个关于什么是可能的外部界限的话题，更不用说什么是必要的了。一个小组[在其描述中简洁地描述了手头的问题](https://www.openstack.org/summit/denver-2019/summit-schedule/events/23798/the-race-to-the-edge)，称“物联网、AR/VR 和联网汽车等应用都需要与最终用户极度接近，使边缘成为这些低延迟、高带宽应用的自然位置。”

[Red Hat 的主要产品经理 Jaromir Coufal](https://www.linkedin.com/in/jcoufal/) 在接受新堆栈采访时解释说，无论您是从电信角度还是从企业应用角度谈论边缘，一个共同点通常是计算背后的硬件，正如名称所示，位于网络边缘的物理远程位置。这提出了边缘计算特有的一些挑战，Coufal 说 OpenStack 可以帮助解决这些挑战。

“当我们开始谈论在边缘部署时，你可以想象有许多最终用户在使用这些服务，你说的是每个国家数百万或数千万的最终用户，这取决于国家的大小。因此，你需要有很多分散的网站，因为你需要在某些地区有一定的覆盖面，”库法尔说。“当您对这些站点进行部署和运营管理时，这就需要减少 IT 专业知识。你不可能在每个地方都有专家。”

Coufal 继续解释说，由于这些挑战，基础设施易于部署、维护，并且能够在尽可能少的人工干预下远程完成，这一点很重要。因此，部署在边缘的基础架构具有自我修复和弹性也很重要，这样当出现问题时，技术人员就不必立即前往现场，从而增加成本和停机时间。

Red Hat 首席软件工程师兼 OpenStack 讽刺项目团队负责人 Julia Kreger 从电信公司的角度阐述了这一想法，他解释说，网络功能的虚拟化还允许网络运营商将这些服务的管理转移到边缘，而不必亲自前往。

Kreger 说:“运营商需要将他们对物理裸机和物理数据中心资产的管理推向更远的地方，更靠近蜂窝基站和最终用户。“当我们开始使用互联网时，有 MAE-East 和 MAE-West，它们是最初的两个主要电信对等点，帮助定义了互联网。随着时间的推移，它分布在世界各地，连接变得越来越紧密，现在人们用光纤连接和电力运送货物集装箱到停车场，因为他们需要更接近最终用户。”

[Red Hat 产品管理总监 Sandro Mazziota](https://www.linkedin.com/in/smazziotta/) 继续解释说，电信公司的边缘使用案例不仅仅是为计算和远程管理服务提供物理远程位置。随着电信公司开始扩展 3G/4G 并提供 5G 网络，他们不仅需要增加更多更好的硬件，还需要在虚拟化硬件栈的边缘提供新的服务。这成为产品化生命周期的一部分。

“人们必须增加带宽容量，现在，借助硬件虚拟化，他们也有能力增加到边缘。当我们推出 3G 时，这还不存在，”Mazziota 说。“他们正在虚拟化网络基础设施。现在，我们看到了人们购买虚拟解决方案并将其部署到边缘的趋势，而不是购买专用硬件。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>