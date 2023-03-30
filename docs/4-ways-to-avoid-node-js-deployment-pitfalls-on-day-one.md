# 在“第一天”避免 Node.js 部署陷阱的 4 种方法

> 原文：<https://thenewstack.io/4-ways-to-avoid-node-js-deployment-pitfalls-on-day-one/>

[](https://www.appdynamics.com/)

 [奥美·哈比

奥美·哈比是 AppDynamics 的产品营销总监。他最初以产品经理的身份加入 AppDynamics，领导其 Node.js、PHP 和 Python APM 代理的开发。Omed 本质上是一名开发人员，在整个职业生涯中指导技术项目时，他爱上了 web 级架构。](https://www.appdynamics.com/) [](https://www.appdynamics.com/)

最近发布的 [Node.js 10.0.0](https://thenewstack.io/a-perfect-ten-node-js-foundation-launches-v-10-0-0/) 将于 2018 年 10 月成为 Node 的官方长期支持发布线，有助于巩固其作为构建快速和可扩展的 web 和移动应用程序的最受欢迎的平台之一的地位。

随着超过 700 万个 Node.js 实例在线，75%的用户计划在未来 12 个月内增加对 Node.js 的使用，Node.js 不再是“城里的新孩子”现在，我们将注意力从为什么您可能想要部署 Node.js 转移到如何启动和运行该平台，因为我们已经过了了解您的阶段。对于准备提高技能的 Node.js 开发人员来说，这意味着更深入地研究如何优化企业级 Node.js 应用程序的实际细节。

正如[研究显示的那样](https://techbeacon.com/survey-paints-discouraging-scenario-enterprise-it-software-delivery-development)，后期部署可能会充满问题，因此开发人员需要成熟的策略和技术来排除 Node.js 应用程序的故障，就像他们部署任何其他产品版本一样。虽然强大的生产前流程有助于最大限度地减少错误、配置故障和其他可避免问题的影响；即使是最好的准备也不能总是避开墨菲定律。

当然，在部署后阶段，Node.js 应用程序将成功或失败地将承诺和潜力转化为现实世界的价值、相关性和业务影响。开发人员遇到的许多问题——无论是否可以避免——也会在应用程序进入生产使用后的前 24 小时内浮出水面。因此，Node.js 部署后的前 24 小时尤为关键。

以下是您可能会遇到的四个常见 Day One Node.js 部署问题，以及解决这些问题的技巧:

1.  **node . js 进程崩溃**

Node.js 被设计为在单个进程上运行，这是构建在 Node 上的应用程序具有高度可伸缩性的关键原因。然而，这种方法也有利弊。也就是说，当代码、依赖性或主机错误使进程崩溃时，这实际上使整个应用程序崩溃。使用 Node.js 监督器和管理器来自动检测和处理故障是处理节点进程崩溃的最佳方式。

在对一个崩溃的 Node.js 进程进行故障诊断时，也要记住这个问题可能涉及应用程序的宿主平台。了解针对 Node.js 应用程序故障排除的特定于平台的最新指南。例如，使用[微软 Azure](https://docs.microsoft.com/en-us/azure/app-service-web/app-service-web-nodejs-best-practices-and-troubleshoot-guide) web 服务和 [Heroku](https://devcenter.heroku.com/articles/troubleshooting-node-deploys) 平台即服务(PaaS)可以节省时间，避免故障排除过程中的挫折。

2.  **超过 API 比率限制**

速率限制是 web 开发人员的一种常见做法，可以用来限制用户查询的数量，作为一种事件节流策略，或者作为一种限制 API 请求的方法。然而，部署应用程序可能是开发人员在 Node.js 应用程序中使用速率限制的关键时刻。您的应用程序收到的实际流量可能与预测的流量相差很大，一旦超过 API 速率限制，应用程序将基本上冻结。

缓存涉及将原始 JSON 编码的数据插入数据库，是使 Node.js 应用程序适应任何 API 速率限制问题的一种相当简单的方法。虽然缓存确实有增加内存使用量的代价，但它可能是一种有用的速率限制解决方法。它还为活跃用户提供了高优先级，并可以减少所需的 API 调用次数。

3.  【WebSocket 问题故障排除

除了插座。io . Node.js 最流行的 WebSocket 库，目前有许多不同的 WebSocket 库可用于 node . js。虽然每个都有自己的 API，但是所有的 WebSocket 库都是建立在 TCP 之上的，并且基本上做相同的事情。

无论您使用哪种 WebSocket 库，任何阻碍您的服务器和客户端之间通信的问题都是一个紧迫的问题。下面是一个快速简单的步骤，您可以按照它来重现可疑的 WebSocket [问题](https://github.com/websockets/ws/issues/543):

*   步骤 1:在自己的 Node.js 进程中创建一个 WebSocket 服务器。
*   步骤 2:使用 WebSocket 客户端连接到此服务器。该客户端应该运行一个单独的进程。
*   步骤 3:结束在第一步中创建的服务器进程。
*   步骤 4:检查状态代码。如果报告的错误代码为 1000(正常)，则这是不正确的，因为在这种情况下，浏览器通常会报告错误代码 1006。

4.  **拒绝服务(DoS)攻击**

拒绝服务攻击提出了一个复杂的问题，涉及网络堆栈上的多层保护。在 API 层可以做的事情不多，但是适当地配置 Sails——node . js 最流行的 MVC 框架——可以减轻某些类型的 DoS 攻击。

Sails 会话可以通过[配置](https://next.sailsjs.com/documentation/reference/sails.config/sails.config.session.html)来使用一个单独的会话存储，比如 [Redis](http://redis.io/) ，这样你的应用就可以运行而不依赖于任何一个 API 服务器的内存状态。这允许您通过在任意多的服务器上部署 Sails 应用程序的多个副本来分配负载。您确实需要在应用程序服务器前面放置负载平衡器，它被配置为确保传入的请求总是被定向到最不忙的服务器。这大大降低了一台过载服务器成为单点故障的风险。

如果您没有使用在 [sails.config.sockets](https://next.sailsjs.com/documentation/reference/configuration/sails-config-sockets) 中启用的长轮询传输，那么 Socket。IO 连接可以[配置](https://next.sailsjs.com/docs/reference/configuration/sails-config-sockets)使用单独的套接字存储(例如 Redis)。这消除了负载均衡器上的粘性会话的需要，以及潜在攻击者将他们的攻击指向特定服务器的可能性。

当您构建业务应用程序时，不愉快的意外会随之而来，但是最大限度地缩短问题发生的时间(甚至是问题的警告信号出现的时间)和您了解问题的时间是至关重要的。作为一种最佳实践，在您的标准部署流程中包括[应用程序性能监控(APM)](https://www.appdynamics.com/) ，同时确保它在关键的生产前 24 小时内到位，可以帮助缩小这一差距。因此，在快速检测、识别和排除常见应用程序问题时，APM 可以提供巨大的帮助。

关于第一天惊喜的好消息是，您将学到很多关于构建更好的 Node.js 应用程序和启动您的应用程序时更少的部署后问题。虽然问题可能会继续发生，但真正严重的问题可能会越来越少。

有关部署和管理 Node.js 应用程序的更多最佳实践，包括如何准备产品发布，请下载 Advanced Node.js:优化、部署和维护企业级 Node.js 应用程序。

[AppDynamics](https://www.appdynamics.com/) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>