# 超越与政委的基准，Redis 的用例性能工具

> 原文：<https://thenewstack.io/beyond-benchmarking-with-commissar-a-use-case-performance-tool-for-redis/>

政委是一个早期的，开源的，基于用例的 Redis 性能工具。它被设计用来进行用例场景测试，而不是只测试速度的基准测试。

[https://www.youtube.com/embed/na6XiY_ij6g?feature=oembed](https://www.youtube.com/embed/na6XiY_ij6g?feature=oembed)

视频

上周在旧金山艺术宫举行的 RedisConf 2015 上，Rackspace 的比尔·安德森展示了一个例子，政委如何模拟存储井字游戏的结果。正如他在 GitHub 上所写的，模拟可以配置给定数量的游戏服务器、用户数、每个用户的匹配数和“观察者”数。这些都是通过环境变量完成的。

> 这允许您利用 Docker 等工具来修改每次运行，同时保持一致的二进制文件。

正如演示的那样，Anderson 展示了使用 Commisssar 硬件每秒可以处理多少游戏。最有趣的是，演示显示了 Redis 花了多长时间来分解关于游戏的数据，以及在客户端花了多长时间。通过这样做，政委可以帮助用户确定是否需要关注应用程序或网络。

通常，基准测试用于显示数据库技术的工作速度。政委展示的不是赛车游戏，而是这款应用每天的运行情况。它简化了基准方法。

Anderson 还在政委中构建了一个名为“潜伏”的工具来显示新工人客户端的效果。它类似于 Redis 中的延迟工具；然而，政委中的延迟工具可以测试多个客户端。在一个例子中，他展示了该工具如何确定网络可变性大大增加了多少，反映了带来更多客户端的影响。这对于在分布式网络中进行横向扩展工作的客户端很有帮助。

最终目标是使政委成为一个跨多种编程语言的多种用例的平台。

Rackspace 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>