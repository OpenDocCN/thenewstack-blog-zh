# 冷启动如何影响无服务器性能

> 原文：<https://thenewstack.io/how-cold-starts-impact-serverless-performance/>

萨姆·戈尔茨坦是斯泰克里公司的产品和工程副总裁。他是一名工程团队领导，拥有打造优秀产品和高产出团队的历史。在加入 Stackery 之前，Sam 在 New Relic 领导软件开发团队，负责基础设施、代理和浏览器监控。

Stackery 赞助了这篇文章。

有很多理由去无服务器，但也有很多理由不去无服务器。例如，在某些情况下，这不是最便宜的选择。你也经常不能把我们所有的服务都搬到 it 部门。事实上，几十年来，物理和虚拟主机作为一种不仅仅是可行的服务器主机替代方案已经经过了试验和测试，这至少阻止了许多人将一些农场押注于新的服务趋势。

最终，最佳虚拟化环境选项应该是:

*   部署速度更快；
*   更容易扩展；
*   易于复制。

然而，虚拟化的好处也将伴随着失去控制。这不是单一产品的副作用或“缺陷”。同一个不需要您配置队列或路由逻辑的系统有时会对队列和路由做一些您不喜欢的事情。

## 开启冷启动

无服务器并不神奇。你写的代码仍然运行在某个地方的 Linux 服务器上，而每个服务器上的每个 Lambda，不可能总是在那个服务器的内存中准备就绪。在某些时候，不常使用的 Lambda 部署将从内存中卸载，或者包含代码的虚拟服务器将关闭。

当您的空闲 Lambda 收到请求时，必须加载代码，响应时间可能会增加。在某些情况下，这种差异可能是极端的:一个在 20 毫秒内响应的简单 lambda 如果空闲超过一个小时，可能需要 800 毫秒才能响应。

更糟糕的是:在[崔琰](https://hackernoon.com/@theburningmonk)的出色探索中，显示了 Lambda 的每个[同时调用都有它自己的冷启动开销](https://hackernoon.com/im-afraid-you-re-thinking-about-aws-lambda-cold-starts-all-wrong-7d907f278a4f)。这意味着，对于不常使用的函数来说，这远不是一个问题，对于突然出现大浪涌的函数来说，这可能会变得更糟。

使用无服务器最常见的原因是它可以更快地将新功能推向市场。如果冷启动在一项服务很少被使用或流量突然激增时变慢，这难道不意味着兰姆达斯到处都不好吗？

## 可能的解决方案(你也许不应该尝试)

1.  **改变语言**

不止一个人观察到 Node.js Lambdas 通常比其他语言启动更快，可能是因为实现更成熟。但是，我们进入 Lambdas 难道不是因为我们可以更快地开发和部署服务吗？当我说改变语言会极大地影响我的工作流程时，我不认为我是少数。

2.  **改变内存分配**

有证据表明，增加内存分配可以提高冷启动性能*和*Lambda 变冷之前的时间。但是难道我们不想根据流量来调整我们的 Lambdas 吗？如果我们为罕见的冷启动进行优化，我们不会花费更多吗？

3.  **乒一下λ**

有一个简单的强力方法来防止冷启动:永远不要让你的 lambda 睡眠。这并不意味着你要为 100%的正常运行时间付费，因为你可以定期发送“pings ”,并且仍然可以得到好处。但是，即使不支付 100%的正常运行时间，我们仍然花费更多，而且似乎没有办法确保同时请求的情况得到覆盖，其中每个新实例都有自己的冷启动。

## 对未知的恐惧

这些数字引发的恐惧是对我们无法控制的事情的恐惧。AWS 对 X 射线提供的信息非常慷慨，所以我们并不是看不到问题。虽然这些演示数据看起来很可怕，但是生产数据并不能支持这个理论。

## 实验战胜不了经验

成千上万的产品以某种方式使用 lambdas，其中许多是没有持续流量的新兴产品。这如何解决这些性能问题？

在 New Relic 的博客上，我们看到生产性能数据并没有证实这一趋势，冷启动[有时比热功能](https://blog.newrelic.com/technology/aws-lambda-cold-start-optimization/)花费的时间少。

为什么？一个可能的答案是，Lambda 的服务器不是开源的，我们只能观察“冷启动”是如何计时的，以及它们是如何在幕后设计的。但是，在生产环境中，一个不依赖于未知的更通用的解决方案是，其他问题远远超过作为延迟原因的冷启动。

数据库查询时间、路由、排队都会造成延迟。其中许多都是我们可以通过架构和查询优化来显著改善的。鉴于我们在生产中看到的情况，关注我们无法控制的问题而不是我们可以控制的问题是毫无意义的。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>