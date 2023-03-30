# Amazon Aurora 的发布标志着向数据库基础架构的转变

> 原文：<https://thenewstack.io/amazon-aurora-release-marks-shift-to-database-as-infrastructure/>

显示 DBaaS 市场正在升温的更多迹象是，Amazon Web Services 本周[发布了 Amazon Aurora](https://aws.amazon.com/blogs/aws/now-available-amazon-aurora/) ，这是一个 MySQL 兼容的关系数据库引擎，专门旨在促进应用程序和基于云的互联网架构的可扩展性。

Aurora 最初是在去年 11 月亚马逊标志性的 re:Invent 会议上推出的，但只在预览版中可用。当时，包括 MOOC 提供商 Coursera、面部识别平台 FacialNetwork 和欧洲奢侈品零售商 Kurt Geiger 在内的客户对新的数据库产品大加赞赏，该产品可以自动调整数据库的大小，从 10GB 到 64TB 不会中断。

现在，这些名字已经被添加到健身计划 Zumba、气候平台 Earth Networks 和下载服务 WeTransfer 中，为亚马逊 Aurora 的功能和可扩展性增加了重量。

Aurora 允许客户为他们的数据库创建多达 15 个副本，并且这些副本可以分布在三个地理区域中(数据库卷以 10GB 数据块的形式以六种方式复制)。Amazon 的 Multi-AZ 技术用于自动重启任何故障转移的数据库，各种技术继续监控崩溃，将数据库缓冲区缓存与数据库处理分开，甚至不断扫描和修复 DB 存储中的数据块。

为了应对市场需求，今年大多数数据库提供商都在想方设法降低延迟、执行实时事务处理和管理可伸缩性。正在采取的方法包括[分片和内存中对等增长](https://thenewstack.io/databases-high-volume-transactions-scale/)、[解决影响可伸缩性的外部因素](https://thenewstack.io/databases-high-volume-transactions-scale-part-three/)，甚至[完全重写数据库核心产品以引入新的批处理算法](https://thenewstack.io/databases-high-volume-transactions-scale-part-two/)。到目前为止，还没有真正的输家:开源产品 Redis 继续扩张，FoundationDB 被苹果收购，DBaaS 产品如 [Orchestrate](https://thenewstack.io/centurylink-acquires-orchestrate-for-its-database-as-a-service/) 和 Compose 被行业巨头 CenturyLink 和 IBM 收购。

正是这两项最新的收购为亚马逊发布 Aurora 提供了背景。随着全球范围内互联网架构需求的激增，企业开发团队正在寻找将数据库管理专业知识需求与其应用程序关注点分离的方法。数据库正继续从单个企业的关注点转移到更多地被看作是一种可以正常工作的外部服务。因此，越来越多的主机提供商购买数据库产品，这样他们就可以通过云基础设施提供数据库即服务。

然而，新的亚马逊 Aurora 版本复制了亚马逊作为云基础设施提供商已经面临的一些障碍。Joe Emison 在他最近的新堆栈文章中记录的 AWS 身份和访问管理(IAM)的安全问题和 AWS 管理控制台固有的复杂性仍然是主要挑战。

随之而来的是更精细的定价模型。一方面，客户开始看到在付费方面有更多的选择，以及更多的按使用量付费的定价模式。Compose 的创始人 Kurt Mackey [在他们最近的收购](https://thenewstack.io/ibm-buys-compose-as-the-dbaas-market-takes-flight/)中暗示了这种可能性，而亚马逊的 Aurora 产品已经有了详细的定价，根据你想提前购买多少存储空间，你想在测试期间按需购买多少用于处理数据库实例，以及你想存储多少备份而变化。地理价格也将发挥作用，特别是当 Aurora 扩展到亚太等地区时，日本消费税将在这些地区生效。

IBM 是新堆栈的赞助商。

特色图片:Raymond Bryson 的“你的 Kindle 目录中有什么”由 2.0 在 [CC 下授权。](https://creativecommons.org/licenses/by/2.0/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>