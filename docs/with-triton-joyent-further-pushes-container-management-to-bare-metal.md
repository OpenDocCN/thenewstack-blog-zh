# 通过 Triton，Joyent 进一步将 Docker 管理推向裸机

> 原文：<https://thenewstack.io/with-triton-joyent-further-pushes-container-management-to-bare-metal/>

随着与 Docker 建立更紧密的联系，云基础设施公司 Joyent 继续通过发布[Triton Elastic Container infra structure](https://www.joyent.com/)解决其所谓的容器“限制”，该平台旨在从根本上简化大规模生产中的容器部署。

本质上，它允许容器在裸机上运行，同时消除了 VM 抽象层，Joyent 的 Bryan Cantrill 称之为“不必要的脂肪层”。

> “这只是你必须管理的其他东西，你必须预先配置的东西。就弹性、性能和密度而言，在虚拟机中运行容器，然后在物理机上运行容器实际上是没有意义的。你想做的是直接在主要硬件上运行容器，”他说。

他说，挑战在于用于容器的 Linux 基础——即名称空间和 cgroups——实际上不是为多租户设计的，这造成了安全问题，使得在裸机上部署 Linux 容器变得困难或不明智。

Triton 服务使用 Joyent 的 SmartOS 底层，该底层已经使用了大约 10 年，它还建立在 Sun Microsystems 以前在 SmartOS 中使用的 Sun Microsystems Solaris 开源版本中所做的一些安全工作的基础上。

“这使我们能够利用我们在运营、多租户运营方面的所有专业知识，也使我们能够利用来自网络、Crossbow 和 CFS 的一系列技术，来解决 Docker 目前在网络、持久性方面的一些主要问题。另外，我们去掉了虚拟机层，”他说，这使客户可以只管理容器，而不是在数据中心的物理位置进行配置。

对于海卫一，它在吹捧:

*   **简化管理:** Triton 将整个数据中心虚拟化为一台弹性的 Docker 主机。Triton 提供了一套实时自省和事后调试工具，允许查看每个容器。

*   **安全性:** Triton 的容器运行时首先是为了安全隔离而构建的，将容器视为网络上的一等公民。

*   **联网:**每个 Triton Docker 容器都有自己唯一的 IP 地址，并提供跨容器的 VXLANs。

*   **裸机性能:** Triton 的容器运行时利用操作系统虚拟化，无需硬件虚拟机管理程序层来提供裸机优势，包括对 CPU、存储和网络资源的低延迟访问。

Cantrill 说，Joyent 去年大部分时间都在开发这款产品。它包括弄清楚如何在 SmartOS 区域内运行 Linux 二进制文件，还与 Docker 讨论了如何在该衬底上运行它。

“Docker 有一个非常强大的 API，这让我们受益匪浅。这很令人惊讶，因为当你下载 Docker 时——Docker 客户端、Docker 命令和 Docker 服务器——它们是相同的二进制文件，这有点不寻常。当你看到这一点时，你会想这些东西彼此分离得有多好，客户端和服务器之间的 API 协议设计得有多好。Docker 中的远程 API 实际上相当健壮，”Cantrill 说。

“因此，对我们来说，创建 Docker 远程 API 端点相对简单，对于 Docker 客户端来说，它看起来像 Docker 守护程序，而实际上它是模仿 Docker 守护程序的 Triton 堆栈。”

由于 Triton stack 基于 Joyent 的开源资产，公司可以通过三种方式使用它:作为 Joyent 的服务，作为 Joyent 的内部产品，或者通过下载开源并自己运行。

> “我们相信新的构建将 100%基于容器，如果我们走向全容器的未来，这确实会引发一个问题，为什么我们要将这种虚拟机抽象带到未来？”坎特里尔说。

“我们认为，除了运行传统工作负载之外，虚拟机抽象在未来并没有真正的一席之地。几乎所有其他供应商都将在硬件虚拟化的虚拟机中运行容器。”

虽然亚马逊网络服务是 Joyent 最强大的竞争对手，但它的竞争对手包括像 [OpenStack](http://openstack.org/) 和 [CloudStack](http://incubator.apache.org/cloudstack/) 这样的项目。该公司十多年来一直专注于集装箱，抓住了 Docker 受欢迎程度的快速上升来推动复兴。

10 月，该公司宣布[又筹集了 1500 万美元](http://techcrunch.com/2014/10/31/joyent-raises-15m-to-bring-enterprise-grade-docker-support-to-its-cloud-platform/)，使该公司的总投资额达到 1 . 2 亿美元。几周内，它宣布将开放其核心技术的源代码:SmartDataCenter、基于容器的编排软件和基于 ZFS 的多租户 Manta 对象存储平台。

去年 12 月，它宣布将 Docker Engine 集成到 SmartDataCenter，以及一个运行 Linux 应用程序的平台，包括那些在 Docker 容器中运行的应用程序，这些应用程序原生于安全的操作系统虚拟化上，没有中间的硬件虚拟机管理程序。该公司还宣布了 Linux 品牌区域(LXz)，这是一个用于容器部署的新平台。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/joyce411/14055128701/in/photolist-nq1d6c-db87pn-6wfZuy-duoBgb-Fjuro-9wYoMd-c5nbxA-e4Bj86-nmrb4f-9VKEEM-r5Eg2L-4Pm7FG-6KWxJf-r7zNjc-KzWMM-e9E3Hc-yeqry-Ls3ax-punv9R-e6JCzH-nkef2Z-76UYX6-8tXMQJ-ekyscZ-iGbhEF-9XDwbA-gx2qwS-piWLJc-9rSZgW-7Uc2n3-bAUTMx-4v6iQN-qZURg5-d1wrVf-nr9Rkn-6GfJ4C-nmEAVo-npcyLi-e9Bian-fWSr61-rJ4xWd-fQaJ9n-r6KdAf-533GP4-ddnGS5-ppsQAz-iJGx8P-aciEY7-7cLx1T-6tZ8MX)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>