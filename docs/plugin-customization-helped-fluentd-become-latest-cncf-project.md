# FluentD 如何通过统一日志记录来帮助监控微服务架构

> 原文：<https://thenewstack.io/plugin-customization-helped-fluentd-become-latest-cncf-project/>

在最新一集的 [The New Stack Makers](https://thenewstack.io/podcasts/Makers) 播客中，我们将了解关于 [FluentD](http://www.fluentd.org/) 的所有信息，这是在[云本地计算基金会](https://www.cncf.io/)旗下的最新开源项目。 [Treasure Data](https://www.treasuredata.com/) 开源开发者 [Eduardo Silva](https://www.linkedin.com/in/edsiper) 和 Treasure Data CTO [友川 Ohta](https://www.linkedin.com/in/kazukiohta) 与 TNS 执行主编 [Joab Jackson](https://twitter.com/joab_jackson) 和联合主持人网络安全管理软件产品高级技术战略总监 [Lee Calcote](https://www.linkedin.com/in/leecalcote) 坐在一起，详细了解这款由 Treasure Data 指导的面向微服务的测井软件。

[FluentD 如何通过统一日志记录帮助监控微服务架构](https://thenewstack.simplecast.com/episodes/how-fluentd-can-help-monitor-microservice-architectures-through-unified-logging)

[https://www.youtube.com/embed/hjkyiRDRu4Q?feature=oembed](https://www.youtube.com/embed/hjkyiRDRu4Q?feature=oembed)

视频

“可靠而轻松地收集大规模数据真的非常非常困难。我们发现，我们把 Fluentd 做成了一个轻量级的、灵活的代理，这个代理有很多插件机制。五年后，我们有大约 600 个插件可用于所有来源和输出，”Ohta 说。

Fluentd 的特色是基于 Ruby gem 的插件机制。DevOps 团队成员可以编写一个 Ruby gem，将其安装到他们的本地 Fluentd 环境中，并开始使用它，而不必一行行地编写代码。“我们有四种插件可供选择。输入、输出、解析器和过滤器。对于输入，有很多协议，比如 net flow、从交换机接收数据、HTTP 甚至 Twitter。输出类型是大量的数据系统。解析器是已知的格式，如 JSON 或输入自定义的 bin 格式。过滤器就是你过滤数据的方式。开发人员将为新发布的或已经存在的特定系统编写插件。

最终，成为 CNCF 的一部分为 Fluentd 和 Treasure Data 带来了急需的资金来改进文档，访问 CNCF 社区集群，以便其团队可以开始测试和测量不同的用例，等等。

“我们的用户通常拥有数千台服务器。你需要 Fluentd 的时候，就是你拥有大量服务器的时候。”

思科赞助了这个播客。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>