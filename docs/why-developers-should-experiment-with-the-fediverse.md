# 为什么开发人员应该试验 Fediverse

> 原文：<https://thenewstack.io/why-developers-should-experiment-with-the-fediverse/>

尽管最近由于埃隆·马斯克收购 Twitter，乳齿象用户数量有所增加，但去中心化社交网络仍处于早期阶段。但是如果你是一个正在寻找下一件大事的开发人员，还有什么更好的时间来试验一个平台呢？“Fe diversity”——一组相互连接的联合网站和应用——可能代表着社交媒体的未来，所以开发者现在应该注意了。

我和[大流士·卡泽米](https://tinysubversions.com/)进行了交谈，他是 fediverse 的早期采用者，也是一名积极使用分散技术的开发者。他也是 Twitter 上机器人的多产创造者，事实证明这是他在 2017 年注册乳齿象的动力。多年来，他和他的机器人创造者同事一直在问自己，“当平台[Twitter]对机器人变得不友好时，我们该怎么办？”嗯，2017 年就是那种情况发生的时候。

“我想说，那是在 2017 年，Twitter 开始以一种前所未有的方式真正打击机器人——打倒了许多坏机器人，但也打倒了许多好机器人。有一个上诉过程[但是]非常费力，而且维护东西变得非常困难。然后他们还改变了所有的 API，这是机器人如何与 Twitter 对话的编程接口。所以他们在没有任何警告的情况下改变了它们，所有的东西都坏了。这就是我刚才说的:看，我显然需要在我控制的软件上托管这些东西。所以 2017 年是我第一次开始特别关注乳齿象的时候。”

## 多元化的灵活性

fediverse 应用程序的功能比 Twitter 这样的集中式平台更加多样化和具有前瞻性。卡泽米过去几年的发展就是一个很好的例子。

2018 年 8 月，卡泽米创建了自己的乳齿象服务器(一个“实例”)，名为[好友营](https://friend.camp/)。但他不想让它成为一个受欢迎的例子——他想运营一个用户不到 100 人的小型社交网络。目标是促进与社区相关的讨论，并获得一种“[团队凝聚力](https://runyourown.social/#keep-it-small)”的感觉第二年，基于他经营朋友营的经验，卡泽米将乳齿象植入了一个新的软件包，他称之为[故乡](https://github.com/hometown-fork/hometown)。它的一个主要特点是“仅本地发布”，这给了用户*不*联合他们的帖子的选项。

我问卡泽米，仅本地选项在朋友阵营中使用的频率是多少？他回答说，100%的活跃用户都使用这个功能，而且“大概 70%的聊天都是在本地社区内进行的。”那么，为什么乳齿象不提供只在本地发布的选项呢？

“乳齿象不提供这种服务的原因之一，”他回答道，“是因为他们担心这些社区本质上是孤立的，而不是真正的联盟——在那种情况下，他们还不如只是一个留言板，对吗？问题是，如果你看看我们服务器上每个用户的帖子数量，它比大多数[乳齿象]服务器要高得多。所以我认为发生的事情是，本地帖子起到了火上浇油的作用——它让人们想发更多的帖子。因此，尽管我们只有 30%的帖子发布到世界各地，但总的来说，从我们的服务器发布到世界各地的帖子比同等规模的大多数服务器都多。”

因此，发帖的灵活性是 Fe diversity 的一个优势——特别是在 homeland 上，但 Mastodon 也比 Twitter 有更多的隐私选项(例如，“未列出”的帖子意味着它不会被索引)。fediverse 的另一个好处是，你可以从一个地方关注不同类型的内容。这类似于 RSS 过去的工作方式，你可以订阅某人的博客，也可以在 Flickr 上订阅他们的照片。在脸书收购 FriendFeed 之前，你可以使用 Feed 阅读器或者 FriendFeed 之类的应用来订阅这两个 feed。你可以用 Fe diversity 做类似的事情。

“举个例子，”卡泽米说，“很多人在乳齿象上有一个账号，然后他们也在 [Bookwyrm](https://bookwyrm.social/) 上有一个账号，这是一个联合 Goodreads 的替代品——他们在那里谈论书籍，评论书籍，等等。但是因为都是联合的，我可以订阅乳齿象上的这两个账户。不像 Goodreads，我必须注册一个 Goodreads 账户才能看到你的书评。”

## 躲在协议后面

说到 RSS， [ActivityPub](https://activitypub.rocks/) 是 fevariety 的底层协议。它由万维网联盟(W3C)的[支持](https://www.w3.org/TR/activitypub/)，因此它是一个既定的网络协议。我问卡泽米，他是否认为大型科技公司最终会支持 ActivityPub，就像它们在 21 世纪初支持 RSS 一样？我补充说，也许 RSS 不是一个好的学习榜样，因为谷歌最终统治了 RSS 生态系统(通过它的谷歌阅读器产品)，但后来放弃了它。

“这很有意思，”卡泽米回答道，“因为谷歌在另一个联合协议上也有优势，那就是电子邮件。但 Gmail 足够有用，能让谷歌赚钱，所以它不会去任何地方。但是还有其他的联合协议——曾经有一段时间 Google Talk 支持 [XMPP](https://xmpp.org/) 【可扩展消息和存在协议；消息和状态的开放标准。]基本上，Google Talk 曾经与其他聊天服务互连。有一会儿，然后就没有了——他们走回去。所以这绝对是你看到的一种模式。”

XMPP 的例子是一个很好的例子，因为它显示了大型科技公司如何在合适的时候践踏开放协议。[2015 年](https://xmpp.org/2015/03/no-its-not-the-end-of-xmpp-for-google-talk/)，XMPP 博客被迫指出 Google Talk 不再完全支持 XMPP 的各种方式——然而谷歌并没有明确表示它已经停止支持。当时，谷歌正在用 Hangouts 取代 Google Talk，但新产品还不能与联邦 XMPP 客户端互操作。快进到 2022 年，仍然不清楚谷歌的哪些产品支持 XMPP。XMPP 网站[声明](https://xmpp.org/about/faq/)“谷歌将其用于谷歌云消息”——不管这是什么意思。

不管 bigco 围绕开放协议耍什么花招，卡泽米并不担心 ActivityPub 会发生什么。“对我来说，好消息是，如果大公司真的介入(支持 ActivityPub)，然后又走回来，”他说，“最糟糕的情况是，我们会回到现在的位置，这仍然是一个相当不错的地方。”

## 提示:成为主机提供商

卡泽米现在为乳齿象创建了机器人，并将它们托管在 Glitch 上([这里有一个例子](https://tinysubversions.glitch.me/u/bottwosentencehorror))，所以他很高兴不再需要依赖 Twitter 的集中式服务器来满足他的技术爱好。“我还在开发一些其他定制软件，让你在 Glitch.com 上拥有一个小型机器人服务器，”他告诉我。

至于更大的生态系统，他渴望看到更多的主机服务提供商出现，这样 fediverse 才能继续扩张。他承认这是“一种先有鸡还是先有蛋的情况”，因为需要有对联合托管的需求，这样它才是可行的。无论如何，这是好奇的开发者开始探索 Fe diversity 的一种方式——成为一个主机，向其他人开放你的服务器，然后在那个平台上为你的社区构建东西，就像大流士·卡泽米所做的那样。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>