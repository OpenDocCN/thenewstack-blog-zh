# Telekube 提供远程管理的“私人 SaaS”Kubernetes

> 原文：<https://thenewstack.io/telekube-offers-remotely-managed-private-saas-kubernetes/>

软件即服务并不适用于所有人，这是 gravity 公司通过其托管的 Kubernetes 服务 T2 Telekube T3 解决的问题。

世界上许多地方的本地数据法律禁止那里的公司使用在谷歌、aws 或其他公共云上运行的 SaaS 软件。美国一些高度管制的行业也是如此。

[Telekube](https://github.com/gravitational/quickstart) 旨在允许软件供应商向这些公司销售。gravity 首席执行官 [Ev Kontsevoy](https://twitter.com/kontsevoy) 解释说，这使他们能够在他们无法控制的基础设施上持续部署和管理他们的软件，如世界任何地方的客户私有云。

他的第一家公司是电子邮件服务 Mailgun，2012 年被 Rackspace 收购。后来在 Rackspace 工作了几年，他看到了客户经常遇到的问题:他们喜欢软件服务的低成本和雇佣管理人员，但要么希望保持对美国数据的控制，要么世界其他地方的当地法律要求数据保留在自己的国家。

## 应用程序应该遵循数据

“当我们在 Rackspace 时，我们看到一些公司在亚马逊上销售他们的软件，但他们也想向 Rackspace 的客户销售他们的软件。但客户会说，‘我们希望你的软件在这里，因为我们的数据在 Rackspace 上。’这种持续的推拉动作在 SaaS 世界非常普遍。应用程序需要遵循数据，而不是相反，”Kontsevoy 说。

gravity 最初专注于从单一代码库交付云中和内部的软件。它首先为企业私有云提供所谓的私有 SaaS，并使跨多个基础架构供应商的远程连续部署成为可能。

Kubernetes 被证明是使应用程序可移植的关键。

他说，Kubernetes 提供了一个标准化层，可以将典型应用程序的几十个微服务、六个数据库和多个监控和日志工具从一个环境迁移到另一个环境。

他说:“我们把客户的应用程序放在 Kubernetes 上，Kubernetes 非常擅长运行传统软件，然后我们使用自己的 Kubernetes 工具像火车车厢一样移动它们。它不必是特定于 AWS 或特定于裸机的。如果它运行 Linux，它会自动运行在 Kubernetes 上。如果它运行在 Kubernetes 上，我们可以让您的应用程序持续部署到任何第三方云中。"

这意味着第三方经销商，如系统集成商，可以在全球范围内转售和管理应用程序，而延迟和当地数据保留法律阻止了美国 SaaS 产品的销售。Kontsevoy 说，其他 Kubernetes 服务提供商专注于内部使用，而 Telekube 允许供应商管理客户数据中心的软件。

比方说，他们可以与欧洲的主机提供商合作，或者为这些客户建立特定的环境。Kubernetes 计划允许客户提高他们已经拥有的基础设施的利用率，从而减少他们的基础设施占用空间并节省资金。

## 自动驾驶上的 Kubernetes

Telekube 是运行在 Linux 操作系统之上、Kubernetes 之下的一个薄层。这一层管理 Kubernetes 的配置，通过持续监控来保持 Kubernetes 的健康，提供特定于基础设施的扩展和集群级快照以及简单的版本升级。

“我们称之为‘自动驾驶的 Kubernetes ’,因为它几乎消除了运行 Kubernetes 集群的所有运营开销，”gravity 的营销主管约翰·毕晓普说。

Telekube 不会对 Kubernetes 本身做任何事情。Kontsevoy 说，这些工具为可靠的 Kubernetes 部署准备了第三方基础设施。

它的演示视频解释说，一个名为“应用程序清单”的文件存储在 resources 文件夹中的一个 YAML 文件中，是唯一的 TeleKube 专用文件。它包含 pod 和服务的定义、应用程序的硬件要求以及基础架构选项，如 AWS、Azure 或裸机服务器。剩下的都是标准的 Kubernetes。

https://youtu.be/ZY0QuVPCP6M

运行“Telebuild”命令会创建一个自包含的 tarball，这就是在各种环境中运行多层应用程序所需的全部内容。tarball 包括 Docker 映像、Kubernetes 资源和一个图形安装程序，客户可以使用它来安装在自己的私有云或裸机服务器上。

Telekube 的第二个组件是 SSH 基础设施，它允许 Telekube 用户可靠地连接到防火墙后的环境，并强制实施特定于集群的基础设施访问权限，例如将 SSH 访问限制到特定的 Kubernetes 集群，甚至可能只限于数据库服务器。

Telekube 的 SSH 层在 Apache 许可下被开源为[传送](http://gravitational.com/teleport/)。Teleport 集成了客户身份管理工具，并自动配置用于访问远程集群的 [kubectl](http://kubernetes.io/docs/user-guide/kubectl-overview/) 和 SSH 跳转主机。

https://youtu.be/bprRpX-4R_0

Kontsevoy 说:“今天，当供应商向第三方销售时，他们基本上是把它扔到围栏外面，并希望它能工作。”“我们允许您在围栏的另一边创建 Kubernetes 集群，并将其连接起来……[以便]持续部署、持续更新和客户支持。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>