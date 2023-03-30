# Fanout 的开源反向代理提供了 API 友好的实时数据推送

> 原文：<https://thenewstack.io/fanout-open-sources-reverse-proxy-server-real-time-api-push/>

最流行的应用程序都有实时用户体验。人们希望看到他们的出租车在地图上移动，看到同事对文档编辑的实时更新，并在他们的帖子被喜欢时立即得到通知。但是根据 [Fanout](https://fanout.io/) 的创始人兼首席执行官 [Justin Karneges](https://github.com/jkarneges) 的说法，为此建立基础设施是一个难题。

总部位于加州山景城的公司的推送技术被描述为反向代理和消息代理的结合。

它源于卡内格斯在 [Livefyre](http://www.adobe.com/marketing-cloud/experience-manager/livefyre-ugc-platform.html) 担任首席技术官时的挫折，Livefyre 提供实时评论功能。

“这是 2010 年、2011 年，但 SaaS 的推进空间还很早。总的来说，这些工具不是为 API 设计的，而这正是我们在 Livefyre 所做的很大一部分，”他说，并补充说，他开始开发他当时希望拥有的工具。"本质上，我们为推送构建了 [Akamai . "](https://news.ycombinator.com/item?id=15339255)

“我们相信，随着世界变得越来越与 API 相关，数据将越来越需要能够跨越 API 边界，以满足下游用户的期望。我们在 Twitter、Dropbox 和 Slack 等大公司看到了实时 API 的早期证据。我们的目标是提供可重复使用的工具，这样任何组织都可以大规模地做同样的事情，”他说。

## **核心处的图钉**

Fanout 已经开源了它的核心技术 [Pushpin](http://pushpin.org/) ，这是一个插入式代理服务器，用于固定打开的客户端连接。

它有云或自托管选项。客户使用他们现有的[基于 HTTP 的 API](http://blog.fanout.io/2013/04/09/an-http-reverse-proxy-for-realtime/) 后端来验证连接并确保可靠的交付。

“我们纯粹是一个服务器端解决方案—服务器端辅助。消费客户不需要知道我们的存在。所以没有独立的客户端库。客户端和我们的边缘服务器之间的 API 契约是由我们的客户定义的。它的工作原理与一些更端到端的系统略有不同，如 [Pusher](https://thenewstack.io/pusher-helps-bring-real-time-apps-masses/) 和 [PubNub](https://thenewstack.io/pubnub-makes-network-programmable/) 。

他解释说，集成有点复杂——你必须有一个后端，可以包括[无服务器/功能即服务(FaaS)](http://blog.fanout.io/2017/12/15/websockets-aws-lambda/) 。它在它的前面作为代理服务工作。好处是你控制了 API 契约，如果你想公开你的 API，这真的很有用。

“实际的流程是，当客户端连接到我们的边缘时，我们实际上向客户的后端服务器发出请求，说:‘嘿，刚刚有一个连接进来，我们该如何处理？这就是我们如何获得那种透明的魔力，”他说。

卡内格斯喜欢用的一个例子是 [CBIX.ca](https://www.cbix.ca/) ，它的一个客户有一个与比特币相关的 API，不需要认证。您可以向 streaming.CBIX.ca 提出请求。定价和交易有不同的终点。该协议类似于 Twitter 的流媒体 API——响应中的每一行都是最小的 JSON 负载。

“关于他们的 API，真正有趣的是我们为它提供动力，但你永远不会知道。如果你去找他们的 API 文档，那就是他们的 API。如果您在 DNS 域上进行查找，您可以看到它确实指向我们，但如果他们出于某种原因不想使用我们，他们可以将 API 指向他们自己的服务器，这将是确切的 API 合同，他们的客户不会在意。我们希望建立一个更加透明的系统，不与 API 合同发生冲突。”

其他客户包括 [Mozilla](https://www.peterbe.com/plog/using-fanout.io-in-django) 、 [Medium](https://blog.superfeedr.com/stream-superfeedr/) 和 [Appbase](https://appbase.io/) 。

[https://www.youtube.com/embed/Q_3QcWeQotk?start=22&feature=oembed](https://www.youtube.com/embed/Q_3QcWeQotk?start=22&feature=oembed)

视频

代理是一个关键的组成部分，但有两个主要的集成点，他解释说。

你必须回答 Fanout 的一个代理请求。当代理请求进来时，您必须告诉它如何处理它。在 HTTP 请求的情况下，你的后端服务器可能会说，‘把它变成与这些发布/订阅通道的流连接。’所以它确实使用了 pub/sub 进行[数据推送](http://blog.fanout.io/2017/01/22/pushpin-reliable-streaming/)的模式，但是它是在幕后。

“客户端不会说，‘嗨，服务器，我想收听 ABC 频道’，它会说‘嗨，domain.com，这里有一个 HTTP 请求’，然后我们的边缘和客户的后端之间会协商频道。客户端甚至不知道它正在订阅任何内容。它不知道通道模式。一旦建立连接，作为一个单独的过程，客户可以将数据发布到 Fanout，我们将通过我们的网络[发送]数据，并通过任何开放的连接注入数据。当你将数据发布到 Fanout 时，你基本上包括了数据有效载荷，它是基于你所拥有的侦听器类型的特定于传输的，但是你可以包括数据的一个或多个表示，”他说。

Fanout 支持通过五种底层传输方式发送数据:HTTP 长轮询、HTTP 流、WebSockets、Webhooks 和 XMPP。

[https://www.youtube.com/embed/G9vVoN2tyeM?start=7&feature=oembed](https://www.youtube.com/embed/G9vVoN2tyeM?start=7&feature=oembed)

视频

该公司使用 Redis 作为内存数据库，ZeroMQ 用于在服务器之间移动消息，Django 用于其网站和 API，C++用于图钉。

展望未来，该公司希望扩展其可靠性功能，目前仅适用于 HTTP，Karneges 说，并扩展到更多地区-目前有三个地区:旧金山，伦敦和新加坡。它还计划充实内部产品，更好地包装其云组件以供本地使用。

特征图片:[贾斯汀·塔拉克森](https://www.flickr.com/photos/31758798@N04/)的[扇出](https://www.flickr.com/photos/31758798@N04/3557342579/in/photolist-6qmj1K-5w812E-k2XTVv-btSbu5-74mvv5-8uZiSZ-e3FoUx-6qqqJ5-83gimB-2v84p-3gjViH-npjwYX-cevs4m-e7Y4fs-5yUMuE-dVy7PS-kLrccP-buikHG-9FuhUT-CxCAr-aqSf5v-8cP1vw-6fSSyE-eejUTR-8VoF1U-5QWTZn-)，在 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>