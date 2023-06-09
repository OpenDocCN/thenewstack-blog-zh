# 为高可用性配置 Google 云平台

> 原文：<https://thenewstack.io/configuring-for-high-availability-in-google-cloud-platform/>

[](https://us.sios.com/)

 [大卫·伯明罕

大卫·伯明罕是 SIOS 科技公司的技术传道者。他是技术社区公认的高可用性专家，并在过去八年中荣幸地当选为微软 MVP:六年当选为集群 MVP，两年当选为云和数据中心管理 MVP。David 拥有多项技术认证，并拥有三十多年的 IT 经验，包括在金融、医疗保健和教育领域。](https://us.sios.com/) [](https://us.sios.com/)

以下是将内部 SQL Server 基础架构迁移到谷歌云平台(GCP)的指南，通过多区域集群，您可以确保系统 99.99%的正常运行时间。

您需要回答的第一个问题是您需要什么样的虚拟机。在 GCP 选择基础架构比选择本地部署的物理服务器要细致得多。幸运的是，Google 雇佣了一个客户工程师团队，他们可以帮助您确定 SQL Server 负载所需的计算能力、RAM 和存储的组合。

如果您运行的应用程序需要高可用性集群计划，那么一旦您确定了该基础架构的样子。对于 GCP 的高可用性，您需要在两个不同的 GCP 区域构建您的 SQL Server 基础架构。然后，您将需要一种方法来确保如果一个 SQL Server 实例出现故障(即使在云中也可能发生这种情况)，另一个实例可以毫不迟疑地接管负载。

## 实现高可用性的两条途径

在 GCP，为高可用性配置 SQL Server 基本上有两种方法。一个是使用 SQL Server 本身内置的技术创建一个永不停机的可用性组(AG)。另一种是创建所谓的无 San 集群，它将第三方提供的技术与 Windows Server 故障转移集群(WSFC)相结合。

从根本上说，它们的工作方式是相似的:一旦确定了支持 GCP 的 SQL Server 工作负载所需的实例大小，您将在一个独立但邻近的 GCP 区创建第二个相同大小的实例。请注意，对于真正的高可用性，仅有两个 SQL Server 实例是不够的；他们需要居住在 GCP 的不同区域。任何危及整个区域运行的事件(例如，数据中心范围的电源故障)都会导致主实例和辅助实例都无法运行，如果它们位于同一区域的话。

通过将它们放置在单独但相邻的区域中，您可以增加 SQL Server 部署保持运行的可能性，因为单独的 GCP 区域同时脱机的可能性要低得多。事实上，如果您将 SQL Server 的主实例和辅助实例放在同一区域，GCP 将为您提供高达 99.95%可用性的可用性服务级别协议(SLA)。为了获得完整的四个 9(99.99%的可用性)，您需要将第二个实例放在单独的区域中。

GCP 的最大优势之一是其内部通信基础设施，连接 Google 区域内各区域的连接提供了足够的吞吐量，即使在两个独立的区域中，您的 SQL Server 实例也可以非常高效地进行通信。这一点很重要，因为 AG 和 SANless 集群解决方案都会将数据从您的主 SQL Server 同步复制到辅助区域中的另一个实例。这也是云中高可用性的关键。您无法使用任何类型的共享存储在 GCP 构建真正的高可用性解决方案，原因与您无法将两个 SQL Server 系统放在同一个区域中一样。将您的关键 SQL Server 数据库存放在任何类型的共享存储上都会产生单点漏洞，而 HA 就是要消除这些单点漏洞。

因此，AG 和 SANless 集群方法都会复制您的 SQL Server 数据库，以便辅助服务器(如果您配置了多个备份系统，则为多个服务器)始终拥有主系统数据库的最新副本。如果 SQL Server 的活动实例出现故障，HA 解决方案将自动故障切换到辅助实例，辅助实例将立即接管工作负载，并使用主基础架构中运行的相同数据的拷贝。

## AG 和 SANless 聚类对比

那么 AG 和 SANless 聚类方法之间有什么区别呢？区别在于实现的细节。AGs 和 SANless 群集解决方案都依赖于 Windows Server 故障转移群集(WSFC ),这是一种内置于 Windows Server 中的技术，可在检测到故障时实现群集应用程序的快速、自动故障转移。然而，从那以后，方法就不同了。

AG 功能内置于 SQL Server 本身。这有两个实际后果:首先，AGs 只处理与 SQL Server 相关联的数据文件。如果 SQL Server 数据库旁边的存储中有任何非 SQL 文件，AG 复制服务将不会复制这些文件。此外，AGs 只复制用户定义的 SQL Server 数据库。SQL Server 本身创建的任何数据库(包括作业和密码数据库)都不会被复制。如果支持您的主 SQL Server 系统的基础架构最终离线了一段时间，这是需要考虑的事情。您可能希望在辅助 GCP 基础架构上备份这些系统数据库，但是您必须通过一些其他方法来管理这些数据的复制。

其次，SQL Server Standard edition 附带的基本 AG 功能允许每个 AG 仅复制一个 SQL Server 数据库。如果您需要为每个 AG 复制多个数据库，或者如果您计划将该数据复制到多个辅助系统，则需要部署 SQL Server Enterprise Edition 内置的 Always On AG 功能。如果您习惯于运行 SQL Server Standard Edition，这将是一次昂贵的升级。

相比之下，无 San 集群方法不受 SQL Server 的限制。它与应用程序无关，只关注将数据块从一个存储系统复制到另一个存储系统。这种独立性的实际结果是，无 San 集群解决方案不仅会复制用户和系统命名的 SQL 数据库，还会复制存储在 SQL Server 数据库所在磁盘上的任何其他文件。不需要单独的复制过程来确保数据的可用性。

此外，因为无 San 群集复制只关注 1 和 0，所以它不会计算正在复制多少个 SQL Server 数据库。它只是跨 GCP 区域复制数据块。如果您的工作负载涉及在 SQL Server Standard Edition 上运行的多个 SQL 数据库，则 HA 的无 San 集群方法使您能够复制任意数量的数据库，而无需升级到 SQL Server Enterprise edition。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>