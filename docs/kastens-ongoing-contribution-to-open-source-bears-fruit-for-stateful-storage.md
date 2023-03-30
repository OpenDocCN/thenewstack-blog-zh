# Kasten 对开源的持续贡献为有状态存储结出了果实

> 原文：<https://thenewstack.io/kastens-ongoing-contribution-to-open-source-bears-fruit-for-stateful-storage/>

Veeam 的 Kasten 创建了 [Kubestr](https://kubestr.io/) 来识别、验证和评估在云原生环境中运行的存储系统。正如【Veeam 的高级全球技术专家 Michael Cade 所描述的，开源的 Kubestr 是一种工具，可以提供关于特定 Kubernetes 集群可用的存储解决方案的信息，以及关于它们性能如何的信息。该软件项目还旨在为 DevOps 团队提供一个“简单的按钮”来自动化这些过程。

在这个由 New Stack 的创始人兼发行人 [Alex Williams](/author/alex/) 主持的 [The New Stack Makers](/podcasts/makers) 播客中，Cade 和 Kasten 软件工程师 [Sirish Bathina](https://www.linkedin.com/in/sirishbathina) 描述了 Kasten 与开源社区的长期合作，以及 Kubestr 如何作为一个雄心勃勃的开源项目的案例研究，以及 Kubernetes 环境中的状态存储在今天的可能性。

[Kasten 对开源的贡献如何在有状态存储上开花结果](https://thenewstack.simplecast.com/episodes/how-kastens-ongoing-contribution-to-open-source-bears-fruit-for-stateful-storage)

正如 Cade 所描述的那样，Kasten 的创新历史和对开源项目的贡献以及它在社区中的作用包括利用或贡献项目。其中包括备份解决方案 Kopia 和以应用为中心的 Kubernetes 数据管理框架 Kanister。“因此，Kubestr 从数据管理和数据保护的角度提供帮助，”Cade 说。“因此，虽然这不是我们第一次涉足开源领域，但我们坚信这对我们的客户和社区来说都是一件大事。”

对 Kubestr 的需求很大程度上是由 Kubernetes 集群内外可行的存储选择激增引起的。由于创建了容器存储接口(CSI ),允许为 Kubernetes 部署解耦存储解决方案，在过去几年中出现了许多 Kubernetes 友好的存储选项。这些包括用于微服务的数据存储的存储系统，如 Cassandra、Redis、MongoDB 和其他 NoSQL、MySQL 或 PostgreSQL 包，由于 CSI，这些包不需要为 Kubernetes 集群进行配置。

“我认为 CSI 为消费者的选择做了很多事情，不再局限于两三个大公司或诸如此类的公司。[DevOps 团队]现在有太多不同的存储选项，我认为我们正朝着好的方向前进，”Bathina 说。“我认为问题在于……如何选择合适的存储。我想，希望库贝斯特能在这方面有所帮助。”

Kubestr 通过自动识别和验证在 Kubernetes 集成平台上运行的存储选项，帮助 DevOps 更好地管理 Kubernetes 集群的大量存储选择。它还提供了基准来衡量实施后存储选项的存储性能。

“我们都喜欢选择，选择的灵活性是一件很好的事情，但它也变得有点令人无法抗拒……这不仅仅是‘从容量的角度来看我想要一些东西’,而是‘我想要更大的东西，我想要更快的东西，’”凯德说。“你可以选择多种形状和不同尺寸的储物件。因此，[Kubestr]面临的挑战是为您希望使用的工作负载选择合适的存储。”

Bathina 说，对于开发运行在云中的应用程序的开发人员来说，了解“你的存储有多快”也很重要。Bathina 说:“对我来说，一个简单的工具(如 Kubestr)只需验证存储就足够快了，是我创建应用程序或部署应用程序的好地方。”“作为一名开发人员，当您构建应用程序以了解您的群集的限制时，拥有这一点点信息就非常有用。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>