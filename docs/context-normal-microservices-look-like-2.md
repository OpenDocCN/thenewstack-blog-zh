# 上下文:正常的微服务是什么样的？

> 原文：<https://thenewstack.io/context-normal-microservices-look-like-2/>

微服务环境没有“正常”可言。如果 2016 年 11 月由来自墨西拿[大学](http://web.unime.it/en)、英国[纽卡斯特大学](http://www.ncl.ac.uk/)和 IBM Research 的六名研究人员组成的团队发布的开创性白皮书(PDF)被信以为真，那么这种平衡状态可能永远也不会实现。

研究人员写道，每个数据中心都有独特的操作要求。一旦微服务被部署到那里，它们所需的配置不仅变得独一无二，而且被嵌入到各自的系统中。

“此外，这些微服务具有控制和数据流依赖性，”白皮书写道。“在处理由异构性能要求驱动的微服务和云数据中心资源的异构配置方面存在挑战…微服务到数据中心的映射需要从大量可能性中选择定制配置，这是不可能手动解决的。”

那么，如果您的工作是使用应用性能管理(APM)平台监控数据中心微服务环境的行为，您在寻找什么？你什么时候能知道某些服务的行为，或者整个系统，是否与众不同？一旦你确定了你工作的地方和时间的“普通”是什么，在它完全改变之前，你预计这种情况会持续多久？

“APM 系统实际上是一个 web 应用程序。因此，一个请求来自最终用户，它在开放的互联网上传播，它到达一些服务器，然后它被馈送到一个数据库，在那里记录被更新，请求返回一个响应，响应沿着相同的路径返回给用户， [Weaveworks](https://www.weave.works/) 的首席执行官 [Alexis Richardson](https://twitter.com/monadic) 在接受本期 [Context](https://thenewstack.io/podcasts/context/) 播客的新堆栈采访时解释道。

“在云原生系统中，架构并不特别简单，”Richardson 继续说道。“可能有 50 个微服务合作，向一个最终用户提供一个响应。这是一个极端的例子。或者一个微服务调用另一个微服务。因此，如果你把它画成一幅画，请求会来回摆动，就像 20 世纪 80 年代的突破控制台游戏一样，直到最终返回给用户，而不是有一个直接的、向上/向下的请求/响应。跟踪所有这些与在典型的 APM 环境中进行跟踪有很大的不同。”

Weaveworks 生产了一个商业版的普罗米修斯监控平台[，名为 Cortex](https://www.weave.works/guides/cloud-guide-part-3-monitor-prometheus-monitoring/) 。Richardson 告诉我们，他同意任何 APM 平台供应商说它可以在学术上将其基于代理的监控系统从客户端/服务器扩展到微服务模型，这有点夸大其词。

他说，“一个为 web 应用程序提供支持的 APM 供应商，现在声称它可以为任何其他类型的应用程序提供同等水平的支持，坦率地说，这是一个非常有希望——或者可能毫无希望——的说法。”

然而，考虑到 APM 平台*正在*扩展到微服务，客户*正在*体验一些成果，这样的评估有多现实呢？这是我们在本期[新堆栈:背景](https://thenewstack.simplecast.com/episodes/show-9-microservices-and-the-hunt-for-the-new-normal)中深入探讨的问题，我们采访了:

*   Weaveworks 首席执行官 Alexis Richardson
*   Sysdig 首席执行官洛里斯·德吉奥安尼
*   **Jim Gochee** ，新遗迹首席产品官

现在请听 SoundCloud 上的“[微服务和寻找新常态”](https://thenewstack.simplecast.com/episodes/show-9-microservices-and-the-hunt-for-the-new-normal)，由 [Scott Fulton](https://twitter.com/SMFulton3) 和 [Luke Lefler](https://thenewstack.io/author/luke/) 为新堆栈制作:

[展示 9:微服务与猎取新常态](https://thenewstack.simplecast.com/episodes/show-9-microservices-and-the-hunt-for-the-new-normal)

IBM 是新堆栈的赞助商。

特征图片:[来自 RetroGames.cz](http://www.retrogames.cz/play_223-Atari2600.php?language=EN) 的仿真雅达利 2600 超级突围游戏。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>