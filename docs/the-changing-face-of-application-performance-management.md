# 应用程序性能管理的变化

> 原文：<https://thenewstack.io/the-changing-face-of-application-performance-management/>

[Raygun](https://raygun.com/) 赞助本帖。

[APM 的变脸](https://thenewstack.simplecast.com/episodes/the-changing-face-of-apm)

您只是简单地“监控”您的应用程序，还是像有些人暗示的那样，您已经升级到“可观察性”了？“可观察性”实际上是“监控”的进化继承者吗，还是仅仅是命名法[的重新命名？在这个微服务和无服务器架构的新世界中，监控(或可观察性)发生了怎样的变化？](https://medium.com/@copyconstruct/monitoring-and-observability-8417d1952e1c)

在本周的 New Stack Makers 播客中，New Stack 的创始人兼主编亚历克斯·威廉姆斯(Alex Williams)与联合主持人 [Bradley Rydzewski](https://www.linkedin.com/in/bradrydzewski) (他是 [Drone.io](https://drone.io/) 的联合创始人)以及嘉宾 [JD Trask](https://www.linkedin.com/in/jotrask) (他是 [Raygun](https://raygun.com/) 的联合创始人兼首席执行官)一起讨论应用性能管理 (APM)在不断变化的术语之外的持续[演变。](https://blog.applicationperformance.com/a-brief-history-of-application-performance-management-apm)

Trask 表示，APM 领域发生的主要变化之一是可用计算的数量以及 APM 用户可用的能力。

Trask 说:“我们开始能够为 APM 工具的客户创造更多价值，这部分是因为我们实际上可以在不占用 90%的计算能力的情况下完成这项工作，这仅仅是因为已经出现的改进。”。“下一个挑战是，既然我们可以收集所有这些额外的数据，我们如何才能将其提炼为一些可操作的见解？仅仅拥有更多数据本身并不是一个巨大的胜利。”

当然，这一点被一些人视为监控与可观察性之争的核心——可观察性不仅仅是观察事情的发生，而是推断这些“可操作的见解”Rydzewski 指出最近流行的 [OpenTracing](https://opentracing.io/) 的想法是 APM 向前发展的一个关键点。

Rydzewski 指出:“传统上，开发人员从单个服务器和数据库的角度考虑应用程序，但这种开放跟踪的想法，即用户在 Android 应用程序或 web 应用程序中采取行动，实际上您可以从客户端软件到服务器到数据库发生的任何微服务跟踪该行动，然后返回，您可以获得这种非常有趣的时间表，显示发生的所有事情，以及花费了多长时间——它真正为您提供了堆栈的整体视图。

对于 Trask 来说，APM 发展的一个关键点就是遵循这些思路，但更侧重于 APM 与应用程序本身的物理结构的分离。毕竟，正是这种分离允许跟踪这些用户路径，并提供比滞后的数据库调用等更深入的洞察力。

“您不应该考虑物理实现，您应该只考虑软件的逻辑表示，无论是大量的服务，还是从第一天开始就只有一台服务器和一个整体软件。这不应该有什么关系，也不应该改变你使用这些工具的方式，”Trask 说，随后补充道，“我们真的不相信未来会不得不考虑你的软件的物理布局。如果你的应用运行在 5000 个容器上，一个容器，10 个物理服务器，一个物理服务器，我们看待世界的方式，我们真的不在乎。”

### 在这个版本中:

[2:16:](https://thenewstack.simplecast.com/episodes/the-changing-face-of-apm?t=2:16) 您认为 APM 在过去几年中有什么发展？你对这种进化有什么看法？
[5:45:](https://thenewstack.simplecast.com/episodes/the-changing-face-of-apm?t=5:45) Brad，你希望在未来几年看到这类技术的哪些发展？你对什么最感兴趣？
[10:21:](https://thenewstack.simplecast.com/episodes/the-changing-face-of-apm?t=10:21) 记录结束和追踪开始的边界是什么？
[17:30:](https://thenewstack.simplecast.com/episodes/the-changing-face-of-apm?t=17:30) 许多正在收听的人会想知道 APM 和 Raygun 这样的工具在 Kubernetes 环境中可以实现什么，以及它如何帮助团队管理它。
[23:09:](https://thenewstack.simplecast.com/episodes/the-changing-face-of-apm?t=23:09) 探索将痕迹与个人用户联系起来的概念，以及这是如何进入 Raygun 的崩溃报告的。
[27:41:](https://thenewstack.simplecast.com/episodes/the-changing-face-of-apm?t=27:41) 如果我不使用 APM，您会发现团队在使用无服务器时会遇到哪些常见的陷阱？

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>