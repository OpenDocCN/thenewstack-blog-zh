# AWS Proton，云本地资源的共享服务库

> 原文：<https://thenewstack.io/aws-proton-a-shared-services-library-for-cloud-native-resources/>

亚马逊网络服务推出了一个新的共享服务平台，名为 Proton T1，旨在将容器、AWS Lambda 无服务器作业和其他云资源整合到一个目录中，使开发者更容易组装一个标准化的组件堆栈来运行他们的应用程序。

Proton 是该公司在本月举行的用户大会 [AWS re:Event](https://reinvent.awsevents.com/) 上首次亮相的众多新的云原生服务和增强功能之一。

迄今为止，考虑到不同的组件可能由不同的开发团队维护，将多个微服务集成到一个内聚的应用程序中是一项困难的任务。

“没有单一的解决方案可以让您在架构部署中提供一致性。通常，平台工程团队或中央工程团队希望实现标准化。但是现在没有好的方法来做到这一点，”AWS 现代应用产品营销负责人 [Aaron Kao](https://www.linkedin.com/in/kaoaaron/) 在接受新堆栈采访时说。

AWS Proton 旨在简化供应、部署和监控由短暂计算元素构建的应用程序的过程，例如内置于容器中的组件或作为无服务器作业运行的组件。

使用 Proton，平台工程师可以在一个模式文件中定义和发布一个堆栈，比如一个容器化的 web 应用程序，或者一个无服务器的数据处理服务。例如，对于 web 应用程序，他们可能希望使用弹性容器服务(ECS)集群、虚拟私有云(VPC)和相关的安全组，以及 AWS Fargate、前端负载平衡器和后端数据 DynamoDB。需要一个监控系统，以及一个用于构建过程的 CI/CD 系统。平台团队将以标准化的方式定义所有这些组件如何组合在一起，以及如何保护它们。

根据 Kao 的说法，Proton 不是一个“[控制平面](https://thenewstack.io/crossplane-a-kubernetes-control-plane-to-roll-your-own-paas/)”或运行时，但它可以为轻松构建一个奠定基础。但是当开发者选择一个堆栈时，Proton 会将其推进构建过程，并将其部署到一组预先定义的云资源中。开发人员可以针对不同的工作重复使用堆栈—平台团队确保所有组件保持最新和打补丁。AWS 本身也提供了许多预构建的堆栈，代表了云计算巨头在安全性、架构和工具方面的最佳实践。

[https://www.youtube.com/embed/yWXT21enYYc?feature=oembed](https://www.youtube.com/embed/yWXT21enYYc?feature=oembed)

视频

来自虚拟会议的其他云原生新闻包括:

*   *   **亚马逊 ECS Anywhere:** 亚马逊的[弹性容器服务](https://aws.amazon.com/ecs)现在可以扩展到用户自己的数据中心，或者扩展到另一个云。一个小代理放在用户的服务器上，它连接回 ECS 控制台，使管理员能够在两种环境中管理集群、安排工作负载和监控容器。这项功能将于 2021 年初推出，定价尚未确定。
    *   **亚马逊 EKS 无处不在:** AWS 自己的弹性 Kubernetes 服务，现在可以下载并在数据中心或第三方云服务上运行。它建立在该公司自己的 Kubernetes 发行版的基础上，但也包括通过 EKS 本身提供的相同的控制集，它为在家 Kubernetes 部署提供了相同的界面，这对于那些已经在管理 AWS 版本的管理员来说应该已经很熟悉了。这款[发行](https://aws.amazon.com/eks/eks-anywhere)将于 2021 年上半年上市。 [AWS 和 Kubernetes 定价](https://thenewstack.io/7-tips-for-cutting-down-your-aws-kubernetes-bill/)也是一个考虑因素。

*   **AWS Lambda 改进**:该公司的“功能即服务”现在可以在容器中运行工作负载及其依赖项，特别是[容器标准](https://thenewstack.io/docker-spins-containerd-independent-open-source-project/)。Kao 提到，许多开发人员现在在容器中工作，这种方法可能比将工作负载打包成 ZIP 文件更容易，这是向这种无服务器服务提交作业的传统方法。计费也有所改进:用户现在将按每毫秒使用计费，而不是按每 100 毫秒计费，这激励程序员编写更高效的程序。
*   **Amazon Elastic Container Registry(ECR)Public:**AWS[Container repository](https://aws.amazon.com/ecr)，它为用户容器图像提供了一个家，现在提供了公开这些图像供公众访问的能力。对于独立软件供应商来说，这可能是一个有用的功能，他们希望为他们的客户和其他感兴趣的团体提供一个位置来下载他们的软件包的官方容器映像，而不会产生可能来自另一个注册中心[，如 Docker Hub](https://thenewstack.io/docker-hub-limits-what-they-are-and-how-to-route-around-them/) 的费用。

TNS 记者 B.C. Gain 在推特上报道了这一事件。

亚马逊网络服务是新堆栈的赞助商。

[特征图像](https://twitter.com/bcamerongain/status/1333816819732377605)由 B.C .增益。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>