# Twitter 风波:我们需要一个公开的公共话语协议

> 原文：<https://thenewstack.io/twitter-turmoil-we-need-an-open-protocol-for-public-discourse/>

我们想留在一个对自己的人民如此冷酷无情的社交网络上吗？这是我们许多人一直在问的问题，因为今天早上有消息称，Twitter 的一半员工被随意解雇了。Twitter 公司将自己标榜为“公共对话”的平台。即使我们承认 Twitter 是西方世界默认的对话平台——很难否认它不是，至少在记者、名人和普通大嘴巴之间是这样——我们难道不应该担心它是基于私有协议的吗？

## 对话协议和 Twitter 的比较

想想其他对话平台:电子邮件可能仍然是私人对话的主要平台，但没有一家公司占据主导地位。这是因为一系列开放协议定义了电子邮件的工作方式。SMTP(简单邮件传输协议)、POP3(邮局协议)和 IMAP(互联网邮件访问协议)是所有电子邮件产品(如 Gmail 或 Outlook)的基础。

另一个对话平台是即时通讯(IM)，尽管这里有点复杂。默认的开放标准是可扩展消息和存在协议(XMPP)，这是 WhatsApp(归 Meta 所有)使用的标准。Signal 有自己的协议，叫做 Signal 协议，但是是免费开源的。Matrix 是一个相对较新的协议，也是免费开源的。Slack 是迄今为止提到的最不开放的产品，它有一个通过 WebSocket 通道发送的 JSON 对象的定制协议(称为实时消息 API)。然而，Slack 也支持常见的 IM 协议，如 IRC 和 XMPP(例如，Matrix 就是这样与之挂钩的)。

那么从协议的角度来看，Twitter 是如何工作的呢？嗯，这就是问题所在——它不使用开放协议，它只在自己的 API 允许的情况下开放。正如我一个月前讨论的那样，Twitter 一直在重新开放其 API，以便为第三方客户提供更多功能。可悲的是，我为那篇文章采访的人 Twitter 开发者平台产品负责人阿米尔·谢瓦特——似乎是今天[失去工作的人之一。此外，几天前，](https://twitter.com/ashevat/status/1588394005112688641)[公司突然取消了原定于本月晚些时候举行的开发者大会 Chirp。对开发者来说，这一切的结果是什么？期待 Twitter 对其 API 的开放性做出又一次让步。](https://twitter.com/TwitterDev/status/1587946525245816832)

## Twitter 支持的蓝天是答案吗？

前 Twitter 首席执行官杰克·多西公开表示，Twitter 应该是一个开放的协议。2022 年 3 月，他给埃隆·马斯克发了同样多的短信:“Twitter 最初是一种协议。本来就不应该是公司。那是原罪。”就在四个月前，多尔西被迫辞去首席执行官一职，因此，考虑到他已经通过该公司赚了很多钱，这么说是不真诚的。然而，值得称赞的是，他已经开始了一个项目，给予 Twitter 他所期望的开放协议:Bluesky。

在 2019 年 12 月的公告消息中，[多尔西在推特上发布了](https://twitter.com/jack/status/1204766078468911106)，称 Twitter 正在资助一个项目，以“开发一个开放和分散的社交媒体标准”，目标是 Twitter“最终成为这个标准的客户”

几周前，[蓝天公司宣布了它正在开发的最新版本](https://blueskyweb.xyz/blog/10-18-2022-the-at-protocol)。现在被称为协议[(“认证传输协议”)，它被定位为联合社交网络的标准。该协议尚未公开，旨在提供账户可移植性(“一个人的在线身份不应由对其用户不负责任的公司拥有”)、算法选择和互操作。在我们等待完整细节的同时，蓝天已经透露，用户身份将通过万维网联盟(W3C)标准、](https://atproto.com/)[分散标识符](https://thenewstack.io/did-you-hear-decentralized-identifiers-are-coming/) (DIDs)进行管理。

这里有一只巨大的大象 Bluesky 的资金目前依赖于 Twitter。Bluesky 是作为一家独立公司成立的，但我们不知道 Elon Musk 是否想继续支付其费用。其他人可能会站出来(提示:@jack 有很多钱)，但即便如此，在我们知道马斯克对其未来发展的影响有多大之前，支持蓝天似乎是有风险的。

## 其他替代协议

乳齿象是最常被提到的 Twitter 替代品，它建立在一个开放协议上，这也是 W3C 认可的标准——activity pub。事实上，这是一个协议，是越来越多的联合社交网络的非正式名称。这意味着，即使 Mastodon 目前是 ActivityPub 的领先客户端，你也可以加入其他 fediverse 应用程序列表中的任何一个，并连接到相同的用户。

fediverse 中另一个正在崛起的协议是 Matrix，我在去年介绍过它。Matrix 是一种用于实时通信的分散式开放标准，迄今为止主要用于即时消息传递。

[据《黑客帝国》的创造者马修·霍奇森(Matthew Hodgson)称，蓝天公司的协议“与《黑客帝国》有很多相似之处，同时专注于大世界的公共微博，并增加了便携账户。”他指出，Matrix 适用于私人和公共通信(包括提供端到端加密)，并承诺“账户可移植性和 P2P 即将到来。”](https://twitter.com/ara4n/status/1587745336348516353)

听起来 Matrix 不像 Bluesky 那样适合社交媒体(假设后者发布了最终协议)，但霍奇森说，“我们希望人们也能在 Matrix 上建立社交媒体。”

值得一提的还有[流言蜚语](https://thenewstack.io/scuttlebutt-decentralize-and-escape-the-social-media-rat-race/)，这是一种鼓励人们连接到小型对等网络的协议。它被分散的社交网络产品使用，如 Manyverse 和 Planetary(后者由 Twitter 的第一位员工 Evan Henshaw-Plath 创建)。

在埃隆·马斯克(Elon Musk)继续对 Twitter 进行彻底改革的同时，这些协议选项中的哪一个获得了支持还有待观察。Twitter 也有可能凭借其专有平台保持对互联网公共话语的控制。不过有一点是肯定的:Twitter 的用户并不稳定，他们正在寻找一种只有开放协议才能提供的保证。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>