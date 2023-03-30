# Netsil 将微服务的性能可视化

> 原文：<https://thenewstack.io/netsil-visualizes-performance-microservices/>

微服务架构需要重新思考传统的应用程序性能管理方法，以便更好地了解应用程序及其各种依赖关系。

本周，Netsil 带着对这个问题的解决方案走出了秘密，推出了其应用运营中心(AOC)，号称“微服务应用的谷歌地图”。

Netsil 采用以网络为中心的方法，提供所有组件容器的实时地图，以及它们的许多依赖关系的通信结构。

“不像 APM 方法需要 Java 或。NET 应用程序，… Netsil 完全在您的容器和应用程序代码之外运行，所以您的应用程序容器是完全未经修改的。它使用网络数据包作为真理的来源，”首席执行官兼联合创始人哈尔乔特·吉尔说。

这家总部位于旧金山的初创公司成立于 2016 年，源于宾夕法尼亚大学的研究以及创始人在谷歌和推特的经历。

首席运营官兼联合创始人 [Shariq Rizvi](https://www.linkedin.com/in/shariqrizvi/) 。Twitter 的前工程总监表示，随着这项服务的增长，显而易见的是，特定于编程语言的传统应用程序性能监控(APM)方法留下了太多的盲点。此外，大量的关键服务，如数据库、负载平衡器、服务发现和 DNS，都不适合使用 APM 进行检测。

“很明显，最大的运营挑战之一是服务依赖性，”他说。“现在，所有这些服务都在相互对话，问题是如何进行有状态部署、管理服务级别目标……需要这种谁在与谁对话的实时地图。我们让工程师花大量时间查看日志，而不是那张地图。

“很明显，这是一个新的世界，一个微服务和 API 的世界，应该有一个没有任何代码更改的地图，在这些地图中，有一些服务级别指标的指标。在谷歌，我们过去称之为监控服务的[黄金信号](https://landing.google.com/sre/book/chapters/monitoring-distributed-systems.html#xref_monitoring_golden-signals)…比如吞吐量、每项服务的延迟。”

[https://www.youtube.com/embed/_g_5VtlzE7s?feature=oembed](https://www.youtube.com/embed/_g_5VtlzE7s?feature=oembed)

视频

AOC 生成映射，自动发现每个 Docker 容器、Kubernetes pod、主机和服务端点，以及它们之间的所有交互。这些映射还捕获 API 调用、数据库查询、DNS 查找和其他服务交互的关键服务健康指标。

它包括在每个节点上安装一个代理。使用 Kubernetes，大多数客户只需安装一个容器，然后在所有工作节点上安装一个守护进程。它开始查看所有网络流量，并收集服务正在通信的所有元数据以及它们使用的协议。

它对数据包的实时分析包括对 AWS RDS、AWS DynamoDB 等外部服务的调用，对 Google Maps、Salesforce、Stripe、Twilio 等的 API 调用。

该公司表示，AOC 对 Kubernetes 特别有用，因为它可以创建主机、名称空间、服务和 pod 的地图，并深入诊断服务配置、服务可用性和服务创建等领域的问题。

该服务包括与 JMX、NGINX 和 MySQL 等服务的 70 多项集成，并允许用户在问题到达关键阶段之前得到提醒，如延迟、错误和吞吐量。用户可以通过用户定义的组、标签和属性或全局设置自己的关键警报规则，并在多个类似的服务中重用它们。可以通过页面责任、电子邮件或 webhook 集成来发出警报。

他说，他不认为 AOC 会取代日志产品，日志产品更传统地用于审计或更深入的根本原因分析和调试，但他认为 AOC 会取代监控和 APM 的竞争对手。

Gill 说:“如果你在谈论事件响应或 CI/CD 用例的实时可见性，了解性能问题，这就是日志记录不太适合的地方。

目前，这项服务只是吸引人们对问题领域的注意，但该公司计划增加更多内容。

“我们计划带来真知灼见，这样我们就能引起人们对云中发生的有趣数据和有趣趋势的关注。这些都在路线图中。吉尔说:“我们希望(为)运营商提供提问和获得答案的能力。”。

服务于餐饮业的营销和技术公司 Limetray 是 Netsil 的早期用户之一。It 栈包括 Kubernetes、Docker 和 AWS。

“随着我们为客户增加更多功能和服务，最大的挑战之一就是了解服务依赖关系。Limetray 的工程副总裁 [Sooraj Elamana](https://www.linkedin.com/in/sooraje/?ppe=1) 说:“Netsil 地图和指标有助于我们了解交易流程，并在延迟和错误影响我们的客户之前快速找出根本原因。

Netsil 的主要投资者之一 Mayfield Fund 的合伙人 Ursheet Parikh 指出了 Kubernetes 和 Docker 的流行带来的复杂性。

“这种(向微服务架构的)转变带来了新的挑战，也创造了重新思考 APM 等整个产品类别的机会。我们对 Netsil 的彻底创新方法感到非常兴奋，这种方法以极大的简单性和易用性为 DevOps 提供了普遍的可观察性。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>