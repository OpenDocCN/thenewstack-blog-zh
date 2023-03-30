# 如何简化你的 Kubernetes 故事

> 原文：<https://thenewstack.io/how-to-simplify-your-kubernetes-story/>

[MongoDB](https://www.mongodb.com/cloud/atlas) 赞助本帖。

 [詹姆斯·布罗德海德

James 在 MongoDB 都柏林办事处领导私有云工程，负责运营经理、Kubernetes 运营商、Atlas 服务代理产品和云开发人员生产力团队。他的兴趣包括分布式系统、持续交付和交付高质量软件。](https://www.linkedin.com/in/james-broadhead-28863b27/) 

每个人都需要一个数据库。在 MongoDB，我们已经认识到 Kubernetes 平台运行数据库工作负载的能力和潜力，自从 StatefulSets 和 Operators 使之成为可能以来。虽然我们认为使用 MongoDB 最简单的方法是使用[Atlas](https://www.mongodb.com/cloud/atlas)——我们的全球云数据库，运行于三大公共云供应商之间——但我们知道一些组织正处于其云之旅的不同阶段。这些组织中的许多都转向 Kubernetes 来运行他们的应用程序和存储层，并希望在那里运行 MongoDB。

Kubernetes 的美妙之处在于，无论是在内部运行还是在混合云环境中运行，您都能够获得在公共云中运行的诸多好处。MongoDB 本机集成了 Kubernetes，因此您能够在现代编排平台上拥有全栈数据库管理功能。

## 进行数据库级别的更改

在容器编排系统的早期，一般的建议是它们适合管理和扩展无状态应用程序——通常是 web 服务器或批处理作业。随着时间的推移，Kubernetes 增加了许多特性，使得运行数据库和其他有状态的异构系统更加自然。

Statefulsets 保证在 pod 重启后保持一致的主机名，PersistentVolumeClaims 允许连接到特定的存储硬件，自定义资源定义和操作符扩展 Kubernetes API，使定义任何复杂程度的服务成为可能(并有一个操作符来执行为您部署它们所需的步骤)。

T4 的 MongoDB Enterprise Kubernetes 运营商 T5 负责这一切。您可以定义您希望 MongoDB 实例拥有的每一项配置，从副本集中的实例数量，到分片集群中的分片，再到您是否需要 SSL 或身份验证，所有这些都在一个 yaml 定义中。然后，您可以将它传递给 Kubernetes API，并为您部署它。这使得基于符合贵公司标准和环境的模板部署 MongoDB 集群变得非常容易——从您批准的特定版本到常见的安全设置和访问控制。

我们的操作员基于我们在编排环境之外部署 MongoDB 的多年经验，通过使用 MongoDB 代理——它处理 MongoDB 配置的更改——而操作员处理它需要的 Kubernetes 对象的请求。这意味着复杂的状态转换——如启用 TLS 或身份验证——可以顺利处理，并且选举次数最少。

除了我们现有的数据库管理平台之外，Ops Manager 和 Cloud Manager 还为部署在 Kubernetes 上的数据库提供了完整的功能集。从备份、监控和警报到我们的[性能顾问](https://docs.opsmanager.mongodb.com/current/tutorial/performance-advisor/)，它提供关于查询性能的建议。

当我们通过操作符扩展可用功能的范围时，我们只需向 MongoDB CustomResourceDefinition 添加字段。因此，当您升级操作符时，您将可以通过 Kubernetes API 获得新的选项。

操作员可通过其 [github repo](https://github.com/mongodb/mongodb-enterprise-kubernetes) 和 [operatorhub.io](https://operatorhub.io/operator/mongodb-enterprise) 联系。我们对即将推出的 Kubernetes 功能所能实现的可能性感到非常兴奋，例如[持久卷快照](https://kubernetes.io/docs/concepts/storage/volume-snapshots/)和对 Statefulsets 的其他改进，并看到运营商生态系统如何继续发展。如果您有一个 Kubernetes 集群，并且对运行 MongoDB 感兴趣，那么使用 Operator，只需简单的**kubectl apply-f MongoDB . YAML**就可以完成部署！

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>