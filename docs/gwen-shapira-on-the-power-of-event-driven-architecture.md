# Gwen Shapira 谈事件驱动架构的力量

> 原文：<https://thenewstack.io/gwen-shapira-on-the-power-of-event-driven-architecture/>

CloudBees 赞助了这个播客。

在 [的前 12 年，格温·沙皮拉](https://twitter.com/gwenshap) 的职业生涯中，她从事关系数据库的工作，在那里她了解到了它们的强大和局限性。在 New Stack Makers 的采访中，Confluent 的系统架构师 Shapira 兴奋地分享了事件驱动架构如何打破这些限制并重新定义服务职责的边界。

事件驱动架构是分离组件和简化流程的更广泛的行业趋势的一部分，以便发布更快并围绕用户活动进行组织。这一切都是为了将应用程序拆分成组件(通常是微服务)，然后通过发布、侦听和响应这些事件，将它们链接在一起，以更好地满足业务需求。

[格温·沙皮拉论事件驱动架构的威力](https://thenewstack.simplecast.com/episodes/gwen-shapira-on-the-power-of-event-driven-architecture)

Shapira 提供的一个简单的例子是在保险领域，地址的改变可以改变客户的风险，这将触发报价的重新计算。传统上，批处理架构会每晚或每周重新计算一次这组数据—您知道，当您被告知“我们将在五个工作日内给您回复”时

或者有一种请求-响应方法，当有人更新地址时，地址服务将请求报价服务进行重新计算。请求需要这个响应，因为否则就没有重新计算的证据。

“当你从责任的角度考虑事情时，为什么地址变更服务要对报价负责？”沙皮拉说。

她称这些为“行为泄漏”——如果报价服务关闭，那么地址就无法更新。你最终会有极其复杂的责任链。

## 业务和软件规划之间的共享语言

在事件驱动架构中，每个服务只是负责发布它的状态变化。因此，地址更改服务只需广播用户更改了地址，然后记录在事件流中。所有其他服务都在持续监听这些事件，然后对其做出反应。

在这种重新定义的边界内，用户地址和报价服务具有完全隔离的逻辑，地址更改服务不需要知道报价服务。一旦发生地址更改，相应的服务就会发布所有的地址更改，然后服务就可以对该事件做出反应，比如更新报价服务。

事件驱动的架构是趋势的一部分，还有 [行为驱动的设计](https://thenewstack.io/two-ways-to-get-started-with-behavior-driven-design-bdd/) 和[领域驱动的设计](https://thenewstack.io/domain-driven-design-aids-planning-microservices-architecture/)，在商业和软件规划和设计之间有一个共享的语言。

Shapira 说，事件驱动架构给了“你这种共享语言来帮助进行这些对话。你可以去找你所在行业的人，问他们:有哪些重要事件？在这个世界上，在这个行业中，发生了哪些有重大影响的事情，我们需要公布，我们需要有一个持续的记录？”

从那里，商业对话走向:当这一事件发生时，预期的反应是什么？

## 独立服务创造效率

事件驱动架构更高效，因为对变更和正常运行时间的依赖性更小。

“在旧世界中，你需要进行大量的协调工作，最终导致业务流程中的大量开销。一旦你完全由事件驱动，你就会更加独立，”沙皮拉说。

虽然她提醒我们，这让我们不必为了前进而与其他团队交流，但我们当然可以也应该交流——在这些重要的交流中，我们的障碍会更少。

这些事件就像一种契约。Shapira 说，一旦围绕用户行为的这些边界被创建，事件驱动的架构就允许更多的实验，为蓝绿色部署、金丝雀测试和 A/B 测试等渐进式交付努力开辟了道路。

然后，一旦你继续进入最复杂的数据流和流程——[机器学习和人工智能](https://thenewstack.io/the-challenge-of-machine-learning-and-how-devops-and-the-edge-will-modernize-data-science/)——事件驱动架构的可能性就会爆发。

图片由 [Xan Griffin](https://unsplash.com/@xangriffin?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/s/photos/drive?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>