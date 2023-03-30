# TidalScale 为大规模应用创造了单一的 DRAM 海洋

> 原文：<https://thenewstack.io/tidalscale-creates-single-ocean-dram-large-scale-applications/>

TidalScale 专注于需要大量内存的客户，例如计算基因组学和大规模模拟和分析，它创建了一个平台，可以将商用服务器硬件聚合到一台软件定义的超级计算机中，而无需相应的费用。

[TidalScale](https://www.tidalscale.com/) 的软件定义的服务器刚刚获得了一个点击式控制面板，可以更轻松地动态创建和有效地向服务器分配资源。

WaveRunner 控制面板使从单一界面动态控制服务器、存储和网络基础设施成为可能。该公司还推出了一种新的 RESTful API 设计，允许 TidalScale 与第三方 REST 兼容的测试和数据集成平台和工具一起运行，如 Jenkins、Docker 等。

“我们试图解决的问题是对灵活数据中心的需求。数据类型和在其上运行的内容分析呈爆炸式增长，而且不可预测。TidalScale 产品经理 [Chuck Piercey](https://www.linkedin.com/in/cpiercey/) 说:“事情变化如此之快，你真的不能静态地定义你的服务器及其性能。

“软件定义的服务器允许您使用商用硬件，并[设置]一台大小完全适合您的工作负载的服务器。”

这家总部位于加州坎贝尔的公司由[艾克·纳西](https://en.wikipedia.org/wiki/Ike_Nassi)于 2012 年创立，他在 SAP 开发其 HANA 内存数据库时担任首席科学家。

在它所谓的“反向虚拟化”中，TidalScale 创建了一个 DRAM(动态随机存取存储器)计算能力的海洋。通过虚拟化 CPU、内存和 I/O 资源，它可以根据需要将组合资源用于工作负载。皮尔斯解释说，这些资源可以像潮水一样流入流出，因此该公司得名。

该技术基于 FreeBSD 管理程序 [bhyve](http://bhyve.org/) 。

它采用了一个分布式虚拟机管理程序的薄层，称为超级内核，运行在计算机集群的每个节点上，或者软件定义的服务器，称为 Tidalpod。超级内核使用机器学习来优化流程，以便在物理服务器之间扩展和共享 CPU、内存、存储和 I/O。

应用程序不需要任何代码更改，甚至不知道它们正在多个服务器上运行。

超内核在该集群上引导一个单一系统映像(SSI)作为客户机。它采用了一个[非统一内存访问](https://technet.microsoft.com/en-us/library/ms178144(v=sql.105).aspx) (NUMA)集群，但是通过在集群中运行的超内核的薄层，它向来宾呈现了一个统一的内存架构。

[https://www.youtube.com/embed/JoPnAz8FXic?feature=oembed](https://www.youtube.com/embed/JoPnAz8FXic?feature=oembed)

视频

## 反向虚拟化

在横向扩展中，超内核将操作系统和数据库整合为一个操作系统和一个数据库，而不是多个操作系统和数据库。

Piercey 说，在内部，TidalScale 只是将 Docker 用作一个容器，但它的一个大学客户允许学生将他们的项目作为 Docker 容器部署在 TidalScale 产生的资源库中。

用户可以使用他们习惯的工具工作，如 Hadoop、MongoDB、Spark 或 MySQL。它只是一台大电脑。Berman 说，开发人员不需要花时间担心分片或处理器位置，因为超级内核会在幕后处理这些问题。

去年夏天，该公司在圣何塞的 IBM 云数据中心使用未经修改的 CentOS 7.2 操作系统在 IBM Bluemix 上创建了一个 15TB 的集群。

“在[圣安东尼奥的德克萨斯大学]，我们正在实施软件定义的服务器，以便我们能够在研究人员的工作负载需求发生变化时，以敏捷、响应迅速的方式为他们提供计算和存储云容量，”德克萨斯大学电气和计算机工程助理教授 Jeff Prevost 表示。“TidalScale 软件中的新功能将帮助我们实现按需扩展和重新配置资源所需的灵活性和精细控制。”

软件定义的服务器也被用作该大学[开放云研究所](http://opencloud.utsa.edu/)的研究机构的现代云数据中心的参考实施。

今年 3 月，TidalScale 宣布合作在 [OrionVM 批发云平台](http://www.orionvm.com/)上提供托管的软件定义的服务器，为面临大数据、分析和内存密集型计算挑战的企业提供 1.3TB 至 13TB 的 DRAM 容量和多达数百个内核。

在将该公司评为 2017 年最酷的供应商之一时，Gartner 分析师 [Stanley Zaffos](https://twitter.com/stanleyzaffos) 写道，“TidalScale 声称为计算和/或内存密集型应用提供近乎线性的性能可扩展性是可信的，如果没有得到充分证明的话——首先考虑到可能使用这种技术的应用的性质。

在它的吸引力中，他提到了它能够减少对大型(超过 4 个插槽)、昂贵服务器的需求，以及它能够高效地重新部署旧服务器。

他还指出了能够使用具有本地存储资源的软件定义的服务器的安全影响，这消除了在运行应用程序之前将数据移动到直连存储(DAS)或云中的需要。

同时，他指出:

TidalScale 的主要价值主张是在松散耦合的物理服务器上分布应用程序，同时线性扩展性能和吞吐量，这违背了许多 IT 专业人员的经验，他们了解编写多线程代码的困难，并知道与松散耦合的多处理器(MP)配置相关的性能瓶颈(也称为 MP 因素)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>