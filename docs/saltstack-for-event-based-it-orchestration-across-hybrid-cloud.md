# SaltStack 用于混合云中基于事件的 IT 流程编排

> 原文：<https://thenewstack.io/saltstack-for-event-based-it-orchestration-across-hybrid-cloud/>

许多 IT 运营团队向 SaltStack 寻求配置管理方面的帮助，但这只是该软件功能的一个子集。组织可以考虑使用 SaltStack 来协调其整个 IT 环境的初始部署，以及后续的安全性和管理。

“Salt 最初]不是作为配置管理工具设计的。SaltStack 专业服务团队的成员加里·里士满(Gary Richmond)说:“它首先是一个编排引擎，但它恰好能够非常非常好地进行配置管理。这就是为什么在配置管理领域，软件经常与 Puppet、Chef 和 Ansible 混为一谈，但是工具并不局限于配置。

在最近盐湖城举行的[Salt conf](https://saltconf.com/)[18](https://saltconf.com/)[用户大会](https://saltconf.com/) 上，开源 [Salt](https://github.com/saltstack/salt) 及其企业组件[Salt stack Enterprise](https://www.saltstack.com/products/saltstack-enterprise/)背后的公司展示了如何使用该软件将智能 IT 自动化应用于建立 IT 基础设施的许多日常操作中， 例如如何在云服务上调配大量虚拟机(采用多种配置)，如何在没有干预的情况下运行完整服务器堆栈的裸机部署，甚至如何管理 VLANs 和其他软件定义的网络设置。

“Salt 的所有功能，它可以在特定节点上做什么，可以在整个环境中进行协调，”Richmond 说，并指出 Salt 将跟踪过程中每一步的成功和失败。如果您对 AWS 上可以启动的虚拟机数量有所限制，Salt 可以对该故障做出响应，并触发备用流程编排。它可以停止该步骤，或者将其回滚到先前的状态。"

SaltStack 产品副总裁亚历克斯·皮伊 指出，这种编排方法在未来几年的 IT 运营扩展中将变得越来越重要。“不管你今天的问题是什么，光靠增加人手是解决不了问题的。您需要使用事件驱动的自动化来协调您的数字基础架构的安全性和管理。然后，通过使用系统来理解机器中的趋势和异常，然后自动做出适当的响应，您开始取代复杂性。随着数字系统的增长，事件驱动的自动化可以轻松扩展以管理所有这些，这比增加 10 名员工要容易得多。”

确切地说，这与我们通常所说的 Kubernetes 如何“编排”容器在集群中的移动是不同的，尽管 SaltStack 也可以配置和维护容器。但是 SaltStack 可以与 Kubernetes 一起使用，决定需要哪些容器，并由 Kubernetes 在集群上调度它们。人们也可以用盐来推出 Kubernetes 本身。

里士满本人是盐的热情拥护者，他的热情是在加入盐栈之前产生的。在之前的工作中，里士满在美国宇航局喷气推进实验室工作。2013 年，当好奇号火星车在火星上着陆时，其着陆的实时视频流产生了巨大的流量，因此里士满领导了一项针对他们的 web 属性的配置管理软件的研究，这种软件可以在没有人工干预的情况下完全支撑起服务器。他比较了木偶，Ansible，盐和厨师。盐被证明是最合适的。

在其核心，Salt 是一个远程执行引擎，一个可以控制和扩展资源的引擎。在 Salt 配置中，主节点跟踪所有资源及其理想状态。minion 在每个资源上运行，并通过服务总线定期检查它需要执行的任何更改。，Salt 可以执行任何可以从命令行运行的操作，并增加特定实例所需的任何数据。

然而，Salt Master 并不局限于管理特定的机器，而是管理整个环境。“这些协调状态可以协调整个环境中的配置部署，”Richmond 在最近一期的新堆栈环境播客中说道。配置服务器后，您可以执行其他特定于环境的操作，如建立安全组或设置虚拟私有云。

Salt 的 API 接口可以驱动这种编排。一个外部调用可以通过 API 进入 Salt，并触发一个编排流程，该流程可以在不同的环境中使用不同的设置创建节点。一个调用和一些 POST 数据可用于启动一个编排状态，该状态利用以前捕获的内联 Salt 支柱数据，因此编排状态将根据提供的参数部署资源。

SaltStack 可用于通过基于 PXE 的服务器进行裸机硬件配置，并自上而下地安装软件，检查存储库中的最新版本。Salt orchestration 不仅可以设置服务器，还可以设置整个 LAMP 堆栈。如果成功设置了数据库服务器，它就可以将其加入应用服务器和负载平衡器。而且，按照 GitOps 的最佳传统，管理员可以建立一个工作流，在这个工作流中，一旦新代码在 Git 或 GitHub 中提交，它就可以自动部署到测试或生产环境中。

SaltStack Enterprise 的图形界面和运营框架为 IT 和安全运营团队提供了一种协调和自动化团队任何成员工作的方式。SaltStack Enterprise 使 IT 团队能够创建作业，然后向用户组分配权限，以便他们可以在特定目标上运行这些作业。对于全球部署，SaltStack Enterprise 还可以管理多个主机，并在它们之间运行作业，将数据保存在中央文件服务器和数据库中。

## **云供应**

使用 SaltStack Enterprise，管理员可以创建一个用于创建基于云的(虚拟机)的作业，然后针对不同的配置，指向描述该配置的适当支柱。 [Salt Cloud](https://docs.saltstack.com/en/latest/topics/cloud/) 提供到不同主机的连接，允许 SaltStack 连接到虚拟机和其他云基础架构。

Salt Cloud 允许你指定提供商，比如 AWS Cloud，Azure，Google Cloud Platform，或者其他几十种云的任意一种。向 SaltStack 提供访问这些服务所需的密钥的路径将允许软件直接提供资源。您可以指定分布、实例的大小以及希望它运行的区域。SaltStack 检查它的环境，查看它在什么上面运行，添加正确的存储库，并进行安装。

当您开始考虑像在 AWS Cloud 上创建大量虚拟机这样的工作时，这种工作流功能变得很有趣，特别是如果许多虚拟机是不同的。

这种方法提供了在运行时使用内联支柱数据改变编排状态行为的可能性。例如，Salt 可以用作持续集成/持续部署(CI/CD)管道的一部分。一旦某个软件的新版本被标记，一个提交后的 git 钩子就会启动一个对 SaltStack API 的调用，为测试提供基础设施。

当今的云资源调配在大多数组织中仍然主要是手动任务，用户可以通过自助服务门户向管理员发送电子邮件来调配虚拟机。没有理由说这个操作不能自动化，因为命令行命令适合用户的权限和所提供的规范:

```
sudo salt-run state.orch orch.create_vm  \  pillar='{"vm": {"hostname": "SaltConf18-SSEOrch-Lab##-Minion01", "role": ["apache", "salt-minion"], "os": "rhel", "provider": "aws", "az": "us-west-1b"}}'

```

SaltStack 不仅限于服务器管理。它可以作为管理软件定义网络(SDN)和 [网络自动化](https://www.youtube.com/watch?v=--cJlZpnv50&index=3&t=1356s&list=WL) 的基础。例如，它可以从虚拟机的底层改变 VLAN。通常，在最有组织的工作流程下，此过程需要 30 分钟，但如果该过程需要某种手动批准，则更有可能需要几天。完成后，管理员仍然需要找到特定虚拟机管理程序的端口和交换机，然后进行更改。

在 SaltStack 下，可以在几秒钟内添加一个新的 VLAN。另外，SaltStack 保存了网络拓扑的实时文档，因此这些文档永远不会过时。

[https://www.youtube.com/embed/--cJlZpnv50?start=1356&feature=oembed](https://www.youtube.com/embed/--cJlZpnv50?start=1356&feature=oembed)

视频

特写图片:索尔特斯塔克的亚历克斯·皮伊。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>