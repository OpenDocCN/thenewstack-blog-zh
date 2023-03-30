# 谷歌云阻止怪物 DDoS 攻击

> 原文：<https://thenewstack.io/google-cloud-stops-monster-ddos-attack/>

[分布式拒绝服务(DDoS)攻击不需要大到对目标造成严重破坏](https://www.zdnet.com/article/ddos-attacks-size-doesnt-matter/)，但不会造成伤害。在最近一次有史以来最大的攻击中，[谷歌抵挡了 HTTPS 的 DDoS 攻击](https://cloud.google.com/blog/products/identity-security/how-google-cloud-blocked-largest-layer-7-ddos-attack-at-46-million-rps)，其峰值为每秒 4600 万次请求(RPS)。这使得它成为迄今为止 DDoS 报道的最大的[第 7 层](https://thenewstack.io/the-osi-7-layer-model-can-help-define-enterprise-application-security/)，应用层。这比之前报道的记录大了 76%。

那么它有多大呢？想象一下，在短短 10 秒钟内，一天的请求从到[维基百科](https://www.wikipedia.org/)都被敲定了。

是啊，太多了。

欢迎来到 2022 年的互联网。几周前，Cloudflare 击退了当时创纪录的 2600 万次 RPS 攻击。在此之前，Cloudflare 在 2021 年 8 月处理了一次 [17.2M RPS HTTP DDoS 攻击](https://blog.cloudflare.com/cloudflare-thwarts-17-2m-rps-ddos-attack-the-largest-ever-reported/)。巨大的 DDoS 攻击越来越频繁地发生。这些让过去的顶级 DDoS 攻击相形见绌。

## 谷歌云装甲拯救世界

在最近的一次攻击中，一名 [Google Cloud Armor](https://cloud.google.com/armor) 客户遭到了攻击。它始于太平洋时间 2022 年 6 月 1 日上午 9:45，对客户的 [HTTP/S 负载均衡器](https://cloud.google.com/load-balancing/docs/https)发起了超过 10，000 RPS 的攻击。这很烦人，但并不令人担忧。

但是，甚至不到十分钟后，当它增长到 100，000 RPS 时，毫无疑问，该公司受到了攻击。谷歌的云装甲自适应保护检测到了攻击，并生成了包含攻击签名的警报。该签名基于几十个特征和属性的流量。这对于已经在其云防护安全策略中使用自适应保护的客户毫无帮助。这使得 Cloud Armor 建立了一个基准正常流量模型。

随后，用户的安全仪表板上弹出警报，并推荐一条规则来阻止带有恶意签名的流量。他们并不愚蠢，确实那样做了。他们可以简单地阻塞交通，但那会使他们真正的交通慢如蜗牛。

之后，攻击增加到数百万次，最终达到 4600 万次的峰值。但是几乎没有恶意流量到达客户的服务器。相反，由于云盔甲已经在谷歌网络的边缘阻挡了攻击流量，服务器继续正常工作。除了攻击者和安全专家，没有人知道袭击正在发生。

在接下来的几分钟里，攻击减少了。69 分钟后的上午 10 点 54 分，它终于结束了。据推测，攻击者发现它没有起作用。

## 这个故事的寓意

现在，根据谷歌的说法，这个故事的寓意是“有了 [G](https://cloud.google.com/armor) o [ogle Cloud Armor](https://cloud.google.com/armor) ，你就能够在谷歌网络的边缘保护你面向互联网的应用程序，并从你的应用程序的上游吸收不受欢迎的流量。”他们没有错。如果你在谷歌云上运行网络服务，我建议你使用谷歌云盔甲。

然而，更大的寓意是，无论您是在自己的裸机上运行简单的 web 服务器，还是为财富 500 强公司运行复杂的 web 服务，您都需要 DDoS 保护。DDoS 攻击变得越来越大，也越来越容易被任何混蛋尝试。我推荐 [Akamai](https://www.akamai.com/solutions/security/ddos-protection) 、 [Radware](https://www.radware.com/products/defensepro/) 和 [Cloudflare](https://developers.cloudflare.com/ddos-protection/) ，排名不分先后。和谷歌一样，其他超云服务也提供 DDoS 保护。

无论你选择什么，都要有所收获。你会很高兴你做了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>