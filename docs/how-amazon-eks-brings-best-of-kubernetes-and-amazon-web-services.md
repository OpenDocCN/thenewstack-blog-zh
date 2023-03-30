# 亚马逊 EKS 带来了最好的 Kubernetes 和 AWS |新堆栈

> 原文：<https://thenewstack.io/kubernetes/how-amazon-eks-brings-best-of-kubernetes-and-amazon-web-services/>

去年 12 月在 AWS re:Invent 上推出的针对 Kubernetes(亚马逊 EKS)的亚马逊弹性容器服务将很快全面推出。亚马逊花了大约六个月的时间来确保管理的 [Kubernetes for AWS 服务](https://thenewstack.io/managing-kubernetes-secrets-with-aws-secrets-manager/)准备好处理生产部署。自宣布以来，亚马逊 EKS 团队一直忙于将 AWS 的一些核心功能与 Kubernetes 集成在一起。

[亚马逊网络服务](https://thenewstack.io/kubernetes-and-amazon-web-services/)已经是运行生产负载的大量 Kubernetes 集群的所在地。开源部署在社区中大受欢迎。许多客户使用它在 Amazon EC2 中快速提供多节点 Kubernetes 集群。Kops 在将部署最佳实践应用于生产中运行的集群方面做得相当不错。亚马逊 EKS 的期望是，它击败通过 Kops 部署的集群的体验和性能。

EKS 需要更长时间才能普遍可用的原因之一是与 AWS 现有构件的集成。从 VPC 网络到 IAM，亚马逊在不破坏预期行为的情况下，仔细集成了核心服务。客户还可以利用 CloudWatch 和 CloudTrail 等标准监控和日志工具来记录和监控 EKS 工作负载。亚马逊 EKS 通过了[云本地计算基金会](https://www.cncf.io/)一致性测试，成为认证托管平台，这意味着所有与上游 Kubernetes 合作的插件和扩展将在 EKS 照常工作。

## 资源调配体验

亚马逊 EKS 与其他托管服务略有不同，如 RDS 和 EMR。与他们的服务相比，客户对服务有更多的控制和更好的可见性。

在 EKS 运行第一个集装箱化工作量之前，有三个高级步骤:

*   提供主节点—这一步包括选择区域、VPC 的子网、节点使用的 IAM 角色的 ARN 以及安全组，以支持主节点和节点之间的通信。在幕后，EKS 创建了一个高度可用的 Kubernetes 控制平面，分布在三个可用性区域。需要注意的是，这个控制平面还在多 az 模式下运行高可用的 etcd 集群。这一步的输出是主服务器的 URL 和 ARN。
*   调配工作节点—客户能够从可用的 EC2 实例系列中选择工作节点配置。根据工作负载的类型，可以选择通用实例或网络/存储优化实例。这些节点是基于现有的 Amazon Linux AMI 作为自动扩展组部署的。客户还可以选择通过打包脚本定制的不同 AMI。这些实例承担的 IAM 角色允许它们加入上一步中创建的控制平面。
*   配置 kubectl——一旦主服务器和工作服务器就位，我们必须将 kubectl——Kubernetes 客户端的 CLI 指向控制平面公开的 API 服务器。EKS 希望对标准配置文件稍作修改，以对用户进行身份验证和授权。这是通过嵌入身份验证扩展来实现的，该扩展将从标准 AWS CLI 配置文件中获取凭证。

亚马逊 EKS 团队保留了很多处理 Kubernetes 的标准工作流程和经验。任何熟悉 Minikube 或 AKS 或 GKE 等其他托管服务的人都可以无缝切换到 EKS。

## 与亚马逊 VPC 整合

AWS 已经建立了一个容器网络接口(CNI)插件，将 Kubernetes 的覆盖网络与 AWS 的网络控制平面集成在一起。EKS 运行一个与 VPC 集成的网络拓扑。这一扩展使客户能够将 EKS 部署视为其 AWS 部署的逻辑扩展。网络访问控制、路由表、私有和公共子网拓扑无缝扩展到亚马逊 EKS 内运行的应用程序。

与其他环境不同，在 EKS 运行的 pod 会获得一个 IP 地址，该地址属于部署该节点的子网的 CIDR。这些 IP 地址在 VPC 内是可路由的，并且符合在网络层定义的所有策略和访问控制。

每个节点运行一个守护进程集，托管特定于 AWS 的 CNI 控制平面。每当 kubelet 调度一个 pod 时，它都会请求守护进程设置允许一个 IP 地址。此时，CNI 控制平面创建一个与连接到该节点的弹性网络接口(ENI)相关联的辅助 IP 地址，并将其移交给 kubelet。这从根本上不同于基于法兰绒或 Contiv 的典型覆盖网络。

上述方法的另一面是，节点可能会用完辅助 ip 地址。对于一个 EC2 实例可以连接多少个 Eni 有一个硬性限制。每个 ENI 可以创建多少个辅助 IP 地址也有限制。这些限制迫使客户在部署之前规划节点配置。当然，也可以创建一个特定的节点组，并将其连接到现有的集群。

与 VPC 的深度集成使得许多客户选择 EKS，而不是通过 Kops 进行 DIY 部署。

## 将 AWS IAM 扩展到 Kubernetes RBAC

AWS 的身份和访问管理(IAM)是业界最好的身份平台之一。基于用户、组、策略和角色的模块化设计为定义身份验证和授权方案提供了合适的粒度级别。

Kubernetes 还有一个定义良好的基于角色的访问控制(RBAC ),以服务帐户、集群角色和角色绑定的形式出现。

亚马逊正在利用一个名为 [Authenticator 的开源项目，用于 Heptio 构建的 AWS](https://github.com/heptio/authenticator) 。这个认证器在 AWS IAM 和 Kubernetes RBAC 之间架起了一座桥梁。基于 Kubernetes 授权的 Webhook 模式，该工具在每次执行操作时都会检查 IAM。

在 1.10 版中，可插拔身份验证提供程序是上游 Kubernetes 发行版的一部分。这个时机对亚马逊 EKS 有利，它正在利用这个特性来支持标准的 kubectl，而没有受到任何攻击。

Heptio Authenticator 的集成使 EKS 能够将其现有的 RBAC 无缝扩展到 Kubernetes。它防止将凭证硬连接到每个节点，还提供了一种机制，使标准的 kubectl 能够与 EKS 一起工作。

亚马逊在 Kubernetes 派对上迟到了。但是，延迟帮助 AWS 团队从托管 Kubernetes 的现有实现中学习。它确保了 EKS 与其他 AWS 服务的最佳集成，这有助于企业客户采用 Kubernetes。

**本文更新于 2022 年 12 月 13 日。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>