# 计算聚合空闲 CPU 以创建分散的超级计算机

> 原文：<https://thenewstack.io/computes-aggregates-idle-cpus-create-decentralized-supercomputer/>

如果您可以利用公司服务器、工作站、物联网设备甚至手机中所有未使用的计算能力来创建一台超级计算机，而无需支付购买费用，会怎么样？

这就是最近推出测试版的 [Computes](http://computes.com/) 背后的想法。

任何有 CPU 或 GPU 的东西都可以加入一个私有的、安全的网状网络，共同创造出创始人[克里斯·马蒂厄](https://twitter.com/chrismatthieu?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)所说的网状超级计算机。其结果是足够的计算能力来执行基于串行的[机器学习](/category/machine-learning/)算法以及大规模并行超级计算任务，即使在生成机器数据的边缘网络上。并且不需要购买更多的基础设施。

举个例子，威斯康辛大学在帕金森氏症的研究中使用了计算机技术。Carrie Rountrey 是通信科学和疾病系的助理教授，她开发了一种算法，通过查看语音邮件中的语音模式来预测疾病的早期发作。

该大学有 20，000 个工作站，希望利用它们来支持研究。

## 边缘计算

马蒂厄承认他痴迷于《终结者》电影中的[天网](https://thenewstack.io/building-the-real-skynet/)人工智能系统，并最初将他之前的公司命名为。后更名为 Octoblu，是 2014 年 12 月被 Citrix 收购的[。](https://thenewstack.io/citrix-acquires-octoblu-the-drone-networking-company-formerly-known-as-skynet/)

Octoblu 是一个让无人机互相交流的系统。它旨在运行于单个网络或物联网网络网格上，这些网络共享一个通用 API 或通信协议，使设备能够发现、查询和发送消息给网络上的其他设备。

Citrix 将该技术[开源](https://github.com/octoblu)，但决定停止内部开发。

Mattieu 说，计算机的早期想法是建立一个集中式云超级计算机，其中云将工作分配给节点，但“我很快意识到云和边缘之间的所有这些线真的不应该存在”。“每个人都试图移动到边缘，就像[自动驾驶汽车](https://www.youtube.com/watch?v=i-p42PImMto)没有时间向云提出请求，然后做一些学习并带着答案回来。一切都必须发生在计算产生的地方。”

该网络是去中心化和分布式的，基于 Mattieu 所谓的“T0”无阻塞技术“T1”

使用区块链技术，您将数据写入一个“块”，在这里您对数据块进行加密哈希、挖掘和签名，然后将其发送到数据库。他解释说，链条上的每台计算机都有整个数据库的副本，这意味着物联网设备太小，甚至无法成为其中的一部分，而且速度很慢。

最著名的比特币的吞吐量仅为每秒[三笔](https://hackernoon.com/beginners-guide-to-bitcoin-s-scalability-debate-66060f3799e5)交易，而以太坊的吞吐量高达每秒 [13 笔](https://medium.com/@FEhrsam/scaling-ethereum-to-billions-of-users-f37d9f487db1)。相比之下，Visa 的网络每秒处理 24000 笔交易。

Computes 使用类似于 [IOTA](https://iota.org/) 的技术，使用[有向无环图](http://ericsink.com/vcbe/html/directed_acyclic_graphs.html) (DAG)或 [Merkle 树](https://www.youtube.com/watch?v=lik9aaFIsl4)来存储事务。它用在 GitHub 上，在 GitHub 中，您可以跟踪每个代码提交，并追溯到它起源的树的分支，并找到每个提交的相关时间戳。

它不需要像区块链网络上的采矿工作证明，也不需要每台设备维护一个完整的数据库，使它更快。

为了创建自组织和自修复网络，每台设备都需要一个 5MB 的软件“纳米核心”

所有东西都是加密的，无论是传输中的还是静止的。他说，只有那家公司的纳米核心知道如何在私人网状网络上群集和组织自己。它使用 IPFS ( [星际文件系统](https://medium.com/@ConsenSys/an-introduction-to-ipfs-9bba4860abd0))，这是一个共享文件的对等系统，也有发布/订阅消息协议。它允许所有节点相互发送消息，并讨论需要在哪个纳米核心上做什么。然后，当这些纳米核请求工作时，就有 IPFS 文件的哈希作为输入，这些核返回 IPFS 哈希，以确定输出文件在这个网状网络中的位置。

目前，这家总部位于亚利桑那州凤凰城的公司专注于需要大规模计算能力的大型企业，如科学研究。

他说，以后，公众可能会有机会通过出售过剩产能赚点钱。

他说，国家帕金森基金会也在考虑这样的前景，即它可能能够将患者和支持者之间的计算结合起来，这些患者和支持者可能希望将他们多余的 CPU 和 GPU 资源捐赠给研究项目。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>