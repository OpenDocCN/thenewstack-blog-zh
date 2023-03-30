# RED 方法:监控微服务的新方法

> 原文：<https://thenewstack.io/monitoring-microservices-red-method/>

有效地监控微服务仍然是一个挑战，因为许多传统的性能监控技术不适合提供所需的系统性能粒度。现在，一位前谷歌和 Weave 工程师开发了一种叫做 RED 方法的方法，似乎越来越受到管理员的青睐。

RED“鼓励你达到某种监控的一致性，”RED 的创始人汤姆·威尔基解释道，他也是新的微服务监控公司[的创始人。威尔基](https://kausal.co/)[在周二于纽约举行的](https://www.slideshare.net/kausalco/the-red-method-how-to-instrument-your-services-83653970) [InfluxData](https://www.influxdata.com/) 的[涌入日](https://influxdays.com/)用户活动上发言。

沿着 RED 描述的通道检测微服务最直接的好处是，为可能不熟悉性能不佳的微服务的工程师提供了一套标准的工具来诊断和纠正问题。RED 提供了“跨服务的一致性，这确实有助于减少随叫随到人员的认知负荷。这有助于他们随时获得更多服务，而不是他们编写的服务。”

当威尔基还是一名支持谷歌分析的 SRE 工程师时，他就使用了这种方法。

“我没有编写任何谷歌分析服务，但我仍然能够随时待命，因为对我来说，它们只是黑匣子。当出现问题时，我只需要遍历我的小图，找出是哪一个抛出了错误，然后去查看日志，向开发人员提交一个错误，重启它，等等，”他说。

红色之所以出现，是因为威尔基对流行的绩效评估方法感到失望。[由 Brendan Gregg](http://www.brendangregg.com/usemethod.html) 创建，围绕这些组使用 buckets 系统性能指标:

*   **利用率** (U):资源被使用的时间百分比。
*   **饱和度** (S):资源必须完成的工作量(工作的“队列”)。
*   **错误** (E):错误计数。

被测量的系统资源可以是 CPU、内存、I/O 通道等等。

威尔基说:“这种模式的好处是，它将猜测为什么事情进展缓慢变成了一种更有条理的方法。”。使用 USE 方法，Kausal 创建了一套 [Grafana](https://grafana.com/) 仪表盘，用于监控 Kubernetes 基础设施，使用 Prometheus 作为后端。

然而，威尔基指出，使用方法有其局限性。例如，很难测量内存的饱和度或已使用的内存量。此外，错误计数也很成问题，尤其是 I/O 错误和内存带宽。“事实证明，Linux 在暴露错误计数方面真的很糟糕，”威尔基说。此外，使用更侧重于基础设施，红色更侧重于最终用户的满意度。

作为替代，威尔基[在 Weave 工作时开发了](https://www.weave.works/blog/the-red-method-key-metrics-for-microservices-architecture/)另一个容易记忆的首字母缩略词，红色。红色[基于请求](http://rancher.com/red-method-for-prometheus-3-key-metrics-for-monitoring/)，这样描述微服务性能:

*   **Rate (R)** :每秒的请求数。
*   **错误(E)** :请求失败的次数。
*   **持续时间(D)** :处理一个请求的时间量。

“我喜欢 RED 的一点是它专注于微服务，而不是更多地关注基础设施的使用方法，”influence Data 的创始人兼首席执行官保罗·迪克斯(Paul Dix)说。鉴于红色是去年 Monitorama 和 Kubecon 等微服务友好会议上的热门话题，潮人邀请威尔基在活动上发言。

威尔基说，红色实际上来自另一套鲜为人知的性能指标，这是他在谷歌担任网站可靠性工程师时学到的，称为[四个黄金信号](https://landing.google.com/sre/book/chapters/monitoring-distributed-systems.html):

*   **延迟**:服务一个请求所花费的时间。
*   **流量**:对系统需求的度量。
*   **错误**:请求失败的比率。
*   饱和度:衡量一项服务有多“满”，通常用延迟来衡量。

和 USE 一样，Wilke 实现了 RED 方法作为 Prometheus 的客户端库。例如，开源的 InfluxDB 时序数据库支持普罗米修斯监控工具的读写 API。Prometheus 可以用作数据收集器，通过管道将结果输入数据库，它还可以从 InfluxDB 中查询数据。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>