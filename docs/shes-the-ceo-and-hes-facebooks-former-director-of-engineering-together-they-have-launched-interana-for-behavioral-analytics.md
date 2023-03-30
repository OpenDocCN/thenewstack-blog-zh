# 她是首席执行官，他是脸书的前工程总监。他们共同推出了行为分析工具 Interana

> 原文：<https://thenewstack.io/shes-the-ceo-and-hes-facebooks-former-director-of-engineering-together-they-have-launched-interana-for-behavioral-analytics/>

Interana 是我们不常见到的少数创业公司之一。这是一个一体化的内存堆栈，旨在进行数据分析。也是一对已婚夫妇领导的科技公司，一个有硬件背景，一个有社交网络血统的软件制造商。

Ann Johnson 是首席执行官和电气工程师，曾在英特尔担任高级职位。Bobby Johnson 是首席技术官，曾在脸书担任了六年的工程总监，负责将该网站的用户从数百万扩大到数十亿。第三位联合创始人 Lior Abraham 在脸书时发明了 SCUBA ，这是一款被超过一半的脸书员工采用的视觉分析工具。

今天，经过几个月的保密，两人将 Interana，一家拥有 820 万美元来自 Battery Ventures 资金的 30 人公司，从测试版推出，并全面上市。他们提供的是分析事件数据以进行行为分析的能力。该事件数据可能包括网页的点击流或来自人们在看电视时按下遥控器上的按钮的数据。

当安·约翰逊专注于系统效率时，鲍比·约翰逊正在利用他在脸书所做的工作，他在那里编写了 Scribe，一个用于从大量服务器收集大量数据的系统，根据 F [acebook 博客帖子](https://www.facebook.com/notes/facebook/scribe-makes-its-open-source-debut/35548642130)的说法，该公司过去常常做这样的任务，如跟踪数据库使用多少内存来向新闻馈送提供上下文。在脸书，他还领导团队开发了 Cassandra、Apache 基金会、开源分布式 NoSQL 数据库。

博比·强森在一次电话采访中说: [Interana](http://www.interana.com/) 对离散时间的事情感兴趣，对由事件触发的事情感兴趣，比如一段时间内一个页面的会话。它是跨多个节点的压缩列存储，使用内存和硬盘进行数据溢出。

在 Interana 中，时间被认为是第一位的，而这并不一定是 SQL 数据库的特征。通过优先考虑时间，Interana 有能力发现数据中的模式和序列，这可能有助于 SaaS 公司，例如，优化获得更多用户的方法。在脸书，Bobby Johnson 以使用互连的数据集而闻名，他了解这些数据集是如何工作的，然后将这些数据输出到图形用户界面中。这种设计理念是 Interana 的核心主题，这在其开发的仪表板中显而易见。

[![DASHBOARD](img/119e22102d94fdd71b9e18404c7377ea.png)](https://thenewstack.io/wp-content/uploads/2014/10/DASHBOARD.png)

Interana 管理的数据通常是半结构化的，在一段时间内设置，根据属性组织。属性越多，分析就越丰富。根据 Interana 白皮书，一个属性可以识别一个重要的现实世界“参与者”——如用户、设备或 IP 地址。

这些将是重要的行为事件，我们可以就此提出问题。通常，单独的数据集包含与时间无关的关于每个参与者的信息。例如，关于用户的人口统计信息或关于产品的元数据。Interana 可以将这些数据集作为“查找表”加载，并通过事件查询引用它们。

Interana 技术的其他一些方面:

*   Interana 是一种 OLAP 技术。根据 Interana 的信息，他们的技术“没有索引，没有 B 树，也没有块碎片。相反，它有很长的连续内存区，其唯一的写入是附加的。这使得写入速度更快，也意味着读取在所有级别都是流水线式的，不会在锁定时被阻塞。”
*   该技术使用面向列的格式，这使得它为扫描进行了优化。SQL 数据库设计用于处理查询中未引用的列，不会浪费 CPU 周期，不会占用 CPU 缓存和 RAM 中的空间。
*   Interana 扫描内存中的数据，但也让它“从一层溢出到下一层”
*   通过利用其时间和实体数据模型，Interana 在分布式查询中跨网络移动最少量的数据。
*   数据存储中的行为引擎是用 C++编写的，并且已经过优化，可以在收到 Interana 扫描的数据时进行处理。这是它与传统数据仓库产品的不同之处。

在过去的几年中，内存数据库领域蓬勃发展。Interana 有点不一样。这项技术的设计将时间作为首要考虑因素，使其非常适合潜在的传感器数据工作，就像网站上的点击一样，都是基于事件的。有很多选择，包括有些类似的产品，如 AWS 红移。SAP 和 Oracle 拥有自己的技术，但使用案例不同，并且不是以 Interana 的方式横向扩展的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>