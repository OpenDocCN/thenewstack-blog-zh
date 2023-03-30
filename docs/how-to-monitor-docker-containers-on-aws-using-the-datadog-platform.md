# 如何使用 Datadog 平台监控 AWS 上的 Docker 容器

> 原文：<https://thenewstack.io/how-to-monitor-docker-containers-on-aws-using-the-datadog-platform/>

编者按:教程是我们为新堆栈开发的新功能。它们旨在展示用于构建和管理新堆栈环境的开发人员工具和管理技术。Datadog 是新堆栈的赞助商。

昨天在 AWS re:Invent 上，Datadog 的马特·威廉姆斯用新的堆栈做了一个演示，演示了如何使用 Datadog 平台监控亚马逊网络服务上的容器。

[https://www.youtube.com/embed/65QumkWMERY?feature=oembed](https://www.youtube.com/embed/65QumkWMERY?feature=oembed)

视频

威廉姆斯说，客户询问如何在 AWS 上监控集装箱。原因是:从一个、两个到数百个或数千个容器很容易。但是理解容器的角色或者它在可用性区域中的行为是很困难的。

在这个例子中，Williams 展示了一个网站上容器的增加以及如何管理负载。通过 Datadog，他展示了用户如何监控这种增长的生命周期。

他展示了运行和停止的集装箱数量。Williams 还展示了如何使用 Redis 基准工具和分布式网络客户端来模拟需求。

通过 Datadog，用户可以看到一段时间内容器的数量以及一些信息，例如 CloudWatch 如何跨实例报告 CPU 使用情况，操作系统如何报告使用情况，以及 Docker 如何报告使用情况。

不同的仪表板从稍微不同的角度显示它。例如，它可以按可用性区域显示监控数据。通过指定不同的标签(如 CloudWatch 或特定区域)来创建图表。其他事件可能是 GitHub 提交和 Docker 容器被启动或销毁的时间。

Datadog 仪表板可以与全世界共享，也可以有内部使用的仪表板。

一个图是由运行在所有实例上的 Docker 容器的总和创建的。它也可以被重叠区域或事件所覆盖。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>