# 你不需要区块链，你需要时间序列数据库

> 原文：<https://thenewstack.io/you-dont-need-a-blockchain-you-need-a-time-series-database/>

[](https://www.linkedin.com/in/nicolas-hourcard-cfa-b7349b37)

[Nicolas hour card](https://www.linkedin.com/in/nicolas-hourcard-cfa-b7349b37)

[Nicolas 是一个终生的技术爱好者，也是 QuestDB 的联合创始人。他以前为罗斯柴尔德和纳斯达克等公司利用时间序列数据。他把时间分配在伦敦和旧金山之间，喜欢网球、滑雪和每年攀登新的山峰。](https://www.linkedin.com/in/nicolas-hourcard-cfa-b7349b37)

[](https://www.linkedin.com/in/nicolas-hourcard-cfa-b7349b37)[](https://www.linkedin.com/in/nicolas-hourcard-cfa-b7349b37)

近年来，区块链在企业应用中的使用激增——事实上，IBM X-Force Red [已经](https://newsroom.ibm.com/2019-03-050-IBM-X-Force-Red-Launches-New-Service-for-Blockchain-Security-Testing) [说过](https://newsroom.ibm.com/2019-03-050-IBM-X-Force-Red-Launches-New-Service-for-Blockchain-Security-Testing)“组织正从它的使用中看到真正的效率和成本节约。”有远见的企业可以选择 R3 的 Corda、Consensys 的 Quorum，甚至 Hyperledger(由 Linux 基金会托管)来支持他们的应用程序。理论上，这样的区块链将提供跨行业支持，从房地产到金融服务，从医疗保健到供应链管理。然而，现实是不同的；根据 HFS 的调查[到目前为止，只有大约 14%的 POC 能够投入生产。](https://www.wipro.com/blockchain/form/state-of-enterprise-blockchain-market-2020/)

这带来了一个重要的问题:您的应用程序真的需要一个企业区块链吗？

在从事区块链和数据库技术的工作之后，我们认为对于许多应用程序来说，你真正需要的是一个高性能的时序数据库。但在我们论证我们的观点之前，让我们先快速提醒一下区块链是什么，以及公共区块链(如比特币)与私人、封闭、企业的区别。

首先，区块链是一个存储长期信息的数据库。[“比特币区块链”](https://en.wikipedia.org/wiki/Bitcoin)被广泛吹捧为革命性技术，因为它引入了完全去中心化的共识机制，绕过了中介。例如，可以在参与者之间验证金融交易，而无需求助于独立的第三方。决定交易是否有效的是网络，任何人都可以成为网络的一部分。一旦通过验证，交易将被添加到新的交易块中。然后，每个新块都将被添加到区块链中。这很好地解决了 T2 的“重复消费”问题，即同一个数字货币可能被消费不止一次。这个网络被称为[无许可](https://www.blockchain-council.org/blockchain/permissioned-and-permissionless-blockchains-a-comprehensive-guide/)，因为任何人都可以参与并开始验证交易。公共的、不受限制的区块链为权力下放提供了新的视角。

对所有人开放的点对点框架可能对数字货币来说是革命性的，但不太适合企业需求，例如，可能包括不想公开披露敏感记录，只允许少数受信任的用户进行批准。进入私有区块链的世界，它是[许可的](https://www.investopedia.com/terms/p/permissioned-blockchains.asp)，这意味着只有选定数量的用户可以批准交易，并且它还提供了一组关于交易可见性、治理等的特定规则。

> 大多数企业应用程序一开始就不需要去中心化，最好由具有单点真实性的集中式数据库来提供服务。

区块链形式的权力下放会给企业带来重大的不利影响。区块链的主要缺点是缺乏可伸缩性。支撑一些区块链企业的以太坊区块链平均每秒只能处理 15 笔交易。这与企业要求相去甚远—单个数据库每秒钟可能会接收几百万个数据点。第二个挑战是区块链依赖[资源密集型共识机制](https://www.lexology.com/library/detail.aspx?g=5b24eabe-ae87-4db7-ad81-205d04c9c14b)，导致更多的处理开销和更高的能耗。

原来，一种称为时间序列(“TSDB”)的特殊类型的数据库与区块链企业共享许多属性。

让我们比较一下私立区块链和临时数据库的属性:

*   **以时间为主轴**:每隔一定的时间间隔将块添加到区块链中。对于每个数据块，都有一个关联的时间戳。时序数据库经过优化，可以高效地接收和检索与时间戳相关的数据点。想想股票价格每微秒都在变化。
*   **不变性**:一旦一个区块被添加到区块链，它就不能被改变。在数据库领域，这类似于“插入”，没有“删除”或“更新”的能力。不是更新记录，而是附加最近的记录，这将事实上成为最新的读数。时间序列数据库通常是只追加的，并且具有这些特征。
*   **Long 256 格式**:这是加密公共地址的格式。在 [QuestDB](http://questdb.io) 中，我们构建了一种比字符串更好的数据类型，可以有效地读写 256 个长区块链地址。

因此，人们可以使用 TSDB 来重放按时间排序的所有单个交易的完整历史；这就是区块链节点的工作方式。其他相似之处包括:

*   **数据复制**:区块链中的每个节点都保存着事务的全部历史。如果一个节点受到威胁，我们将依靠其他节点来提供完整的历史记录。同样，这个概念在传统数据库中已经存在了几十年:如果一个数据库出现故障，我们可能需要另一个数据库作为备份。
*   **共识**:区块链会有多方(即节点)同意某个特定的事务。在传统数据库中有共识算法，如 [Raft](https://en.wikipedia.org/wiki/Raft_(algorithm)) 和 [Paxos](https://en.wikipedia.org/wiki/Paxos_(computer_science)) ，类似于投票机制。
*   **分片**:不是让所有节点计算所有操作来验证交易和执行智能合约，而是分配节点仅处理某些计算。数据库分片将大型数据库分解成更小的块(称为分片),以促进跨多个服务器的水平伸缩。

区块链功能的其他方面可以在应用程序中处理。例如，私人账本允许不同方共享和查看数据，由于软件的规则，这些方不需要相互信任——这可能是银行和监管机构共享对客户交易数据的数据访问。我认为这种数据访问可以通过位于数据库层之上的业务逻辑层来完成，以便向外部提供数据。

对于政府无法影响的数字货币等抵制审查的用例，有比特币等未经公共许可的区块链。大多数企业应用程序一开始就不需要去中心化，最好由具有单点真实性的集中式数据库来提供服务。如果时间是你的主轴，时序数据库是你的最佳选择。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>