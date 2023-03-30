# 帕勒的数据是如何收集的

> 原文：<https://thenewstack.io/how-parlers-data-was-harvested/>

[右翼社交网络 Parler 已经消失](https://www.zdnet.com/article/aws-cuts-off-parler-ceo-aims-to-rebuild-infrastructure/)。[亚马逊网络服务(AWS)](https://aws.amazon.com/) 关机。而且，可以说，帕勒不会回来了。然而，帕勒的数据，包括[死亡威胁](https://www.pacermonitor.com/view/LHNWTAI/Parler_LLC_v_Amazon_Web_Services_Inc__wawdce-21-00031__0010.0.pdf?mcid=tGE3TEOA)和带有地理标记的已删除信息，已经被删除，并被公布在众多公共网站上。这是怎么做的。

一名网名为 [@donk_enby](https://twitter.com/donk_enby) 的黑客从 1 月 6 日开始下载每一篇 Parler 帖子，寻找“有罪”证据。那一天，美国总统唐纳德·特朗普在白宫外的一次集会上，敦促他的一群支持者游行到附近的国会大厦。由此引发的混乱导致五人死亡，包括一名警察。据报道，帕勒曾被攻击者用来帮助协调他们对国会大厦的攻击。据称，他们考虑不周的计划是迫使国会推翻 2020 年的选举结果，并让唐纳德·特朗普继续担任总统。

当 AWS 关闭 Parler 的消息传出后，donk_enby 查阅了 Parler 的所有公开记录。2000 年，从 Parler 中收集了超过 70TB 的数据.冬克·恩比随后将数据上传到互联网档案馆。已经制作了许多其他的数据副本。冬克·恩比在推特上写道[帕勒的数据可能包括删除的和私人的帖子](https://twitter.com/donk_enby/status/1348281461435207680)，视频包含“所有相关的元数据”

有传言称 Parler 的数据已经被窃取，因为当 Twilio 禁止 Parler 使用其程序时，它取消了 Parler 认证其账户的能力。事实并非如此。Twilio 的一名代表表示:“关于 Parler 遇到的网络安全问题的报告，我们的安全团队调查了这些指控，并没有发现任何证据表明他们的安全问题与 Twilio 或我们的产品有关。”

对于这些谣言，donk_enby 有她自己的简短回复，以及实际上发现了什么数据:“自从[许多人似乎对这个细节感到困惑](https://twitter.com/donk_enby/status/1348666166978424832)并且有一个胡扯的 reddit 帖子在流传:只有通过网络公开的东西才被存档。我没有你的电子邮件地址、电话或信用卡号码。除非是你自己在 parler 上贴的。”

也就是说，[美国共和党国会议员和](https://greene.house.gov/) [Qanon 阴谋论者](https://www.independent.co.uk/news/world/americas/us-election-2020/marjorie-taylor-greene-mask-trump-impeachment-b1786952.html)Marjorie Taylor Greene要求[人们在 Parler](https://twitter.com/katherinetheok/status/1348672091659378690/photo/2) 上分享他们的电话号码和电子邮件地址。即使会员没有分享这些信息，Parler 通过不删除包括 GPS 坐标在内的图像和视频元数据，使得追踪许多 Parler 用户的真实身份成为可能。

删除的邮件也被捕获。那是因为 Parler 的专有程序实际上并没有删除它们。相反，它只是简单地将它们标记为对用户不可见。糟糕，糟糕的安全程序。

那么，到底是怎么做到的呢？

一点也不复杂。冬克·恩比早些时候[对 Parler iOS 客户端](https://github.com/d0nk/parler-tricks)进行了逆向工程，该客户端是用 Python 编写的。donk_enby 利用其 API(一款越狱的 iPad)和 [Ghidra](https://www.nsa.gov/resources/everyone/ghidra/) (一款美国国家安全局(NSA)开源逆向工程工具)利用 Parler 设计中的弱点。有了这些，donk_enby 和其他人按顺序删除了所有 Parler 公开帖子的 URL。这反过来使她能够捕捉和保存消息。

更简单的是，Parler 的 API 不需要认证。任何人在任何时候都可以使用它来查看其所有成员的公共内容。也没有数据节流。一旦数据开始流经 API 管道，唯一的限制就是服务器发送信息的速度和你的互联网连接速度。

如果帕勒的部分听起来真的很愚蠢的编程，你不会错。它有一个像鲸鱼一样大的安全漏洞。

在 [Wired](https://www.wired.com/) 的一份报告中，[开放加密审计项目](https://opencryptoaudit.org/)的联合主管 Kenneth White 说，核心问题是它对其按时间顺序排列的消息 URL 使用简单的加 1 构成了不安全的直接对象引用(IDOR)问题。把所有这些放在一起，你不需要访问管理帐户或成为一个疯狂的黑客天才。

怀特告诉《连线》，“这就像一个[计算机科学 101 糟糕的家庭作业](https://www.wired.com/story/parler-hack-data-public-posts-images-video/)，那种你第一次学习网络服务器如何工作时会做的事情。我甚至不会称之为新手错误，因为作为一名专业人士，你绝不会写出这样的东西。”

真正的问题不是攫取公共记录；在 AWS 关闭 Parler 之前，它已经能够抓取万亿字节的数据。

幸运的是，donk_enby 在“大拉动”中找到了朋友来帮助下载 Parler 的几乎所有数据。存档团队(Archive Team)是一个致力于从天空中的巨大比特桶中保存网站和数据的志愿者组织，他们带来了自己的人和一个新开发的下载工具。这与自动创建新 Parler 帐户的[脚本](https://gist.github.com/d0nk/7251444a195dbb60ab9cc69987070e21)相结合，使得 Parler 的大部分数据被记录下来并存档，以供历史和潜在的合法使用。

此时，数据很大程度上只能以原始形式获得。然而，一些项目已经被创建，以使任何想了解 Parler 内幕的人都可以方便地获得 Parler 用户的信息、视频和照片。

这个故事的技术寓意？如果你打算写一些声称是私人的和安全的社交网络，你应该有一个关于安全的线索。Parler 的安全性是一个糟糕的笑话，这个笑话现在已经在它的数百万前会员中流传。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>