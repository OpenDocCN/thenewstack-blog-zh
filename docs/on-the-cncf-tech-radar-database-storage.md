# CNCF 理工大学雷达:数据库存储

> 原文：<https://thenewstack.io/on-the-cncf-tech-radar-database-storage/>

在云本地环境中管理数据库存储仍然是许多组织面临的一个主要挑战。在最新的[云本地计算基金会(CNCF)技术雷达报告](https://www.cncf.io/blog/2020/11/18/cncf-end-user-technology-radar-database-storage-november-2020/)中，数据库存储也成为需要探索的首要问题。

在本版[新堆栈分析师](/podcasts/analysts)播客中，主持人 [Alex Williams](/author/alex/) ，[新堆栈的创建者和发布者，同时主持人还有](https://uk.linkedin.com/in/cheryljhung)[云原生计算基金会(CNCF)生态系统副总裁 Cheryl Hung](https://www.cncf.io/)和[高级员工工程师 Dave zolottsky](https://www.linkedin.com/in/dzolotusky/)[讨论无状态数据库存储、报告的最新结果以及用户群体的观点。](https://www.spotify.com/us/)

播客嘉宾都参与了 CNCF 理工大学雷达报告，来自数据库存储用户社区，他们是 [Jackie Fong](https://www.linkedin.com/in/jackiesfong/) ，Ticketmaster 的工程领导者，Kubernetes 和开发人员，以及 [Mya Pitzeruse](https://www.linkedin.com/in/mjpitz) ，软件工程师，OSS 投稿人 [effx](https://www.effx.com/) 。

[在 Tech Radar:数据库存储](https://thenewstack.simplecast.com/episodes/on-the-tech-radar-database-storage)

当 Pitzeruse 第一次开始致力于团队项目将操作转移到云时，数据库存储是“一个大的未回答的问题”。但是，尽管托管服务替代数据库存储“对我们最初谈论的许多产品来说都很有意义”，但 Pitzeruse 说，“我们开始研究的其他用例表明，托管服务不太适合这种情况。”。

“我们真的很想知道社区成员是如何部署和管理我们正在利用的那些系统的较小实例的，或者是如何转移到可能提供不同保障的替代生态系统中去的，”Pitzeruse 说。“所以，我们尝试了很多不同的方法。”

方的团队也面临着类似的难题，即当迁移到云时，如何找到最可行的数据库存储系统。此外，Ticketmaster 还面临着传统内部数据管理和跨远程地理位置维护数据延迟的挑战，同时仍保持合规性。

Fong 说，顾客“需要买票——如果这个特定的座位现在是空的，半秒钟后就可能没有了。“所以我们的数据必须是即时的。这是基于云的解决方案与内部解决方案之间的一场激烈斗争。”

Pitzeruse 和 Fong 在云上管理数据库的挑战反映了 Spotify 所面临的挑战。数据延迟和访问对 Spotify 的商业模式也尤为重要，因为消费者希望通过 Spotify 的服务即时点播音乐。

“我们对存储的试验非常规避风险，因为……像播放列表这样的东西对我们的业务至关重要，”佐洛图斯基说。“而且，在我们将所有数据、所有播放列表转储到数据存储之前，我们不能将这些数据存储在未经大量其他人验证的数据存储上。”

Spotify 的数据库存储管理很大程度上依赖于以团队为中心的方法。

“我们有一个中央平台团队，我们在很大程度上让功能团队做出自己的决定，但在存储这样的事情上，很少有功能团队愿意做出自己的决定，”Zolotusky 说。“因此，在这种情况下，这在很大程度上取决于该团队可以帮助支持什么，以及功能团队需要什么具体的东西。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>