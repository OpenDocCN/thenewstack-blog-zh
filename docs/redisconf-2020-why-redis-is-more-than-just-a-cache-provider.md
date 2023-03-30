# RedisConf 2020:为什么 Redis 不仅仅是一个缓存提供商

> 原文：<https://thenewstack.io/redisconf-2020-why-redis-is-more-than-just-a-cache-provider/>

当[亚马逊网络服务](https://aws.amazon.com/) (AWS)开始为[elastic cache](https://aws.amazon.com/elasticache/)提供开源的 Redis NoSQL 数据库时，AWS 实际上开始与它的一个客户 [Redis Labs](https://redis.com/) 直接竞争。然而，到那时，Redis 的开放源码版本已经仅仅是那些希望超越测试并熟悉其 NoSQL 数据库功能的组织的一个起点。

Redis Labs 仍然经常被视为提供数据缓存功能——其更高级的 NoSQL 数据库功能不太为人所知。Redis 实验室的首席执行官和联合创始人 Ofer Bengal 上周在 RedisConf 2020 虚拟会议上发表主题演讲时说，这种声誉代表了一种误解。

Redis 以其高速缓存以及用于实时数据分析和大型数据集处理的相关闪存高速缓存而闻名，同时还提供全文搜索、时序数据以及消息传递和队列功能等功能。例如，据该公司称，数据库系统功能还演变为以有利于高度分布式微服务数据的方式处理动态和快速移动的数据集。

例如，Bengal 表示，今天每天有 540 万个 Redis 容器在 Docker Hub 上发布。Bengal 表示，根据 StackOverflow 的年度[开发者调查](https://www.google.com/url?q=https://insights.stackoverflow.com/survey/2019%23technology-_-most-loved-dreaded-and-wanted-databases&sa=D&ust=1589744374557000&usg=AFQjCNG9VRZnss-P_2H5kWPJZG5Mfs-Zxg)，超过 10 万名开发者连续三年将 Redis 评为“最受喜爱的数据库”。

“然而，许多人仍然认为 Redis 是一个非常好的缓存系统，而不是一个数据库。也许这是因为记忆仍然被认为不够强大，或者我们没有做得足够好，向社区展示这些年来 Redis 增加的增强功能，”Bengal 说。“无论情况如何，我们希望在这次会议期间，你们将重新发现 Redis 及其作为数据库的独特能力。”

除了提供一个有趣的虚拟活动，充满了酒吧——当作者冒险去那里时，酒吧从未开放——一个 Redis 乒乓游戏和一个在屏幕上与其他与会者交流的机会，Redis 还宣布了新的数据库工具和功能。会议期间推出的新 Redis 工具包括: [RedisGears](https://redis.com/redis-enterprise/redis-gears/) 无服务器引擎、 [RedisAI](https://oss.redis.com/redisai/) 以及关于最近发布的 [Redis 6.0](https://redis.io/download) 和 [Redis Enterprise 6.0](https://redis.com/redis-enterprise-6/) 的更多细节。

Redis 实验室还表示，它已经与微软建立了合作伙伴关系，因此 Redis Enterprise 作为 Redis 的两个新的 Azure Cache 层提供。会议还包括许多研讨会、演示和问答环节。

在一次会议主题演讲中，Redis 实验室的首席产品官 Alvin Richards 表示，一个新的开源项目正在进行中，名为 RedisRaft。理查兹说，Raft 将提供的复制状态机的算法应该为数据一致性“开辟一套全新的用例”。他说今年夏天会有更多的信息。

Bengal 在他的主题演讲中也对长期持乐观态度，尽管新冠肺炎带来了悲剧性的影响，它继续在世界各地带来许多困难。

“我想我们都意识到世界已经变了，很可能再也不会回到我们以前的样子了，”Bengal 说。“根据大多数预测，新常态将严重依赖几乎所有领域或类别的在线服务。”

## 扩展的 Azure 支持

根据合作伙伴关系，Redis 实验室表示，Azure 客户将受益于 Redis 数据库功能，包括 Flash 和模块上的 Redis。最终，Azure 将依靠 Redis 为客户数据提供混合云架构的缓存。

Redis 将为 Azure 提供的增强的缓存功能“将在 bill 之后的每个月在客户中显示出来，”微软公司副总裁 Julia Liuson 在一次主题演讲中说。"通过合作，我们还将提供一个简化和精简的支持体验，柳森说. "对于有问题的客户，我们将简单地首先给微软打电话来解决任何服务问题，并且我们将根据需要指定 Redis 实验室来解决与软件相关的问题。"

## 适用于无服务器的 RedisGears 1.0

[RedisGears 1.0](https://github.com/RedisGears/RedisGears/releases) 首席技术官 [Yiftach Shoolman](https://www.linkedin.com/in/yiftachshoolman/?originalSubdomain=il) 在他的主题演讲中描述了 RedisGears 1.0 是如何缩短批量、交易和事件驱动的数据处理时间的。可编程无服务器引擎提供了一个管道，称为 yield 函数，为用 Python 编写的代码提供数据管道(与其他语言的兼容性即将推出)。

*   除了事务、批处理和事件驱动的数据处理之外，Redis Labs 传达的 RedisGears 功能包括:
    *   通过提供管理现有数据库和数据仓库系统更新的繁重工作，允许 Redis 作为单个数据服务运行，从而消除了获取和准备数据的需要。
    *   允许开发人员组合并写入其他 Redis 数据类型和模块，以实现更简化的体系结构。

## 雷迪赛

Shoolman 还透露了一些基准测试结果，他说这些结果表明 RedisAI 可以减少数据库应用程序的延迟并提高吞吐量，包括事务处理。根据 Redis 实验室的说法，RedisAI 在这些基准测试结果中的表现优于其他人工智能引擎。

Shoolman 说，RedisAI 开发中的关键挑战是“确保智能推理速度快”。

Shoolman 表示，RedisAI 是一个在 Redis 内部运行的人工智能平台，依赖于神经网络进程，支持 TensorFlow 等流行的后端系统，有助于使其“高度可扩展”，Schoolman 说。

Redis 实验室表示，RedisAI 的主要功能包括:

*   生产中人工智能的最小化延迟和增加的吞吐量。
*   与 MLFlow 集成。
*   内置对 TensorFlow、PyTorch、ONNX 运行时等主要 AI 后端的支持。
*   在数据所在的共享集群内存上运行的能力。

## Redis 6.0

增强安全性和扩展更多数据库管理操作能力是 Redis 实验室为 Redis 6.0 和 Redis Enterprise 6.0 版本增加访问控制列表(ACL)和基于角色的访问控制(RBAC)能力的主要动力。

Redis 6.0 包括 ACL，使管理员能够增强操作安全性并降低用户出错的风险。通过更有效地部署这些控件，可以防止用户错误地访问和清除数据缓存。对于商业客户，Redis Enterprise 6.0 允许管理员使用 RBAC 更好地扩展他们的 Redis ACLs，以便跨数据库实现更一致的策略。

在他的主题演讲中，Richards 说 Redis 6.0 的新功能也证实了 Redis 实验室的说法，即 Redis 是一个“数据库而不仅仅是一个缓存”

“认证、加密、全球可用性和一致性都是你对数据库所期望的特征的关键方面，”理查兹说。“当我在上下文中谈论所有这些事情时，我指的是作为数据库的 Redis…我们试图做的一部分是向您展示 Redis 是如何随着时间的推移而发展和变化的。”

AWS 和 Redis 实验室是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>