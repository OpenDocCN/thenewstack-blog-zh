# PingCAP 的 TikV 将如何处理中国 8 亿网络购物者的交易

> 原文：<https://thenewstack.io/how-pingcaps-tikv-is-set-to-process-data-from-chinas-800-million-internet-shoppers/>

[KubeCon + CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/) 赞助本帖。

[PingCAP 的 TikV 如何处理中国 8 亿互联网购物者的交易](https://thenewstack.simplecast.com/episodes/how-pingcaps-tikv-is-set-to-process-transactions-from-chinas-800-million-internet-shoppers)

不久前，[平盖](https://www.linkedin.com/in/kevinsxu/)全球战略和运营总经理[许海波](https://www.linkedin.com/in/kevinsxu/)还记得在他的祖国中国，走进一家网吧被他描述为“黑暗和昏暗”的地下室，玩[魔兽世界](https://worldofwarcraft.com/)和吃面条。

“那些日子确实存在，但不再那么多了——现在有许多手机供应商，几乎所有的事情都在你的智能手机上完成，”徐说。

但在 2014 年至 2017 年就读斯坦福大学法学院(Stanford University Law School)后——当时他在校园里参加了高级计算机科学课程，因为他认为法学院“无聊”——中国的互联网经济已经变成了一个截然不同的地方。

“关于中国互联网经济有趣的事情是，第一，自从我上次统计以来，它拥有世界上最多的互联网用户，大约 8 亿人，相当于美国总人口的两倍半，现在可能更多，”徐说。"他们不仅是互联网用户，而且大多是移动用户."

[KubeCon + CloudNativeCon 中国开源峰会 2019](https://www.lfasiallc.com/events/kubecon-cloudnativecon-china-2019/) 在上海举行，为与徐一起录制最新一期 [The New Stack Makers](/podcasts/makers) 播客提供了完美的背景。除此之外，徐还展望了 PingCap 的 [TikV](https://github.com/tikv/tikv) 开源分布式事务关键值数据库如何帮助满足中国互联网经济 8 亿用户的需求，该数据库拥有超过 5，500 个 GitHub stars，并已成为云原生计算基金会的孵化级托管项目。([知乎](https://www.zhihu.com/signup?next=%2F)，中国 Q & A 网站，也是 TikV 项目维护者。)

在中国互联网上处理如此大量的交易数据需要后端系统的单一视图，当然包括所有备份数据。这就是底层编程语言 Rust 和 TikV 的 Raft 协议发挥作用的地方。“随着数据集的增长，当你向集群中添加更多的节点时，你不想在这方面妥协，这就是 Raft 的用武之地，”徐说。“对我们来说，当涉及到 TikV 的设计时，这就是所有其他决策点出现的地方，因为…您不希望您的银行账号出错。即使作为一个不那么重要但仍然重要的例子，比如亚马逊订单，你也不希望这是错误的。”

对徐来说，中国网购者对工程师的要求很有趣，也很有挑战性。“很多人都在谈论中国经济的规模、估值和股市，”徐说。“从一个开发者的角度来看，我觉得有趣的是，你能想出什么样的技术解决方案来吸收所有这些需求。”

Xu 描述了 TikV 和开源的 TiDB(它提供了 SQL 处理层)如何能够扩展到他所说的“一天就有数十亿美元的交易价值”的需求。他说 TiDB 和 TikV 是独立的，“所以它们是两个独立的代码库。”徐说，通过将 TiDB 服务器扩展为无状态节点，这有助于更容易地扩展吞吐量，因此“你可以根据流量模式或促销或公司可能正在运营的任何其他类型的事情来扩展和收缩”

“这非常灵活和有用，因为他们确实有这些疯狂的在线购物日，如果你从金钱的角度考虑，这有点荒谬，但更荒谬的是，如果你像工程师一样，在后端工作，试图确保你的服务不会下降。因此，在我看来，所有这些需求都来自于对更好的创新技术的需求，这种需求来自于这个经济体的特点。”

[https://www.youtube.com/embed/t7WoL13__D4?feature=oembed](https://www.youtube.com/embed/t7WoL13__D4?feature=oembed)

视频

### 在这个版本中:

[1:13:](https://thenewstack.simplecast.com/episodes/how-pingcaps-tikv-is-set-to-process-transactions-from-chinas-800-million-internet-shoppers?t=1:13) 给我们介绍一下 TikV 和 PingCAP
6:17:那么 ping cap 优化 TikV 的方式有哪些呢？
[10:26:](https://thenewstack.simplecast.com/episodes/how-pingcaps-tikv-is-set-to-process-transactions-from-chinas-800-million-internet-shoppers?t=10:26) 为什么建在铁锈里？
[15:56:](https://thenewstack.simplecast.com/episodes/how-pingcaps-tikv-is-set-to-process-transactions-from-chinas-800-million-internet-shoppers?t=15:56) 在中国市场的背景下，你如何看待 TIDB 和 TikV 在企业间的合作？
[19:55:](https://thenewstack.simplecast.com/episodes/how-pingcaps-tikv-is-set-to-process-transactions-from-chinas-800-million-internet-shoppers?t=19:55) 随着向外扩展的继续，中国的提供商和您的客户面临哪些挑战？
[24:05:](https://thenewstack.simplecast.com/episodes/how-pingcaps-tikv-is-set-to-process-transactions-from-chinas-800-million-internet-shoppers?t=24:05)CNCF 孵化状态对 TikV 意味着什么？在接下来的几个周期中，我们应该期待什么？

Alex Williams，The New Stack 的创始人兼主编，主持了这个播客。

云计算原生计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>