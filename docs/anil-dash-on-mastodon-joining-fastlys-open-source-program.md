# Anil Dash 谈乳齿象加入 Fastly 的开源程序

> 原文：<https://thenewstack.io/anil-dash-on-mastodon-joining-fastlys-open-source-program/>

Anil Dash 是我认识很久的一个人，套用 Kara Swisher 在她几乎所有播客开头的一句话。我记得 2007 年在旧金山的 Web 2.0 博览会上，我和他坐在一起，听取他关于发展我的科技博客业务 ReadWriteWeb 的建议。当时，达什正在为 Six Apart 工作，该公司拥有可移动博客平台(RWW 曾使用过)。感觉就像在和我哥哥聊天。尽管他比我小几岁，但他有一种冷静、睿智的气质，这与我当时的天真形成了鲜明对比。他还把握住了网络创新的脉搏；今天也是如此，当我通过 Zoom 赶上 Dash 时，我发现了这一点。

现在，Dash 是 Fastly 的开发人员体验副总裁，Fastly 是领先的内容交付网络公司之一。我很好奇 Fastly 的[快进项目](https://www.fastly.com/blog/fast-forward-lets-build-the-good-internet-together)的最新进展，该项目于 11 月启动，旨在支持开源互联网项目。原来，Fastly 资助的一个项目是乳齿象，开源 Twitter 的替代品。

“乳齿象已经加入了快进计划，”他证实道。“我们正在考虑支持其基础设施。”

达什本人也很快在《乳齿象》上为[赢得了超过 25000 名粉丝。他一直是社交媒体的超级用户(他的 Twitter 粉丝有 57.4 万)，所以值得注意的是，他现在在乳齿象上的对话比 Twitter 上的多——关键是，如果其他超级用户也这样做，那最终将为乳齿象创造一个转折点。](https://mastodon.social/@anildash@me.dm)

Dash 坚信社交媒体的未来将是联合的；至少部分是因为这是对早期博客世界最好的一面的回归，他和我都是其中的一部分。然而，为了实现这一未来，眼前的挑战是扩展基础设施。

“当我分享读写网的链接时，那是开放协议和互操作性——我们可以用这种方式建立社交，对，我们有这些白日梦。仅乳齿象，这只是 Fe diversity 的一部分，将在未来几周内通过所有不同的实例，达到 1000 万用户。你我都清楚地记得，在不到那个规模的时候，每天都有一条‘失败的鲸鱼’。”

他指的是早期臭名昭著的 Twitter 宕机——似乎每隔一两天，该网站就会宕机，并显示一幅由 8 只橙色小鸟托起鲸鱼的漫画。

“这就是《快进》生来要做的事情，”达什继续说道。“通过提供快速的规模、快速的信任和安全性，我们所做的一切。我们可以通过支持一个开源项目来建立对开放网络的信任，这个项目的最大挑战不是构建新功能，不是构建 API——所有这些都不是——而是规模和在全球范围内的实时性。”

Dash 认为 Fastly 的快进计划“从根本上实现了 Fe diversity”，并有助于使乳齿象成为“一个令人难以置信的平台[……]，否则它将非常令人担忧或脆弱，如果[Fastly]不在那里，它将危及整个平台的采用。”

## *新*新栈

在担任 Fastly 的现任职务之前，Dash 是 Glitch 的首席执行官，Glitch 是一个基于浏览器的应用程序创建工具，去年 5 月被 Fastly 收购。他现在继续管理 Glitch，这(除了其他事情之外)允许他监视开发人员之间的趋势。这就是为什么当他在最近的[乳齿象帖子](https://mastodon.social/@anildash@me.dm/109719178668601387)中说“Fe diversity+wasm+tailscale 的新网络正在非常迅速地走向一些非常惊人的东西时，我的耳朵竖了起来。”

在过去的一年里，我已经报道了[Fe diversity development](https://thenewstack.io/the-fediverse-points-to-our-social-media-future-post-musk/)，我在 New Stack 的同事们已经走遍了 [WebAssembly](https://thenewstack.io/what-is-webassembly/) (Wasm)，但是到目前为止，第三个还没有得到科技媒体的太多关注。Tailscale 是由前谷歌工程师在 2019 年创立的，[将自己](https://tailscale.com/kb/1151/what-is-tailscale/)描述为“一种 VPN 服务，使你拥有的设备和应用程序可以在世界任何地方访问。”但是它是如何与 fediverse 和 Wasm 一起使用的呢？

事实证明，Jason Donenfeld 开发的开源 VPN 协议 WireGuard 才是真正让 Dash 感兴趣的。Tailscale 建立在这个协议之上。Donenfeld 目前似乎没有参与 Tailscale，但他在他的网站上提到[它在 2022 年向 WireGuard 项目捐赠了一笔资金。](https://www.wireguard.com/donations/)

关于 Tailscale，Dash 解释说:“消费者的体验就像虚拟专用网络一样。”。他已经亲自在他所有的机器和设备上安装了它，这样他就可以轻松地在他的机器之间传送东西。但他建议说，开发者还有更大的权力。“如果你在你所有的服务器或所有的开发环境上安装 Tailscale，”他说，“你可以立即在它们之间路由东西，就像它们在本地网络上一样——不管它们是在数据中心，还是在某人的云上，还是在你的本地机器上，还是其他什么地方。”

然后他把这个绑在了 Fe diversity 上。

“所以想象一下，如果我能在笔记本电脑上运行我的 fediverse 服务器或 Mastodon 服务器，并将其发送到互联网上；然后用 Fastly 缓存，很明显，对吗？让它更快更有性能。”

他在这里得到的是联合社交软件(Fe diversity)，加上 Wasm(一个随处运行的沙盒环境)，加上 WireGuard(安全网络)是一个强大的组合，适用于希望解决 Twitter 和脸书等平台的隐私困境和集中控制问题的开发人员。

当达什在乳齿象上发布这个“新网络”堆栈时，他的帖子得到了大量的评论。一些评论者说他忽略了提到开源数据库引擎 SQLite。

“SQLite 作为一种可以统治所有这些的数据库，确实发生了一些有趣的事情，”Dash 承认。

## 超级用户联合起来

在之前，我已经在[写过几篇](https://thenewstack.io/the-creator-of-activitypub-on-whats-next-for-the-fediverse/) [时报](https://thenewstack.io/why-a-twitter-founding-engineer-is-now-all-in-on-mastodon/) [关于在这个](https://thenewstack.io/devs-are-excited-by-activitypub-open-protocol-for-mastodon/)[后马斯克](https://thenewstack.io/twitter-turmoil-we-need-an-open-protocol-for-public-discourse/)的社交软件时代，这对开发者来说是一个多么激动人心的时刻。但事实是，我们还需要现有平台的超级用户——像 Anil Dash 这样的人——来帮助引导新用户离开集中式平台，转而使用联合平台。

Dash 在开发者社区中也处于一个独特的位置，因为他负责他们最喜欢的平台之一:Glitch。他对开放网络技术如 Fe diversity、Wasm、Tailscale 和 SQLite 的支持有助于进一步推动对话——尤其是如果对话发生在 Fe diversity 上。

再加上 Fastly 的财政援助，以帮助乳齿象扩大规模，现在 Fe diversity 有了一些真正的动力——用户、开发者和(希望很快)新的创业公司。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>