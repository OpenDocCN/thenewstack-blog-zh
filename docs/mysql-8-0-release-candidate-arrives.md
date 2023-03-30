# MySQL 8.0 将带来 Unicode 9.0、无模式 JSON、更好的地理空间支持

> 原文：<https://thenewstack.io/mysql-8-0-release-candidate-arrives/>

MySQL 用户本周得到了一份礼物，这是最新发布的 [MySQL 8.0](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/) 的候选版本 1。这个新版本的开源数据库管理系统增加了移动优先、对 Unicode 9 的默认支持和无模式 JSON 支持。

这也是 [Oracle](http://www.oracle.com) 抛弃了平台的 5.x 版本语义，并转向一个不严格的语义，但仍然类似语义的版本系统，将这个新的分支称为 8.0。以前，主要更新是在 5.x 链上，而数据库的实验版和集群版分别被标记为版本 6.x 和 7.x。

MySQL 团队已经“改进了服务器内部的一些东西，使我们在未来更加敏捷。我们有一个结构更好的代码库，一个真正的事务性数据字典，”甲骨文 MySQL 开发副总裁托马斯·乌林说。

Ulin 说，MySQL 8.0 版本非常专注于更彻底地支持移动应用程序。为此，该团队在平台的基础上增加了对 GIS 的支持。Ulin 将其归类为为 GIS 提供一流的公民支持。

这与 [PostgreSQL](https://www.postgresql.org/) 的策略形成对比，PostgreSQL 在一个单独的项目 [PostGIS](http://postgis.net/) 中提供 GIS 支持。“MySQL 8.0 中的 GIS 是实际代码库的一部分，”Ulin 说。“这不是您必须单独下载和管理的附加组件。这就简单多了。这给了那些喜欢 MySQL 的人，但是他们可能正在寻找更好的 GIS 支持的解决方案。他们现在应该能在 MySQL 中找到最好的 GIS 支持。”

MySQL 8.0 还将 Unicode 的最新版本作为默认版本。Ulin 表示，它现在支持 [Unicode 9.0](http://unicode.org/versions/Unicode9.0.0/) ，对于移动应用程序，这意味着对表情符号的更大支持，如消息应用程序性能。Unicode 的 9.0 版本

对于 MySQL 版本 5.7，最重要的是 JSON 支持。由于 MySQL 8.0 是下一个版本，该团队通过添加函数来检查本机 JSON 类型的磁盘大小，从而扩展了这种支持。还添加了数组和对象聚合函数，以及一些格式化函数。

这个版本还添加了不可见的索引，对于那些负责维护和向现有数据库添加新索引的人来说，这应该会更容易。“当您想要添加或删除索引时，您可以使它们不可见以查看效果，并且如果它从根本上影响了性能，则重新添加索引。相反，当你想引入一个索引时，你可以添加这个索引，看看它如何影响系统的性能，而不影响应用程序。

MySQL 8.0 RC1 今天发布，最终版本尚未确定发布日期。Ulin 表示，该团队希望在正式发布之前推出另一个候选版本。

![](img/9aafd88d856198113166dc8309420b65.png)

肯·特雷罗亚尔在 [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>