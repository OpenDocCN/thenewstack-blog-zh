# Kubernetes 本地工作流引擎 Argo 加入 CNCF

> 原文：<https://thenewstack.io/argo-the-kubernetes-native-workflow-engine-joins-the-cncf/>

本月早些时候， [Argo 项目](https://argoproj.github.io/)，一个用于 Kubernetes 部署和运行作业和应用程序的容器原生工作流引擎，作为孵化级托管项目加入了[云原生计算基金会](https://www.cncf.io/) (CNCF)。

通过加入 CNCF，Argo 项目希望与已经是该基金会成员的许多项目更密切地合作，并“让组织能够使用 GitOps 在 Kubernetes 上声明性地构建和运行云原生应用程序和工作流，”Intuit 产品开发副总裁 [Pratik Wadher](https://www.linkedin.com/in/pratikwadher) 在一份声明中说。

Argo 最初于 2017 年在 Applatix 创建，后来被 Intuit 收购，该项目已经集成或使用了许多 CNCF 项目，包括 gRPC、Prometheus、NATS、Helm 和 CloudEvents。组成 Argo 的四个子项目包括 [Argo Workflows](https://github.com/argoproj/argo) ，一个支持 DAG 和基于步骤的工作流的 Kubernetes 的容器原生工作流引擎， [Argo Events](https://github.com/argoproj/argo-events) ，一个基于事件的依赖管理器，用于触发工作流和应用， [Argo CD](https://github.com/argoproj/argo-cd) ，它支持任何 Kubernetes 资源的基于 GitOps 的声明性连续交付，以及 [Argo Rollouts](https://github.com/argoproj/argo-rollouts) ，它提供声明性渐进交付策略，如 canary 和 blue-green 部署。

[https://www.youtube.com/embed/OdzH82VpMwI?feature=oembed](https://www.youtube.com/embed/OdzH82VpMwI?feature=oembed)

视频

Wadher 在一封电子邮件中解释了 Intuit 的团队如何在 Argo 之前拼凑工具，试图创造同样的效果。

“我们在许多业务部门使用不同的部署工具，并且没有在 Intuit 部署软件的标准方法。Wadher 写道:“一些开发团队使用像 Jenkins 这样的 CI 工具来‘编写’他们的部署过程，另一些使用 Spinnaker，还有一些使用自主开发的工具并将多个部分缝合在一起。“显然，当我们迁移到基于 Kubernetes 的平台时，这些完全不同的工具无法工作，充其量只能提供次优的开发人员体验。例如，这些方法需要让 Jenkins 访问生产系统，这会带来安全风险，并使部署变得复杂且容易出错。”

虽然可能有人希望将 Argo 比作持续集成、持续交付(CI/CD)管道，但 Wadher 解释说，它“远不止于此”，而且它“独特地提供了一套基于 Kubernative-native GitOps 的工具，将作业、事件和服务的部署和运行集成到单个框架中。”Wadher 解释说，由于包含单点登录(SSO)、基于角色的访问控制(RBAC)以及审计和安全功能，Argo 为运行大型多集群 Kubernetes 部署的企业量身定制了其功能。此外，他说，它的可伸缩性、DAG 支持和工件管理使它“在 ML 和数据社区非常受欢迎。”

具体来说，Argo 是作为一个 Kubernetes-native 工具创建的，它将使用 Git 作为事实的单一来源，其中开发人员可以推送提交，避免手动部署，以及随之而来的错误。

“开发人员可以将他们的应用程序部署到多个集群中，并集中监控和排除应用程序故障，而无需登录 Kubernetes。此外，Argo CD 还自动将应用程序回滚到以前的状态，”Wadher 写道。“这大大减轻了开发人员的负担，他们现在更有信心在一天之内将变更推向生产。有了 Argo CD，我们的开发人员平均每天要进行 200 多次生产部署，而以前每次部署要花好几天时间。”

展望未来，Wadher 说，Argo 的未来将主要由社区决定，但 MLOps 和连续渐进交付将是两个主要关注领域。对于 MLOps，他期望 Argo 事件和工作流之间有更好的集成，有更好的监测和报告。另一方面，他表示，该项目计划全面支持渐进式交付，集成众多服务网格，并扩展“GitOps 范式”来管理所有计算方法，包括批处理、基于事件的服务以及 Kubernetes 中的控制平面元素。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>