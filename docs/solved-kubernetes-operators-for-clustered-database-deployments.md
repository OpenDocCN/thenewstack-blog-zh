# 解决了！用于集群数据库部署的 Kubernetes 操作员

> 原文：<https://thenewstack.io/solved-kubernetes-operators-for-clustered-database-deployments/>

[](https://www.couchbase.com/)

 [Ravi Mayuram

作为工程高级副总裁兼首席技术官，Ravi 负责 Couchbase 数据平台的产品开发和交付，该平台包括 Couchbase 服务器和 Couchbase 移动设备。他从甲骨文来到 Couchbase，在那里他担任高级工程总监，领导推荐系统和社交图、搜索和分析以及轻量级客户端框架领域的创新。在甲骨文工作期间，Ravi 还负责启动云协作平台。此前，Ravi 曾在 BEA、Siebel、Informix、HP 和 startup BroadBand Office 担任高级技术和管理职务。Ravi 拥有德里大学的数学硕士学位。](https://www.couchbase.com/) [](https://www.couchbase.com/)

正如我们在各个行业无数次见证的那样，今天的企业技术观察短语是:要么敏捷，要么死亡。企业、它们的产品和服务以及它们与客户的互动方式正在经历一场彻底的革命。一种新的商业模式或技术刚刚成功推出，就会出现一种新的、改进的范式来取代它。唯一可行的解决方案是保持敏捷和适应。

将敏捷性融入企业技术栈 ***是*** 我们时代的挑战。持续集成和持续部署(CI/CD)已经成为领先公司尽快实施的主要模式，以满足变化和敏捷性的需求。

在 CI 方面，有数百篇文章和数十种工具可以满足应用程序开发人员的敏捷性需求。因此，应用程序开发几乎完全脱离了传统的 IT 部门，进入了 DevOps。

然而，问题的裁谈会方面更具挑战性。虚拟机(VM)和容器技术都是为了解决连续部署问题而出现的，但都取得了有限的成功。这些技术擅长封装和部署许多看起来相同的东西，如文件服务器、应用程序和微服务组件，其中每个服务都是非常独立的。但是，当在分布式集群环境中部署复杂的有状态数据库组件时，它们就有所欠缺。大多数情况下，数据库部署需要复杂的脚本来确保以正确的顺序配置、部署和操作相互依赖关系。

这些手动编码的脚本很难包含像可用性区域、灾难恢复和级联故障场景这样的功能，如果它们包含这些功能，通常也缺乏灵活性。脚本也往往非常特定于云提供商，因此限制了灵活性，使得云无关的部署几乎不可能。在过去的几年中，这导致了 CD 的碎片化:由 DevOps 处理的易于打包和容器化的企业服务，与由 IT 或其他专业团队处理的困难、复杂、特定于云的集群技术(如数据库)相比。

但是，如果我们能够使甚至是“复杂的”CD 变得简单和自动化，允许定制的、有状态的、上下文敏感的部署，那会怎么样呢？进入 Kubernetes 运营商框架。Operator Framework 是一个开源工具包，以有效、自动化和可伸缩的方式管理 Kubernetes 的本地应用程序，称为 Operators。从根本上说，它们允许复杂的、相互依赖的、分布式的服务(如集群数据库)来描述如何通过简单的 YAML 配置文件来部署、操作和管理它们。

自动化集群数据库的部署和操作实现了 CI/CD 承诺的目标。它减少了数据库部署中耗时、易出错的手动干预，改进了资源管理，并将数据库置于 DevOps 域中，使数据库成为您的敏捷 CI/CD 基础架构的另一个组件。数据库管理员不再需要专注于让数据库“启动并运行”，然后“保持其运行”，因为这正是 Operator 框架将自动为他们做的事情。这对系统架构师来说也是一个好消息，因为它简化、阐明并自动化了整个应用程序部署架构，使其更可靠、更不脆弱。

让我们看一个具体的例子 Kubernetes 的 Couchbase 自治运营商。基于多年使用 Kubernetes 容器的经验，Couchbase 工程师使用 Operator 框架为 Couchbase 数据平台创建了一个定制的 Kubernetes 操作符——这是第一个这样做的 NoSQL 数据库产品！Couchbase Autonomous Operator 可自动执行部署、纵向扩展和横向扩展操作、升级、集群监控、节点故障检测和自动恢复、跨可用性区域的数据分发，并通过跨数据中心复制(XDCR)的自动配置实现灾难恢复。Couchbase Autonomous Operator 使 DevOps 人员可以轻松定义他们需要的配置和操作参数，告诉 Kubernetes 部署适当的资源并监控它们的故障。DevOps 人员可以从 Kubernetes 或 Couchbase 管理控制台收集关于集群及其操作的状态和信息。

Couchbase 及其用于 Kubernetes 的自治操作符消除了应用程序前端和数据库后端之间的管理摩擦。历史上，尤其是对于关系数据库，数据库、模式和应用程序的更改必须分别进行，迫使管理员单独准备、管理和部署每个组件。

使用 Couchbase，您可以让应用程序需求和变更驱动所有的修改。更新运行这些实例的所有节点所涉及的管理任务和实际机制现在由 Kubernetes 完成。DevOps 只需要指定“什么”需要发生以响应应用程序的变化，而 Kubernetes 操作员将负责“如何发生”这使得 DBA 和“Ops”团队从维护数据库的平凡任务中解放出来

通过使用 Kubernetes 操作符，Couchbase 能够使 Couchbase 数据平台成为企业 CI/CD 目标中的平等伙伴。随着云平台、应用程序需求和客户交互的变化，DevOps 可以更好地控制数据库变化，并确保未来的灵活性。反过来，数据库管理员可以专注于数据库管理的更高价值方面，并为应用程序和最终客户提供更高质量的“数据”服务。

关于 Kubernetes 的 Couchbase Autonomous Operator 的更多信息，请点击此[链接](https://www.couchbase.com/products/cloud/kubernetes)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>