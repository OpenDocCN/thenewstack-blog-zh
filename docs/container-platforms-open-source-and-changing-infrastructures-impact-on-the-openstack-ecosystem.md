# 容器平台、开源和不断变化的基础设施对 OpenStack 生态系统的影响

> 原文：<https://thenewstack.io/container-platforms-open-source-and-changing-infrastructures-impact-on-the-openstack-ecosystem/>

在本期《新堆栈制作者》中，我们将探讨 OpenStack 如何在集装箱化环境中投入使用，目前正在塑造生态系统的开源项目，以及围绕基础设施的变化如何塑造 OpenStack。New Stack 创始人 [Alex Williams](https://www.linkedin.com/in/alexwilliams2) 和联合主持人网络安全管理软件产品 Cloud &容器技术负责人 [Lee Calcote](https://www.linkedin.com/in/leecalcote) 坐下来与思科产品管理和战略总监 [Duane DeCapite](https://www.linkedin.com/in/duanedecapite) 进行讨论，了解他的想法。

[open stack 生态系统如何适应容器世界](https://thenewstack.simplecast.com/episodes/how-the-openstack-ecosystem-is-adapting-to-the-container-world)

DeCapite 首先强调了一些项目，这些项目有助于为那些在 [OpenStack](https://www.openstack.org/) 中使用容器的人创造更好的体验。其中包括 OpenStack 容器部署平台 [project Magnum](https://wiki.openstack.org/wiki/Magnum) 、Docker LibNetwork 上的[Kuryr](https://github.com/openstack/kuryr-libnetwork)、OpenStack 中子和 [OpenStack Nova](http://docs.openstack.org/developer/nova/) 。“在 Magnum 架构本身中，您甚至可以在 LibNetwork 之外使用 Neutron 插件对容器进行联网。有了最新版本，你可以拥有任何中子插件，打开虚拟开关，你可以拥有[印花布](https://www.projectcalico.org/)。Kuryr 实际上将 Docker CNM 或 LibNetwork 直接映射到中子 API，”DeCapite 说。

[https://www.youtube.com/embed/w3TEdtYEAdc?feature=oembed](https://www.youtube.com/embed/w3TEdtYEAdc?feature=oembed)

视频

随着 OpenStack 不断发展成为当今开发人员的新标准，客户需求也随之改变。为了使基础设施编排更加简单，OpenStack 提供了 [heat 模板](https://wiki.openstack.org/wiki/Heat)来为其用户在云上运行多个应用。“许多客户使用 heat 模板，因为这是一种以编程方式将大量 OpenStack 服务集中在一个地方的好方法，”DeCapite 解释道。

Williams 继续指出，传统上，基础架构一直是从低层次的角度来解决的，现在已经发展到以应用程序为中心的角度。对于开发人员来说，这种转变不仅改变了他们编写代码的方式，还引入了各种 PaaS 解决方案来简化这一过程。“基础设施即服务对 OpenStack 有着巨大的需求。以真正协调、程序化的方式完成基础存储、计算和网络。

总的来说，今天的 PaaS 解决方案是使用 OpenStack 的最重要的变化之一，不仅增加了灵活性，而且从整体上提高了开发人员的生活质量。“我认为就获得额外功能而言，基于 OpenStack 的 PaaS 背后的生态系统真的引起了很好的共鸣。从客户的角度来看，这也很好，因为他们可以选择。他们可以在 OpenStack 或其他环境上实现 PaaS。有了这种划分，客户和开发人员就有了很大的灵活性。”

特征图片: [fotologic](https://www.flickr.com/photos/fotologic/) 的[平台](https://www.flickr.com/photos/fotologic/4050074409/in/photolist-7aTG28-eAyXvz-6YUL4d-eLQLfe-A7YAm-exDiLX-dqZutS-cqV1qC-8SL4iD-nh7EHy-mzt4x-aYuFDk-5FNCHS-foRWi-6jyEF9-iiiew-4zuPoA-4RieE4-4HX3i-2u8hGG-5bR83G-bgKfQZ-4HT8on-6G1dg2-D7sXv-9fCwGW-eF9qVy-7KAkvD-9fkUZ3-dn6pEC-dChpMG-iPwM71-eh2XC5-9fzoPt-9fzr34-9fzoLc-cTSmeN-6bzP7B-9fCwMJ-fShWQ-4DMpea-ayA3Wa-78qMam-7rjMZA-9gUHKY-puH29s-jiUx9-7KEhcY-obPu2F-9fzqFr)由 2.0 在 [CC 下授权。](https://creativecommons.org/licenses/by/2.0/)

思科和 Docker 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>