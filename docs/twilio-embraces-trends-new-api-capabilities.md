# Twilio 推出新的 API，用于简化电话应用的工具

> 原文：<https://thenewstack.io/twilio-embraces-trends-new-api-capabilities/>

在周四于三藩市举行的[信号会议](https://www.twilio.com/signal)上，基于云的电话平台主持人 [Twilio](https://www.twilio.com/) 推出了更新的 API 和新的类似亚马逊[Lambda](https://aws.amazon.com/lambda/)的功能，供希望将电话功能集成到他们的应用程序中的开发者使用。通过这样做，该公司推出了一种新的 API 声明方法，旨在为客户带来更轻松的开发体验。

Twilio 产品副总裁 Patrick Malatack 表示，开发人员正在围绕他们的 Twilio 应用程序构建许多相同的功能，扩展他的公司的产品以包括许多这些原本是自主开发的功能，可以减少开发人员的工作量。

Malatack 说 [Twilio Engagement Cloud](https://www.twilio.com/engagement-cloud) 是一个新的 API，它让开发人员以声明的方式访问 Twilio 的功能，这与 [GraphQL](http://graphql.org/) 采用的方法没有什么不同。尽管 Engagement Cloud 没有直接参与周四的发布，但新的 API 给开发者带来的好处基本上是一样的:允许开发者提出复杂的要求，例如请求与三个特定人员的会议线路，以及录制通话的选项。

“它允许你说，‘我想声明一种关系，一套技能，一套围绕你作为开发人员所知道的东西的 API。’“你把这些信息交给 Twilio，它就会围绕这些信息构建智能应用，”马拉塔克说。鉴于他们的技能，我们会自动将电话转接给正确的代理。他们将通过这个 iOS 或 Android 的应用程序令牌获得客户姓名、电话号码等信息。你可以通知客户，它会在正确的渠道通知他们。"

新的 [Twilio Proxy](https://www.twilio.com/proxy) 工具补充了这一功能，为开发人员提供了一种声明关系的方式。Malatack 表示，许多这些功能都是由 Twilio 客户手工构建的。

除了 Twilio 的功能，该公司还增加了它支持的分销渠道的数量。虽然 Twilio 已经以语音、视频和短信支持而闻名，但该公司本周宣布，它现在还可以插入 [Twitter](https://twitter.com/) direct messages、 [Facebook Messenger](https://www.messenger.com/) 、 [Alexa](https://developer.amazon.com/alexa) 通知，以及 HipChat 和 [Slack](https://slack.com/) 等聊天程序。

Twilio 现在还支持自动语音识别，这是通过谷歌提供的。Malatack 表示，这种新的支持实际上是 Twilio 扩大其媒体引擎能力的更大努力的结果，媒体引擎可以获取录制的媒体，并将其传递给第三方服务，如谷歌的语音识别 API。

Malatack 告诉我们，为了让开发人员尽快启动并运行，他的公司周四也宣布了 Twilio 功能。这种无服务器计算环境托管在 Twilio 云中，允许开发人员构建类似于 Amazon Lambda 函数的东西，并在 Twilio 自己的云上本地运行。

副总裁补充说，开发人员可以“直接在 Twilio 云上”编写代码。当一个入站呼叫到来时，它将运行该代码，我们将应答该呼叫并执行您在它上面的任何逻辑。你可以储存。WAV 文件或 MP3 播放持有音乐，或播放某些钟声。而是让开发人员专注于他们的代码能做什么。”

目前 Twilio Functions 支持 [Node.js](https://nodejs.org/en/) 。该服务为所有 Twilio 库提供支持，并从 Node.js 开始。Malatack 表示，构建功能的努力不仅受到亚马逊的影响，还受到 Twilio 客户热衷使用的另一家云提供商的影响。

“当然有人在亚马逊上运行 Lambda，但我们也看到有人在 Heroku 上开发，因为它更容易，启动更快，”Malatack 指出。“我们总是问自己，‘我们能做些什么来缩短 Hello-World 的时间？减少总体上真正重要的事情？“我们怎样才能让这变得更容易，”我们决定为什么不直接在 Twilio 中运行应用程序逻辑。"

通过 Pixabay 的特写照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>