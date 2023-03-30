# DBaaS 时代的开源数据库

> 原文：<https://thenewstack.io/open-source-databases-in-the-age-of-the-dbaas/>

[](https://www.percona.com/)

 [彼得·扎依采夫

彼得·扎依采夫是 Percona 的联合创始人兼首席执行官。作为 MySQL 策略和优化方面最重要的专家之一，Peter 利用他的技术眼光和创业技能将 Percona 从一个两人的商店发展成为业内最受尊敬的开源公司之一。Percona 是在内部和云环境中为 MySQL、MariaDB、MongoDB、PostgreSQL 和其他开源数据库提供最佳企业级支持、咨询、托管服务、培训和软件的领导者。Percona 在 30 多个国家雇用了 140 多名开源专业人员，为 3000 多名客户提供服务，包括互联网巨头的*名人录*，大型企业和许多令人兴奋的初创公司。](https://www.percona.com/) [](https://www.percona.com/)

虽然我喜欢开源提供的自由，但这并不是我开始开发自由开源软件的原因。早在 1999 年我职业生涯之初，我是一名俄罗斯学生，开始了我的第一次创业，我需要一种尽可能最具成本效益的方式。这个时候服务器已经商品化了，它们可以相对便宜地获得——特别是如果你足够节俭来获得三年前的硬件——但是软件并不便宜。如果你想合法购买，你需要为微软堆栈或甲骨文数据库支付大量的美元。这是 20 世纪 90 年代末的俄罗斯，你也可以花几块钱买到盗版，但我没兴趣这么做。

事实上，我的第一次创业是因为开源软件才起步的。Linux、Apache、PHP、MySQL 都还处于起步阶段，功能和易用性都不如当今大多数开源技术，但它们让创新蓬勃发展，否则就不会出现这种情况。

现在，20 多年后，世界已经发生了变化，世界各地足智多谋的创始人不太可能出售二手服务器，而是宁愿使用云服务来创办他们的技术公司。

然而，同样的逻辑也适用:如果您使用的是商用云技术，那么与选择仅由一家供应商提供的解决方案相比，您可能会有许多低成本的选择。例如，现在如果你正在寻找便宜的亚马逊网络服务 EC2 替代品，有像 Linode 或 [Hetzner](https://www.hetzner.com/cloud) 或更便宜的 S3 替代品这样的供应商，还有 [Backblaze](https://www.backblaze.com/b2/cloud-storage-pricing.html) 提供更具成本效益的存储。事实上，你有看似合理的替代方案，这意味着供应商被迫在定价模式上更加保守。

如果你使用的是高度差异化的云服务，还远未商品化，你没有同样的选择自由，所以你被迫接受提供解决方案的供应商的定价和服务质量。换句话说，你被困在供应商锁定中。

如果我们看看数据库，许多人消费数据库的首选方式是通过 DBaaS(数据库即服务)，而不是手动安装和管理数据库软件。如果这是您已经接受的方法，您在云中的选择将会有所不同，尽管它们都无法提供您从基于开源软件和商品化服务的解决方案中获得的可移植性:

**作为 DBaaS 的无差别开源解决方案**:如果你看看 MySQL 或 PostgreSQL，有来自各种供应商的 DBaaS 选项，包括所有顶级云提供商。所有这些都将或多或少地提供与最新开源软件的兼容性，以及类似的功能。然而，会有许多细微的差别，例如:您用来提供数据库的 API 高可用性是如何实现的；如何监控数据库，等等。这一切都意味着移动所需的工作量比自己动手的环境要高。云供应商已经认识到了这个问题，这可能是为什么他们一直在缓慢地[提高价格溢价](https://medium.com/@rbranson/rds-pricing-has-more-than-doubled-ef8c3b7e5218)以换取 DBaaS 的便利性，而不是自己动手。

**作为 DBaaS 的差异化/增强型开源解决方案**:云供应商正在通过构建专有的“开源兼容产品”引入更多差异化，与原始开源版本相比，这些产品可为您提供额外的功能。[亚马逊极光](https://aws.amazon.com/rds/aurora/)可能是这类数据库中最知名的，但它并不孤单。[阿里云的 HybridDB for MySQL](https://www.alibabacloud.com/products/hybriddb-for-mysql) 是另一个很好的例子。这些数据库倾向于提供的特性之一是更好的性能，这意味着即使您不认为您的应用程序依赖于任何特殊的特性，您也可能是这样。再次，这将意味着你有供应商锁定，虽然是一个金笼子，但更大的困难，如果你想移动到不同的供应商。

专有的云原生数据库:有许多为云设计的数据库技术，它们没有任何你可以自己运行的开源(或共享源代码)的等价物。这方面的例子有 DynamoDB、CosmosDB、Google Cloud Spanner、BigQuery 和 Snowflake。这些解决方案是一种极端的供应商锁定，但不像披着羊皮的狼，至少不会把它们误认为类似于开源的东西。

**共享源代码数据库即服务**:在过去的几年里，许多开源数据库供应商已经改变了他们的许可证，以保护自己免受竞争，例如 Amazon 和其他云供应商。MongoDB Inc .将其服务器许可证更改为非开源服务器端公共许可证(SSPL ),因此，MongoDB Atlas 在云中没有任何竞争。毫不奇怪，该公司的股价正在上涨，但 MongoDB Atlas 用户的口袋并没有表现得那么好。在这里挑出 MongoDB 是错误的，因为许多其他“开源”数据库公司已经将其关键组件的许可证更改为某种形式的共享源代码许可证，甚至是专有许可证，以确保与它们的竞争不实际:Redis Labs、Confluent 和 Elastic 是追求这一策略的公司。与 MongoDB 不同，他们还没有改变整个产品的许可，所以他们有云竞争，尽管功能减少了。这是一个完全合法的策略，对于公司来说，它通常具有商业意义——但它会导致用户被供应商锁定，最终会影响这些用户的利益。

## 前进的道路

开源创新需要时间。Linux 成为领先的服务器操作系统需要时间，Apache 和 Nginx 在 web 服务器市场领先也需要时间，MySQL 和 PostgreSQL 成为新应用程序开发的主导关系数据库也需要时间。我相信随着时间的推移，DBaaS 也将被真正的开源解决方案所商品化，这些解决方案可以在任何公共云或私有云上工作。

虽然目前没有开源 DBaaS 解决方案可以与主要云供应商的产品在简单性方面相媲美，但我们确实看到这些技术的基础正在建立。例如，Kubernetes 已经成为数据中心的主流容器编排解决方案，而 Terraform 能够进一步抽象不同云供应商的细微差别。我们已经有各种针对 Kubernetes 操作者的开源项目，可用于 [PostgreSQL](https://github.com/zalando/postgres-operator) 、 [MySQL](https://github.com/presslabs/mysql-operator) 和 [MariaDB](https://github.com/abalki001/mariadb-operator) ，Percona 为 Percona XtraDB 集群 (MySQL 兼容)提供完全支持的 [Kubernetes 操作者，为 MongoDB](https://www.percona.com/doc/kubernetes-operator-for-pxc/index.html) 提供 Percona 服务器的 [Percona Kubernetes 操作者。如果避免供应商锁定对你很重要，这是我追求的方向，以确保开源在云中的未来。](https://www.percona.com/doc/kubernetes-operator-for-psmongodb/index.html)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>