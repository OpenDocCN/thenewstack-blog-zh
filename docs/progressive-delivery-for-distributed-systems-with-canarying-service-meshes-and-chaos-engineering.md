# 基于加那利、服务网格和混沌工程的分布式系统渐进交付

> 原文：<https://thenewstack.io/progressive-delivery-for-distributed-systems-with-canarying-service-meshes-and-chaos-engineering/>

[利用加那利、服务网格和混沌工程渐进交付分布式系统](https://thenewstack.simplecast.com/episodes/progressive-delivering-distributed-systems-with-canarying-service-meshes-and-chaos-engineering)

开发人员的角色发生了演变——从代码猴子到创造性工作者。这是一个激励和留住一些最受欢迎的角色的好方法，让工作更有创造性，不那么单调乏味。但是这种运动是对我们日益复杂和分布式系统的一种回应:这些角色必须自动化，以允许开发人员专注于更多的问题解决和系统弹性。

在本期 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中，我们将与[监控和分析服务 Datadog](https://www.datadoghq.com/careers/) 的开发者倡导者 [Jason Yee](https://twitter.com/gitbisect) 探讨渐进式交付在分布式软件开发中的作用。

通过渐进式交付帮助开发人员进行不同思考的方法之一是他们发布软件更新的方式。RedMonk 的 James Governor 将这种方法称为渐进式交付，它利用了在更广泛地部署变更之前，您可以将流量路由到特定用户子集的不同方式，从而限制了生产测试的爆炸半径。

第一个进步的开源框架是 [Capistrano](https://github.com/capistrano/capistrano) ，它可以在多个服务器上运行脚本。从那里，它是通过滚动部署完成的，在滚动部署中，不是一次向每个人发布，而是通过创建大量副本，一次只向一台服务器发布来限制停机时间。然后是蓝绿色部署——尽管 Yee 说你用什么颜色命名并不重要，它有时被称为红黑色——在这种部署中，你同时维护两个几乎相同的生产环境，就像方向舵一样，你逐渐将流量从一个转移到另一个，当出现问题时再转移回来。

Yee 说，真正推动这种分段交付的是金丝雀部署。金丝雀让一切都慢下来，让你可以根据你所学到的来衡量和改变。他后来在这一集中说，你必须手动控制 Kubernetes 中的任何发布，这可能很乏味。

我们还与 Yee 讨论了 Datadog 测量的内容。该公司借鉴了谷歌的[黄金信号来监控分布式系统](https://landing.google.com/sre/sre-book/chapters/monitoring-distributed-systems/#xref_monitoring_golden-signals)，涵盖了延迟、流量、错误和饱和度。这种方法有助于识别异常值和异常值。他举了一个流量上升的例子，这可能是更多用户的信号，也可能是一个危险信号，表明您有重复的代码给系统带来了额外的压力。

Yee 还指出，服务网格是在网络上获得更多控制和可见性的极好方式。谷歌自己的开源[服务网被称为 Istio](https://istio.io/) 。它允许您为超时、加密、重试、基于角色的访问控制、流量路由等设置自动化。它还允许您定制系统对某些行为的响应。

最后，我们讨论了[混沌工程](https://thenewstack.io/chaos-engineering-can-give-distributed-systems-stability/)，Yee 将其描述为思考我们系统的弹性——“如果这以某种方式中断，我们将对我们的系统有什么了解？”

Datadog 本身会定期执行游戏，在游戏中它会杀死某个服务或依赖项，以了解威胁弹性的因素。这些游戏日是构建任何正在被测试的东西的人和站点可靠性工程师之间的伙伴关系，因为他们最了解这些东西，并且一旦出现问题，他们会立即响应。这使团队能够测试监控和警报，确保仪表板到位，有操作手册和文档可遵循，确保站点可靠性工程师准备好最终接管。

### 在这个版本中:

[0:35:](https://thenewstack.simplecast.com/episodes/progressive-delivering-distributed-systems-with-canarying-service-meshes-and-chaos-engineering?t=0:35) 技术传播者的角色。
[6:18:](https://thenewstack.simplecast.com/episodes/progressive-delivering-distributed-systems-with-canarying-service-meshes-and-chaos-engineering?t=6:18) 将指标捆绑到技术传道者的角色上。
[13:02:](https://thenewstack.simplecast.com/episodes/progressive-delivering-distributed-systems-with-canarying-service-meshes-and-chaos-engineering?t=13:02) 蓝绿色测试。
[24:17:](https://thenewstack.simplecast.com/episodes/progressive-delivering-distributed-systems-with-canarying-service-meshes-and-chaos-engineering?t=24:17) 如何用 Kubernetes 进行金丝雀测试。
[28:08:](https://thenewstack.simplecast.com/episodes/progressive-delivering-distributed-systems-with-canarying-service-meshes-and-chaos-engineering?t=28:08) Istio 和服务网格。
[32:45:](https://thenewstack.simplecast.com/episodes/progressive-delivering-distributed-systems-with-canarying-service-meshes-and-chaos-engineering?t=32:45) 混沌工程。

来自 Pixabay 的 Krzysztof Niewolny 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>