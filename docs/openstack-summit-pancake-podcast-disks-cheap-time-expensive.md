# OpenStack 峰会煎饼播客:磁盘很便宜，你的时间很贵

> 原文：<https://thenewstack.io/openstack-summit-pancake-podcast-disks-cheap-time-expensive/>

为了录制我们在 2016 年巴塞罗那 OpenStack 峰会上的煎饼早餐，我们邀请了 CERN 的基础设施经理 [Tim Bell](https://twitter.com/noggin143) ，CERN 的分布式系统架构师 [Ricardo Rocha](https://www.linkedin.com/in/ricardo-rocha-739aa718) ，以及 Red Hat Ansible 社区架构师 [Robyn Bergeron](https://twitter.com/robynbergeron) ，以及英特尔软件开发人员 [Dan Bode](https://github.com/bodepd) 加入我们[的讨论](https://youtu.be/iNpAm0dTpGI)关于 OpenStack 的巨大可扩展性、可编程基础设施以及有时令人震惊的[大帐篷](https://thenewstack.io/tns-makers-openstack-tokyo-canonical-ubuntu-project-midokura-ibm/)复杂性

[#119: OpenStack 峰会煎饼播客——磁盘便宜，你的时间贵](https://thenewstack.simplecast.com/episodes/119-openstack-summit-pancake-podcast-disks-are-cheap-your-time-is-expensive)

什么是可编程基础设施？对英特尔来说，这个术语的意思是，“你可以写代码或配置的系统，你可以在一个修订控制系统中描述你的整个基础设施，所以你可以做代码审查，”Bode 说。这种方法会给你一个“内置的审查过程，你可以用它来理解正在做什么改变，谁在做改变，为什么。”

说到基础设施，CERN 的 it 团队非常依赖自动化。他们的系统必须收集来自粒子粉碎[大型强子对撞机](http://home.cern/topics/large-hadron-collider)的数据，该对撞机每秒产生大约 1pb 的数据[(谢天谢地，这些数据被过滤到该组织的两个数据中心](https://www.openstack.org/videos/video/neutron-at-cern-moving-thousands-of-production-nodes-from-nova-network)的 2.5 GB/秒，运行大约 19 万个内核)。

Bell 说，扩展到如此大规模构建的诀窍是“扩展机器的数量，而不扩展运行它们的人数”。他说，自动化是这里的关键。

尽管 CERN 传统上使用虚拟机来加快其研究人员的部署过程，但它现在正在寻找容器来进一步加快工作流程。Rocha 指出，打包一个科学应用程序以便在 CERN 的机器上运行需要大量的工作，研究人员经常需要帮助。Rocha 说，有了在 OpenStack 上运行的容器，“他们将获得一个可以专注于工作的环境，而不必知道他们基础设施的细节”。

对于这项工作，OpenStack 的 [Magnum](https://twitter.com/thenewstack/status/791559901780803584) 为 CERN 提供了便利。“我们发现 Magnum 作为一个框架吸引人的地方是我们已经有了 OpenStack 基础设施，”贝尔说，他也是 [OpenStack 董事会成员](https://www.openstack.org/foundation/)。“因此，我们有项目框架、工作流，以及围绕服务必须投资的所有额外工具。我们可以将 Magnum 插入其中，为用户提供选择自己的编排引擎的灵活性。”

“CERN 用户在技术上非常先进，让一个中央团队告诉他们必须使用 [Kubernetes](/category/kubernetes/) 或必须使用 Mesos 并不是一件容易的事情，而使用 Magnum，我们能够做的是告诉人们做出自己的选择。与效率相比，这更关乎灵活性，”贝尔说。

因此，Kubernetes 不仅可以用在 OpenStack 之上，而且在 OpenStack [Kolla](https://github.com/openstack/kolla) 项目的帮助下，它还可以用来部署 OpenStack 本身。“Kolla 是一个在 Docker 容器中部署 Ansible 或部署 OpenStack 的项目，”Bergeron 解释道。

虽然 OpenStack 大帐篷带来了复杂性，但正是这种复杂性为高可扩展性铺平了道路。

“我很高兴看到人们正在进行的大量探索，我也很高兴看到人们更擅长做开源的事情，并实际参与所有这些社区，提供反馈。这实际上意味着[这]可能都是可行的，”贝杰龙解释道。

这个煎饼播客和这篇文章是由[英特尔](https://www.intel.com/content/www/us/en/it-management/intel-it/it-managers.html)赞助的:

[英特尔的 Matthew Brender 讨论遥测技术和英特尔 Snap 工具](https://thenewstack.simplecast.com/episodes/intels-matthew-brender-discusses-telemetry-and-the-intel-snap-tool)

[英特尔](https://www.intel.com/content/www/us/en/it-management/intel-it/it-managers.html)和[红帽](https://www.openshift.com/)是新堆栈的赞助商。

特征图片:(从左到右):里卡多·罗查、罗宾·贝吉龙、蒂姆·贝尔、丹·博德。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>