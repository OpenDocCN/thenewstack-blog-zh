# Argyle Data 如何使用脸书的 PrestoDB 和 Apache Accumulo 来检测欺诈

> 原文：<https://thenewstack.io/how-argyle-data-uses-facebooks-prestodb-to-detect-fraud/>

Argyle Data 的业务是[检查巨大的交易池](http://www.argyledata.com/)以寻找欺诈行为。这是一个新的领域。众所周知，边界并不总是有一套明确的规则。

我们所拥有的是探索这一新领域的新方法，在这一新领域，欺诈的形式往往难以察觉。特别是允许 Argyle 查询大量数据的机器学习技术，这些技术利用了键/值存储技术。

Argyle Data 的 CMO 伊恩·豪厄尔斯(Ian Howells)在接受 New Stack 的采访时解释说:“根据定义，规则是关于过去的欺诈经历。“规则不会发现新的欺诈。我们正从规则转向复杂的机器学习。整个主旨是，不要去发现你知道的，而要去发现你不知道的，因为罪犯在不断进化。”

Argyle Data 的首席执行官 Tom Ryan 表示，典型的电信客户已经因为欺诈损失了 2%的收入，尽管有些客户损失高达 5%。在这种情况下，典型的欺诈行为是触发高级号码的拨号，通常受害者无法阻止它。

税收流失不止于此。Ryan 告诉 New Stack，呼叫中心花费数小时与客户进行(合法的)对话，抱怨意外的费用。“但具有讽刺意味的是，最大的问题是声誉和品牌受损导致的流失，”他表示。“这是我们的移动客户最关心的问题。事实上，对于我们在金融服务行业的客户来说，这是他们的首要任务，一切都是为了保护他们的品牌。”

Argyle 拥有自己的技术来检测数据仓库中的欺诈行为模式。与此同时，电信公司正在从电路交换基础设施的最后残余转向超高速、基于 IP 的网络。过去由你可以握在手中的分立元件执行的功能，正在被转移到软件中。欺诈模式也是如此。

这些模式比软件发展得更快。正如豪威尔斯告诉我们的，阿盖尔的建筑师们发现自己陷入了困境，他们开始问自己这个问题:

> 脸书会如何处理欺诈？

最后，一个容易回答的问题。脸书开发了自己的高速数据管理技术。与大多数成功的美国公司的模式相反，脸书与世界其他国家分享正在开发的技术。[我们在这里讨论过:PrestoDB](https://thenewstack.io/airbnbs-airpal-reflects-new-ways-to-query-and-get-answers-from-hive-and-hadoop/) 。

Argyle Data 负责产品管理的副总裁 Arshak Navruzyan 表示:“在一个数据集内，可能会有许多不同的攻击模式，甚至可能会随着时间的推移而发生变化。“这就是算法方法看起来非常有效的地方。我们使用 Presto 来合成数据集，并行编写非常大规模的查询，以基本上产生这些[模式]。然后在算法上，我们使用概率方法来解释它们，以隔离可能具有欺诈性的部分流量。”

Argyle 的操作确实涉及机器学习，但 Navruzyan 警告我们不要对此过于夸张。他说，深度学习和神经网络算法有利于学习语音模式，这种模式不会发生变化。事实上，他怀疑深度学习系统是否有助于欺诈检测。

“我们做的东西相当复杂，在图形模型领域——[隐马尔可夫模型](http://www.nature.com/nbt/journal/v22/n10/full/nbt1004-1315.html)，条件随机场，马尔可夫随机场——但它们是非常著名的方法，”他评论道。“我认为，在我看来，深度学习的东西似乎只是一厢情愿的想法。”

Argyle 将 Presto 与 [Apache Accumulo](https://accumulo.apache.org/) 结合使用，这是一个分布式的键/值存储，据该网站称，它“基于 Google 的 [BigTable](https://research.google.com/archive/bigtable.html "BigTable") 设计，构建在 Apache [Hadoop](http://hadoop.apache.org/ "Hadoop") 、 [Zookeeper](http://zookeeper.apache.org/ "Zookeeper") 和 [Thrift](http://thrift.apache.org/ "Thrift") 之上。”Argyle 使用这些数据分析技术从电信公司提取数据，并将它们组装到键/值存储中。这使得查询响应时间一致，即使数据集的大小不尽相同。“即使我有 1tb 的数据，所有东西都被分割成 1gb 的平板电脑，并分布在数百台甚至数千台甚至数万台服务器上。”

他说，虽然 Hadoop 的 HBase 也有类似的设计，但在分析大型数据集方面，它并不像 Accumulo 那样成熟。

假设一个电信公司的系统抽样调查一个用户呼叫另一个用户。Navruzyan 说，由于 Accumulo 的统一响应时间存储，它可以检索两个用户的全部通话记录。然后，Argyle 可以对这些数据运行一个概率模型，根据双方的通话记录来确定可疑活动的可能性。

## 突然进入超空间

Navruzyan 继续说，从那里开始，Argyle 可以在超空间中使用概率分布和密度估计函数。

我真的可以惹恼你，并在这里结束这篇文章。但我不会。

正如弗吉尼亚大学关于该主题的研究论文所示[PDF]，空间分析已经被执法部门用作研究工具好几年了。他们的理论是这样的:以一个犯罪事件的各种属性，以线性的尺度定量地呈现它。如果你把这些线性尺度中的每一个都当作一个轴，那么你可以假设一种构型空间，或者“超空间”，其中每一个轴都是一个维度。因此，沿着一个或多个轴的任何量的变化都成为该空间中的运动。

这是 Arshak Navruzyan 称之为简单的方法之一。

“很快，就有了进行近似查询的能力，”他指出。“当您拥有非常大的数据集时，如果您的数据呈正态分布，您不一定需要扫描整个数据集来得出一个近似的答案。你可以对数据进行采样，然后获得大约 95%的准确率，而不必查看数据的每个元素。”

当您以 95%的准确度综合各种被分析的属性，以确定它们在这个配置空间中指向的大致方向时，您不需要度/分/秒的准确度来得出某个东西很可能出错的结论。电信公司可以使用这些信息来阻止对其网络的攻击蔓延，从而减少维护带来的直接成本和客户支持带来的后续成本。

在脸书的开发人员集思广益解决困扰数据仓库用户 20 多年的效率问题之后，世界其他地方正在收获他们的劳动成果……以一种略显简单、速度极快的方式。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/23905174@N00/1594411528/in/photolist-GcQtX-3qTLZW-4JL8Lh-bkSvHb-53ESnK-4LERXZ-ABJEr-cCboAL-51GXnC-4HmP3K-ba9ZqX-57m1HL-bACRyv-gkYZmm-4JGGSu-4tpr3X-5ry9hb-4VvEAF-2XzEQh-ei83rk-4JCnrB-fTUEXS-26Rj6Z-oq4jNW-AoDU3-5KQyH9-fUofPN-9HmR8k-4JGpKJ-4JCs9P-dkErhJ-bAj1MA-4FD3zH-9DV8aB-fbYFA3-j57cA8-6oCFCE-dCaA49-btvxaD-nkVhwt-hfSTXv-xHkpJ-bmQwuK-7dCaMZ-7y8GH4-rA7Bae-eysota-4JGqTd-4VzTDQ-4JCmJP)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>