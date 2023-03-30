# 马上。Intuit 发布首款开源 Cassandra 集群管理器

> 原文：<https://thenewstack.io/pronto-intuit-releases-first-open-source-cassandra-cluster-manager/>

[DataStax](https://www.datastax.com/) 赞助本帖。

 [登松·博克塔

Denson 是 Intuit 的软件工程师。](https://www.linkedin.com/in/denson-pokta-4128783/) 

正好赶上美国税收季推迟的 2020 年最后期限，Intuit 发布了第一个管理 [Apache Cassandra](https://cassandra.apache.org/) 集群的框架。数据持久性平台团队通过 [DSE Pronto](https://github.com/intuit/dse-pronto) 为 Cassandra 社区做出了我们的第一个重大贡献。Pronto 是一个基础设施即服务自动化套件，用于在 Amazon Web Services (AWS)中部署和管理 DataStax Cassandra 集群。

Pronto 在 AWS 中提供了 Cassandra 自动化框架，内置了多年的 Cassandra 运行、性能调优和自动恢复功能。

Pronto 将包括 Packer、Terraform 和 Ansible 在内的开源套件捆绑在一起，所有这些都内置在 Docker 映像中。这些工具被广泛采用的本质也意味着该框架应该可以很容易地扩展到其他两个云巨头，Google 云平台和 Azure。

Pronto 是我们对 Cassandra 进行九年定制的结果，Cassandra 是一个高度可靠和可伸缩的数据库系统，但并不总是直观的。

## DSE Pronto 抽象出管理 Cassandra 的复杂性

我在 Intuit [的同事 Ben Covi](https://www.linkedin.com/in/bencovi/) 和 Nancy Li 开发了 Pronto GitHub 存储库，在此之前，他们没有发现第三方的类似工具套件具有自我管理集群所需的可配置性。管理自己的 Cassandra 集群并不容易。Pronto 解决了这个问题。

Pronto 起源于数据持久性平台团队的一个项目，TurboTax 是其中最大的用户。TurboTax 是一个监管良好的行业，有成千上万的集成合作伙伴。因此，涡轮税绝不简单。

我们在 AWS 的生产中支持超过 42，000 个峰值 TPS，在生产中支持超过八个集群。我们目前最大的生产集群是每个 AWS 区域有 72 台服务器，或者跨两个区域有 144 台服务器。Cassandra 必须处理大量数据，如津贴、纳税申报单、备案、用户体验以及支持 TurboTax 所需的一切。

Cassandra 有一个操作学习曲线，这就是我们决定开源 Pronto 自动化框架的原因，该框架已经在 Intuit 中“内包”。

维护 Cassandra 集群实际上并不容易。很多人没有很好地维护 Cassandra，结果他们的状态很差。我们的自动化框架在 Intuit 中很受欢迎，使维护和保持 Cassandra 健康变得更容易。

当我们第一次开始时，我们为每个纳税年度实现了 Cassandra，这意味着每个纳税年度都有一个新的集群。但是回到七年前的七个集群成本太高，也很难管理。所以我们把四年的税收合并为一年。

当我们每个群集有一年时间时，它掩盖了许多问题。整合后，我们意识到有很多停顿。

我亲自经历了从内核、JVM 到 Cassandra 级别的所有调试和优化。Cassandra 不能很好地删除已删除的数据。我们每周都在运行生产测试，以确保服务不会每次都降级，并且必须运行 [Cassandra 垃圾收集器](https://docs.datastax.com/en/dse/6.0/dse-admin/datastax_enterprise/operations/opsTuningGcAbout.html)来回收磁盘空间。

## 九年来，Intuit 一直依赖 Cassandra 的可扩展性和可靠性

尽管我们多年来面临挑战，但我们从未考虑放弃卡桑德拉。九年来，它一直是我们的核心基础架构。

Cassandra 是一个非常可扩展的系统。如今，我们支持 TurboTax 的最大生产集群在每个 AWS 区域拥有 72 台 Cassandra 服务器。一直在为我们表演。这是我们这些年来坚持使用 Cassandra 的最大原因，尽管在这九年中我们已经改变了许多技术。

[TurboTax 生态系统](https://www.intuit.com/partners/)非常复杂，确保我们的团队为几乎所有 TurboTax 服务的所有微服务提供持续支持是我工作的一部分。我们首先选择 Cassandra 是因为它的扩展能力，因为这些税务服务不能有任何停机时间。

我们今天与 Cassandra 的稳定关系证明了它是随着我们的客户群和服务而增长的，从那以后我们一直在增长。虽然我们不得不进行大量的定制，但 Cassandra 在这段时间内有了显著的改进，云变得更加容易，并且有了我们创建的自动化框架，我们的日常工作变得更加容易。

虽然 Cassandra 非常可伸缩和可靠，但它并没有在开始时进行优化。数据持久性平台团队所做的所有 Cassandra 优化都包含在 Pronto 项目中，包括一个自我修复功能(当一台服务器停机时，它会自动启动另一台服务器)。

Cassandra 在许多过渡和定制过程中保持稳定。

由于 Cassandra 没有模式，客户可以定义自定义模式，为在 Cassandra 上使用 Intuit 系统的客户提供一定的灵活性。一切都以实体关系的形式存储在系统中。然后，客户端需要定义它们的模式来使用该系统。

在内部，我们支持 500 多种模式，仅使用八个 Cassandra 表实现。我们最初的 Cassandra 实现是不可伸缩的。实现新的模式花了一年时间，但是模式的改变是从客户端抽象出来的。他们不知道我们换了新的模式。

从 Intuit 数据中心迁移到 AWS 也不容易。我们实现了自己的迁移工具，花了一年时间编写代码和执行任务，然后又花了两年时间迁移八个集群。

在此期间，数据中心和基于云的堆栈需要同时全面运行。

在这些过渡期间，Cassandra 没有停机时间，也没有数据泄漏。

安全地执行和实现它花了很长时间。这很可怕，但整件事执行得相当成功。就性能和可伸缩性而言，我认为 Cassandra 相当独特。非常稳定。复制非常令人印象深刻。

我们测试了 AWS 中从一个区域到另一个区域的重定位，我们测量的时间大约是 40 毫秒。

Cassandra 即使在两个地区有活动的无状态微服务时也能保持高可用性。令人印象深刻的是，它能够以非常快的方式保持这种最终的一致性。

## 为什么 Intuit 全力支持开源

不仅仅是稳定性和可靠性吸引了数据持久性平台团队来到 Cassandra。九年前，在我们从 Oracle 数据库管理迁移的过程中，我们只考虑更经济实惠的开源软件。

拥有一个健康活跃的开源社区对我们来说很重要。如果你看看 Cassandra，与成立于 20 世纪 70 年代的甲骨文相比，它相当年轻。拥有开源项目比我们拥有它的专利更快地让社区发展到今天的程度。

我们为什么要开源 Pronto 框架？这是目前管理卡珊德拉的唯一选择，我们需要帮助改进它。我们希望其他人能帮助维护它，而不仅仅是我们。这就是我们如何构建 Cassandra 的，我相信还有其他 Cassandra 专家可以改进我们的框架。

Pronto 目前有大约 10 个贡献者，不仅仅是来自数据持久平台，而是来自整个 Intuit，我们称之为“内部资源模型”。

在 Intuit，很多人现在都在使用我们的框架，因为它很有效，让他们的生活更轻松，因为 Cassandra 在整个公司都在使用。

Pronto 非常适合希望使用 Cassandra 并管理自己的容器集群的公司，我们欢迎新的贡献者。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>