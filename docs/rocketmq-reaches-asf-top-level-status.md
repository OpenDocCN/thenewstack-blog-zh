# RocketMQ 成为 Apache 软件基金会的顶级成员

> 原文：<https://thenewstack.io/rocketmq-reaches-asf-top-level-status/>

RocketMQ 是一个分布式消息和流媒体平台，它使阿里巴巴在去年 11 月黑色星期五般的全球购物节期间处理了 1.2 万亿并发在线消息，它已经成为阿帕奇软件基金会的顶级项目。

据阿里巴巴和 RocketMQ 的联合创始人[冯·高斯林](https://github.com/vongosling)称，分布式消息和流媒体平台是为[阿里巴巴](https://www.alibaba.com)的电子商务和交易平台创建的，这是世界上最复杂和高流量的在线交易处理(OLTP)系统之一。

该公司于 2012 年将其开源，并于 2016 年 11 月捐赠给 ASF。4.0 版本于去年 2 月发布。

Gosling 解释说, [RocketMQ](https://github.com/apache/rocketmq) 是为阿里巴巴许多子系统之间的排队、解耦、缓冲和控制数据流而设计的。对于这样的在线系统，它是高流量和延迟敏感的。RocketMQ 在提高吞吐量、减少响应时间和消除延迟峰值方面投入了大量精力。

它已被中国、印度和其他国家的数千家企业广泛采用。客户包括中国拼车公司[滴滴出行](https://www.cnbc.com/2017/04/28/didi-chuxing-raises-funding-round-valuation-china.html)、快递服务[顺丰快递](http://www.sf-express.com/us/en/)、微众银行、北京大学和中国科学院。

分布式消息传递引擎的功能包括:

*   低延迟；在高压下，1 毫秒内的响应延迟超过 99.6%；
*   面向财务，具有跟踪和审计功能的高可用性；
*   行业可持续，万亿级消息容量有保障；
*   厂商中立，支持多种消息协议，如 JMS 和 OpenMessaging
*   大数据友好，批量传输，具有通用集成，可提高吞吐量；和
*   海量积累，给定足够的磁盘空间，不损失性能。

[https://www.youtube.com/embed/H9HGE9VOimY?start=45&feature=oembed](https://www.youtube.com/embed/H9HGE9VOimY?start=45&feature=oembed)

视频

RocketMQ 团队在一篇 InfoQ [帖子](https://www.youtube.com/watch?v=H9HGE9VOimY&index=36&list=PLbzoR-pLrL6pLDCyPxByWQwYTL-JrF5Rp&t=42s)中描述了该项目的前三个阶段:

1.  数据存储在关系数据库中的推送模式。
2.  数据存储由文件系统管理的拉模式。
3.  拉模式以及一些推操作。经过大量优化，它具有低延迟和高性能，尤其是在高并发和大量数据的情况下。

RocketMQ 由四部分组成:名称服务器、代理、生产者和消费者。名称服务器提供轻量级的服务发现和路由。代理通过提供按照主题对消息进行分组的轻量级队列机制来处理消息存储。生产者支持分布式部署。消费者支持集群消费和消息广播，提供实时消息订阅机制。

他们还将 RocketMQ 与其他流行的消息平台进行了比较，包括 [ZeroMQ](http://zeromq.org/) 、 [RabbitMQ](https://www.rabbitmq.com/) 、 [ActiveMQ](http://activemq.apache.org/) 和 [Kafka](https://kafka.apache.org/) 。

完全在中国开发，Gosling 描述了当项目进入 Apache 孵化器时的“文化冲突”，包括语言问题和对 Apache 方式的理解。

他说，该项目一直在删除汉字，改进代码风格，编写英文文档，并增加更多测试，以使该项目更加用户友好，并吸引世界各地的开发者。

它还增加了一些功能，如发送批处理，通过 [SQL92](http://rocketmq.apache.org/docs/filter-by-sql92-example/) 、 [logappender](http://rocketmq.apache.org/docs/logappender-example/) 和[open messaging](http://rocketmq.apache.org/docs/openmessaging-example/)的实现进行过滤，使 RocketMQ 更加强大。其中大部分已经在[4.1 版](https://rocketmq.apache.org/release_notes/release-notes-4.1.0-incubating/)发布。

为了更好地服务社区，团队创建并维护了两个存储库，一个作为内核版本，另一个用于社区贡献。Apache RocketMQ 项目管理委员会成员 [Xinyu "yukon" Zhou](https://github.com/zhouxinyu) 表示，社区贡献了一些与其他 Apache TLPs 的集成项目，如 Apache Storm、Apache Ignite、Apache Spark 和 Apache Flume。

OpenMessaging 和版本 5.0 正在路线图上。他说，RocketMQ 5.0 将开发更多原子消息语义，旨在满足复杂的面向云的应用程序和数据处理的要求。

它还与 ASF 内从事 ActiveMQ、RabbitMQ 和 Kafka 等项目的其他小组合作，为用户开发连接这些产品的开放标准，并减轻从一个产品换到另一个产品的工作。

特征图片:[乔·刘易斯](https://www.flickr.com/photos/sanbeiji/)的[火箭](https://www.flickr.com/photos/sanbeiji/2147901653/in/photolist-4BmqU5-8W68Ad-bCvcSH-kZK3f-aiFWaU-a8sC52-av1gT2-6PtDCU-bpAgUo-b1hETp-4QHUYV-fiUqLe-4VB6TB-8gZitE-9nknaV-5zjZJe-dHCcsv-ojB13P-v8SkR-6Ppvnx-omGMXB-dD5z4M-5N2x1V-24UCkr-232wxm-YKVNMG-9K7N24-9GPMB9-8gbPRD-9ST8U4-5N2x6D-dda8XX-a72sn-9ST8Gi-4gNyk8-Vn1vg9-oDuRzD-4VBdvg-9Lrxt5-5N6Pvb-5XH6XE-6Ag25v-5EmzY6-cUfzWu-4VB7fv-bB9diP-aru9U5-4VPoN2-5N2x12-4TGzwh)，授权**CC BY-SA 2.0**。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>