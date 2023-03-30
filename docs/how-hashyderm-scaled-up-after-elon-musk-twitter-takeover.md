# Hachyderm.io，从辅助项目到 38，000 多个用户，并且还在增加

> 原文：<https://thenewstack.io/how-hashyderm-scaled-up-after-elon-musk-twitter-takeover/>

早在四月份， [Kris Nóva，](https://www.linkedin.com/in/kris-nova/)现在是 GitHub 的首席工程师，开始[在她的地下实验室里创建一个关于乳齿象](https://thenewstack.io/build-your-own-decentralized-twitter-part-3-hello-mastodon/)的服务器作为辅助项目。

[https://www.youtube.com/embed/JfM1-AF-_9o](https://www.youtube.com/embed/JfM1-AF-_9o)

视频

然后在 10 月下旬，埃隆·马斯克以令人垂涎的 440 亿美元收购了 Twitter，并开始在这家社交媒体巨头裁员数千人，并做出一些改变，疏远了长期用户。

[hachderm . io，从边项目到 38，000+用户，还在统计](https://thenewstack.simplecast.com/episodes/hachyderm)

在接下来的几周里，诺瓦的爱好网站 Hachyderm.io 的使用量激增。

“服务器开始时非常小，”她在新的 Stack Makers 播客中说道。“我认为，我的一个朋友变成了我的两个朋友，我的 10 个朋友变成了我的 20 个同事，就这样，他们中的许多人都是科技行业的名人。现在突然之间，我要照看 3 万人。”

诺娃说，尽管最近几天新用户加入 Hachyderm 的速度有所放缓，但截至 12 月 20 日，用户数量仍超过 38，000 人。

Hachyderm.io 仍然由少数志愿者运营，他们也负责内容审核。Nóva 现在正在向美国国税局申请非营利组织身份，打算围绕 Hachyderm 建立一个新的组织。

这一集《创客》由 TNS 特稿编辑希瑟·乔斯林(Heather Joslyn)主持，讲述了 Hachyderm 的起源，以及随着科技社区的 Twitter 用户被它吸引而扩大规模所面临的挑战。

Nóva 和 Joslyn 加入了 DigitalOcean 的首席产品官 Gabe Monroy 的行列，帮助 Hachyderm 应对其快速增长的技术需求。

## HugOps 和解决存储问题

突然有一个社交媒体网络来“照看”带来了许多挑战，包括快速扩大规模所涉及的技术问题。Monroy 和 Nóva 都在微软工作时参与了 Kubernetes 项目，“所以我们都在关注横向分布的生活。”但是乳齿象应用程序的结构被证明是混乱的。

“在这里，我正在操作一个 Ruby on Rails monolith，它被设计成在一个硬件上垂直缩放，”Nóva 说。“我们试图打破这种局面，让它在我身后的机架上水平运行。因此，我们在很早的时候就遇到了很多麻烦，因为我们只考虑了服务本身，并开始将其分解为微服务。”

存储也迅速成为一个问题。“我们有一些非企业级的消费级固态硬盘。我们每天进行数百万次读写，仅仅是保持 Postgres 数据库在线。这在我们的分布式覆盖范围内导致了连锁故障和连锁停机，仅仅是因为我们的 Postgres 服务跟不上。”

数字海洋帮助解决了存储问题；该网站现在使用位于德国的数据中心，其服务器由 DigitalOcean 管理。(在此之前，它的服务器被[放在诺瓦的地下实验室里。](https://community.hachyderm.io/blog/2022/12/03/leaving-the-basement/))

Monroy 是 Nóva 的老朋友，是 Hachyderm 的早期用户，当他注意到网站上的问题时就会联系他，比如当他难以发布视频并注意到其他人抱怨类似问题时。

“这是一个正在形成的‘成功/失败’,其规模令人难以承受，”蒙罗伊说。“所以我给诺瓦发了条短信，‘嘿，发生什么事了？我能帮上什么忙吗？

“在社区中，我们喜欢谈论 HugOps 的概念，对吗？当人们在这方面有问题时，你伸出手去，试着帮助他们。你给我一个拥抱。所以，这就是我所做的一切。诺瓦非常清晰明了:这就是我正在做的事情。这些是问题所在。这些是你可以提供帮助的领域。”

## 维持“社交媒体的 NPR”

一个特别的挑战促使诺瓦寻求非营利地位:运营成本。

“现在，我可以自己承担成本，”她说。“我运营着一家 Twitch stream，我们正把它的收益用于运营服务。”但她承认，随着 Hachyderm 的成长，这种情况不会持续下去。

“就我而言，它的整个目标是尽可能保持可持续性，”诺瓦说。“这样我们就不必用广告、营销或产品营销来抵消运营成本。我们可以尽量让它保持中立，坦率地说，尽可能地乏味——社交媒体的 NPR，如果你能想象出这样的事情的话。”

查看完整集，了解 Hachyderm 如何扩展和规划未来的更多细节，以及 Nóva 和 Monroy 对 Twitter 现状的看法。

* * *

*反馈？在 Hachyderm.io.* 上的 [@hajoslyn](https://hachyderm.io/@hajoslyn) 找我

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>