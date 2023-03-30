# 如何看待库伯内特斯

> 原文：<https://thenewstack.io/end-user-perspective-monitoring-kubernetes/>

几周前，我们有机会和[罗斯·库库林斯基](https://twitter.com/rosskukulinski)一起聊聊[库伯内特](/category/kubernetes/)巴斯。当他不管理 NodeSource 的商业 [Node.js](/tag/node.js/) 产品时，Ross 帮助他的咨询客户实现 Kubernetes。他在 Kubernetes 1.0 之前就开始在生产中运行 Kubernetes，因此他提供了宝贵的见解，其中许多他将在本月晚些时候在 Node.js Interactive US 上分享。

当 Kukulinski 能够说服客户为大地构造付费时，他会使用原生仪表板和 CoreOS 大地构造仪表板。我们听到了对 Kubernetes 管理界面的抱怨，所以我们征求了他的意见。当被问及今年早些时候改进 Kubernetes 仪表板的努力是否成功时，他说:

“看看 1.4 版…我认为新的仪表盘非常棒。以前不怎么好。它过去非常糟糕，非常无用，但新版本非常好，”库库林斯基说。

Skippbox 的 iPhone 界面允许快速监控和管理。

我们还讨论了 Kukulinski 如何在桌面上和移动中监控部署。他是 Skippbox 小屋的早期采用者。由 Skippbox 创始人 Sebastien Goasguen 创建的 Cabin 目前可用于 iPhones 和 iPads，但 Android 版本将很快推出。当有人四处走动，有人从类似 [PagerDuty](https://www.pagerduty.com/) 的服务中收到警报时，这一功能尤其有用。

在这些情况下，它允许您立即对情况进行分类。你不仅能够评估形势，在很多情况下，你还能采取行动。正如 Kukulinski 解释的那样，“我能够添加更多的实例，换句话说，使用 Skippbox 应用程序扩大规模。显然，我没有在这个应用中编码…[但]它确实给了我对 Kubernetes 基础设施相当广泛的见解。事实上，作为一个移动设备，它给了我非凡的洞察力。”

虽然他是 Skippbox 的忠实粉丝，但有许多监控活动必须在桌面上处理。在这些情况下，他使用了两个 SaaS 应用程序:1) [Datadog 的](https://docs.datadoghq.com/integrations/kubernetes/) Kubernetes 集成，他将其与 PagerDuty 结合使用，以及 2) [Sysdig Cloud](https://sysdig.com/) 。在与他合作的限制使用 SaaS 的客户中，他发现他们正在使用定制的 ELK stack、 [statsd](https://thenewstack.io/collecting-metrics-using-statsd-a-standard-for-real-time-monitoring/) 和 [Graphite](https://graphiteapp.org/) 的部件。他还没有尝试过 Prometheus 或 Sysdig 的内部解决方案。

## Kubernetes 和敏捷性

使用容器的最大原因之一是考虑到应用程序的灵活性和可移植性。库库林斯基似乎同意这一点。他告诉我们，“Node 给了我们这样的自由和灵活性，并真正将敏捷带回了软件开发，我认为 Kubernetes 在运营方面也做了同样的事情。作为开发者，我不想考虑虚拟机，我想考虑应用。Kubernetes 作为一种编排，实际上作为一种部署机制，为我提供了我可能喜欢的 PaaS 中的相同结构，但我知道它的级别足够低，如果我需要做任何特殊的事情，我可以围绕它创建自己的工具。”

[英特尔的乔纳森·唐纳森讨论 Kubernetes](https://thenewstack.simplecast.com/episodes/intels-jonathan-donaldson-discusses-kubernetes)

Cloud Native Computing Foundation、CoreOS 和 Sysdig Cloud 是新堆栈的赞助商。

特征图像是 [Kubernetes](http://kubernetes.io/) 标志。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>