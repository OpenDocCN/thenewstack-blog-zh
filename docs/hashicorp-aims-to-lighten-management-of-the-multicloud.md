# 哈希公司的目标是减轻对多云的管理

> 原文：<https://thenewstack.io/hashicorp-aims-to-lighten-management-of-the-multicloud/>

据公司联合创始人兼首席技术官 [Mitchell Hashimoto](https://github.com/mitchellh) 称，当其他供应商提供在特定环境下运行良好的解决方案时，[已经](https://www.hashicorp.com/) [hiCorp](https://www.hashicorp.com/) 将其未来视为简化多种环境的管理。

他说，HashiCorp 继续在云(特别是多云)上“加倍下注”，并响应客户的请求，将他们从云的自动化和敏捷性中学到的东西带回私有数据中心。另一方面，它专注于与 Kubernetes 的互操作性。

“我们一直关注工作流而不是技术，并确保我们的技术能够在这些环境中工作——本地和云、虚拟机和容器，”他说。

“我一直认为异构性会一直存在，但随着工作负载迁移到云，从这种传统/旧的方式迁移到这种新的方式，它会变得更简单，你会发现，虽然没有完成，但在一段时间内处于稳定状态。但我认为，这并不是完成向云的过渡，而是比以往任何时候都多。”

他解释说，迁移到云的人也选择采用 Kubernetes 这样的平台，有些人正在考虑不同的模式，如无服务器，同时还拥有私人数据中心和云。

“我们的客户告诉我们，有很多供应商为他们提供针对每种特定环境的解决方案，但很少或根本没有为他们提供真正适用于他们的解决方案，”他说。

上周在旧金山举行的 2018 年 HashiConf 会议上，该公司宣布了其产品套件的新功能，其中最重要的是 Terraform 0.12，他说这是其基础设施的供应工作流。它包括对 HashiCorp 配置语言 HCL、远程操作的改进，以及在不同用户需要的级别上提供协作的承诺。

“这是开源软件有史以来最大的一次更新，有着巨大的配置改进，并且 100%受到了社区的欢迎，”他说。

根据 GitHub 刚刚发布的 Octoverse 报告，就贡献者而言，HCL 是 2018 年增长最快的编程语言之一。贡献者的数量在过去的一年里翻了一番。

[https://www.youtube.com/embed/x8dI4VXhNF8?start=118&feature=oembed](https://www.youtube.com/embed/x8dI4VXhNF8?start=118&feature=oembed)

视频

[远程规划和应用](https://www.hashicorp.com/blog/terraform-remote-operations)功能提供了一种利用 Terraform 企业功能的方式，如访问控制和 Sentinel 策略实施，同时保留用户习惯的核心 CLI 工作流。

桥本说:“我们还宣布，我们认为围绕基础设施的[协作问题](https://www.hashicorp.com/blog/terraform-collaboration-for-everyone)对每个人都是一个问题。”。“从历史上看，我们只是为大型企业保留了协作功能。但我们通过倾听社区了解到，从[你的公司]是两个人的那一刻起，每个人都需要不同层次的协作功能。从两个人到两千人，每个人都需要一些东西，一路走来都在变化。”

该公司宣布了一个面向小型团队和爱好者的免费层，一个面向企业的中间层，它将为需要这些额外功能的企业保留已开发两年的企业产品。

“以前，对于那些较低的层次，我们的社区不得不去其他地方，”他说。免费的 Terraform 协作功能将于今年晚些时候开始测试。

随着 Consul 1.4 的发布，它增加了多个数据中心服务网格功能，以实现服务之间的安全通信以及不同云和内部数据中心之间的安全策略共享…6 月，它发布了与 Kubernetes 和 Envoy 的原生集成，这是服务网格解决方案最广泛采用的代理之一。Kubernetes 内部和外部的服务现在可以自动配置为通过内置代理或特使代理进行安全连接。

该公司于 7 月在阿姆斯特丹举行的 [HashiDays](https://www.hashidays.com/) 开发者大会上宣布了其 [Consul Connect](https://thenewstack.io/hashicorp-extends-consul-to-support-other-service-meshes/) 服务网格功能。它允许对单个服务进行分段，以实施访问控制，提供锁定这些服务的能力，并且只允许其他特定的、经过验证的服务访问。

[https://www.youtube.com/embed/HISixqinrC0?feature=oembed](https://www.youtube.com/embed/HISixqinrC0?feature=oembed)

视频

它的秘密管理和加密工具库已经达到 1.0。新版本侧重于企业稳定性、生态系统集成和规模。Vault 1.0 还使自动解封功能(以前是 Vault Enterprise 的一部分)在开放源代码中可用。支持在阿里云、AWS、谷歌云、微软 Azure 上自动解封。Vault 1.0 将于 11 月正式上市。

其集群调度程序 Nomad 版将于 11 月发布。Nomad 0.9 增加了高级调度功能、NVIDIA GPU 支持、对作业提交的 web UI 支持以及改进的资源静态可视化。它通过一个插件系统为集成奠定了基础，这将使社区能够轻松地贡献和维护新的任务驱动因素。Nomad 0.9 将于 11 月推出预览版。

据 TechTarget 报道，该公司避免将 Nomad 作为 Kubernetes 的竞争对手，称两者可以一起使用，尽管它指出 HashiConf 的发言人并没有这样做。该公司已经讨论了提供类似 Kubernetes 即服务产品的托管服务，但尚未公开披露何时会实现。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>