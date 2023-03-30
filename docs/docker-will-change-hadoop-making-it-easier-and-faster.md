# Docker 将改变 Hadoop，让它变得更简单、更快速

> 原文：<https://thenewstack.io/docker-will-change-hadoop-making-it-easier-and-faster/>

Hadoop 峰会将于本周召开，届时将会有更多关于 Docker 等新平台如何改变 Hadoop 环境下数据分析方式的讨论。

为大数据提供基础设施软件平台的 BlueData 通过其名为 EPIC Lite 的免费版本增加了对 Docker 容器的支持。它允许用户在笔记本电脑上的 Docker 容器中启动虚拟 Hadoop 或 Spark 集群。

该公司还宣布了其“夏季发布”[版本 1.5 的 EPIC](http://www.bluedata.com/blog/2015/06/bluedata-epic-summer-release/) ，该版本支持更新的 Hadoop 和 Spark 版本，与 Apache Ambari 和 Cloudera Manager 集成，支持常见的大数据分析应用程序和“自带应用程序”功能。

VMware 资深人士 Kumar Sreekant 和 Tom Phelan 在 2012 年创立了 BlueData，希望为私有数据中心的大数据基础架构创建一个类似亚马逊 EMR(亚马逊弹性 MapReduce)的自助服务模型。该公司已经筹集了 1900 万美元，并于去年 9 月摆脱了隐形模式。

它的 EPIC 软件解决方案——不要与 EHR 医疗保健巨头混淆——可以在任何硬件、任何服务器和任何存储环境上运行。它的目标是企业内部运行的 Hadoop 裸机部署。

它的目标是为客户简化 Hadoop，利用技术解决 I/O 性能问题，允许计算和存储分离，并提供工具来管理虚拟化基础架构中的多租户环境。

该公司声称它正在拥抱 Docker，因为它希望为大数据应用程序带来虚拟化的好处，同时提供容器的简单性和裸机服务器的性能。

同时，它承认了另一个动机。

该公司产品副总裁 Anant Chintamaneni 表示:“我们希望确保开发人员和数据科学家能够创建自己的集群，这在今天非常困难……能够指向任何数据并进行分析。”。这些人“可以把它放在他们的笔记本电脑上，迅速获得 Cloudera 或 Hortonworks 的功能。”

他说，该公司希望让用户从笔记本电脑上使用该软件，如果他们喜欢，他们会向 it 老板索要。

> “就成熟程度而言，《码头工人》是目前镇上最好的节目……”钦塔马尼尼说。“Docker 是我们在笔记本电脑或虚拟机上提供用户体验的一种手段，您可以在其中[创建]一个包含多个节点的集群。数据科学家希望不止一个节点来检查算法。您想知道您的应用程序在真实的集群中会如何运行。”

企业版是为多租户和多用户设计的。Lite 包含的图像更少，因为公司希望保持轻量级。

MapR 产品管理副总裁兼 Apache Drill 项目管理委员会成员 Tomer Shiran 表示:“随着越来越多的人接受 Docker 容器，像 BlueData 这样的公司将 Docker 添加到他们受支持的虚拟机管理程序集是有意义的。

“Docker 容器提供了比传统虚拟机更好的 I/O 性能，因此我预计这些 Hadoop 集群在部署到 Docker 上时会运行得更快。”

BlueData 认为虚拟化不会消失，但像 VMware 一样，它正在拥抱容器技术并将其集成到自己的产品组合中，它看到了 Docker 背后的势头，并试图保持领先地位。

“我们认为容器是实现虚拟化优势的另一种方式，”营销副总裁 Jason Schroedl 说。

“我们的计划是开发一个可以在任何虚拟化环境中运行的大数据平台，我们相信我们可以为客户带来容器的好处。”

他说，到目前为止，该公司还没有看到企业客户对 Docker 软件的大量需求，但预计未来会有更多需求。

他说，Docker 在企业内部正在走向成熟，根据 Hortonworks 产品管理副总裁 Tim Hall 的说法，更多 Docker 原生的私有和公共云平台正在兴起，Hadoop 正在成为提供的关键服务。

在明天于加利福尼亚州圣何塞开幕的 Hadoop 峰会上，将有三场涉及 Docker 与 Hadoop 的会议。例如，Hortonworks 的 Sidharta Seethana 和 Altiscale 的 Abin Shahab 将讨论 Apache [YARN](http://hadoop.apache.org/docs/current/hadoop-yarn/hadoop-yarn-site/YARN.html) 和 Docker 生态系统。 

提供 Hadoop 即服务产品的 Altiscale 决定[在 Docker 容器](https://thenewstack.io/running-hadoop-docker-production-scale/)中运行 Hadoop，尽管这意味着其系统将需要直接供应和管理 Docker 容器，而没有 Hadoop 2.0 中引入的数据处理框架 YARN 的好处。然而，该公司发现这种方法既可重复又可自动化。

[Pachyderm](http://www.pachyderm.io) 旨在通过使用 Docker 为 Hadoop 堆栈提供一个 [MapReduce 替代方案](http://www.infoq.com/news/2015/02/pachyderm-build-modern-hadoop)来简化大数据分析。它基于 CoreOS 的 Fleet 和 etcd，而不是 Apache 工具，如 YARN 和 Zookeeper。

霍尔表示，有两种方法可以解决这个问题，Hortonworks 正在双管齐下。

首先是关于使用 Docker 托管 Hadoop。它通过最近收购 Sequence IQ、和 Hortonworks 数据平台(HDP)的 [Cloudbreak 做到了这一点。它使用 Docker 图像，并在任何主要的云平台上推出 HDP，包括微软 Azure、亚马逊网络服务、谷歌云平台。](http://hortonworks.com/press-releases/hortonworks-to-acquire-sequenceiq-to-speed-hadoop-deployments-into-the-cloud/)

第二个是关于通过 YARN 使用 Docker 容器进行应用部署。这是 HDP 2.2 的一个技术预览功能，客户一直在探索如何利用它。

“本质上，Docker 提供了一种为 Hadoop 隔离和打包应用的好方法。我们也在研究 Slider 框架和 Docker 如何协同工作来简化这种部署，”Hall 说。

“我们的一个客户正在考虑为他们的数据平台采用类似的方法，使用 HDP 对 Docker 的支持——上图和下图。他们使用 Cloudbreak 在云中的 Docker 上部署 Hadoop，并计划将他们的数据应用程序构建为 Docker 映像，并在 YARN 上运行。还有许多其他客户和合作伙伴采用我们在 Docker 上的 Hadoop 进行不受环境限制的部署。这种架构选择背后的主要驱动力是敏捷性、创新速度和一致性。”

另一种更传统的方法是将 Hadoop 与虚拟机或 OpenStack 结合使用。

他说在 Docker 上运行 Hadoop 的好处包括:

*   快速安装(预拉式 rpm)。
*   开发/QA/生产采用相同的流程/映像。
*   单/多节点的流程相同。

在 YARN 上运行 Dockerized 应用的优势包括:

*   更好的软件隔离。
*   开发/QA/生产采用相同的流程/映像。
*   更好的应用分发和版本控制。

他说，大数据应用开发者越来越倾向于使用 Docker 将他们的应用容器化。此外，在裸机而不是虚拟机上运行 Docker，为类似 Hadoop 的应用程序提供性价比，也很有意思。此外，YARN 正在成为大数据应用之外的应用部署平台，他说。这推动了人们对支持 YARN 中的原生容器部署支持的兴趣，也是对 YARN 之上的应用管理框架的需求。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>