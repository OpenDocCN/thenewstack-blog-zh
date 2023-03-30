# 牧场主实验室正在为码头集装箱建造一个平台

> 原文：<https://thenewstack.io/rancher-labs-building-os-docker-containers/>

牧场主实验室的人正在重新组建乐队。他们正在与系统集成商 [Redapt](http://www.redapt.com/) 合作，就像他们在经营 Cloud.com 的时候一样。这一次，目标是为容器创建一个 超融合基础设施平台。

他们的目标是通过定义应用打包和运行时标准，极大地简化和降低为容器化工作负载构建私有基础架构堆栈的成本。

Rancher Labs 联合创始人兼首席执行官盛亮表示，Docker 的流行推动了人们对基础设施的彻底反思，包括存储、网络、负载平衡、防火墙等。

“Docker 映像是可移植的，但是如果这些映像被绑定到这些基础设施服务上，而这些基础设施服务实际上并不那么可移植，那么这就破坏了 Docker 无处不在的一些价值。我们认为，如果我们能够建立一套用软件编写的、可以在任何地方运行的丰富的基础设施服务，这将为客户带来价值，”他说。

这是其容器管理平台 Rancher 和 RancherOS 背后的想法，这是一个为运行容器而构建的基本(20MB)操作系统。除了容器基础设施平台，它还宣布 Rancher 支持为 Docker 编排持久存储服务。

梁说，Redapt 和他之前的公司曾在 2011 年前后合作，为当时最大的游戏制造商之一 Zynga 开发私有云。

传统的方法是构建云，进行虚拟化，然后在其上运行容器，但“通过超融合基础设施，我们消除了许多复杂性和层次，”他说，从而产生了一个易于管理的交钥匙平台。

虽然大多数人在虚拟机和云中运行容器，但他认为虚拟化不会消失,“…在某些情况下，当人们在自己的数据中心大规模运行时，他们希望获得最后一点性能，他们希望对资源调度有更多的控制，因此消除一些额外的层以提高性能和资源利用率是有意义的。”

他在谈论消除独立的虚拟化和云管理层。

“在[这个平台]中，RancherOS 和 Docker 在裸机上运行，但我们仍然必须管理虚拟机工作负载，因为这些用户中的许多人仍然有无法容器化的传统工作负载。它可能运行在 Windows 或旧版本的 Linux 上。

“我们仍然支持 KVM，但我们不再单独管理 KVM。我们只是在一个容器中运行 KVM，所以管理栈实际上是相同的。你用来管理容器的管理栈，你也可以用它来管理 KVM。它们被有效地包装成 Docker 图像。这就是我们如何管理虚拟化工作负载的向后兼容性。但是已经取消了单独的虚拟化层。再也没有 CloudStack、OpenStack 这样的层了。如果您想要一台虚拟机，我们只需在一个容器中运行它，这并不是什么新鲜事。谷歌这么做已经很多年了。”

据该公司称，该平台:

*   基于基于英特尔 x86 的服务器和固态硬盘。
*   支持虚拟机和容器；编排框架 Compose、Swarm 和 Kubernetes 以及流行的 DevOps 工具如 Chef、Puppet、SaltStack 和 Ansible。
*   为有状态容器提供了丰富的持久存储特性。
*   使开发人员能够通过将公共云中的实例注册为计算资源来扩展容量。
*   在不同主机上运行的容器和虚拟机之间提供网络隔离和连接。
*   提供强大的资源调度程序，提高计算资源的密度和利用率。

顺便提一下，它没有一个很酷的名字，它只是“超融合基础设施平台”梁说，容器市场似乎还没有准备好像以前的专有软件套件那样的一体化打包选项。他说，他的客户往往是运营自己的数据中心的公司，他们不想建立自己的云，但没有提到任何人。

“我们特意使其更加灵活，因为一些潜在客户有非常具体的要求，甚至包括服务器的品牌和型号。重要的是我们让体验变得顺畅，”他说。

这些都是非常新的技术。它的 Rancher 产品自 6 月以来一直处于测试阶段。该公司计划在 2016 年第一季度全面上市。它计划在明年上半年推出 RancherOS 和超融合基础设施平台，梁称 RancherOS 尚未进入测试阶段。

## **Docker 存储插件**

梁说，Docker 宣布的网络和存储插件模型对 Rancher Labs 来说是一个福音。

“网络是容器要解决的第一个问题，”他说。“[版本] 1.9 对我们帮助很大。最初，Docker 没有插件框架，我们必须做大量的幕后工作，与 Rancher 一起联网才能让它工作，”他说。

它将其持久存储服务设计为这些插件之一。该公司解释说，牧场主可以用来:

*   使用作为容器提供的任何软件定义的存储平台，如 Gluster、Ceph 和 Nexenta，直接在容器主机上协调存储服务的部署和配置。
*   使用 Docker Compose 和这些存储服务启动应用程序，以自动创建持久的 Docker 卷来支持传统数据库等有状态应用程序服务。
*   使用任何特定于供应商的高级存储功能，如快照、备份、远程复制和数据分析。
*   在任何虚拟机或裸机服务器上部署应用程序及其所有存储服务，运行在任何公共云或私有数据中心。

梁说，该公司一直在与软件定义的存储供应商合作，以简化 Rancher 的部署和存储管理。

Portworx 首席技术官 Gou Rao 在介绍 Docker 用于在 Linux 容器中托管有状态应用程序的存储软件[时表示，围绕基础设施的一切，包括网络和存储，都是“事后想到的，它们被视为附加功能”。](https://thenewstack.io/five-storage-companies-that-speak-to-dockers-next-wave/)

尽管 Docker 宣布 ClusterHQ 的 Flocker 是其第一个存储合作伙伴，但竞争对手已经在排队了。

Red Hat 刚刚宣布在其原子主机平台中支持 Ceph 和 Gluster 存储选项的[插件，以及几个尚未命名的第三方插件。](http://www.informationweek.com/cloud/platform-as-a-service/red-hat-preps-containerized-cloud-workloads-in-openshift/d/d-id/1323056)

与此同时，一家名为 Hedvig [的公司通过软件定义的路线将分布式应用连接到现有存储](https://thenewstack.io/hedvigs-software-defined-storage-and-the-test-to-dockers-plugin-system/)。

Taneja Group 的高级分析师和顾问 Mike Matchett 解释说，虽然 Flocker 正在映射外部存储和容器，但 Rancher 正在直接从作为容器运行的 SD 存储映射到其他容器，并指出他没有得到关于 Rancher 的简报。当然，容器托管的 SD 存储需要在某个时候映射到某个地方的持久存储。

“现在有几种方法可以试着剥集装箱储猫的皮。好消息是，容器世界现在有了一些非常有趣的存储架构方法和选项。具有挑战性的部分是，不清楚哪种解决方案提供了最健壮、最可靠和最高效的 IO，”Matchett 说。

他指出，我们从虚拟化中了解到，虽然存储和 IO 通道抽象/隔离具有巨大的优势，但它也会使可见性、故障排除、性能优化和容量规划变得复杂。

“与容器世界纯粹主义者交谈很有趣，他们可能仍然坚持认为容器架构旨在用于相对无状态的微服务托管，将持久存储放入其中违背了原则。但随后，实际的 IT 界开始考虑在容器中托管各种工作负载，”他说。

“容器方法的潜在优势是巨大的，因此我完全预计容器体系结构将继续快速发展，以支持甚至取代越来越多的虚拟机用例。”

Docker 和 Red Hat 是新堆栈的赞助商。

专题图片:[西雅图市档案馆](https://www.flickr.com/photos/seattlemunicipalarchives/)[工程计划存储，2001](https://www.flickr.com/photos/seattlemunicipalarchives/3762792170/in/photolist-6Jvi25-4CmaCB-4Cmawe-4Aerdd-pgFtoj-dYxjR3-aceMrn-p2W5E3-8Vpf9R-joAi8B-aCZGkf-rFp88W-o7LSyT-qAQasV-oSpATg-ooY8cg-dSt1CS-46LwV4-4C7eEk-aUg5p6-rp2CUv-4CbwW5-4C7eCB-oK7qnC-oM7ub3-fNsLXg-d2fU27-ouDMQh-rW7Y5q-5NuLW9-rFnHBJ-dQo6G8-8jLHvA-oSpAyt-oQDzQy-5YLvsU-6hwm4D-7xx3kV-jSusRu-7n6njn-5oVGxk-aUg8cx-ouDoHM-ouDnTv-aUgdnB-e2pDsg-ahvqtx-kCZryt-8nMcKK-7Wc3u3) ，获 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>