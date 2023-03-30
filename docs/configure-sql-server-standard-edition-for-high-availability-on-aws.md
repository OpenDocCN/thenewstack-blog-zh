# 为 AWS 上的高可用性配置 SQL Server Standard Edition

> 原文：<https://thenewstack.io/configure-sql-server-standard-edition-for-high-availability-on-aws/>

人们并不总是清楚如何在亚马逊网络服务上为微软 SQL Server 标准版构建高可用性(HA)基础设施。

毕竟，在 AWS 上部署 SQL Server 有两条不同的途径。一个涉及亚马逊关系数据库服务(Amazon RDS)，另一个涉及亚马逊弹性计算云(Amazon EC2)。

其中任何一个都可以跨多个可用性区域(本质上是独立的数据中心)进行配置，以确保数据中心没有单点漏洞。

亚马逊 RDS 是完全托管的服务；您只需要告诉 AWS 您想要一个多中心的 SQL Server 实例。AWS 将为您设置好，然后您就可以开始运行了。

但是，使用 Amazon EC2，您将需要完成设置和维护基础设施的大部分工作。AWS 将部署并支持您选择的底层虚拟机(VM ),它将确保 VM 上运行的操作系统得到正确配置和更新，但在 Amazon EC2 上，从那以后您就可以控制了。

Amazon RDS 使启动和运行变得容易，但是 Amazon EC2 给了你更大的灵活性和控制力。您为 SQL Server Standard Edition 的高可用性部署选择的环境取决于您想要使用的 [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) 的版本、您要使用的数据库数量以及您想要确保的高可用性级别。

## 使用哪个版本的 SQL Server？

让我们从您打算使用的 SQL Server 版本开始。毕竟，如果您已经在使用 SQL Server 的某个特定版本，并且正在考虑迁移到具有相同版本的 AWS，那么您将希望确保您可以在您选择的环境中使用该版本。

Amazon RDS 支持当前主流的或扩展支持的 SQL Server 标准版的所有版本。实际上，这意味着 2014、2016、2017 和 2019 版本的 SQL Server。只要您有兴趣使用其中一个版本，Amazon RDS 就可以用您指定的 SQL Server Standard Edition 版本配置一个 HA 解决方案。

但是，如果您想要运行的应用程序依赖于 SQL Server 的另一个版本，比如 2012 年或 2008 年 r 2 版本，那么您必须选择 Amazon EC2。Amazon EC2 只为您的 HA 配置提供虚拟硬件；在该虚拟机上，您可以运行所需的任何 SQL Server 许可版本。

## 您将运行多少个 SQL Server 数据库？

在决定是在 Amazon RDS 还是 Amazon EC2 上运行 SQL Server Standard Edition 时，这很快成为一个重要问题。Amazon RDS 通过使用 SQL Server 的基本可用性组(AG)功能来确保 HA。

这确保了写入连接到活动虚拟机的存储中的 SQL Server 数据库的任何数据也将写入连接到位于另一个 AZ 中的辅助虚拟机的存储中的 SQL Server 数据库的副本。

如果活动基础架构由于某种原因离线，SQL Server 的基本 AG 功能将故障切换到辅助基础架构，您的操作可以继续进行，中断最少。因为以前活动的 SQL Server 实例中的数据已经存在于辅助基础架构的存储中，所以您实际上可以从主基础架构离线之前停止的地方继续操作。

依靠基本 AG 功能来确保 Amazon RDS 上的 HA 的缺点是，SQL Server Standard Edition 只允许在活动和辅助基础架构之间复制一个 SQL Server 数据库。您也许可以创建多个 ag，每个 ag 复制一个 SQL Server 数据库，以克服这一限制，但是这很快就变得很麻烦。

每个 AG 都有自己的监听器，不能保证所有的数据库都会一起故障转移。如果您的数据库相互依赖，这可能会导致问题。如果您要使用 SQL Server 企业版中内置的“永不停机”AG 功能来配置 Amazon RDS 基础架构，则可以在一个 AG 中复制多个 SQL Server 数据库，但这需要您从 SQL Server 标准版迁移到更昂贵的 SQL Server 企业版。

如果您致力于使用 SQL Server 标准版，Amazon EC2 为您提供了确保 HA 的其他选项。

除了在 Amazon EC2 环境中使用 SQL Server Standard Edition 中的 AG 功能，您还可以在所谓的故障转移集群实例中配置您的虚拟机，并依靠 SIOS 的[无 San 集群](https://us.sios.com/products/sios-datakeeper/)软件来协调数据复制。无 San 集群软件将数据从主基础架构复制到辅助基础架构，就像 SQL Server 中的 AG 功能一样，但无 San 集群方法对可以从一个基础架构复制到另一个基础架构的数据库数量没有限制。

您的主基础架构上的所有 SQL Server 数据库都可以复制到辅助基础架构上，与在 Amazon RDS 上升级到 SQL Server Enterprise Edition 相比，您将以更低的成本获得这一好处。

## 您的环境需要什么级别的可用性？

在权衡 Amazon RDS 与 Amazon EC2 选项时，要考虑的最后一个区别是您需要的应用程序可用性程度。

Amazon RDS 是一项完全托管的服务，这无疑减轻了 IT 团队的负担。然而，在 Amazon RDS 下为 HA 提供的[服务级别协议](https://thenewstack.io/when-99-service-level-objectives-are-overrated-and-too-expensive/) (SLA)是 99.95%可用性，而在 Amazon EC2 下提供的 SLA 是 99.99%可用性。

99.95%的 SLA 意味着在 Amazon RDS 环境中，您的 SQL Server 配置每年可能会离线长达 4 小时 22 分钟，但仍然符合 SLA。在停机事件期间，您的任何虚拟机或 SQL Server 数据库都将无法访问。相比之下，亚马逊 EC2 SLA 为 99.99%，每年停机时间不超过 53 分钟。

在这里，真正由您来决定您最终需要的可用性级别。如果每年超过 53 分钟的潜在停机时间是不可接受的，那么 Amazon EC2 是正确的选择。如果您只有一个要复制的数据库，您可以使用 SQL Server Standard Edition 的基本 AG 功能，但是如果您有多个需要从主基础结构可靠地复制到辅助基础结构的数据库，您可以使用无 San 群集软件来复制数据库。

您还可以选择使用您想要的任何版本的 SQL Server，如果您仍然依赖于一个已有十多年历史的 SQL Server Standard Edition 版本，并且不想将您的应用程序移植到 SQL Server 的更高版本，这一点可能非常重要。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>