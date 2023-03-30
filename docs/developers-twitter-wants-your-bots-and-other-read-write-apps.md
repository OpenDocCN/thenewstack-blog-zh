# 开发者:Twitter 想要你的机器人(和其他读/写应用)

> 原文：<https://thenewstack.io/developers-twitter-wants-your-bots-and-other-read-write-apps/>

自从 Twitter 将其开发者 API 恢复为“第二版”并乐观地欢迎所有在 Web 2.0 末期被它扫地出门的第三方开发者回来，已经过去两年多了。为了了解 Twitter 在 API v2 方面取得了哪些进展，我采访了 Twitter 开发者平台产品负责人 Amir Shevat。

具有讽刺意味的是，Shevat 是 Twitter 上机器人的忠实粉丝，并希望看到更多机器人。具有讽刺意味的是，[直到今天](https://twitter.com/i/events/1577379178185269248)，由于太多的机器人，埃隆·马斯克一直试图退出他 4 月份与[收购 Twitter](https://thenewstack.io/what-elon-musks-twitter-takeover-means-for-developers/) 的交易。但当然，Shevat 谈论的是实际有用的机器人——例如聊天机器人或提供有趣内容的人工智能驱动的机器人。马斯克所说的这种机器人是那些借用他的个人资料照片并在他的用户名后面添加几个数字的机器人(例如@elonmusk37658)。

事实证明，机器人可能是充分利用 Twitter API v2 的关键。Shevat 撰写了一本名为*设计机器人:创造对话体验*的 [2017 O'Reilly 书](https://www.amazon.com/Designing-Bots-Creating-Conversational-Experiences/dp/1491974826/)，他认为“软件作为一种积极的创造者是一种巨大的力量。”他指的是创造内容的软件，他认为生成性人工智能软件(目前的趋势——见 DALL-E 和 Stable Diffusion)可能有能力做到这一点。

“如果有人创造了一个机器人，你可以在推特上发布你希望人工智能画或创造的东西，人工智能会用这个来回复，我会很高兴，”他说。"我认为这将是 API 的一个惊人的实现."

这肯定会把网络的读/写时代带到一个新的水平，在那里是机器，而不仅仅是发有用信息的人。它还可以追溯到 2000 年代末的第一波 Twitter 应用，其中许多都是读/写的——TweetDeck 就是一个最好的例子。不幸的是，Twitter 在 2012 年对其 API 所做的改变阻止了“写”功能的进一步使用。因此，根据 Shevat 的说法，2022 年许多使用 Twitter API 的第三方开发者只使用“读取”数据。

> Shevat 的 API v2 的目标之一是鼓励开发人员再次使用“编写”功能。

“我认为到目前为止，开发者已经选择了 read APIs，”他说，“这是可以的，因为这是我们希望他们用我们的条款和条件做的事情。但是现在，在我们使我们的平台更加开放之后，有更多的机会通过使用公共对话来参与——并成为一名创造者。”

虽然 Shevat 希望看到生成性人工智能创造全新的内容，但他也很乐意看到更多重复使用现有内容的机器人。他提到了一个名为 [#artbots](https://twitter.com/search?q=%23artbots&src=hashtag_click) 的标签潮流，特别是[一个由](https://twitter.com/artistmonet)[安德烈·塔拉舒克](https://twitter.com/andreitr)开发的机器人，它在推特上发布莫奈的照片。塔拉舒克创造了许多这样的艺术机器人，最近[声称](https://twitter.com/andreitr/status/1576960279979601920)已经在它们身上聚集了 650 万粉丝。

“没有足够的连接系统，”Shevat 指出，“比如，从互联网上获取内容并在公共对话中分享。我认为这是一个很好的机会。”

## Twitter 内容的新格式

除了机器人，Twitter API v2 也试图创新内容格式。7 月，Shevat 的团队推出了一项[定制时间轴](https://twitter.com/ashevat/status/1546586432608821250)实验，允许第三方控制时间轴算法(这是在私下测试中，所以尚未公开发布)。然后在 8 月，Twitter 戏弄了 [Tweet Tiles](https://twitter.com/ashevat/status/1562862418514288640) ，它通过为特定网站或移动应用程序重新格式化推文来“让开发者扩展推文体验”。Twitter 目前正在与《纽约时报》、《华尔街日报》和《卫报》进行测试。

Twitter 有一个公开的路线图，在“嵌套”、“孵化”和“最近孵化”的类别下列出了类似的项目

![Twitter Tiles](img/417863b82d98360c562593ef96fdee26.png)

Twitter Tiles，一个当前的 Twitter 实验。

这里的共同主题是，Twitter 正在让开发者对整个 Twitter 用户体验拥有更多控制权——甚至有可能将算法钥匙交给时间轴。Shevat 有一个有趣的类比来解释这一点:Twitter 目前就像一部旧的诺基亚手机，但他希望它像一部全新的智能手机。

“Twitter 现在就像诺基亚的电话，”他解释道。“如果你记得老诺基亚的电话；它的电池寿命很长，即使你把它从三楼扔下来，也不会有任何损伤。但它只有一个应用程序，那就是 *Snake* 。我认为我们可以把 Twitter 变成 Android 或 iOS——开发者可以在客户端内部创建一个界面。”

自定义时间线和图块实验都是这方面的例子。“Tiles 是关于推文本身的，”他说。“你如何修改、改变(或)控制用户界面，或许在推文本身内部创造动态互动？”

Shevat 认为这种类型的功能将使开发人员在“公共对话”中拥有更大的权力，这是他在我们的讨论中多次使用的一个短语。在其关于页面的[上，Twitter 声明“我们为公众对话服务。”Shevat 的目标似乎是让开发者决定*如何最好地为其服务。*](https://about.twitter.com/en)

## 那么，Twitter 又是一个全平台了吗？

在 Twitter 的早期，初创公司可以基于 Twitter API 构建成功的创收产品——这就是 TweetDeck 和许多其他第三方客户端所做的。2012 年的打击给这些公司中的大多数敲响了丧钟(尽管 TweetDeck 本身避免了这种命运，因为它在 2011 年被 Twitter 收购)。我问 Shevat，现在创业公司是否有可能基于当前版本的 API 开发全功能产品？

“我有一个专门的团队在思考帮助开发者在 Twitter 上赚钱的能力，”他回答道。“我希望人们筹集资金，在 Twitter 上开发应用程序……我们是用于公共对话的应用程序，在公共对话中，你可以做很多事情。如果你把它作为公共对话的一部分一起演奏，沃尔多会很棒。”

毫无疑问，Shevat 热衷于帮助第三方开发者——事实上，他的经验丰富，因为他之前在谷歌、Slack 和 Twitch 担任过类似的职位。恢复和鼓励用户写 Twitter 的举措也值得称赞。但如果说今年的埃隆·马斯克事件表明了什么，那就是开发者不能完全依赖 Twitter 保持其 API 平台像目前这样开放。如果他真的提出收购要约，谁知道马斯克未来会对 Twitter 做什么？公共对话将很快掌握在私人手中，这意味着第三方开发者面临更多的不确定性。

也就是说，我希望开发者能借此机会为 Twitter 创造出令人惊叹的生成性人工智能机器人和其他有趣的“编写”应用。趁着阳光明媚，抓紧时间！如果你仍然不确定，你可能想报名参加 Twitter 即将于 11 月 16 日举行的开发者大会 [Chirp](https://developer.twitter.com/en/chirp#agenda) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>