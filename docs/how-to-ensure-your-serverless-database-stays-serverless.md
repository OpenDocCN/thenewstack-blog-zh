# 如何确保您的无服务器数据库保持无服务器

> 原文：<https://thenewstack.io/how-to-ensure-your-serverless-database-stays-serverless/>

[](https://twitter.com/acoliver)

 [安德鲁·奥利弗

Andrew 是一名自由撰稿人和软件开发人员，在开源、数据库和云计算领域有着悠久的历史。他创建了 Apache POI，并在开源倡议委员会任职。他还帮助包括 JBoss、Lucidworks 和 Couchbase 在内的初创公司进行营销。](https://twitter.com/acoliver) [](https://twitter.com/acoliver)

无服务器很容易。与 DevOps、Kubernetes 和标准云架构中的其他一切相比，这就像洗了一个热水澡。这并不是说“没有运营”，因为任何计算功能都必须得到维护、监控和部署。例如，人们可能想要用特征标志来控制什么是开或关的。还会出现其他问题，但是没有什么比供应服务器和维护底层基础设施更糟糕的了——当然也没有什么比 Kubernetes 配置更糟糕的了。

但是无服务器应用程序仍然在与状态作斗争。如果数据库架构没有改变以匹配无服务器应用程序，那么管理数据库和数据库如何表示世界的问题将不可避免地泄漏到应用程序代码中。一旦发生这种情况，无服务器应用程序就变得更像是一个[奇美拉](https://resistance.fandom.com/wiki/Chimera)——一半无服务器，一半有服务器，看起来很有挑战性，而且很痛苦。本文概述了在从更传统的 RDBMS 转向无服务器方法以克服这些状态冲突时需要记住的内容。

## 无服务器数据库的第一条规则

无服务器的第一个[规则是没有服务器。无服务器应用程序不必担心连接到实际的数据库服务器。事实上，像 AWS 的 Lambda 这样的无服务器框架使得处理连接或连接池变得相当痛苦。无服务器应用程序应该通过 API 和事件进行交互。这种互动是保持事物…嗯…无服务器的唯一方式。](https://blog.rowanudell.com/the-serverless-compute-manifesto/)

数据不同于无服务器应用程序或基础设施的其余部分。无状态服务可以在云中自由移动。状态仍然存在于磁盘的某个地方——即使那个磁盘现在是一个芯片。该状态可能以副本的形式存在，但是需要担心确保那些冗余副本和相关数据是一致的。无服务器应用程序不应该考虑这些问题。只要应用程序遵循惯例，基础设施就应该保证一致可用的持久性。

## 为完整性提供功能

无服务器惯例是将应用程序构造成操作对象图的函数。因此，走向无服务器也意味着走向实用。然而，大多数数据库都有查询和数据操作语言，这些语言本质上是命令式编程模型。

例如，SQL 可能是声明性的，但是您必须在命令性代码中将多个 SQL 语句串在一起才能完成任何复杂的事情。这种命令性的、通常是远程的代码给底层数据带来了破坏一致性的机会。

有人可能认为数据库保证了一致性，但是开发人员通常会误解隔离级别保证和数据加入事务的时间问题。在用户相对较少的客户机-服务器应用程序中，人们受益于这些边缘情况发生的可能性；但是在大规模分布式应用程序中，这种可能性会发生逆转。

对于像 PostgreSQL 这样的传统关系数据库，答案通常是创建一个存储过程(并不是说这能解决所有问题)。然而，部署和维护存储过程对于一个无服务器的应用程序来说有些不自然，并且不是很“低运营成本”默认情况下，它也是一种“奇怪”的语言。不过 PostgreSQL 也支持 Python 并且有一个支持 JavaScript 的外部模块。Python 或 Javascript 的这些数据库实现感觉与编写普通 Python 或 NodeJS 应用程序完全不同。此外，大多数示例或文档都使用默认语言。

存储过程还将应用程序逻辑引入到数据库中，并将数据库公理引入到应用程序逻辑中——换句话说，是关注点的泄漏。而且，[游标和 refcursors 也有效率问题](https://stackoverflow.com/questions/42292341/correct-use-of-cursors-for-very-large-result-sets-in-postgres)。使用游标的存储过程中的事务控制也可能很复杂，并且[会产生意外的数据完整性问题](https://www.postgresql.org/docs/13/plpgsql-transactions.html)。

无服务器数据库需要将功能作为完整的事务操作来执行。本质上，开发人员应该能够将一个功能从应用层发送到数据库，并让它作为一个独立的操作来执行。这个函数看起来、尝起来和闻起来都应该像常规的函数应用程序代码，不同之处在于操作有状态的对象。通过将操作转移到函数中并将其发送到数据库，无服务器数据库应该超越真实世界的事务完整性，甚至超过客户机-服务器 RDBMS。

## 无服务器/数据库不匹配

应用程序模型和数据库理解数据的方式之间的差异可能会导致一致性错误，并在性能和规模方面产生成本。现代的对象关系映射工具可以隐藏这个问题，但是它们引入了复杂性并且需要数据转换。当每项操作都需要多层转换时，这就增加了很高的成本。

在云中，你只需为每项操作支付几分之一的费用，但它们会累积起来。目标不是让开发人员煞费苦心地优化运营成本，而是使用适合并遵循最佳实践的工具和 API。

底层基础设施应该了解可用性区域、地理位置、ACID 保证以及在云中一致管理数据的所有内容。应该有一种方法将数据组织为具有实体集合的功能应用程序——但这应该与我的应用程序组织数据的方式紧密匹配，而不是引入不匹配或新的范例。不言而喻，它应该[自动扩展并适应无服务器基础架构](https://thenewstack.io/what-front-end-developers-need-to-know-about-serverless-databases/)的消费模式。

## 部署语义

通常，数据库惯例会妨碍服务和微服务部署。考虑部署依赖于底层数据存储的服务的情况。在传统的 SQL 数据库中，这可能不仅涉及部署服务，还涉及部署 SQL DDL 和 DML，以改变表结构和改变底层数据。

存储过程必须通过相同的方法部署到数据库中。因此，必须关闭服务，操纵数据，修改或部署过程，然后恢复服务。在此停机期间，任何相关服务也会停止。这种数据库部署要求服务完全不可用。例如，它不能一次在一个可用性区域中完成。不考虑不便或正常运行时间问题，这就是没有服务器的“滋味”。虽然无服务器或 NoSQL 数据库不能完全避免数据转换问题，但它们可以缓解这些问题——尤其是当微服务包含数据操作的离散功能时。

最后，多租户功能和灵活的文档结构提供了避免停机或至少使停机更具体的其他机会(例如，仅针对特定客户)。现代的开发和服务理念是，部署时不需要停机，并且在必要时，应该为最少数量的用户停机。

## 在无服务器数据库中寻找什么

无服务器数据架构应该看起来像一个[无服务器 API](https://fauna.com/) 。它应该是功能性的，包括查询和数据操作语言。数据库应该保证函数内部的一致性。数据库模型应该看起来像一个对象图——尽可能与应用程序的对象图相似。消费模型应该与整个应用程序或系统中的其余服务相匹配。

然而，一个功能列表并没有很好地抓住无服务器数据库应该是什么的问题。有一种“无服务器的味道”，或者说一种说不出的味道，就是感觉没有服务器。不仅是操作，还有代码的设置和工作方式。这是真正的“一切”进入工作。感觉很自然地就像无服务器基础设施和架构的其余部分。它只是“感觉没有服务器。”

通过 Pixabay 引导图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>