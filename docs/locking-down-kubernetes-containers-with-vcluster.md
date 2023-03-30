# 使用 vcluster 锁定 Kubernetes 容器

> 原文：<https://thenewstack.io/locking-down-kubernetes-containers-with-vcluster/>

还记得当[容器](https://thenewstack.io/ci-cd-devops-and-containers-a-winning-trio/)还是全新的时候，我们都担心恶意行为者会从一个容器跳到另一个容器吗？我知道。正如[红帽资深杰出工程师 Daniel Walsh](https://www.linkedin.com/in/dan-walsh-a8729b2/) 早在 2014 年就说过，“[集装箱不包含。](https://opensource.com/business/14/7/docker-security-selinux)“集装箱往往是安全的，但集装箱突破，如 [CVE-2019-5736](https://nvd.nist.gov/vuln/detail/CVE-2019-5736) 可能会发生。因此，当开发工具和 Kubernetes 多租户初创公司 [Loft Labs](https://loft.sh/) 宣布其开源软件 [vcluster](https://www.vcluster.com/) 现在可以用于虚拟集群的隔离模式时，这就是你可以利用的新闻。

如果您不了解 vcluster，这里有 411。Vcluster 跟随 [k3v](https://github.com/ibuildthecloud/k3v) 的脚步，k3v 是基于流行的 [k3s](https://k3s.io/) Kubernetes 发行版的虚拟化 Kubernetes 的概念验证。如今，vcluster 使您能够在底层 Kubernetes 集群的命名空间内运行轻量级虚拟 Kubernetes 集群。这种方法减少了群集蔓延，实现了更安全、更易于维护的多租户，并旨在实现更高效的资源共享，最终节省基础架构成本。

## 独立的控制平面

它的新功能是旋转虚拟集群，这些集群通过独立的 Kubernetes 控制平面进行逻辑隔离。然而，在这些虚拟集群、pod 及其[容器](https://thenewstack.io/containers-microservices-two-peas-devops-pod/)中运行的工作负载在默认情况下并没有被隔离。相反，它们的作用域在一个名称空间内。

这对于这样的用例非常有用，例如使租户能够设置自定义名称空间，具有适当的基于角色的访问控制(RBAC)权限，因此他们可以在其虚拟化集群中开发，而无需要求集群管理器或站点可靠性工程团队为他们创建或修改[customresourceditions](https://kubernetes.io/docs/tasks/extend-kubernetes/custom-resources/custom-resource-definitions/)(CRDs)。这意味着，[v cluster 用户和首席](https://www.linkedin.com/in/mtougeron/) [Adobe](https://www.adobe.com/) 云工程师 Mike Tougeron 写道，“突然之间，开发团队可以按照他们喜欢的方式运行他们的定制运营商，并且它仍然会尊重主机集群的多租户特性。”

这非常方便。当工程师构建、测试和调试云原生软件时，虚拟集群通常被用作开发环境。虚拟集群也可以用作执行[持续集成/持续交付(CI/CD)](https://practical-tech.com/2018/07/10/continuous-integration-and-delivery-tool-basics/) 管道的临时环境。

## 启用安全控制，自动配置

以前，用于 vcluster 工作负载的任何 Kubernetes 安全机制都必须由集群管理员手动创建。现在，借助 vcluster 的隔离模式，无需手动配置即可启用和自动配置各种 Kubernetes 安全控制。其中包括:

*   Pod 安全标准(准入控制策略)
*   资源配额和限制范围
*   网络策略

Loft Labs 将此视为虚拟集群的默认最佳实践规则集。正如 Loft Labs 的联合创始人兼首席执行官 Lukas Gentele 所说，“以前，管理员必须为虚拟集群本身添加安全约束，这增加了复杂性，并需要持续维护。现在，在隔离模式下，我们作为项目维护人员提供了一组默认的安全措施，我们推荐这些措施作为隔离虚拟集群的最佳实践。”

如果您需要更高的安全性，隔离模式会强制实施基线工作负载隔离策略。Gentele 继续说道:“当然，管理员可以根据他们的使用情形和组织的安全策略调整隔离限制，但我们让他们更容易使用 vcluster，同时从一开始就默认实施更严格的安全边界。”

## Kubernetes 多租户

Vcluster 在解决 Kubernetes 多租户问题方面还有其他优势。其中包括:

*   比简单的基于名称空间的多租户更好的隔离；
*   降低云计算成本，因为虚拟集群比独立的单租户集群更加轻量级和资源高效；
*   应用程序工作负载与底层群集的共享基础架构工作负载(如共享入口控制器或网络插件)的逻辑分离和封装。

同时，虚拟集群用户可以预期他们的虚拟集群的行为就像任何常规的 Kubernetes 集群一样，因为 [vcluster 现在是经过认证的 Kubernetes 发行版](https://loft.sh/blog/vcluster-becomes-first-certified-kubernetes-distribution-for-virtual-kubernetes-clusters/)。换句话说，它通过了所有的[云本地计算基金会(CNCF) Kubernetes 一致性测试](https://www.cncf.io/certification/software-conformance/)。

Tougeron 认为 vcluster 在 CI/CD 和 canary 或 blue/green 部署方面有很大潜力。我也是。云原生开发人员应该认真研究一下 vcluster。这可能是您一直在寻找的安全开发 Kubernetes 环境的关键部分。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>