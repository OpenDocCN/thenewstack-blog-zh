# 为什么要分区存储，为什么是现在？

> 原文：<https://thenewstack.io/why-zoned-storage-and-why-now/>

[](https://www.linkedin.com/in/swapna-yasarapu-a4a0282/)

[Swapna Yasarapu](https://www.linkedin.com/in/swapna-yasarapu-a4a0282/)

[Swapna Yasarapu 是西部数据公司数据中心 SSD 闪存的高级主管。Swapna 拥有超过 20 年的混合战略领导和技术专业知识，为数据中心客户提供产品。Swapna 拥有加州大学洛杉矶分校安德森管理学院的营销和战略 MBA 学位，以及加州大学尔湾分校的计算机系统和软件理学硕士学位。](https://www.linkedin.com/in/swapna-yasarapu-a4a0282/)

[](https://www.linkedin.com/in/swapna-yasarapu-a4a0282/)[](https://www.linkedin.com/in/swapna-yasarapu-a4a0282/)

我们知道数据继续以惊人的指数速度增长。据 IDC 全球数据圈[称，未来三年创建的数据量将超过过去 30 年创建的数据量。数十亿个互联系统将从智能视频、消费者和传感器中产生无数的情境化数据，这些数据必须被捕获、转换和分析，才能为行业、企业和人们带来价值。](https://www.businesswire.com/news/home/20200508005025/en/IDCs-Global-DataSphere-Forecast-Shows-Continued-Steady)

存储是从数据中创造价值的基础。面临的挑战是如何高效、经济地构建数据存储基础架构，以满足数据需求，同时降低总拥有成本(TCO)。

尽管业界继续提高硬盘驱动器(HDD)和固态驱动器(SSD)介质的位密度以跟上数据增长，但仍需要新的方法来大规模提高存储效率。为了应对 zettabyte 级时代的挑战，现在应该考虑的一项创新和架构是[分区存储](https://www.westerndigital.com/company/innovations/zoned-storage)。

分区存储使云服务提供商和企业数据中心客户能够构建更高效、高度可扩展的数据存储层，以极具竞争力的总拥有成本满足不断增长的数据需求。在开放规范和 Western Digital 等公司的支持下，分区存储汇集了基于标准的工具、库、资源和一个技术文档网站 [ZonedStorage.io](http://zonedstorage.io/) ，使数据中心架构师能够了解和利用分区块管理的优势。分区块管理背后的技术意味着主机和存储应用程序都可以智能地大规模放置数据，以充分利用最高的可用存储容量，通常采用叠瓦磁记录(SMR)硬盘和最近批准的 NVMe 固态硬盘分区命名空间(ZNS)标准。

## 新工作负载，新方法

过去十年中出现了超大规模数据，带来了创建、消费、处理和货币化数据的巨大规模和贪婪性。如今，许多现代大规模工作负载自然地序列化或写入更大的顺序区块中，包括在线备份和归档、视频监控、物联网和其他机器生成的数据、法规遵从性数据以及其他应用程序。存储密度、瓦特/TB 和 TCO 是这些工作负载成功的关键参数。

现在是变革的大好时机，但需要以不同的方式访问和管理存储，更好地了解数据的工作负载结构，以及如何将数据放置在介质上以实现最佳效率。分区存储为开发人员和架构师提供了工具和资源，以智能地将数据放置在 HDD 和 SSD 介质上，并进行优化以获得更好的性能、更短的延迟、可预测的 QoS，最重要的是，更高的密度和更低的 TCO。

## 分区存储的味道

分区块管理背后的技术意味着主机和存储应用程序都可以智能地大规模放置数据，以充分利用最高的可用存储容量，通常采用 SMR 硬盘和最近批准的 NVMe 固态硬盘 ZNS 标准。

SMR 是硬盘特有的，其中数据磁道相互重叠，利用了读磁头的尺寸比写磁头小得多的事实。通过将 HDD 数据轨道重叠或“叠放”在彼此之上，可以在相同的占地面积内实现更高的面密度和容量。 [Dropbox](https://dropbox.tech/infrastructure/smr-what-we-learned-in-our-first-year) 转向主机管理的叠瓦式磁记录(SMR)硬盘，使用 SMR 比传统硬盘多存储 20%,同时节省了 20%。Dropbox 继续其战略路线，利用[最高的存储密度和最低的 TCO](https://www.westerndigital.com/company/newsroom/press-releases/2020/2020-10-26-western-digital-and-dropbox-team-to-accelerate-deployment-of-cloud-infrastructure) 为其云基础设施服务，为其 6 亿多在线客户服务。

ZNS 带来了最适合多租户、超高容量驱动器、改进的性能、QoS 和利用率的新一代固态硬盘，同时最大限度地降低了公共云和内部企业基础架构的总拥有成本。

> 分区存储使云服务提供商和企业数据中心客户能够构建更高效、高度可扩展的数据存储层，以极具竞争力的总拥有成本满足不断增长的数据需求。

ZNS 将 SSD 划分为固定大小的区域，在每个区域内按顺序写入。但现在，这些区域与 NAND 本身的底层架构(芯片、平面、读取页面、擦除页面)紧密相连，因此将数据视为一个块可以消除很多复杂性。

ZNS 固态硬盘和 SMR 硬盘遵循业内类似的现有协同效应，因此可以在标准化的统一分区存储软件框架下跨 ZNS 固态硬盘和 SMR 硬盘利用主机软件。

通过部署 ZNS 固态硬盘，使用 ZNS 将数据中心性能提高了 4 倍，QoS(服务质量)提高了 2.5 倍。在当前传统的基于 SSD 的部署中，应用程序无法将数据放置智能从主机向下传递到 SSD。因此，使用传统固态硬盘部署的应用程序通常会产生较高的 WAF(写入放大),因为当数据写入到跨应用程序堆栈一直到固态硬盘的介质时，每一层都会独立执行垃圾收集。这会导致整个部署效率低下，从而降低应用程序的整体性能和服务质量。而在基于 ZNS SSD 的部署中，应用程序可以通过将数据写入分区来智能地将数据放置在 SSD 中，从而消除 WAF 倍增，并为应用程序提供一致的高 QoS。

## 为什么现在是进入状态的时候了

该行业正处于一个转折点，存储效率的提高不仅要靠更高的位密度，还要靠应用程序和操作系统智能地将数据放入存储设备方面的重大进步。通过不再将所有存储设备都视为随机 I/O、512K/4KB 扇区体系结构，并采用生命周期与分区存储 HDD 和 SSD 的实际物理特征相似的顺序写入数据块来适应许多大规模工作负载，可以实现 TCO 收益。

分区存储计划使数据中心架构师能够立即开始为 SMR 硬盘和 ZNS 固态硬盘进行设计，不仅可以利用最高容量的数据存储解决方案，还可以前瞻性地考虑他们的长期数据战略，并优化他们的工作负载，以尽可能最佳的总拥有成本实现更高的效率和性能。通过为 SMR 硬盘和 ZNS 固态硬盘利用统一的软件堆栈，云提供商和数据中心架构将收回这一投资，并为未来的数据增长提供扩展空间。

帕特里克·托马索在 [Unsplash 上拍摄的特写照片。](https://unsplash.com/collections/1817672/shapes?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>