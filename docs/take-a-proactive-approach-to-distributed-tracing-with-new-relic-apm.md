# 使用 New Relic APM 主动进行分布式跟踪

> 原文：<https://thenewstack.io/take-a-proactive-approach-to-distributed-tracing-with-new-relic-apm/>

[利用新文物 APM](https://thenewstack.simplecast.com/episodes/taking-a-proactive-approach-to-distributed-tracing-with-new-relic-apm) 积极开展分布式追踪

多年来，分布式跟踪的发展经历了许多变化。TNS 创始人亚历克斯·威廉姆斯(Alex Williams)与高级产品经理维克·苏亚雷斯(Vic Soares)坐下来讨论该行业的发展方向，以及客户如何在他们的工作流程中充分利用分布式跟踪。

新遗迹最近宣布，它已经使分布式跟踪在新遗迹 APM 中普遍可用。“它是为那些编写了依赖面向服务的架构，微服务架构的应用程序的人准备的，以帮助他们理解请求的路径，”Soares 说。Williams 随后询问了现代应用程序开发和分布式跟踪的背景，因为随着时间的推移，现代软件变得越来越复杂。Soares 指出，分布式跟踪允许用户能够看到事情是如何流动的，错误在哪里，以及影响延迟的问题发生在哪里。

“我倾向于认为，在某些情况下，一名优秀的工程师已经从被动模式转变为主动模式。进入主动模式的工程师正在研究他们的代码是如何执行的。我们在这里看到的一个例子是，我们从查看跟踪开始说，“哦，这里是延迟发生的地方，这里是我们可以优化的地方，比如说对系统进行 *n* 次调用，我们可以将其减少到一次，或者减少对数据库的查询，这种说法，“然后当你开始剥离洋葱层时，你会得到一些有趣的发现，”Soares 说，并补充说，“对于任何超时的请求，我们能够向我们调用的系统发送取消请求。您可以进行一些优化，但如果看不到可以跟踪的完整调用路径，就无法进行优化。”

New Relic 还在他们的开发周期中引入了一个叫做“钢丝”的概念“我们不是在一次冲刺中完成系统的一个组件，我们所做的是端到端地建立整个系统的原型，并产生一个功能，我们说我们接受数据，我们存储数据，我们处理数据，将数据可视化并在网页上显示出来。这可能是最简单的事情，但它证明了端到端的概念，“好吧，我们正在构建这一功能，”我们不会预先优化它的任何领域，我们将尽最大努力提供某种价值。我们提供这种价值，然后在此基础上发展壮大。借助分布式跟踪功能，我们为一个平台奠定了基础，使我们能够扩展到其他领域。我们本可以等待分布式跟踪与我们想要做的所有事情一起发布，但我们却发布了一个 steel thread，一个为客户提供价值并允许我们增长的最小体验。”

### 在这个版本中:

[1:52:](https://thenewstack.simplecast.com/episodes/taking-a-proactive-approach-to-distributed-tracing-with-new-relic-apm?t=1:52) 新遗迹 APM 现已发布分布式追踪公告。
[6:40:](https://thenewstack.simplecast.com/episodes/taking-a-proactive-approach-to-distributed-tracing-with-new-relic-apm?t=6:40) 你认为在未来的一年里，分布式跟踪会有哪些进步？
[11:12:](https://thenewstack.simplecast.com/episodes/taking-a-proactive-approach-to-distributed-tracing-with-new-relic-apm?t=11:12) 就开发人员的体验而言，您如何看待分布式跟踪功能？
[15:41:](https://thenewstack.simplecast.com/episodes/taking-a-proactive-approach-to-distributed-tracing-with-new-relic-apm?t=15:41) 公司可以通过哪些方式开始分布式跟踪？
[19:55:](https://thenewstack.simplecast.com/episodes/taking-a-proactive-approach-to-distributed-tracing-with-new-relic-apm?t=19:55) 这些概念如何融入你对团队的思考，以及团队如何合作开发更复杂的应用架构？
[23:39:](https://thenewstack.simplecast.com/episodes/taking-a-proactive-approach-to-distributed-tracing-with-new-relic-apm?t=23:39) 了解在分布式跟踪解决方案中要检测和实现什么。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>