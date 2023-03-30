# JFrog 为 AWS 在任何地方提供工厂化的 EKS

> 原文：<https://thenewstack.io/jfrog-brings-artifactory-on-prem-for-aws-with-eks-anywhere/>

DevOps 平台 [JFrog](https://jfrog.com/) 在本周的[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) [Re:Invent 2021](https://reinvent.awsevents.com/) 大会上推出了其 [Artifactory](https://jfrog.com/artifactory/) 通用工件库的新部署选项，将该服务带到亚马逊的[Elastic Kubernetes Service(EKS)Anywhere](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html)。

JFrog 产品营销主管 [Jag Mirani](https://www.linkedin.com/in/mirani) 解释说，JFrog Artifactory 作为 [DevOps](https://thenewstack.io/category/devops/) 的数据库，提供了许多公共存储库无法提供的保证。

## **软件装配线**

“当开发人员开发软件时，他们要处理各种依赖关系和二进制文件。米拉尼说:“从开发人员开始，一直到生产，软件有一条完整的流水线。“沿着这条装配线，会生成许多工件和二进制文件。所有这些东西都在 Artifactory 中进行了策划，因此它成为与您的软件开发生命周期相关的所有二进制文件的唯一真实来源。”

除了简单地存放这些工件，Artifactory 还为用户提供了安全性，确保他们不会成为依赖混淆攻击的受害者，以及通过 API 扩展和集成其他工具的能力。在此版本中，JFrog Artifactory 在可在本地运行的私有实例中可用。

EKS Anywhere 在去年的 AWS Re:Invent 上首次[发布](https://aws.amazon.com/blogs/aws/reinvent-2020-preannouncements-for-tuesday-december-1/)，并在今年早些时候[全面推出](https://aws.amazon.com/blogs/aws/reinvent-2020-preannouncements-for-tuesday-december-1/)，使组织能够在内部运行 AWS 的 EKS 托管的 Kubernetes 服务，而不是在公共云中。Mirani 说，这给 EKS 带来了一些公司，否则这些公司可能会因为法规而无法使用这项服务。此外，许多公司可能已经投资了基础设施，并且不愿意放弃这项投资转向云。

借助 EKS Anywhere，用户可以像使用标准 EKS 一样，在本地创建和操作 Kubernetes 集群。Mirani 说，这种一致性是将 JFrog Artifactory 带到 EKS 任何地方的主要原因之一。

“对我们来说，重要的是它的相同性。而是当你在本地运行 Artifactory，或者在任何公共云上运行它时，你的体验都是相同的 Artifactory 体验，”Mirani 说。“困扰 IT 环境的一个问题是必须了解每个操作环境的特性。在某种程度上，这变成了一个障碍，必须了解您可能处于的每一个操作环境。事实上，它是 EKS 本地的，与您在云中获得的 EKS 相同，或者反之亦然，与您在云中获得的 Artifactory 相同，这是其吸引力的关键部分。”

Mirani 说，这种一致性还提供了一定程度的灵活性，能够在未来改变部署。

Mirani 说:“当你想在任何方向上从一个部署改变到另一个部署时，你不必考虑培训和运营差异以及必须学习不同环境的问题。“拥有运营一致性是一个巨大的优势，因为如果我现在用 Artifactory 在本地运行 EKS，而在未来，我决定迁移到云，这将是同样的 EKS 体验，这将是同样的 Artifactory 体验。这是一个已经消除的巨大障碍。”

JFrog Artifactory for EKS Anywhere 现已在 [AWS Marketplace](https://aws.amazon.com/marketplace/pp/prodview-336ywgv7fmo4u) 上市，安装只需几分钟。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>