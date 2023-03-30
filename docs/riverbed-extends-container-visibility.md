# Riverbed 为 SteelCentral 应用程序监控平台增加了容器支持

> 原文：<https://thenewstack.io/riverbed-extends-container-visibility/>

网络系统提供商 [Riverbed Technology](https://www.riverbed.com/) 在其 [SteelCentral](https://www.riverbed.com/products/steelcentral/index.html) 应用性能监控平台中引入了容器监控，该平台不需要修改开发人员构建应用或容器的方式。

“容器的传统 APM(应用程序性能管理)方法是在容器内插入脚本。问题是要求开发代码的人负责监控代码，”Riverbed 产品营销总监[埃里克·希勒](https://www.linkedin.com/in/erikhille/)说。

“我们没有在 DevOps 生命周期中使用工具，而是采用了一种新的方法——拥有自己的微容器，它可以查看其他容器，并在它们变得活跃时使用工具。我们可以独立于代码来完成这项工作。”

在以前的版本中，它在容器管理器级别添加了监视，以观察容器和外部世界之间的所有对话，而不触及任何容器基础设施。高级产品经理[徐伟贤·卡拉亚涅夫](https://www.linkedin.com/in/peco-karayanev-7719291/)解释说，通过观察主机上的交互，用户可以判断集装箱是否有问题，或者延迟是否是由外部通信引起的。

这个版本深入探讨了容器运行的应用程序。他们说，与此同时，它将监控从 DevOps 团队的盘子上移开。

探索容器内部的想法似乎与基本想法不一致——似乎是一个不可穿透的、孤立的黑匣子。

Karayanev 坚持认为这可以安全地完成，尽管他没有详细说明该公司为此开发的知识产权。

“我们处于系统级别，只要系统管理员允许，我们就可以提供更改。我们不会盲目的进去，把自己注射到每一个容器里。它使用 DevOps 工程师开发的基于角色的访问，”他说。

该系统提供系统级的工具，允许 it 检查应用程序内部的分析和自动发现机制。他说，在运行时，无需改变任何东西，它就可以开始观察容器内部正在运行什么，不同组件之间的关系，绘制整个环境的地图，并从最终用户的角度以及应用程序和业务流程内部跟踪响应时间。

这种方法旨在透明地与容器编排器一起工作，如 Kubernetes 或 Docker Swarm。

此外，该公司已将应用程序日志消息集成到应用程序性能数据中，以便为每项交易提供完整的端到端交易记录。

“传统日志分析的问题是——从日志文件中抓取日志——并用 Elastic 或 Splunk 对其进行索引，这些位与业务交易无关，”Karayanev 说。“所以作为一名开发人员，你搜索日志分析——搜索一条日志消息，告诉你这一行代码可能[导致了问题],但是你没有上下文。当日志消息出现时，用户在做什么？哪一层在呼叫记录该消息的层？这可能是一个非常复杂的交易。您还必须手动关联来自日志分析和 APM 的数据。

“我们制作了非常详细的交易全栈记录。我们确切地看到日志消息是从哪里发出的，我们观察它们并在它们发生的确切位置记录它们。然后所有这些都被存储起来，并在上面运行分析。”

Sysdig 首席执行官[洛里斯·德吉奥安尼](https://twitter.com/lorisdegio)告诉新的堆栈,[很难获得容器的可见性](https://thenewstack.io/look-inside-container-monitoring/)并以有意义的方式从容器中解读指标。

【Rancher 的一篇博客文章最近比较了 10 种集装箱监控解决方案，包括 [ELK stack](https://www.elastic.co/) 、 [Prometheus](https://prometheus.io/) 和 Sensu 框架。“客观比较监控解决方案的一个挑战是，架构、功能、部署模式和成本可能会有很大差异。Rancher 的 Gord Sissons 写道:“一种解决方案可以从单个主机中提取与 Docker 相关的指标并绘制图表，而另一种解决方案可以聚合来自许多主机的数据，测量应用程序响应时间，并在特定条件下发送自动警报。

随着今年早些时候对大约一年半前 [Riverbed 收购的](https://www.networkworld.com/article/3101329/infrastructure/riverbed-acquires-aternity-to-get-an-end-user-perspective.html) [Aternity](https://www.networkworld.com/article/3101329/infrastructure/riverbed-acquires-aternity-to-get-an-end-user-perspective.html) 的整合，该公司增加了对最终用户体验的可见性，完善了其应用、网络和基础设施管理产品组合。Hille 说，现在你还可以从该设备追溯到代码、数据库和其他可能影响该设备上应用程序性能的因素。用户能够在一个无缝的工作流程中端到端地分析流量。

此版本增加了与 IT 服务管理提供商 [ServiceNow](https://www.servicenow.com/) 的集成，以提供闭环故障排除和支持。Hille 说，这个想法是为那些技术人员提供丰富的性能信息，并在性能受到影响时结束部门之间的指责游戏。

SteelCentral 设备通过引入 40Gb NIC 卡，以更快的速度提升了捕获网络性能的能力，将流量容量增加了一倍，达到每分钟 2000 万个经过重复数据删除的流量或 2 亿个原始流量，并增加了集中管理大规模、大容量 npm 存储库的新功能，即面向 JavaScript 的包管理器，以及全球环境。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>