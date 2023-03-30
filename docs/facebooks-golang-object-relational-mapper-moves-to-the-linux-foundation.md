# 脸书的 Golang 对象关系映射器迁移到 Linux 基础上

> 原文：<https://thenewstack.io/facebooks-golang-object-relational-mapper-moves-to-the-linux-foundation/>

最初在脸书创建并于 2019 年开源的 Go 实体框架 [Ent](https://entgo.io/) ，已经[加入](https://www.linuxfoundation.org/press-release/ent-joins-the-linux-foundation/)的 [Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)。Ent 帮助开发人员处理复杂的后端应用程序，他们可能需要处理大量的实体类型以及它们之间的关系。

Ent 的创建者和主要维护者 Ariel Mashraki 说，当他在[脸书连接](https://www.facebook.com/connectivity)团队工作时，该团队致力于为世界带来互联网连接，该团队需要一个对象关系映射(ORM)工具来处理他们正在处理的网络拓扑映射，但找不到一个合适的工具，所以他们创建了 Ent。经过几年的开源并看到社区的采用和参与增加，脸书决定将 Ent 项目转移到 Linux 基金会的管理之下，在那里它将找到一个供应商中立的未来之家。

随着向 Linux 基金会的转移，Mashraki 说这使他能够离开脸书，在仍在 Ent 工作的同时共同创建数据图初创公司 [Ariga](https://ariga.io/) ，该项目正在寻求其他希望参与的公司的更多参与。

传统 ORM 将面向对象编程中的对象映射到数据库。Mashraki 解释说，Ent 提供了这种基本的 ORM 功能，同时还提供了一些附加功能，这就是它成为“实体框架”的原因。根据[的一篇博文](https://www.linuxfoundation.org/press-release/ent-joins-the-linux-foundation/)，Ent“使用图概念来建模应用程序的模式，并采用先进的代码生成技术来创建类型安全、高效的代码，与其他方法相比，极大地简化了数据库的工作。”

对此，Mashraki 进一步解释说，创建 Ent 时考虑了三个特定的设计原则。首先，它使用图的概念，比如节点和边，来建模和查询数据，这意味着数据库可以是关系型的，也可以是基于图的。其次，Ent 的代码生成引擎分析应用程序模式，并为开发人员生成类型安全的显式 API，以便与数据库进行交互(如 MySQL、PostgreSQL 或 AWS Neptune)。最后，Ent 在 Go 代码中表达了与实体相关的所有逻辑(包括授权规则和副作用),这为 Ent 直接从模式定义中自动生成 GraphQL、REST 或 gRPC 服务器提供了内置支持。Mashraki 说，所有这些不仅有助于处理这些大型数据集，而且在这样做的同时还提供了更好的开发人员体验。

这意味着，对于开发人员在其 Ent 模式中定义的每个实体，都会为开发人员生成显式的、类型安全的代码，以便高效地与他们的数据进行交互。类型安全代码提供了卓越的开发体验，因为 IDE 非常了解 API，可以提供非常准确的代码完成建议，此外，使用这种方法可以在编译过程中捕获许多类错误，这意味着更快的反馈循环和更高质量的软件，”Mashraki 在一封电子邮件中写道。此外，网络拓扑在图概念中更容易建模和查询。试图维护以关系术语遍历数百种类型实体的代码和查询太容易出错且太慢，而 Ent 就是直接从这种痛苦中产生的。”

Mashraki 说，由于 Ent 既在 Go 中编写，又在 Go 中生成代码，该框架在云原生社区中找到了一个天然的家，许多云原生计算基金会(CNCF)项目都使用该框架。虽然 Go 是一个自然的选择，但 Mashraki 说他们也在考虑添加其他语言，比如 TypeScript，因为它在前端开发人员中很受欢迎。

至于 Go，Mashraki 在谈到即将到来的泛型添加时表示，这一举动“将减少生成代码的数量，并将使不使用代码生成就创建泛型扩展成为可能。我们已经在进行实验了。”

展望未来，Mashraki 说，耳鼻喉项目目前有两个主要举措正在进行中。首先，迁移 API“旨在与云原生技术(如 Kubernetes 和 Terraform)无缝集成。”接下来，ent 将获得一个新的查询引擎，它将允许在同一个 Ent 模式上定义多种存储类型，例如，它将允许开发人员使用同一个 Ent 客户机查询 SQL、blob 和文档数据库。

“我们邀请更多的公司加入这一努力，成为其中的一部分，”Mashraki 补充说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>