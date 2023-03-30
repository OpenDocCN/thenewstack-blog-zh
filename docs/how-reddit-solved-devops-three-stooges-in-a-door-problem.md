# Reddit 如何解决 DevOps 的“三个臭皮匠”问题

> 原文：<https://thenewstack.io/how-reddit-solved-devops-three-stooges-in-a-door-problem/>

本月，Reddit 的一名软件工程师分享了一个真实世界的例子，说明微服务如何帮助提高 Reddit 的恢复能力——这是一个[深思熟虑的案例研究，来自他自己处理搜索请求突然激增](https://www.reddit.com/r/RedditEng/comments/obqtfm/solving_the_three_stooges_problem/?utm_source=share&utm_medium=ios_app&utm_name=iossmf)的经历。这是一个分享你所知道的，在更大的社区中帮助他人的很好的例子，只是通过走一走你遇到的有趣的问题和解决方案。但这也是一个例子，说明一个长期存在的问题如何在 [DevOps](https://thenewstack.io/category/devops/) 的微服务世界中找到新的解决方案。

最棒的是，他用《活宝三人组》中一个有趣的比喻完美地诠释了这一切。

在 LinkedIn ，[上，Rajiv Shah](https://www.linkedin.com/in/rajshah5/) 称自己是后端分布式系统和搜索工程师(在担任机器学习高级软件工程师 II 一年多之后)。但在他的帖子中，Shah 首先简洁地向不熟悉经典好莱坞喜剧三人组的读者解释了三个小丑的混乱。

沙阿写道:“他们经常试图在简单的日常任务上合作，但总是以妨碍对方和伤害对方而告终。”。例如，穿过一扇门时，它们都会相撞，“最终，没有人能通过。”

“就像强迫走狗通过门口一样，我们也遇到过通过分布式微服务架构推送请求的类似模式。”

[https://www.youtube.com/embed/MhWoTFUsHfc?feature=oembed](https://www.youtube.com/embed/MhWoTFUsHfc?feature=oembed)

视频

## 驯服“雷兽”

这是解释一个数十年之久的问题的另一种方式，这个问题也被称为雷群问题。这种现象如此普遍，以至于在“行话文件”中有了自己的条目[，这是一部开创性的程序员文化概要(最后一次更新是在 2003 年),描述了它在 Unix 系统中的出现。](http://www.catb.org/jargon/html/T/thundering-herd-problem.html)

还有一个维基百科页面是关于 Thundering Herd 问题的，详细描述了它是如何在 Linux 内核和微软 Windows 的 I/O 完成端口中被处理的。(该页指出，一些系统甚至试图在重试之前随机安排等待时间，以打破同步，否则当雷霆万钧的一群人回来时，可能会发生这种情况。)

去年在 USENIX 计算系统协会的 LISA 会议上，[劳拉·诺兰](https://twitter.com/lauralifts?lang=en)的一次演讲中提到了这一现象，劳拉·诺兰曾是[谷歌](https://about.google/)在爱尔兰的员工站点可靠性工程师之一。(演讲的题目？是什么打破了我们的系统:黑天鹅的分类。))

[https://www.youtube.com/embed/LSQUO_Yi9oM?feature=oembed](https://www.youtube.com/embed/LSQUO_Yi9oM?feature=oembed)

视频

诺兰解释说，典型的例子是，当几个进程被安排在夜间运行时，创建它们的工程师不假思索地选择午夜的钟声作为它们的开始时间。但是其他的例子包括移动客户端突然在相同的特定时间开始更新，甚至是非常大的进程同时更新。

“我在谷歌工作，所以我们不得不担心人们启动 10，000 个工人 MapReduce——尤其是实习生！”诺兰说。

她还在 Slack 上看到了这种情况，当重启一个服务器时，突然引发了 Slack 客户端的大规模重新连接(然后查询它们的频道和用户列表以及任何最近的消息……)

“真正的防御是不要陷入‘哦，好吧，我怎样才能让一群雷鸣般的人为我服务？’”诺兰说因为正如我们所见，有各种不同的方式会发生这种情况。"

类似的事情也发生在 Reddit 上。是的，团队已经实现了一个可以缓存响应的系统(以避免在以后收到相同的请求时不得不进行第二次完整的旅行)。但是 Shah 的帖子解释说，这些响应也有一个“[生存时间](https://en.wikipedia.org/wiki/Time_to_live)”，如果中断持续更长时间，缓存最终会被刷新。

最终结果？“当网站恢复时，我们被淹没在请求中……其中许多是在短时间内重复提出的，”他写道。但是由于没有已经缓存的响应来处理这些重复项，“这会导致流量泛滥，以至于没有一个请求在请求超时内成功，因此没有响应被缓存；网站很快又恢复了“植物面孔”

事实上，沙阿也听说过这种现象被称为“缓存踩踏”(以及“狗堆效应”)。

## 深入细节

Reddit 的解决方案？Shah 写道，将重复数据删除/缓存移动到其堆栈中的不同点，具体来说，移动到其微服务级别，以及“可以处理许多并发请求的 web 堆栈”。然后，工程师只需实现代码，确保不会无意中同时处理两个副本(使用分布式锁)。剩下的工作就是检查已经获取的响应是否存在，如果没有找到缓存的响应，就创建新的响应。

Shah 写道，负载的减少是显著的——尤其是在处理数万个请求的环境中。

“可以把重复数据删除想象成迫使傀儡乐队在厨房门口排成整齐的队伍。然后第一个走狗进了厨房，端着一碗扁豆汤出来，那碗汤就被缓存了。”

"然后，另外两个小丑得到缓存碗汤."

Shah [在随后的评论中承认，尽管事实上，他们都在喝完全相同的一碗汤。所以他提供了另一个比喻。“也许不是厨房，而是艺术工作室？第一个傀儡等待，然后得到一张画。另外两个小丑拿到了那幅画的复印件？”](https://www.reddit.com/r/RedditEng/comments/obqtfm/solving_the_three_stooges_problem/h4znucb/)

Reddit 的 API gateway 将所有来自不同平台的请求整理成一种标准形式，以便于处理(同时丢弃任何不相关的多余变量)。但是，当它们达到微服务级别时，重复数据删除最终会使用一种称为哈希表的简单编程结构来处理，其中一个值会与一个唯一标识符(一个键)配对，以便以后可以检索它。这为发现重复值提供了一种简单的方法，因为它们已经被赋予了一个标识符。

“重复数据删除”还可能涉及对原始请求的其他操作。(例如，丢弃 URL 中的[跟踪参数](https://en.wikipedia.org/wiki/UTM_parameters)，符合请求的[内容类型头](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type)，针对一天中的时间进行调整。沙阿写道:“换句话说，你应该包括所有可能以任何方式影响回答的变量。”。

因为工程师在微服务级别工作，他们也很容易定制个人响应。这个阶段也让他们有机会记录和监控请求，或者设置对特定事件的响应。在这篇文章的压轴戏中，Shah 称微服务为“用户和底层数据存储之间的最后一道防线”

他补充说，“我们相信这个解决方案是一个自然的组合，容易推理，灵活，可维护，有弹性。”

## Reddit 的书库

![Stooges_Malice in the Palace_curly_scene (public domain, via Wikipedia)](img/320d74a6c598daa4d5790a93ed4d123d.png)

Shah 在一个例子中提供了代码片段，其中分布式锁是使用 Pottery 的 Redis 的 red lock(T2)实现的。(在其 [GitHub 知识库](https://github.com/brainix/pottery)中，Pottery 将自己描述为“人类的 Redis”和“访问 Redis 的 Pythonic 方式……有助于更容易地访问 Redis，也有助于实现微服务弹性模式，并且它已经在大规模生产中经过了战斗测试。”)这让 Shah 可以使用 Python 的线程。锁 API(它包含一个方便的内置超时，如果线程过早死亡，它将释放锁)。

Shah 还分享了一些关于 Reddit 技术栈的细节，承认其工程师发现 [gevent Python 库](http://www.gevent.org/)对于用少量实例处理大量请求非常有用。他写道，它允许 Reddit 工程师将所有重复的请求塞进一个大队列(每个请求都在等待通过分布式锁)，“然后，当线程获得锁并串行执行时，这些队列将被清空。”而且不会耗尽可用线程池。

Reddit 有一些使用 Django 和 Flask 框架的组合运行 gevent 库的经验，但也有使用 Python 3 和它自己的[底板库](https://github.com/reddit/baseplate.py)(在其 GitHub 存储库中定义为“Reddit 对我们服务的公共形状的规范”)。

但 Shah 的帖子补充说，有很多方法可以实现他对门口三个臭皮匠问题的特殊解决方案。“您可以让它为任何能够处理许多并发输入/输出绑定请求的 web 或微服务堆栈工作”——只要有某种方法可以在所有后端实例之间共享数据(对于分布式锁和缓存响应)。

## 重新思考这个问题

当 Shah 在 Reddit 的编程论坛上分享他的帖子时，它收到了超过 1600 张赞成票(以及 186 条不同的评论)。这个帖子甚至得到了 Reddit 首席技术官兼创始工程师克里斯·斯洛维的积极回应。斯洛维在 LinkedIn 上发布了[，“老实说，我喜欢从‘雷霆一族’到‘三个臭皮匠’问题的重构，因为它更好地评估了当你遇到它时的感受。”](https://www.linkedin.com/feed/update/urn:li:activity:6816701581887725568/)

最终，Shah 希望各地的开发者都能从他的三个臭皮匠的类比中获益。

正如他在博客中所说的，“我们希望你可以用它来让你自己的微服务边界入口对吵闹的闹剧流量更有弹性。”

![Three_Stooges_1937 (via Wikipedia) Public Domain - old advertising trade card.](img/2fe2538c85dd06841e91b2ae32f039b7.png)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>