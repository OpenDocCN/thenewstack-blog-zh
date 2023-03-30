# Redis 不仅仅是一个缓存

> 原文：<https://thenewstack.io/redis-is-not-just-a-cache/>

[Redis](https://redis.io/) 不仅仅是缓存。据 AWS 首席工程师 [Madelyn Olson](https://github.com/madolson) 在底特律 kube con North America[新堆栈制造商](https://thenewstack.io/the-aws-open-source-strategy/)的采访中称，它用于更广泛的云原生生态系统，适合许多面向服务的架构，并简化了现代应用程序的部署和开发。

[Redis 不仅仅是缓存](https://thenewstack.simplecast.com/episodes/redis-is-not-just-a-cache)

奥尔森说，人们有一个主要的后端数据库或其他一些工作流，需要很长时间才能运行。它们将中间结果存储在 Redis 中，这提供了更低的延迟和更高的吞吐量。

[https://www.youtube.com/embed/9JVqpPqDjo8](https://www.youtube.com/embed/9JVqpPqDjo8)

视频

奥尔森说:“但是你可以用很多其他的方式来使用 Redis。”“一种常见的方式是我喜欢称之为数据投影 API。因此，你基本上采取了一堆不同的数据来源，可能是一个 Postgres 数据库，或一些其他类型的 Cassandra 数据库，你把这些数据投射到 Redis。然后从 Redis 实例中提取。对于低延迟应用程序来说，这是一个非常非常好的使用案例。”

Redis 创建者 [Salvatore Sanfilippo 的](http://invece.org/)方法提供了一个如何为开源做贡献的课程，Olson 在我们的采访中详述了这一点。

奥尔森说，Sanfilippo 是唯一拥有该项目的写权限的维护者。这意味着贡献者将不得不参与相当多的活动，以获得 Sanfilippo 的回应。所以奥尔森做了开源贡献者想要被注意时会做的事情。她“砍柴和挑水”，这个术语在开源中反映了处理需要注意的任务的工作。这帮助 Sanfilippo 扩大了自己的规模，并帮助奥尔森参与到这个项目中来。

奥尔森说，进入开源开发工作令人望而生畏。一个新的贡献者将会面对有更多经验的人，并且害怕公开问题。但是如果一个贡献者有一个用例，并且帮助文档或者一个 bug，那么大多数开源维护者都愿意帮忙。

“开源的一个大问题是，它们通常资源有限，对吗？，”欧森说。“开源通常有很多志愿者。所以他们通常非常愿意让更多的人来帮助这个项目。”

现在在 AWS 做开源项目是什么感觉？

奥尔森说，自 2015 年奥尔森加入 AWS 以来，事情发生了很大变化。在那个时候，API 是专有的。今天，它几乎与过去完全相反。

奥尔森说，现在保持内部的东西需要批准。不需要内部分化。比如开源的 Redis 最重要，AWS 在上面作为托管服务。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>