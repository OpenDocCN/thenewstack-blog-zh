# Kubernetes 和亚马逊网络服务

> 原文：<https://thenewstack.io/kubernetes/kubernetes-and-amazon-web-services/>

据云巨头亚马逊网络服务公司称，该公司管理着世界上数量最多的 Kubernetes 集群。在这段播客记录中，AWS 高级工程师 [Jay Pipes](https://www.linkedin.com/in/jaypipes/) 讨论了 AWS 对 Kubernetes 的使用，以及该公司对 Kubernetes 代码库的贡献。

[Kubernetes 和亚马逊网络服务](https://thenewstack.simplecast.com/episodes/kubernetes-and-amazon-web-services)

## Kubernetes 和 AWS 的区别

Kubernetes 是一个开源的容器编排平台。AWS 是最大的云服务提供商之一。2021 年，该公司在全球创造了 611 亿美元的收入。AWS 提供商业 Kubernetes 服务，称为[亚马逊弹性 Kubernetes 服务](https://aws.amazon.com/eks/) (EKS)。它通过添加控制平面和工作节点简化了 Kubernetes 体验。

[https://www.youtube.com/embed/MHS-RPmNdqQ](https://www.youtube.com/embed/MHS-RPmNdqQ)

视频

除了提供商业 Kubernetes 服务之外，AWS 还支持 Kubernetes 的开发，让工程师致力于开源项目的工作。

Pipes 说:“服务团队中的所有工程师都有责任了解正在发生的事情以及上游社区为上游社区做出的贡献，并使其成功。”“如果我们所依赖的上游开源项目受到影响或做得不好，那么我们的服务也不会做得好。同样，如果我们能够帮助上游项目取得成功，这意味着我们的服务将会更加成功。”

## AWS 中的 Kubernetes 是什么？

除了 EKS，AWS 还有许多其他工具来帮助 Kubernetes 用户。一个是用 AWS 构建的开源、灵活、高性能的 Kubernetes 集群自动缩放器。Pipes 说，与 Kubernetes 的内置集群自动缩放器相比，Karpenter 提供了更细粒度的缩放能力。Karpenter 没有使用集群自动缩放器，而是部署了 AWS 自己的 Fleet API，它提供了卓越的调度功能。

Kubernetes 用户的另一个工具是 [cdk8s](https://cdk8s.io/) ，这是一个开源软件开发框架，使用熟悉的编程语言和丰富的面向对象 API 来定义 Kubernetes 应用程序和可重用的抽象。它类似于 [AWS 云开发套件](https://aws.amazon.com/cdk/) ( *CDK* )，帮助用户使用 [AWS CloudFormation](https://aws.amazon.com/cloudformation/) 部署应用，但输出不是 CloudFormation 模板，而是 Kubernetes 可以理解的 YAML 清单。

## AWS 和 Kubernetes

除了向 Kubernetes 提供开源开发帮助之外，AWS 还提出帮助支付托管 Kubernetes 开发和部署过程的大量费用。目前，Kubernetes 上游构建过程托管在谷歌云平台上，而工件注册托管在谷歌的[容器注册](https://cloud.google.com/container-registry/)中，总共有大约 1.5TB 的存储空间。Pipes 说，每个月，仅 AWS 一家就要支付 9 万到 10 万美元的出口成本，仅仅是为了在 AWS 托管的基础设施上安装 Kubernetes 代码。

AWS 一直致力于 Kubernetes 资产的镜像，这些资产将驻留在该公司自己的云服务器上，从而消除了通常由[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)承担的谷歌出口成本。

“通过这样做，我们完全消除了从谷歌数据中心到 AWS 数据中心的出口成本，”Pipes 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>