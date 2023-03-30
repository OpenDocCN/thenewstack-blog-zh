# AWS 无服务器容器平台的发展:Fargate

> 原文：<https://thenewstack.io/the-evolution-of-serverless-container-platform-on-aws-fargate/>

本月早些时候，亚马逊网络服务 re:Invent 发布了一个有趣的公告，即亚马逊弹性 Kubernetes 服务(EKS)在 AWS Fargate 上的[全面上市](https://aws.amazon.com/blogs/aws/amazon-eks-on-aws-fargate-now-generally-available/)。通过这种集成，AWS 客户可以在无节点、无服务器的环境中部署 Kubernetes pods。任何运行 Kubernetes 版本 1.14 的亚马逊 EKS 集群都可以为 Fargate 配置。

在这个由四部分组成的系列中，我计划涵盖 Fargate 的发展、设计和 Fargate 上 EKS 的架构、部署工作流、平台的局限性和优势，最后是 Fargate 与 Azure Container 实例和 Google Cloud Run 的比较。周五查看第二期，下周再查看剩余的帖子。

## **无服务器集装箱平台的崛起**

亚马逊不是第一个也不是最后一个将无服务器容器平台(SCP)支持添加到其云基础设施的供应商。2017 年，微软推出了[Azure Container Instances](https://azure.microsoft.com/en-us/services/container-instances/)(ACI)作为无服务器容器环境，后来扩展到了 [Virtual Kubelet](https://github.com/virtual-kubelet/virtual-kubelet) 项目。今年早些时候，谷歌出于同样的目的在 GCP 推出了云运行。像 Fargate 一样，Cloud Run 可以在现有的 Kubernetes (GKE)集群环境中运行。见我对 [Azure 容器实例](https://thenewstack.io/azure-container-instances-proof-microsoft-innovating-containers/)和 [Google Cloud 运行](https://thenewstack.io/how-google-cloud-run-combines-serverless-with-containers/)的分析。

每个无服务器容器平台的目标都是一样的——带上容器映像，带着端点离开。这一承诺让我们想起了第一代 PaaS 产品，如 Cloud Foundry、Heroku 和 Engine Yard，它们期望将源代码作为输入，将面向公众的 URL 作为输出。SCP 和 PaaS 之间的关键区别是输入——容器图像和 tarball。

### 近距离观察亚马逊 ECS

亚马逊弹性集装箱服务(ECS)标志着 AWS 进入集装箱化基础设施市场。当它在 2014 年宣布时，Kubernetes 还没有出现，这迫使 AWS 从头开始构建一个容器编排平台。ECS 是围绕具有 Docker Compose 兼容性的弹性豆茎建模的。该服务充当运行容器的 EC2 实例群的编排层。

因为 ECS 是一个容器编排平台，很像 Kubernetes，所以它采用 Docker 容器映像，在 EC2 实例中进行调度，并根据需要扩展容器。容器映像包装在 ECS 任务定义中，该定义声明了资源需求，如 CPU 单元、内存、网络端口等。ECS 服务定义将扩展任务以满足所需的实例数量。它还将任务实例连接到负载均衡器，以便在运行的实例之间路由流量。

正如我们所看到的，ECS 任务定义非常类似于 Kubernetes pod，而服务定义模仿 Kubernetes 部署。

但是，与 Kubernetes 不同的是 ECS 集群的概念。在 ECS 中，集群是任务和服务的隔离的逻辑边界。它不同于 Kubernetes 集群，后者是主节点和工作节点的集合。

在启动任务和服务之前，客户需要创建一个包含一个或多个 EC2 实例的集群。参与集群的每个 EC2 实例运行一个代理来与 ECS 控制平面对话。可以把这个代理想象成在 Kubernetes 集群的每个节点中运行的 Kubelet。

Amazon ECS 希望客户处理底层 EC2 基础设施。他们需要知道很多细节，比如实例类型、AMI、EBS 大小、VPC 子网、安全组等等。在安排集群中的第一个 ECS 任务之前，需要做大量的基础设施准备工作。这主要是因为 ECS 处理 EC2 的方式，EC2 仅处于任务和服务协调级别，而不是调配、配置和扩展设备群。

### AWS Fargate:从等式中移除基础设施

2017 年，亚马逊推出了 AWS Fargate，这是一个计算引擎，用于部署和管理容器，而不必管理 EC2 基础设施。AWS Fargate 成为在 Amazon ECS 上启动容器化工作负载的选项之一。

Fargate 的核心是让 ECS 用户专注于任务和服务定义，而不是管理集群基础设施。选择 Fargate 部署选项的 ECS 客户将永远不必与 EC2 打交道。

在幕后，Fargate 仍然使用一个或多个 EC2 实例来运行容器。实例配置被映射到任务定义中提到的资源需求。AWS Fargate 用户看不到 EC2 实例，因为它们不在他们的帐户中运行。相反，Amazon 在一个专用的、私有的 VPC 中提供运行 Fargate 任务的 EC2 实例，外部世界无法访问该实例。如果服务定义通过 ELB 或 ALB 公开，则 Fargate 的子网连接到与负载平衡器相关联的弹性网络接口(ENI)。我们将在本系列的后续文章中对此进行更深入的研究。

另一个有趣的事实是，每个 Fargate 任务只在一个 EC2 实例中运行。Amazon 不会在同一个 EC2 实例上调度多个任务，即使它们共享相同的定义。如果一个任务定义有多个容器，那么它们都位于同一个 EC2 实例中。运行 Fargate 工作负载的 EC2 实例的 AMI 针对容器化工作负载进行了高度优化。

总之，Fargate 是 ECS 之上的一个类似 PaaS 的层，它抽象了基础设施，使用户能够专注于应用程序的期望状态。

在下一篇文章中，我们将仔细研究 Fargate 架构及其与 EKS 的集成。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>