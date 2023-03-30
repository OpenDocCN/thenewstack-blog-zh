# Amazon Aurora，AWS 的新型分布式关系数据库

> 原文：<https://thenewstack.io/amazon-aurora-a-new-distributed-relational-database-from-aws/>

编者按:本周我们在 AWS re:Invent，我将在这里发布 AWS 新闻和来自展厅的报道。我对开发者工具生态系统的参与者特别感兴趣，所以我希望花大部分时间与用户和 AWS 生态系统中的公司交谈。期待来自会议的一系列简短帖子——与我们通常做的有点不同。但我们的目标是让大家感受一下这里的氛围，感受一下这个新堆栈世界正在发生的事情。

AWS 今天早上在 AWS re:Invent 上推出了一款名为 Amazon Aurora 的 MySQL 兼容数据库。该数据库设计为容错、可扩展，是高端 SAN 环境的替代产品。

它与 MySQL 兼容，可以扩展到每分钟 600 万次插入。它可通过 AWS RDS 服务获得。

关系数据库将根据需要以 10gb 的增量增加存储空间。它可以扩展到 64tb。随着存储的数据越来越多，存储以线性方式扩展。

根据 [AWS 博客，](https://aws.amazon.com/blogs/aws/highly-scalable-mysql-compat-rds-db-engine/)存储跨三个 AWS 可用性区域复制，每个可用性区域有两个数据副本。Aurora 还内置了并发和自我修复功能，分布在固态硬盘驱动的存储中。

> “Amazon Aurora 可以容忍在处理写入时丢失两个数据副本，在处理读取时丢失三个数据副本。”

根据 AWS 的说法，通过这种方法，数据被备份到[亚马逊简单存储服务](https://aws.amazon.com/s3/) (S3)，这是并行完成的，不会给数据库实例带来任何负载。即时备份是自动的。

Aurora 是我们经常看到的融合系统。它结合了“存储、网络、计算、系统软件和数据库软件”

今天来自 AWS 的消息是向新堆栈架构转变的另一个例子，新堆栈架构可以利用他们的前辈无法比拟的分布式基础设施。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>