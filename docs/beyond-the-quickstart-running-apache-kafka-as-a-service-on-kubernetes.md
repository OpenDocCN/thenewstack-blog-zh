# 超越快速入门:在 Kubernetes 上运行 Apache Kafka 服务

> 原文：<https://thenewstack.io/beyond-the-quickstart-running-apache-kafka-as-a-service-on-kubernetes/>

[](https://www.linkedin.com/in/gwenshapira/)

 [格温·沙皮拉

格温是 Confluent 的一名工程负责人，管理着云原生 Kafka 团队。Gwen 还是 Apache Kafka 的项目管理委员会成员,《Kafka -权威指南》的作者，以及行业会议的发言人。](https://www.linkedin.com/in/gwenshapira/) [](https://www.linkedin.com/in/gwenshapira/)

在 Kubernetes 上运行 Apache Kafka 作为一项服务为不同的环境提供了许多好处，特别是对于那些专注于成为云原生的组织。经过几年在 Kubernetes 上运行 Kafka 的经验，我们了解到这并不复杂。

为了澄清我们所说的 Kafka 即服务的含义，请将其视为一种 24×7 完全托管的服务，无需内部 Kafka 专业知识，从而实现自动化供应、管理和运营。最重要的是，开发人员可以专注于真正重要的事情:编码。随着组织继续采用以云为中心的方法，Kubernetes 上的 Kafka 与任何种类的云原生开发齐头并进，以便为下一代应用程序开发和管理提供更好的配置。

 [Prachetaa Raghavan

Prachetaa 是 Confluent 公司的软件工程师。在加入 Confluent 之前，他曾在 Delphix、VMWare、NVIDIA 等公司领导工程团队并担任技术职务。](https://www.linkedin.com/in/prachetaa/) 

在 Kubernetes 上运行 Kafka 使 Kafka 更有弹性，伸缩变得更快更容易。过去需要几个月的升级现在只需几天就能完成，这就是商业价值。使用 Kafka 操作符，您可以自动化 Kafka 部署，并从头开始在 Kubernetes 上快速部署它。通过对基础架构进行抽象，让用户指定“是什么”和资源调配者指定“是谁”，整个配置和自动化流程只需完成一次，就可以在任何地方运行。

就连 Google Cloud 的首席工程师、Kubernetes 领域极具影响力的人物 Kelsey Hightower 也怀疑有状态工作负载能否在 Kubernetes 上优雅地运行。我们在这里告诉你，这不仅是可能的，而且是必要的。在本文的后面，你可以读到在 Kubernetes 上设置 Kafka 最常见的三个问题，以及我们关于如何避免这些问题的提示。

## 集群网络

为了确保人际网络在外部和内部都能正常工作，有必要确保你有某种形式的健康检查。这可以通过在 Kubernetes 集群内部或外部运行的 Kafka 生产者和消费者(或者两者)来完成。此外，网络实施可能因所使用的云提供商而异。同一资源的不同实现通常会带来巨大的挑战。积累网络专业知识，了解如何在问题出现时进行管理，并进行适当的监控和遥测，使用户能够立即了解问题是否出现以及何时出现。

### 你如何把它做好？

Kubernetes 提供了许多网络选项，如节点端口、入口、负载平衡器，以及使用 [Red Hat OpenShift](https://www.openshift.com/try?utm_content=inline-mention) 的路由。Kafka 要求生产者和消费者根据分区和分区领导者的位置与单个经纪人交谈。基于不同的网络选项，您必须正确地配置您的网络，以便生产者和消费者能够单独寻址代理。

Kafka 在代理配置中公开了“advertised.listeners”选项，这允许客户端直接连接到代理。当配置 Kubernetes 服务以允许访问代理时，您还将在代理中配置“advertised.listeners ”,以确保生产者和消费者能够连接到各个代理。

Kubernetes 抽象了基础设施，遵循一种接口模式，其中第三方提供者可以创建他们自己的遵循标准接口定义的插件。因此，您还可以构建自己的路由层，以确保能够处理代理。Kubernetes 允许您通过入口资源来实现这一点。

如果您从同一个 Kubernetes 中连接到 Kafka，您可以通过创建一个无头服务作为您的引导端点到达任何代理来解决这个问题。同时，您可以单独寻址这些 pod，因为 Kubernetes 允许您使用特定的 DNS 名称来寻址这些 pod(只要“advertised.listeners”也得到适当的配置)。

如果您从 Kafka 的 Kubernetes 集群外部连接到 Kafka，可以使用许多网络选项，如节点端口、入口等。，您仍然需要确保满足处理单个代理的需求，并且 Kafka 得到了适当的配置。

## 安全性

网络通道有许多不同的安全、身份验证、授权和加密层，静态数据的加密也是如此。你需要确保经纪人和 ZooKeeper 之间的沟通(感谢 [KIP-500](https://cwiki.apache.org/confluence/display/KAFKA/KIP-500%3A+Replace+ZooKeeper+with+a+Self-Managed+Metadata+Quorum) ，这正在消失)以及生产者和消费者与经纪人之间的沟通。Kubernetes 生态系统发展如此之快，以至于服务网格，如 Istio(一个设计为在 Kubernetes 容器中运行的开源服务网格平台)，降低了安全通信的压力。此外，当针对 Kafka 进行适当配置时，用户可以确保内部和外部通信通过 mTLS(也称为相互身份验证)得到适当保护。

然而，不同的 Kubernetes 集成会带来不同的问题。例如，使用 Istio，每当一个代理关闭时，作为关闭过程的一部分，仍然需要与集群中的其他代理进行通信。当一个 pod 被终止时，envoy sidecar 容器被不确定地终止，并将关闭该代理和它需要将分区复制到的其他代理之间的网络连接。

### 你如何把它做好？

为了用 Kafka 在 Kubernetes 上正确地保护你的数据，生产者和消费者需要以加密的方式发送数据。要做到这一点，创建 SSL 证书并用这些证书配置代理允许生产者和消费者与代理之间的通信被加密。例如，Istio 可以帮助加密这些通信。与 Kubernetes 的集成进展迅速，现在能够更好地支持 Kafka 的许多功能和更大的生态系统。

mTLS 或 SASL(有许多不同的形状和形式，如 SASL 明文或 SASL 急停)可以帮助认证经纪人。一旦通过身份验证，请确保配置 ACL 以允许细粒度授权。

数据到了 Kafka 之后，下一个阶段就是数据存储。通过 Kubernetes 中的分层存储和持久卷，您可以轻松地加密静态数据，以确保在未经授权的用户访问 Kafka 日志或日志段的情况下，数据不会被读取。分层存储到基于云提供商的存储，如 S3，可以在配置存储桶时轻松加密，并与 AWS KMS 轻松集成。

另一方面，Kubernetes 允许您通过基于存储类类型适当地配置存储类来加密持久卷。但是，静态持久卷是预先创建的，如果需要，您可能必须确保对其进行加密。

## 储存；储备

根据您在 Kubernetes 上运行 Kafka 的位置，您可能需要根据 Kubernetes 中可用的置备程序来处理存储。三大云提供商(AWS、Google Cloud 和 Microsoft Azure)对网络附加存储进行了抽象，Kubernetes 支持多种存储系统，包括 NFS、CIFS、Ceph、GlusterFS 等。

如果您跨不同的区域运行 Kafka，则需要以区域感知的方式创建存储卷，Kubernetes 使用拓扑感知的卷供应以本机方式提供了这种方式。

### 你如何把它做好？

Kafka 是一种有状态服务，这意味着需要一个持久卷(PV)来防止 pod 故障导致的数据丢失。因此，您希望使用安装在 pod 上的存储，以便当 pod 需要移动时，Kubernetes 可以将该存储安装到不同的节点上，并成功地调用 pod。PV 声明以及存储类别有助于调配安装在机架上的存储。

Kafka 还提供分层存储，这使得在 Kafka 中存储大量数据变得易于管理，并减少了操作负担和成本。基本思想是将数据存储和数据处理分开，允许各自独立扩展。Kafka 为 AWS G3、GCS 和 Pure Storage FlashBlade 提供分层存储，所有这些都支持静态加密。这使得数据从离开您的客户端的那一刻起就被加密，静态存储，并在返回您的消费者的过程中一直保持加密。

## 后续步骤

虽然在 Kubernetes 上运行 Kafka 需要大量的投资，并且你需要对不同的部分有一个坚实的理解，但是 Kafka 和 Kubernetes 的好处是巨大的。如果您了解最初的障碍，正确管理节点和代理之间的内部和外部通信，维护适当的安全协议，并注意存储配置，这两者一起带来了灵活性和自动化。一旦您在初始阶段进行了投资，就可以运行大量的应用程序，并且不再需要针对特定应用程序重新构建工具。

另一方面，如果你不想管理任何这种复杂性，你可以免费尝试[汇合](https://www.confluent.io/confluent-cloud/)，这样你就可以把时间花在创建和构建上，而不是被操作所困扰。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>