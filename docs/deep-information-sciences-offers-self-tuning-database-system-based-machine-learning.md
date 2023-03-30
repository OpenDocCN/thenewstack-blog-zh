# Deep Information Sciences 提供了一个基于机器学习的自调优数据库系统

> 原文：<https://thenewstack.io/deep-information-sciences-offers-self-tuning-database-system-based-machine-learning/>

在日益拥挤的数据库世界中，Deep Information Sciences 通过其最新发布的 deepSQL 重新构想了大数据和云的数据库。

该软件包将机器学习与关系数据库相结合，旨在以云规模  同时运行数据流、交易和分析。它基于创始人兼首席技术官 [Thomas Hazel](https://twitter.com/thomashazel) 对数据库背后的基础科学的十年研究。

首席战略官 Chad Jones 在提到 B 树、B+树和其他算法时表示:“自 20 世纪 70 年代末以来，数据库科学在算法层面一直没有进步。“一个擅长写作，一个擅长阅读，但他们不能两者兼顾，你必须不断优化他们。”

琼斯说:“在 21 世纪的 T4，我们已经发现这些算法可以走多远，它们确实阻碍了我们做很多事情，比如弹性伸缩和我们想在云中做的事情。”

这家总部位于波士顿的公司成立于 2010 年。它在去年 4 月将 deepSQL 推向市场，然后添加了 Docker 支持，并在 9 月加入了 AWS Marketplace。它的最新版本是上个月发布的，称之为“[自适应数据库](http://insidebigdata.com/2015/10/10/adapt-or-die-machine-learning-databases-for-the-new-economy/)”它已经从适马 Prime Ventures、Stage 1 Ventures、AlphaPrime Ventures 和其他公司获得了 1800 万美元的投资。

该公司旨在解决与传统数据库相关的问题，包括限制灵活性、性能和规模的并发性、缓存和校准。另外，它被吹捧为“自我调整”——不需要人为优化。

该公司此前提供了一个自适应引擎，位于 MySQL 或 Percona 数据库下；据 451 Research 的分析师 Jason Stamper 称，它现在更进一步，集成了其开源数据库发行版，同时保持与 MySQL 生态系统的兼容。

该公司对传统数据库问题的解决方案被称为 CASSI(连续适应顺序信息摘要),它基于自调整循环，包括四个阶段:观察和分析；预测和适应；编排和优化；并结束循环。

对于传统数据库，DBA 必须优化不同的参数来调整应用程序的性能。

“问题是，如果我要做所有这些需要重启数据库的事情，或者在某些情况下需要重建数据库，我是离线进行的，这需要反复试验。而且他们是针对写操作或读操作进行优化，而不是两者都优化，”Jones 解释道。

“我们能够把内存和磁盘分开，”琼斯说。“我们已经将这些东西分离出来，以便它们可以独立配置。我们已经实现了机器学习，它能够模拟机器上的资源、机器上的工作负载类型及其要求，以及机器内部的信息、结构、元数据等。”

当工作负载与系统交互时，在保持在线的同时，机器学习将预测需要组织到内存中的内容，以处理工作负载的并发运行。

“假设我有一个数据库，我遇到了暴风雪，铁锹卖得很疯，我想知道卖出了多少袋岩盐，这样我就可以提供‘买一把铁锹，一袋岩盐打八折’，”琼斯说。

“通常，我必须获取这些信息，进行 ETL[提取、转换和加载]到一个单独的数据库中，并对其进行分析，这需要很多时间。这降低了对正在发生的事件的洞察力的深度，”他说。

“我们能够做的是，当事件发生时，机器学习将观察正在发生的事情；它将监视事务，现在我得到了一个针对分析优化的工作负载。我将动态地重新组织信息在内存中的呈现方式，这样我不仅可以快速处理事务，还可以处理从数据中获取信息的分析。”

DeepSQL 以可追加的方式写数据。

“我不必坐在那里问，‘哪里有空位？’然后写入，因为这需要 IOP 从系统的 IOP 角度来看，这需要大量开销。大多数系统在受到 CPU 或内存限制之前，在可伸缩性方面都会受到 IOPS 的限制。因此，向数据库扔一台更大的机器并不一定能获得更大的可伸缩性，因为一旦 IOPS 用完，更多的 CPU 和内存也无济于事，”他说。

他说 deepSQL 减少了 80%的 IOPS，然后当你增加 CPU 和内存时，就有了可预测的线性可伸缩性。

“当我添加这些资源时，我们的数据库内核会理解，因此如果我有一个虚拟化平台，我可以动态添加 CPU 和内存，它会识别并开始使用它，而无需人工干预。所以数据库管理员不必坐在那里优化它。机器学习根据不断变化的工作负载来处理所有这些问题，因此系统可以读取、写入和处理查询，其性能水平是我们所有竞争对手的 64 倍，”他说。

他说，大多数数据库性能的提高只是通过转移到固态硬盘，而内存甚至更快。

对于内存系统，“我的数据库只能和我的内存一样大，这并没有改变科学。这是一个更快的媒介，但权衡是令人难以置信的。如果我拔掉电源线，我会丢失内存中的数据库。我们能够做到的是最好的内存系统，在磁盘上具有 [ACID](http://databases.about.com/od/specificproducts/a/acid.htm) 合规性。一些内存系统在后面写入磁盘，但我们说内存中需要所有数据来回答传入的问题和进行写入等，我们会预测您需要什么，但我们会在数据传入时尽快将其写入磁盘，这样您就可以两全其美。”

他说，该公司刚刚做了一个例子，在一个带索引的表中有 1.2 万亿行，在 0.3 秒内从这些行中返回 1200 条记录。

Stamper 表示，他看到越来越多的公司对能够在同一个数据库上处理分析和事务性工作负载感兴趣，因为他们寻求更快的问题答案，并试图避免两种工作负载分开处理时所需的 ETL(提取、转换和加载)步骤。

然而，他表示，这可能不再是 SQL 的最大优势。

“这是因为我们相信，它的自我调整能力，加上它的可扩展性，使它成为一个有吸引力的命题，对于许多行业来说，他们开始发现他们的数据库是昂贵的或劳动密集型的，以扩大或扩大，”斯坦普说。

该公司拥有一系列客户，包括克罗地亚的 Ruder Boskovic 基因组研究所和 WordPress 管理的托管服务提供商 GEMServers。

它的速度和自调优能力对佛罗里达州立大学的研究计算中心(RCC)很有吸引力，RCC 是一家高性能计算/超级计算商店，没有专门的 DBA 员工。

RCC 临时主管兼运营经理 Paul Van Der Mark 表示，deepSQL 非常适合处理复杂数据集但不是数据库专家的研究人员。

“我们有几个教员需要在 20 到 40 GB 的‘大型’数据库上运行查询，我们甚至有一个研究人员从未自己编写过 SQL 查询，”他说，并补充说基因组和气象数据集要大得多，“他说我们测试了 Deep 引擎，发现与标准 MySQL 存储引擎相比，它提供了非常好的性能，而无需手动调整变量。"

DeepSQL 集成了流行的云自动化平台，包括 BOSH、Cloud Foundry、Chef、vCloud Director、vagger、Compose、OpenStack 和虚拟化平台，包括 VMware、KVM 等。**

特征图片:[托拜厄斯·韦扬德](https://www.flickr.com/photos/0xtob/)的[下](https://www.flickr.com/photos/0xtob/13179033293/in/photolist-m5zZrX-e3ya4U-43umN-8GaEHP-pMWVdy-atri3a-6SiRUL-52Q9dA-deemGL-6Sj8iu-6SjE4y-9q6WQz-6SifJd-qJjSxi-P3wiM-6SiQJC-3j7SE-9q9ZXC-6SirmU-6SiSCN-BptDW-bftu5n-oqHzr2-Jpyac-vVWee-9jYNRQ-kJTcjH-cFWYby-rAddpB-7h7iDf-oDBTam-7h7iRb-iXFWSA-ouBMHg-o5yDZM-8mPBcL-m9LHS5-c8KNg3-kJTXiT-qG4PXp-zFNDL-4HNKAo-qAqszN-7YafAL-qskF3N-yRFf4-mVHb1q-ELp8o-b9KjEM-713z7x)，授权**下 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>