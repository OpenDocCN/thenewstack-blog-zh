# Aljabr 旨在简化数据管道的维护和供给

> 原文：<https://thenewstack.io/aljabr-aims-to-simplify-care-and-feeding-of-data-pipelines/>

云技术非但没有让事情变得更简单，反而增加了数据处理的复杂性，尤其是在分布式系统中——这是初创公司 Aljabr 正在面临的问题。

它的创始人——[约瑟夫·杰克斯](https://github.com/josephjacks)，Kubernetes 工具包 [Kismatic](https://github.com/apprenda/kismatic) 的联合创始人； [Petar Maymounkov](https://github.com/petar) ，分布式哈希表[的合著者 Kademlia](https://pdos.csail.mit.edu/~petar/papers/maymounkov-kademlia-lncs.pdf)；《配置管理系统》 [CFEngine](https://cfengine.com/) 的作者 [Mark Burgess](https://github.com/markburgess) 专注于简化构建和维护数据管道的过程。

人们正在基于从许多不同来源摄取数据来构建管道，无论是实时、批量、点击流数据、传感器数据，还是他们从应用程序中提取的数据。杰克解释说，他们希望对这些数据进行转化分析和智能处理。

对于开发人员和基础设施人员来说，随着这些管道的建立，他们不得不应对用于处理和转换通过这些管道的数据的技术类型的激增。Aljabr 希望为数据工程师和 DevOps 基础设施人员简化端到端工作流管道开发流程。

“问题空间真的很大，”他说。“如果你与数据工程师或开发人员交谈，当他们在构建数据管道时，整个过程极其复杂。这非常容易出错，你必须处理许多不同的技术，并且很难推出这些管道并维护它们，因为它们是特定于技术的。如果你使用 Kafka、TensorFlow 或 Spark，不同的数据处理、不同的数据转换、排队系统——通常要建立跨越所有这些技术的管道，你必须建立许多定制的基础设施，并且你必须编写许多代码来完成这些工作。”

要做到这一点，一般来说，成本和复杂性都太高了，他说。他们通常最终会为这些技术中的每一种构建孤立的、分散的数据管道。

“你可能有建立在 TensorFlow 上的机器学习管道，这是一个完全不同的管道，用于使用 Kafka 进行流媒体或事件驱动的东西。不同的基础架构，不同的团队管理它。这其中有很多复杂性。您可能在基础设施的不同部分有一组完全不同的管道，在 Spark 之类的东西上进行流处理。

“我们正在建立一种方法来极大地简化它，在那里你可以有一个可重复的管道，用于实时数据、批量数据、跨系统的不同范例，而不是必须为每一个建立独立的基础设施，”他说。

Aljabr 的创始人专注于两种基本的管道类型:

*   构建和部署管道，例如在连续交付中。
*   数据处理应用，如机器学习和训练。

他们对如何进行这项工作的细节守口如瓶——“我们仍然是秘密的，”杰克说——但在 GitHub 上发布了一个项目，为他们的工作提供了一些线索。这是一种有向无环图( [DAG](https://en.wikipedia.org/wiki/Directed_acyclic_graph) )脚本语言，名为 [Ko](https://github.com/kocircuit/kocircuit) ，用 Go 编写，建立在 Maymounkov 的实验性 Escher 语言的基础上。

Ko 在一个简单的 DAG 模型中公开了 Kubernetes APIs，充当实现通用管道的基本汇编代码。Ko 被设计成通用的，使其高度可重用，同时完全是类型安全的。Ko 计算模型称为递归电路，支持全类型推理、并发和无死锁同步。

Ko 被设计成通用的，使其高度可重用，同时完全是类型安全的。它的 GitHub 页面提到了一个正在开发中的 Ko 编译器，它能够以任何语言编码生成实现，还有一个 Ko 解释器，它可以与 Go 中的任何技术一起工作，并且可以与任何目标语言集成。

Jacks 说，该公司可能会在 11 月左右发布一个基于其正在开发的产品的开源项目。

与此同时，创始人们更多地在博客上谈论问题，而不是他们如何解决问题。他们声明:

“Docker 提供了一种方法来制造组件，将它们构建到库中，组装它们，甚至修复或升级它们，并查询它们的历史。Kubernetes 增加了一种新的(更贵的)试验板，只需轻轻一按开关，它就能真正被包装成产品。现在的问题是:我们能否以一种普通数据科学家或系统管理员容易理解的方式，为数据管道和 Dag 重复这些进步？”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>