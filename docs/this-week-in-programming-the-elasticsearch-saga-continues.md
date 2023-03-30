# 本周节目:弹性搜索传奇继续

> 原文：<https://thenewstack.io/this-week-in-programming-the-elasticsearch-saga-continues/>

首先，如果你还没有跟上亚马逊网络服务和 T2 弹性服务的发展，这里有一个最简短的回顾。几年前， [AWS 基本上把 ElasticSearch](https://thenewstack.io/what-the-fork-amazon/) 作为服务提供，这让开源社区非常沮丧。作为回应，过了一段时间，今年早些时候，Elastic 决定[改变 ElasticSearch 的许可](https://www.elastic.co/blog/why-license-change-AWS)以限制其下游使用，这又一次让开源社区感到沮丧。AWS 随后宣布将[分叉该项目以保持其完全开源](https://aws.amazon.com/fr/blogs/opensource/stepping-up-for-a-truly-open-source-elasticsearch/)，突然[成为场景中明显的](https://thenewstack.io/this-week-in-programming-elasticsearch-turns-aws-into-the-open-source-champion/)好人。最后，就在几个月前， [AWS 在 Apache 许可下发布了 OpenSearch](https://thenewstack.io/this-week-in-programming-aws-completes-elasticsearch-fork-with-opensearch/) ，版本 2.0 (ALv2)，基本上完成了这个循环。

直到现在。

本周，ElasticSearch 和 AWS 之间的[较量仍在继续，这一次，Elastic 进一步试图关闭对 ElasticSearch 的访问，并将 AWS 拒之门外。作为回应，AWS 表示，它正在努力保持 OpenSearch 和 Elasticsearch 的客户端与开源软件兼容。](https://thenewstack.io/amazon-elastic-and-the-fight-for-open-source-freedom-in-the-enterprise/)

AWS 表示，“OpenSearch 旨在提供与 Elasticsearch 7.10.2 开源发行版的有线兼容性，该软件是从其衍生而来的，”这使得迁移到 OpenSearch 变得很容易。虽然 Elastic 对此无能为力，但他们可以对一些常用的开源客户端库进行修改。

“在过去的几周里，Elastic 向其中几个客户端添加了新的逻辑,拒绝连接到 OpenSearch 集群或运行 Elasticsearch 7 开源发行版的集群，甚至是那些由 Elastic 自己提供的集群。虽然客户端库仍然是开源的，但它们现在只允许应用程序连接到 Elastic 的商业产品，”AWS 写道。

如果 Elastic 希望重新获得开源社区的青睐，这肯定不像是一条路。

相反，在这种情况下，AWS 似乎再次成为开源的救星，这一次承诺提供“一组新的开源客户端，使应用程序可以轻松连接到任何 OpenSearch 或 Elasticsearch 集群”，这些客户端“将来自产品检查添加之前相应的 Elastic 维护的客户端的最新兼容版本。”

“本着开放和互操作的精神，我们将做出合理的努力来保持与所有 Elasticsearch 发行版的兼容性，即使是那些由 Elastic 制作的发行版，”他们写道。

与此同时，当 OpenSearch 社区致力于创建替换库时，AWS 建议用户不要升级到任何弹性维护客户端的最新版本，以免他们的应用程序可能停止运行。

## 本周的节目中

*   **脸书开源计算完整性工具:**你们这些《权力的游戏》粉丝最终应该会对脸书最新的开源项目[临冬城感到满意，这是一个严格的证明者和验证者](https://engineering.fb.com/2021/08/04/open-source/winterfell/)。除了文化参考，[临冬城](https://github.com/novifinancial/winterfell)是[可扩展透明知识论证(STARK)](http://cryptowiki.net/index.php?title=Zero-knowledge_Scalable_Transparent_Arguments_of_Knowledge_(zk-STARKs)#:~:text=Scalable%20transparent%20knowledge%20argument%20(STARK)%20as%20a%20STIK%20implementation,-In%20the%20past&text=Two%20main%20transformations%20of%20evidence%20systems%20into%20realizable%20argument%20systems%3A&text=Interactive%20STARK%20(iSTARK).,an%20interactive%20knowledge%20argument%20system.) 证明者和验证者的实现，更具体地说，它使普通开发人员能够“受益于计算完整性(CI)的证明，这通常需要深入的密码学知识才能实现。”CI 证明允许用户运行一个计算，得到一个结果，然后“让任何人相信你做了正确的计算，而不需要他们自己重新运行计算。”其中的一个子集是零知识证明(ZKP)，它允许相同的功能，同时也隐藏了输入。所有这些都与区块链最近的趋势越来越相关，但脸书写道，“zkp 在区块链空间之外也有许多潜在的应用”，但由于所需的专业知识和计算，它们还没有真正起飞。“我们开发临冬城是为了弥合这些差距，让普通开发者也能接触到 zkp，”脸书在博客中写道。用 Rust 编写的《临冬城》已经发布到 Crates.io，并附带一个端到端的[教程](https://github.com/novifinancial/winterfell#usage)以及一个[示例 crate](https://github.com/novifinancial/winterfell/tree/main/examples) 。

*   **Rust 推动 GATs 稳定化:**在本周一篇关于[推动 GATs 稳定化](https://blog.rust-lang.org/2021/08/03/GATs-stabilization-push.html)的博客文章中，[特征工作组](https://www.rust-lang.org/governance/teams/compiler#wg-traits)的成员 Jack Huey 一再向他们的读者保证，不管他们是否知道、理解，添加通用关联类型(GATs)的举动是“非常令人兴奋”的，确实是一件“大事”。显然，Rust 已经试图添加 GATs 有一段时间了——[RFC](https://github.com/rust-lang/rfcs/pull/1598)于 2016 年 4 月首次开放，甚至早于 const generics 的推出。如果你仍然怀疑它的重要性，他指出了 GitHub 上的跟踪问题，指出这是“Rust 知识库上投票最多的问题。”这里的主要消息是 generic_associated_types 特性不再是“不完整的”，这意味着如果您试图在每夜构建中使用它，您将不再收到警告。对于为什么这很重要，GATs 到底是什么的完整推理，请阅读博客文章，了解为使 GATs 工作而对编译器进行的所有更改，但除此之外，团队还希望您帮助稳定新功能。“我们需要您测试此功能，提出您发现的任何问题或潜在的诊断改进。此外，我们希望你能告诉我们一些 GATs 在 Zulip 上实现的有趣模式，”他们写道。
*   **FSF 想知道你对 GitHub Copilot 的看法:**虽然有些人可能觉得 [GitHub Copilot](https://copilot.github.com/) ，GitHub 的新“人工智能配对程序员”在公开可用的源代码上接受培训，是[一般不侵犯版权](https://thenewstack.io/this-week-in-programming-github-copilot-copyright-infringement-and-open-source-licensing/)，自由软件基金会(FSF)对新的“[服务作为软件替代品](https://www.gnu.org/philosophy/who-does-that-server-really-serve.en.html)并不确定在围绕 Copilot 的哲学和法律问题白皮书征集中，FSF 写道“Copilot 提出了许多其他需要更深入研究的问题”，例如以这种方式训练的神经网络是否可以被视为合理使用，以及该工具创建的代码是否可以被视为侵犯版权。“即使一切在法律上可能都没问题，”他们写道，“活动人士想知道，一家专有软件公司基于他们的作品建立一项服务，是否存在根本性的不公平。”因此，FSF 正在征集关于这一主题的白皮书——具体兴趣领域的列表见博文——并将为发表的论文支付 500 美元。

*   统计数据如下:如果挖掘数字让你兴奋，我们最近发布了两个版本来满足你的统计需求。首先，[2021 年栈溢出开发者调查在这里](https://stackoverflow.blog/2021/08/02/2021-stack-overflow-developer-survey-results/)，来自全球超过 80，000 名受访者的答案，提供了从开发者如何学习，到他们最常用的语言和框架，以及哪些语言和框架提供最好的报酬等方方面面的见解。剧透:Rust 连续第六年再次成为“最受喜爱”的语言。点击进入[完整结果](https://insights.stackoverflow.com/survey/2021#overview)了解更多信息。就在我们讨论这个问题的时候，[red monk 编程语言排名](https://redmonk.com/sogrady/2021/08/05/language-rankings-6-21/)也在本周出炉，显示了一个在计算方面基本稳定的领域，JavaScript 仍然是第一名，Java 与 Python 一起回到第二名。根据 RedMonk 的说法，更值得注意的是 Go、Kotlin 和 Rust 的相对停滞，它说“这可能反映了系统语言的新现实。”这三者被归为“企业应用程序语言选择的潜在挑战者”，RedMonk 指出 Java 似乎不会有任何发展。“因此，通过自身的适应性和企业的惰性的结合，Java 似乎有可能保留企业应用程序市场的大部分份额，这意味着它的潜在挑战者——像 Go、Rust 这样的语言，以及在较小程度上因为共享 JVM 平台而出现的 Kotlin 与其说是与 Java 竞争，不如说是相互竞争，”他们写道。“如果这一假设是正确的，我们应该预计 Java 将保持其性能，未来从 Go、Kotlin 和 Rust 那里获得的收益(如果有的话)将更难获得，因为它们正在争夺更小的工作负载池的份额。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>