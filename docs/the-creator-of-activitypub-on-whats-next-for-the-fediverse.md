# 一个关于 Fediverse 下一步的活动的创建者

> 原文：<https://thenewstack.io/the-creator-of-activitypub-on-whats-next-for-the-fediverse/>

Evan Prodromou 从事去中心化社交媒体已经将近 15 年了，他在 2008 年创建了一个名为 Identi.ca 的开源 Twitter 替代品。该服务经过几次演变，最终成为 pump . io——这是 2022 年核心 fediverse 协议 [ActivityPub](https://thenewstack.io/devs-are-excited-by-activitypub-open-protocol-for-mastodon/) 的起源。

在接受 New Stack 的采访时，Prodromou 谈到了 ActivityPub 是如何发展的，Mastodon 的利弊，以及他在 Fe diversity 中看到了开发人员的机会。

正如我在以前的文章中所报道的，在埃隆·马斯克混乱地接管 Twitter 之后，[联合社交软件](https://thenewstack.io/lighting-a-bonfire-under-social-media-devs-and-activitypub/)的时代似乎终于到来了。因此，我首先问普罗德罗莫，他是否对乳齿象目前的流行有一种认同感。

“我百感交集，”他苦笑着回答。“有一种欢欣鼓舞的感觉，事实是越来越多的人开始体验社交媒体的这种(联合)结构及其好处。这很好。我尽量不幸灾乐祸太多，对吧，[因为]成千上万的人失去了他们在 Twitter 的工作。许多人正在失去对他们的健康、心理安全或接触世界非常重要的社区。所以我尽量不吹嘘 Twitter 有这么多问题有多好。同时，看到乳齿象起飞真的很令人兴奋。这个非常活跃的社区，能够查看我的乳齿象时间表，看到许多帖子和有趣的对话，这非常神奇。”

## Fediverse 的简短技术历史

在维基百科上，fediverse 被定义为“用于网络发布的联合(即互联)服务器的集合。”维基百科在其术语历史中首次引用了 Prodromou，引用了 Ideniti.ca 和随后的 OStatus 开放标准。按照 Prodromou 的描述，OStatus 是一个由不同的独立协议组成的堆栈，这些协议共同构成了联邦的基础。

他解释说，OStatus 的成分是“PubSubHubbub、Salmon、WebFinger 和 Atom 上的 Activity Streams 所有这些都基于 XML，这是一种更古老的序列化格式，在 21 世纪初很流行，随着 JSON 的出现，它变得不那么流行了。”

当 Prodromou 在 2010 年 3 月宣布 OStatus [的时候，他把它宣传为一种让“不同社交网络上的人互相关注”的方式。注意，在那个时候，Activity Streams](https://web.archive.org/web/20100307052403/http://ostatus.org/2010/03/04/its-started) [是](http://activitystrea.ms/?utm_source=thenewstack&utm_medium=website&utm_content=inline-mention&utm_campaign=platform)(用项目网站的话说)“Atom feed 格式的扩展，用来表达人们在网络上做什么。”

但是正如 Prodromou 在我们的谈话中暗示的那样，随着 2010 年代的开始，XML 格式很快就不再流行了。这迫使我们重新考虑联邦的底层协议，这次使用基于 JavaScript 的 JSON 作为数据格式。

“在 2012-2013 年，我开始致力于 pump.io，这是使用 JSON 中的新活动流对该结构[OStatus]的重新思考，”他解释道。“我真的很想创造一个简单的引擎，可以让这个协议工作。我使用 Node.js 来构建它——使用 Node.js 是一种美妙的体验。”

他所指的活动流协议现在被称为 [JSON 活动流 1.0](https://activitystrea.ms/specs/json/1.0/) ，这是基于 JSON 的活动流的第一个版本。它于 2011 年 5 月发布。Prodromou 不是该规范的作者，但他是 W3C 在 2017 年 5 月发布的当前 [2.0 版本 Activity Streams](https://www.w3.org/TR/activitystreams-core/) 的共同编辑。

## 乳齿象:很复杂……

尽管他在 2000 年代末和 2010 年代做了基础性的工作，最终导致了 ActivityPub 的 W3C 规范[, Prodromou 努力将自己的微博产品转变为可持续的业务。](https://www.w3.org/TR/activitypub/)

[Identi.ca](https://identi.ca/) 仍然存在，作为运行在 [pump.io](http://pump.io/) 协议上的开源软件。但它并没有成为联合社交软件的旗舰产品。这一荣誉属于乳齿象，一个由德国开发者 Eugen Rochko 创造的独立产品。当它在 2016 年推出时，乳齿象使用 OStatus 作为其协议。然后 2017 年 9 月转投 ActivityPub。

当我在 2022 年 10 月的#TwitterMigration 期间重新加入乳齿象时，我在乳齿象上搜索 Prodromou，但找不到他。他最终在 11 月再次签约，但这让我想知道他对乳齿象的真实想法。毕竟，他早在 2008 年就试图推出一款非常相似的产品。

“首先让我说，成功是无可争辩的，”他回答说。“很明显，在所有创建联合社交软件的尝试中，乳齿象是迄今为止最成功的。”

他把乳齿象的成功归功于由 Eugen Rochko 领导的“非常务实和以用户为中心的开发团队”。

也就是说，Prodromou 认为乳齿象没有使用他帮助定义的协议的全部功能。

“现在，我希望看到的关于 fediverse 架构的下一步发展是，在 ActivityStreams [2.0]中，我们定义了一个客户端到服务器的 API。因此，类似于 Twitter API，它用于创建在 Twitter 上运行的应用程序，如 TweetDeck。我们为 ActivityPub 定义了一个[类似的]标准 API。因此，任何 ActivityPub 服务器都会公开相同的 API，[所以]你可以有一个 TweetDeck，它可以与 Pleroma 或 Mastodon 或 Pixelfed 或其他任何东西一起工作。就那些面向用户的应用程序而言，这有点有趣。但当你开始谈论彼此互动的网络应用时，事情就变得非常有趣了。”

目前，Mastodon 的主要 API 是它的自定义 API，Prodromou 认为这限制了想要在 fediverse 中构建的开发人员的创造力。

“将 Fe diversity 带到下一个层次，并看到标准客户端 API 的实现对我来说意义重大，”他说，“因为这将释放我们在网络上看到的内容的创造力。”

## 新型社交网络的时代到了

除了他希望看到的技术改进，Prodromou 还思考了 fediverse 最终会变成什么样。他认为，人们需要一段时间来“从 Twitter 体验中戒毒”，并意识到他们的社交媒体世界不再受企业操纵。虽然他认识到 fediverse 社区中的一些人不希望对他们在乳齿象上的订阅进行排序或优化，但他的目标是有所不同。

“我希望在优化你的订阅源、网络等方面做更多的工作。他举了一个例子，一个初级软件开发人员围绕学习 RUST 组织他们的 feed，并与在该主题上给予指导的人联系。

“因此，在追求我们自己的职业发展、个人发展和人际关系目标时，从软件中获得一些帮助……我认为这真的很有趣，”他继续说道。“这不是 Twitter 或脸书将要做的事情，因为他们正在优化让你点击广告。”

我说，当前这个时期的 fediverse 让我想起了 21 世纪初，当时网络都是关于 RSS 提要和开放数据的，我们有工具来聚合、过滤和“混搭”这些数据。

Prodromou 表示同意，并说“有机会在 fediverse 上围绕利益集团做类似的事情。”他希望为人们提供分组、排序、连接、提醒、通知等工具。

他说，“我真的很想看到人们把社交软件看作是提升他们的生活，让他们的生活变得更好的东西。”

这当然是我从 Mastodon 和 fediverse 开发人员社区感受到的氛围。自己去看看吧，也许可以从跟随 ActivityPub 大师开始。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>