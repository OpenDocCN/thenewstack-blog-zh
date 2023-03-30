# 谷歌云的分布式关系数据库扳手走向全球

> 原文：<https://thenewstack.io/google-takes-cloud-spanner-global/>

谷歌 Cloud Spanner 是谷歌平台的分布式关系数据存储服务，今年早些时候作为区域服务发布，现已全球化。

最初的[版本](https://thenewstack.io/google-cloud-spanner-view-field/)提供了跨三个[可用区域](https://cloud.google.com/compute/docs/regions-zones/)的数据同步。随着谷歌[多区域配置](https://cloudplatform.googleblog.com/2017/11/with-Multi-Region-support-in-Cloud-Spanner-have-your-cake-and-eat-it-too.html)的发布，它提供了跨多个可用区域以及跨地区和大洲的同步。

“对于全球化的客户，他们拥有全球用户群，并且想要一个全球数据库，以确保他们的关键任务数据可用，最新准确，这就是 Cloud Spanner 提供的选项，”Cloud Spanner 的谷歌产品经理 Deepti Srivastava 说。

Srivastava 说，Spanner 是从零开始建立的，一直拥有这种全球能力，但该公司希望获得客户对它的反馈。

“我们希望确保我们不只是为了技术而发布酷技术，而是我们实际上在解决客户的问题，客户确实需要这样做，”她说。

此外，它提供了 99.999%的可用性服务级别协议，没有计划内停机，每年停机时间不到五分钟。她说，这表明了该公司对该系统可靠性的信心水平。

该公司吹捧该数据库提供了熟悉的关系数据库语义和非关系规模和性能。人们谈论最多的功能之一是通过 GPS 接收器和原子钟提供的交易的高度一致性，这是一种名为 [TrueTime](https://research.google.com/pubs/pub45855.html) 的计时技术。

[https://www.youtube.com/embed/UKz4vXO4MxY?feature=oembed](https://www.youtube.com/embed/UKz4vXO4MxY?feature=oembed)

视频

实际上，Spanner 创建了一个全球关系数据库，而不仅仅是一个在全世界复制数据的特性。但是仅仅因为它提供了这种能力并不意味着每个公司都应该使用它。

世界各地各种各样的数据治理法规，包括将于 2018 年 5 月提交欧盟的[通用数据保护法规](http://www.eugdpr.org/) (GDPR)，专家表示，大多数公司都没有做好准备，这给这样一个数据库的使用带来了巨大的挑战。

Srivastava 说，这也是 Spanner 早期仅作为区域性产品发布的原因之一。

“如果你有数据治理法规，我们总是建议你使用区域产品，因为这样你就可以保证数据只在该区域内复制，”她说。

在 MySQL 实现中所需的手动分片变得过于笨拙之后，谷歌内部开发了 Spanner 来支持诸如 [AdWords](https://adwords.google.com/) 和 [Google Play](https://play.google.com/) 等服务。在内部使用了近 10 年后，它发布了 Cloud Spanner。

营销自动化提供商 [Marketo](https://www.blog.google/topics/google-cloud/welcome-our-latest-alliance-and-gcp-customer-marketo/) 和加拿大电信计费服务 [Redknee](https://www.redknee.com/) 等客户已经转移到 Spanner。

在未来几个月，笔记网站 [Evernote](https://www.pcworld.com/article/3167594/data-center-cloud/heres-how-evernote-moved-3-petabytes-of-data-to-googles-cloud.html) 计划用单个 Cloud Spanner 实例替换 750 多个 MySQL 实例，以管理超过 80 亿条客户笔记。

对于开发人员来说，Spanner 提供了 Java 数据库连接( [JDBC](https://en.wikipedia.org/wiki/Java_Database_Connectivity) )驱动程序和 Java、Go、Python 和 Node.js 等语言的软件开发工具包，微软开放数据库连接( [ODBC](https://docs.microsoft.com/en-us/sql/odbc/microsoft-open-database-connectivity-odbc) )驱动程序和 C# SDK 正在开发中。

[cocroach db](https://thenewstack.io/cockroachdb-1-0/)，最近宣布的 [YugaByte](https://thenewstack.io/yugabyte-new-database-solve-sql-vs-nosql-dilemma/) 和中国项目 [TiDB](https://github.com/pingcap/tidb) 也旨在创建像 NoSQL 系统一样可扩展的 SQL 数据库，同时维护 [ACID 事务](http://www.service-architecture.com/articles/database/acid_properties.html)，但是它们没有复制 TrueTime。

谷歌云是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg viewBox="0 0 68 31" version="1.1" xmlns:xlink="http://www.w3.org/1999/xlink"><title>Group</title> <desc>Created with Sketch.</desc></svg>