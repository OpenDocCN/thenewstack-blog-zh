# Reddit 的合作像素艺术项目 Place 剖析堆栈

> 原文：<https://thenewstack.io/dissecting-reddits-place-stack/>

2005 年，一名面临三年商学院课程的英国学生担心自己无法偿还上大学所需的巨额贷款。他设计了一个计划，在互联网上以每个 1 美元的价格出售像素。这听起来可能有点疯狂，亚历克斯·图实际上建立了他所谓的[百万美元主页](http://www.milliondollarhomepage.com/)，在那里他出售的像素刚刚超过一百万美元。

这是一个疯狂的互联网成功故事，听起来更像一篇洋葱文章，而不是一个实际的业务。图的计划只是为了让他完成大学学业，但该网站今天仍然在线，证明了一个想法在网上是多么疯狂和看似暗淡。

有什么更好的互联网历史来制造愚人节玩笑呢？ [Reddit](https://www.reddit.com) 因其愚人节恶作剧而闻名。它包括将随机用户以一对一的一对一聊天方式联系起来，并将 Reddit 用户群分成两个团队。

因此，他们今年的想法是创造一点合作像素艺术诞生了。这个想法是为用户提供一个大页面，用户可以每隔五分钟左右添加一个像素的颜色。听起来很简单，但在实践中，它变成了一个只有在 Reddit 的重量级基础设施之上才能成功的项目。

pixel 页面名为 Place，在 72 小时内有超过 100 万的独立用户。这些人组成社区，并在地图上创建领地，为之战斗和谈判。例如，彩虹之路试图在屏幕上找到自己的路，因为用户可以接触到挡在它前面的项目。在其他地方,[前传迷因](https://www.reddit.com/r/PrequelMemes/)的人们接手了一大块来复述达斯·普雷吉斯的故事。

[https://www.youtube.com/embed/RCAsY8kjE3w?feature=oembed](https://www.youtube.com/embed/RCAsY8kjE3w?feature=oembed)

视频

Reddit 基础设施高级软件工程师 Daniel Ellis 表示，Place 项目主要在 T2 的亚马逊网络服务 T3 中运行，Reddit 本身也是如此。用于连接 WebSockets 集群的堆栈“ [RabbitMQ](https://www.rabbitmq.com/) 向用户实时广播消息。我们让[快速地](https://www.fastly.com/)在边缘缓存初始的画布加载。埃利斯说:“我们在后端使用了 [Python](https://www.python.org/) ，还有 [Redis](https://redis.io/) 和 [Cassandra](http://cassandra.apache.org/) 。

Redis 用于存储颜色和像素信息，而 Cassandra 保存关于每个像素的作者和时间戳的信息，通过将鼠标悬停在特定像素上可以看到这些信息。这是团队面临的最初选择:哪个数据库应该执行哪个任务？

Place 背后的大部分基础设施已经被 Reddit 使用:例如，RabbitMQ 处理传入的 upvotes 和 downvotes。系统“用 [Kafka](https://kafka.apache.org) 将事件发送到事件收集器管道。我们在卡夫卡有一个巨大的活动管道。这是相当低的吞吐量，而且非常稳定，”埃利斯说。

“我们的 RabbitMQ 实例有一个问题，”Ellis 说，就是它与 WebSockets 集群的交互。具体来说，RabbitMQ 管理插件试图对交换进行簿记，这是不必要的，而且会降低速度。埃利斯说，当记账被关闭时，事情就变得明朗了。

这个问题出现在现场，而应用程序实际上是在其存在的 72 小时内使用的。为了解决这个问题，埃利斯说，该团队降低了每个用户像素放置之间的冷却计时器。起初，用户可以每 5 分钟添加一个像素，但当 RabbitMQ 出现问题时，他们将其降低到 10 分钟。

改为 10 分钟引发了用户的阴谋论。埃利斯一度把时间调到 10 点 03 分，希望人们会注意到并发表评论，但很少有人注意到，他闷闷不乐地说。

在他在 Reddit 的其他工作中，Ellis 说团队正试图变得更加面向测试。他说，该团队使用无人机进行自动化测试，自从两年前从酱实验室加入 Reddit 以来，他已经了解了金丝雀部署的价值。

“我们有一个查看内部指标的自定义自动缩放器。埃利斯说:“只有当人们抛弃我们的时候，我们才会出现真正大的异常峰值。”。

至于 Place，他说，在公开使用 72 小时后，Reddit 上筋疲力尽的团队决定是时候关闭它了。“我原本希望它能持续更长时间，但在第三天，我们说它已经完成了。我们在它启动的那一刻就关闭了它，“整整 72 小时。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>