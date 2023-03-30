# 对于 Robin Systems，所有东西都在一个容器中

> 原文：<https://thenewstack.io/robin-systems-everythings-container/>

虽然关于容器的讨论主要集中在它如何简化应用程序开发，但 Robin Systems 正在将容器化作为其以应用程序为中心的数据中心战略的一部分。

它将容器化应用于 Hadoop 和 MySQL 等不太适合 Docker 的应用。与此同时，Robin 通过 Linux 上的硬件多租户专注于效率而不损失性能；DH2i 对 Windows 环境也采取了同样的策略。

上个月，它在圣何塞的 [Strata+Hadoop World](http://conferences.oreilly.com/strata/hadoop-big-data-ca) 上推出了 [Robin 集装箱化平台](http://www.prnewswire.com/news-releases/robin-systems-announces-containerization-platform-for-enterprise-applications-industrys-first-application-defined-data-center-software-platform-300249771.html)。

“这是基于容器作为核心技术的下一代平台，但我们做了大量的资源管理、存储和数据管理，以及让人们能够在裸机上整合应用程序，以消除虚拟机蔓延，”罗宾的首席营销官苏希尔·库马尔说。

让应用程序及其需求成为数据中心的焦点，服务器和存储之间的界限对应用程序不可见。

“我们的技术将软件定义的数据中心提升到了应用程序定义的数据中心的新高度，”他说。

“在过去，你会说‘这台机器就是为了这个应用。’您没有在那里运行另一个应用程序，因为您不确定它们是否会相互影响。由于我们独立运行运行时应用程序的容器，我们不必担心哪台机器运行什么，”Kumar 说。

根据 Kumar 的说法，通过 Robin，用户可以部署多个硬件集群，例如在同一台虚拟机上运行 Hadoop 集群的多个节点。“这更多地是由应用程序的需求决定的，而不是您必须将您的应用程序映射到机器边界。有了罗宾，这些界限就看不见了。”

该平台能够:

*   整合数据库和大数据应用。
*   减少虚拟机蔓延。
*   通过可移植性更快地部署应用程序；轻松制作用于测试和开发目的的克隆。
*   通过应用驱动的存储管理优化数据容量和性能。
*   通过跨应用程序和集群实现数据共享，消除数据重复。

Robin Systems 成立于 2014 年，10 月[筹集了 1500 万美元](http://techcrunch.com/2015/10/06/robin-system-raises-15m-for-its-data-centric-compute-and-storage-containerization-software/)，由 USAA 的一家子公司和 DN Capital 牵头，使其资金总额达到 2200 万美元。它的客户包括 AutoWeb 和 USAA。

它一直在吹捧沃尔玛电子商务的体验，在测试中，该公司将摄取 2.5 亿个文件的时间加快了 8.5 倍，并将查询性能提高了 2.5 倍。该公司还发现，它可以将其硬件占用空间从 16 台服务器/320 个核心减少到 10 台服务器/160 个核心。

美国柯尔百货公司首席技术官 Ratnakar Lavu 在 2016 年 BigDataSV 上接受 SiliconAngle 采访时表示，美国柯尔百货公司百货公司一直在测试 Robin 系统，现在正在寻求将该技术扩展到整个基础设施。

## **工作原理**

Robin 将其平台标榜为一个完整的开箱即用的解决方案，在一个由商品或云组件创建的共享平台上提供企业数据驱动的分布式应用程序。

它创建了一个计算和数据连续体，因此可以在每台机器上部署多个应用程序，以确保最佳的硬件利用率，并确保每个应用程序的多租户协调和隔离。容器提供了跨机器和云的移动性。

该平台将计算层和存储层分离，并将分布式持久存储层与集成的主机端分布式缓存层相结合，为应用程序提供高性能的存储访问。其虚拟存储池充当计算层的数据块存储。RAID6 配置为持久数据提供了高可用性。

计算或“数据加速层”是一个分布式主机端缓存层，它使用固态硬盘为虚拟存储池提供读写加速。每个计算节点上的数据加速层为应用层提供了一个文件系统接口。通过将 SSD 用作数据缓存，可以加速对此文件系统的读写。通过跨固态硬盘分条数据，最大限度地提高了读写带宽。

Robin Central Manager (RCM)充当基于代理的编排器，用于管理 LXC 或 Docker 容器的“虚拟集群”的部署。

## **把所有的东西装箱**

“在我们的平台中，每个应用程序都部署在一个容器中，”Kumar 说。

“很多关于容器的认知都是基于 Docker。他解释道:“Docker 已经采用这项技术来解决应用开发问题。

“我们从 IT 优化的角度来看待集装箱。我们使用容器在裸机上提供零性能影响虚拟化，”Kumar 说。“人们可以将无法部署在 Docker 容器上的要求苛刻的企业应用程序部署在容器上进行整合，而不会影响性能。这关系到部署、服务质量和应用程序生命周期管理。我们端到端地处理整个应用程序。

“就像虚拟化让机器变得更加敏捷一样，我们又向前迈进了一步。我们将应用程序视为本机实体，从加速部署到管理性能和服务质量，我们无所不为。”

他解释说，每个容器都暴露在一个原始设备中，所以看起来像是有本地存储。该原始设备只能被该容器看到，这是数据隐私。

“因为我们控制着从应用程序到主轴的所有 I/O 路径，所以我们可以标记 I/O，并确保从应用程序到磁盘的所有可预测的性能，”他说。

存储在后端集中式存储层上完成，因此即使计算层看到虚拟存储层，数据也会在存储层的多个不同节点上进行分条。

“如果应用程序死亡，我们的软件可以透明地处理这种情况，方法是启动无状态容器或幸存节点上的任何容器，并将它们重新路由回存储卷。因此，它使计算层更强大、更有弹性和可替代性，”库马尔说。

任何数据都分布在多个磁盘驱动器上，以防止机器停机。

他说:“以数据为中心的工作负载的关键优势在于，像 Hadoop 这样的大多数分布式应用程序都进行串行复制，它们这样做是因为商用硬件不具备保护数据的智能。“当您拥有数 Pb 的数据时，仅拥有两个数 Pb 的数据来拥有另外两个副本就非常昂贵。因为我们使用擦除编码等技术在存储层保护数据，所以我们的客户能够完全关闭三向复制，或者恢复双向复制，并恢复 50%的存储容量。”

特征图片: [Calsidyrose](https://www.flickr.com/photos/calsidyrose/) 的[鸟尾纸](https://www.flickr.com/photos/calsidyrose/4606988133/in/photolist-82724T-34Ydj3-7B5fbe-3qAHLk-6RHmg4-7B5fbn-qN2ytU-8bnb7h-fKi35t-8bnaLf-8corT4-8biQi2-nSY2ky-bFtrLa-6wdQXY-qLJpU1-8bn9Jo-86Hdkt-snJwGd-57ySQ4-5sh1fi-aqxbPz-8CmV2r-8bn7cL-8bn7Y9-8bn6S5-5HeT7T-5HjbJU-snHCwE-m1n7o-rHi6Eb-sEi2oc-c5ZCKs-8bn6s5-c5ZCG7-eEFoAr-9aXYkz-c4i8Vw-9b21bL-9c1dgW-rpUC1R-4Zpjgk-9EGBeE-CzgKVv-F4Qm7R-FWNijN-snJBQu-rksnuc-9Diw7r-Cx2pXq)，授权于**的[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)T7。**

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>