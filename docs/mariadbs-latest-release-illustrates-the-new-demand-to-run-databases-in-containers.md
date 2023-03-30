# MariaDB 的最新版本说明了在容器中运行数据库的新需求

> 原文：<https://thenewstack.io/mariadbs-latest-release-illustrates-the-new-demand-to-run-databases-in-containers/>

对数据库如何与容器技术一起使用的兴趣变得越来越明显。例如， [Couchbase 服务器](http://blog.couchbase.com/2015/june/running-couchbase-server-under-docker-on-joyent)可以使用 Joyent 的 Docker 容器服务 [Triton](http://blog.couchbase.com/2015/june/running-couchbase-server-under-docker-on-joyent) 在 Docker 下运行。现在[关系数据库 MariaDB](https://mariadb.com/) 发布了一个新版本，包含了对 Docker 容器的支持。

“随着自动化工具的采用，Docker 的采用也在增长。…在企业内部，很多都是日常工作，”产品管理副总裁 Roger Levy 说。“它正在部署另一个数据库，正在升级和重新配置。这些不是吸引人的地方，但却是顾客花费大量时间和精力的地方。我们真的希望通过 MariaDB Enterprise 为他们提供支持和易用性。”

该公司的夏季发布公告包括:

*   能够运行基于 Docker 的 MariaDB 实例，并拥有经过测试和认证的 Docker 版本的 MariaDB Enterprise 的私有存储库。
*   通过 Chef 提供、配置和部署 MariaDB 的 Chef 食谱。它计划稍后出版一本木偶烹饪书。
*   将 MariaDB Enterprise 添加到微软 Azure Cloud 中，该云将于 9 月在其 Azure marketplace 中正式发布。谷歌和 AWS 计划稍后提供服务。
*   它之前推出了针对服务器的优化二进制文件，该公司称这提供了 15%至 20%的性能提升。它对其集群功能也做了同样的事情，使用了 Galera 集群技术。他说，优化的集群二进制文件产生了类似的 15%到 20%的性能提升。
*   MaxScale 中捆绑的数据库可伸缩性和高可用性框架，MaxScale 是其先前发布的代理系统，允许在不影响最终用户的情况下进行扩展。它增加了可以启动恢复的故障检测，通过可选的客户端 SSL 增加了安全性，如果您不想共享路由密码，可以在途中运行 MaxScale。它计划在未来进一步构建 MaxScale 功能，将 MariaDB 连接到平台的其他部分，例如在 MariaDB 和 Hadoop 集群之间复制的能力。
*   能够通过 MaxScale 事件触发器启动电子邮件通知和外部脚本。
*   MaxScale binlog 服务器扩展到支持 MariaDB 10 主服务器和从服务器。
*   增强了其连接器的功能，包括故障转移到 JDBC 连接器。Levy 说，亚马逊将在亚马逊新的 Aurora 数据库服务中推荐 MariaDB 连接器。

MariaDB 是 MySQL 数据库的社区开发分支，Oracle 在 2010 年以 74 亿美元收购了 Sun Microsystems。

然而，MySQL 团队的一些成员，包括 David Axmark、Michael 'Monty' Widenius 和 Kaj Arn，离开了 Oracle，成立了自己的 MySQL 支持公司 SkySQL，并于去年秋天更名为 MariaDB Corp .

这家总部位于芬兰的新公司已经筹集了 3190 万美元的风险投资，包括 2013 年由英特尔牵头的财团提供的 2000 万美元融资和 2 月份 340 万美元的 B 轮融资。

其商业产品 MariaDB Enterprise 使用 Red Hat 的 Linux 模型，作为订阅服务提供，由基于开源 MariaDB 社区服务器的服务器二进制文件组成。

Levy 称 MariaDB 为 LAMP stack 中的新“M”。它与 Canonical 和 IBM 合作开发了一款名为[的新版本 Turbo LAMP，目标是电子商务](http://www.theinquirer.net/inquirer/news/2409757/mariadb-teams-up-with-ibm-and-canonical-to-reinvent-the-lamp)。它现在是 Red Hat 和 SUSE 体系结构中的默认数据库。它的客户包括谷歌、维基百科、家得宝、迪士尼等。

今年早些时候，谷歌在 MariaDB 中添加了加密功能，以帮助阻止 SQL 注入的攻击。对于春季版本，MariaDB 扩展到可以在 Red Hat Enterprise Linux 7.1、SUSE Enterprise Linux Server 12、Ubuntu 14.04 和 IBM POWER 8 架构的二进制文件上运行。

它还推出了 [MaxScale，一个开源代理](https://www.zdnet.com/article/why-mariadb-says-maxscale-will-make-life-easier-for-developers-and-admins/)，允许数据库和应用程序分离，这意味着管理进程可以在不影响应用程序的情况下运行，应用程序的修改不会影响底层数据库。它提供负载平衡、分片和防火墙保护等功能，而无需修改现有的应用程序。

MariaDB 也包含在 Pivotal Cloud Foundry、Rackspace 和其他云堆栈中。Gartner 预测，到 2018 年，超过 70%的新内部应用程序将在开源数据库管理系统上开发。

市场上无数的数据库处理不同类型的数据:图表、JSON 文件、键值存储、社交图表等等。Orchestrate 的首席执行官和联合创始人 Antony Falco 之前告诉新的堆栈，他认为生产中有 35 到 40 个 10 年前不存在的数据库。

Falco 表示，投资者已经预测到市场正在发生的整合——例如，CenturyLink Cloud 收购 Orchestrate 和[收购 Foundation DB](http://techcrunch.com/2015/03/24/apple-acquires-durable-database-company-foundationdb/)——是不可避免的。

Levy 看到了创建多用途数据库的市场趋势。他说，MariaDB 的核心是一个跨国数据库，尽管它提供了一个处理图形数据的引擎，并支持与列存储 Cassandra 的接口。他说，未来它将增加新的功能，如 JSON 和 key-value store，并计划稍后与谷歌和 AWS 建立新的合作关系。

“与其他类型的数据库相比，关系型和事务型数据库添加所谓的 ACID 功能(原子性、一致性、隔离性、持久性)更容易，因为关系型和事务型数据库已经知道如何维护所有数据的一致性和完整性，可以添加键值等功能，”他说。

他说，在业内经常听到关系数据库不能伸缩的说法。

“然而，我们的一些客户，如谷歌、维基百科和 Booking.com，正在运行这个星球上一些最大的数据库。…我们已经证明，关系数据库可以扩展到相当可观的长度。”

[ClusterHQ 肯定看到了在容器中运行数据库的企业的需求](https://clusterhq.com/assets/pdfs/swisscom-case-study.pdf)，所以这是 MariaDB 的一个好策略，据 ClusterHQ 营销副总裁 Michael Ferranti 说，ClusterHQ 是数据量管理器和集群管理工具 Flocker 的母公司。

“很高兴看到 MariaDB 的使用以及他们对提供官方 Docker 映像的关注，这使得在容器中运行 MariaDB 更加容易，”他说。

“由于 Flocker 可与运行在 Linux 上的任何数据库配合使用，因此现在很容易在容器中运行 MariaDB，并使其可在服务器之间移植，这是大多数在生产中运行数据库的运营团队的要求。”

在 InfoQ 的一篇文章中，ClusterHQ 的首席技术官和创始人 Luke Marsden 谈到了在容器中运行数据库的四个[优势](http://www.infoq.com/articles/microservices-revolution)，包括:

*   **开发/生产奇偶校验:**通过在开发和生产环境之间创建奇偶校验，您更有可能在早期发现错误，这表明应用程序的所有部分，包括像数据库这样的有状态服务，都应该在本地进行测试，就像它们将在生产环境中运行一样。
*   避免厂商锁定:在容器出现之前，在多个云上运行是很棘手的，但是 Docker 的一次编写，随处运行的口号承诺了一种避免厂商锁定的方法。然而，数据库在靠近应用服务器时工作得最好，因此在云主机之间移动无状态应用服务器的能力价值有限。但是，如果有必要进行完整的数据中心迁移，可以在数据中心之间移动整个容器化的应用程序。
*   **减少 ops 的管理面:**如果容器格式的标准化只针对无状态应用程序组件，那么标准化的好处就减少了，因为仍然有两个系统需要管理:无状态和有状态。在所有有状态和无状态的应用程序组件以及底层基础设施之间提供一个狭窄且定义明确的外围应用，可以减少开发人员和操作人员之间的对立关系。
*   **裸机性能，无需牺牲多租户:**随着越来越多的企业依赖软件来交付服务，他们需要优化基础设施成本，同时提高性能。在容器中运行数据库有助于将重点放回收入上。

Ferranti 说*，*最大的缺点是，如果没有合适的工具，如果一个容器被移动到不同的服务器上，运行在容器中的数据库就会崩溃。

“使用 Docker，当您在服务器之间移动容器时，这通常被称为调度或重新调度，数据库访问的数据量会保留在原始服务器上。当一个数据库在没有数据的情况下启动时，应用程序基本上就崩溃了，”他说，并指出使用 Flocker，数据量会随着容器一起移动。

Docker 托管平台 Tutum 在 2014 年 4 月构建了首批 MariaDB 容器映像之一。Tutum 在 GitHub 中有其容器化的 [MariaDB 开源存储库，它也在 DockerHub 中公开，据 Tutum 首席执行官兼联合创始人 Borja Burgos Galindo 称，它已经被下载了超过 17，000 次。](https://github.com/tutumcloud/mariadb)

他说，通过维护自己的 Docker 映像，MariaDB 将使数据库的安装和部署更容易，并补充说，尽管在使用容器时仍然存在容量和数据管理问题，但运行容器化的数据库对于开发和测试来说是非常好的。

Docker、IBM、Pivotal 和 Red Hat 是新堆栈的赞助商。

特征图片:“[乐高专卖店！](https://www.flickr.com/photos/michellecarl/5715686271/in/photolist-9H5op2-dA6HrY-mYEsUz-6xp5kM-bxuzPB-4hy8eU-5m7veh-7fg7us-ihAsYz-ahh1C2-qhVoWM-9xKTDp-82ig1o-4timE6-7iSPhd-6vMJtt-7orfYt-qa6VsQ-7FPamb-h1LDfR-bM8Jz-r4EwVt-owwUFg-5Vvuep-7JST4c-7xgpCC-c9advh-onrv64-bzSJhX-u31y6J-aeZrkG-ncUwbn-eqAZd-nH5rSe-8R6D8a-hxa7sJ-pKg5VW-7fdp3o-doGCXZ-9pTN6g-27YN1-7jAjDg-o9xZ5N-GHwGa-brES3w-GEMtY-7mDAeH-ga7URa-oELxiw-nBy41d)[米歇尔·卡尔](https://www.flickr.com/photos/michellecarl/)的在 [CC BY-ND 2.0](https://creativecommons.org/licenses/by-nd/2.0/) 下获得授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>