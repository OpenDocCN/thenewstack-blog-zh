# Pusher 有助于将实时应用带给大众

> 原文：<https://thenewstack.io/pusher-helps-bring-real-time-apps-masses/>

当然，你可以构建自己的实时功能，比如多人游戏、聊天和 web 及移动应用的仪表盘，但是你真的想这么做吗？并维护它？总部位于伦敦的 [Pusher](https://pusher.com/) 的托管平台旨在从技术团队的盘子里拿走那个。

“你可以用几行代码把它集成起来。使用服务器端 API，您可以非常快速地将其交付给客户端。而且你不必担心管理、扩展和恢复能力，”[工程副总裁萨姆·斯塔格](https://twitter.com/swstagg)说。

“当有成千上万的客户时，这可能会成为一个真正的扩展问题。我们通过 API 从客户那里获得所有这些。”

据该公司称，自 2010 年推出以来，Pusher 已经吸引了超过 10 万名开发者。

*   《T4 时报》用它来推送现场选举结果——Pusher 在那里保持了超过 25 万个连接——以及用于幻想评分结果的 [DraftKings](https://www.draftkings.com/) ,但 Pusher 的功能不仅限于推送通知。
*   它使[金融时报的](https://markets.ft.com/data)专家能够对新闻和实时交易表提供实时评论。注册用户可以在单独的流中聊天。
*   [Lyft](https://www.lyft.com/) 使用 Pusher 在地图上追踪一辆汽车，当它靠近时向你发送通知，并允许与司机聊天。
*   它还为电视节目“人是什么样的？”的互动游戏提供了动力(内奸是谁？)，风靡荷兰，为比利时公司小城英雄。超过 300，000 人参与进来试图解开鼹鼠之谜。
    和 [PrePlay](http://preplaysports.com/#game) 将其用于第二屏幕评论和社交媒体应用，以增强观看体育或电视节目的体验。

Pusher 被设计成一个大规模可伸缩和有弹性的发布-订阅消息总线。

它[在中间使用 Redis](https://making.pusher.com/redis-pubsub-under-the-hood/) ，连接 30 多个客户端和服务器[库](https://pusher.com/docs/libraries)。API 服务在服务器端连接，并在客户端使用 web 套接字服务。虽然客户端 API 可以在多种编程语言中使用，但是如果无法通过 web 套接字进行连接，它还提供了一个 JavaScript 实现作为后备。

它提供了一个可查询的 API，webhooks 和一个调试工具。它最近增加了与 DataDog 的集成，用于监控 19 个指标，并通过 Slack 提供警报。大多数客户在 Amazon Web Services 上使用多租户集群，但是最大的客户使用专用的基础设施。它宣称能够帮助开发者创建符合欧洲和其他 T2 当地数据保护法规的应用程序。

斯塔格说，它的主要竞争对手是 DIY 思维，尽管当人们使用[开源选项](https://www.quora.com/What-are-open-source-self-hosted-alternatives-to-Pusher-or-pubnub-com)时，他们没有意识到在生产中管理它们所带来的挑战。

雅虎开源了它的 Pulsar pub/sub 消息系统，Asana 的北海巨妖提供了其他选项。覆盖开放套接字的项目包括 Node.js 的 [SocketCluster](http://socketcluster.io/#!/) 和 C++的 [RudeSocket](http://rudeserver.com/socket/api.html) 。

与此同时，还有一系列相互竞争的[托管提供商](https://www.leggetter.co.uk/real-time-web-technologies-guide/)，比如 [Socket](http://socket.io/) 、 [Ably](https://www.ably.io/) 和 [PubNub](https://thenewstack.io/pubnub-makes-network-programmable/) 。

去年秋天，该公司[推出了 Pusher Labs](https://www.developer-tech.com/news/2016/mar/24/pusher-launches-rd-lab-avoid-innovators-dilemma-focus-tools-better-apps-less-code/) ，为一个专门的团队提供了一个独立于其日常运营的下一代平台，以帮助其客户用更少的代码改进他们的应用程序。斯塔格说，该公司还没有准备好谈论这一倡议，但将在今年晚些时候宣布。

在一篇博客文章中，博士生迈克尔·沃克说，他去年夏天在公司工作，开发了一种分布式消息总线，它是用 Raft consensus 用 Go 编写的。由于垃圾收集性能不佳，该公司之前[废弃了一个基于 Haskell 的替代系统](https://making.pusher.com/latency-working-set-ghc-gc-pick-two/)。

专题图片:[香侬道尔](https://www.flickr.com/photos/doyleshannon1980/)的《[瓶中的信息](https://www.flickr.com/photos/doyleshannon1980/13210632005/in/photolist-m8nWDk-bDJMEZ-7EhmPU-4uCSf9-75CQVt-fez25V-9PucUL-4qydtJ-qCUKaa-akeWwW-cxNsfy-mUegg6-9F82jc-4EmHZi-6g1QQn-cbWvhq-9ZvMbF-aupXZo-Jxm1n-dp2kFq-9HC5HJ-9VTTke-FU8jX-eiRY3H-4JSmHq-8TNBga-4SJjXT-4RFxLY-9jGNUm-8Efaeu-5NoHUB-57hfDX-Hs7UBj-4wiU2-4DfbLL-5tX2Sg-bX8Czj-cZNgC3-6MRDq3-iy2tU3-eenoRy-a9u2Jk-4qi2KK-aSAADP-ao5V87-gEGo7y-ahwMgi-8XEKv3-9BoJFk-oY2rKL)，经 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>