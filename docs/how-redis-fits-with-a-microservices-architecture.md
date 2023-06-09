# Redis 如何适应微服务架构

> 原文：<https://thenewstack.io/how-redis-fits-with-a-microservices-architecture/>

[](https://www.linkedin.com/in/kyle-davis-9336085a/?originalSubdomain=ca)

[Kyle j . Davis](https://www.linkedin.com/in/kyle-davis-9336085a/?originalSubdomain=ca)

[Kyle 是 Redis Labs 的开发者权益主管。Kyle 是一个热情的全栈开发人员，经常使用 Node.js 和 Redis，这在他关于这两者的长期博客系列中有所记载。此前，Kyle 在高等教育部门工作，帮助为学者和管理人员开发工具和技术。](https://www.linkedin.com/in/kyle-davis-9336085a/?originalSubdomain=ca)

[](https://www.linkedin.com/in/kyle-davis-9336085a/?originalSubdomain=ca)[](https://www.linkedin.com/in/kyle-davis-9336085a/?originalSubdomain=ca)

当今许多广泛使用的数据库系统是在一个公司在整个企业中采用单一数据库的时代开发的。这个单一的数据库系统将在一个地方存储和运行企业的所有功能。你或许可以想象一下:一个房间里摆满了冰箱大小的机器，许多超大的卷对卷磁带机。

但是 Redis 的发展不同于许多其他流行的数据库系统。Redis 建于 NoSQL 时代，是一个灵活、通用的数据库，专门设计用于存储大量数据，这些数据大部分都是空闲的。微服务架构有相关的目标:每个服务都是为特定的用途而设计的——而不是运行业务中的所有东西。

Redis 被设计用来存储经常变化和移动的活动数据，具有不确定的结构，没有关系的概念。Redis 数据库占用空间小，即使使用最少的资源也能提供巨大的吞吐量。类似地，微服务架构中的单个服务只关心该服务的输入输出和私有数据，这意味着 Redis 数据库可以支持各种不同的微服务，每个微服务都有自己单独的数据存储。这很重要，因为拥有许多服务的本质意味着每个服务必须尽可能快地执行，以弥补服务间通信带来的连接和延迟开销。

### 描述 Redis 驱动的微服务架构

 [洛里斯·克洛伊

洛里斯是 Redis 实验室的开发者倡导者，他在米兰研究生物信息学，并参加了 2014 年的谷歌代码之夏，在那里他开发了利用 NoSQL 数据库支持下一代测序数据分析的工具。之后，他在一个犯罪学研究中心工作了一年，担任数据工程师。最近，他转到了后端开发人员的职位，在那里他利用以前的经验，使用 Go 和 Redis 构建高性能服务。](https://redis.com/) 

微服务架构的一个关键特征是每个单独的服务都是独立的——该服务不与另一个服务紧密耦合。这意味着微服务必须维护自己的状态，为了维护状态，你需要一个数据库。

微服务架构可以包含数百甚至数千个服务，开销是规模的大敌。仅仅为了运行而消耗大量资源的基础设施会冲淡微服务架构的优势。

理想情况下，服务数据应该与其他数据层完全隔离，允许非耦合的扩展和跨服务争用慢速资源。由于服务是专门为满足单一角色(就业务流程而言)而设计的，它们存储的状态本质上是非关系的，非常适合 NoSQL 数据模型。Redis 可能不是微服务架构中所有数据存储的一揽子解决方案，但它肯定非常适合许多需求。

一旦你建立了一个服务，它需要与其他服务对话。在传统的微服务环境中，这发生在使用 REST 或类似约定的私有 HTTP 端点上。一旦收到请求，服务就开始处理请求。

虽然 HTTP 方法是可行的并且被广泛使用，但是还有一种替代的通信方法，在这种方法中，服务写入和读取类似日志的结构。在这种情况下，这就是 Redis Streams，它允许一种异步模式，其中每个服务都在自己的流上宣布事件，并且只监听属于它感兴趣的服务的流。此时，双向通信是通过两个服务观察彼此的流来实现的。

然而，即使在不使用 Redis 进行存储或通信的服务中，Redis 仍然可以发挥至关重要的作用。为了交付低延迟的最终响应，每个服务必须尽可能快地响应自己的请求，这通常超出了传统数据库的性能阈值。在这种情况下，Redis 扮演了一个缓存的角色，服务的开发人员在这里决定数据不总是需要直接从主数据库中检索，而是可以更快地从 Redis 中提取。

类似地，需要通过 API 访问的外部数据服务也可能太慢，这里可以使用 Redis 来防止不必要的冗长调用影响系统的整体性能。

*要了解 Redis 在微服务架构中的具体应用，请[下载我们的电子书或索取纸质书](https://redis.com/docs/redis-microservices-for-dummies/)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>