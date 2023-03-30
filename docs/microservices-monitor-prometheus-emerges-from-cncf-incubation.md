# 微服务监视器普罗米修斯出现在 CNCF 孵化

> 原文：<https://thenewstack.io/microservices-monitor-prometheus-emerges-from-cncf-incubation/>

最初由 SoundCloud 创建的用于监控一组复杂的动态供应软件服务的软件已经从由 [云本地计算基金会](http://cncf.io/) (CNCF)赞助的孵化项目中毕业。

[Prometheus](https://prometheus.io/) 是继最初由谷歌开发的 Kubernetes 开源容器编排引擎之后，第二个从 CNCF 毕业的开源软件程序。本周在慕尼黑举行的年度普罗米修斯大会上，CNCF 宣布了他们的毕业。

SpaceNet 项目经理和 Prometheus 的核心贡献者之一 Richard Hartmann[说，Soundcloud 的工程师在 2012 年创建了 Prometheus，以监控现在被认为是微服务的环境，其中小型松散连接的组件被集装箱化，并根据需要动态部署。](https://twitter.com/twitchih)

Prometheus 采用*拉动*模式，定期从预定义的目标收集指标，评估并显示结果，如果满足预定义的条件，必要时会发出警报。不可避免地，Prometheus 在许多重要方面不同于标准的基础设施监控工具，例如 Nagios。

主要变化之一是普罗米修斯对服务发现的使用。在那之前，监控工具会通过 IP 地址找到他们监控的内容。然而，在微服务环境中，服务总是在主机之间移动，因此 IP 地址中的硬编码是不可伸缩的。相反，Prometheus 设计为咨询服务发现代理，以便在特定服务移动时跟踪它。

其次，Prometheus 带来了一个新的多维、基于标签的数据模型，与标准的层次数据模型相比，该模型更容易对需要测量的内容进行建模。所有数据都作为时间序列数据收集在键值数据存储中。虽然设计为在单个服务器上运行，但该软件每秒可以收集超过一百万个数据点。

Soundcloud 于 2015 年开源了 Prometheus，[于 2016 年 5 月贡献给了 CNCF](https://thenewstack.io/cloud-native-computing-foundation-prometheus-second-hosted-project/)。自从进入 CNCF 的孵化项目以来，该项目已经有 30 次官方更新。普罗米修斯现在有近 20 个活跃的维护者，4300 多个贡献者和 19000 多个。用户包括[shuttle cloud](https://prometheus.io/blog/2016/09/07/interview-with-shuttlecloud/)[Datawire](https://prometheus.io/blog/2018/03/16/interview-with-datawire/)[digital ocean](https://prometheus.io/blog/2016/09/14/interview-with-digitalocean/)[Weaveworks](https://prometheus.io/blog/2017/02/20/interview-with-weaveworks/)[ShowMax](https://prometheus.io/blog/2016/05/01/interview-with-showmax/)和 [iAdvize](https://prometheus.io/blog/2017/05/17/interview-with-iadvize/) 等。随着时间的推移，用户群已经从核心操作人员扩展到那些测试容器和微服务架构并发现可伸缩性问题的组织。如今，大型企业越来越关注普罗米修斯。

因此，Prometheus 团队希望通过编译模板和最佳实践来增强软件，因此不需要大量的专业知识就能享受所有的好处。

“就其核心而言，Prometheus 是一个构建监控的框架，这既是优点也是缺点。它允许你做任何事情，但你必须做一定量的跑腿工作，”哈特曼说。“我们需要降低准入门槛。”

哈特曼说，为了让[从 CNCF 孵化项目中毕业](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc)，只要[管理机构是稳定的](https://prometheus.io/governance/)，并且软件的持续维护和开发可以持续进行，企业就可以相信软件将被用于生产环境中。该软件还集成了其他 CNCF 云原生软件项目，如用于服务发现的 Kubernetes。

[https://www.youtube.com/embed/PDxcEzu62jk?feature=oembed](https://www.youtube.com/embed/PDxcEzu62jk?feature=oembed)

视频

CNCF 是新堆栈的发起人之一

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>