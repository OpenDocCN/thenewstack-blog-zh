# Kubernetes 认证“解决”:SPIFFE/SPIRE 转移到 CNCF 孵化

> 原文：<https://thenewstack.io/kubernetes-authentication-solved-spiffe-spire-move-to-cncf-incubation/>

自从 [SPIFFE](https://spiffe.io/) (面向所有人的安全生产身份框架)和[SPIRE](https://spiffe.io/spire/)(sp iffe 运行时环境)项目[加入](https://www.cncf.io/blog/2018/03/29/cncf-to-host-the-spiffe-project/)[云原生计算基金会(CNCF)](https://www.cncf.io/) 以来，现在这些项目已经[从沙箱级别转移到孵化级别，加入了许多孵化级别的项目，如 OpenTracing、gRPC、Linkerd、Rook、etcd、CloudEvents、Argo 等等。这一举动意味着这些项目已经满足了许多](https://www.cncf.io/blog/2020/06/22/toc-approves-spiffe-and-spire-to-incubation/)[需求](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc)，比如维护者和产品用例的多样性，并且已经通过了[安全审计](https://github.com/cncf/sig-security/tree/master/assessments/projects/spiffe-spire)，没有导致任何严重错误。

当我们上次在 Kubecon+CloudNativeCon 北美 2019 期间赶上 SPIFFE/SPIRE 时，他们刚刚在 alpha 中推出了许多功能，包括[将联合身份引入分布式架构](https://thenewstack.io/spiffe-spire-brings-federated-identity-to-distributed-architectures/)。SPIFFE 和 SPIRE 产品经理安德烈斯·维加(Andres Vega)说，现在，这些功能都已普遍可用且稳定，项目已准备好投入生产，大规模运行，并有广泛的使用案例。

“我们正在讨论联合云提供商服务、替换机密以及无需用户名和密码即可进入数据库的所有高级用例。所有这些都开启了许多可能性。在很大程度上，Kubernetes 内部的身份验证已经解决，如果你去找云提供商，他们有自己的本地安全控制，但具有挑战性的部分是混合用例，”Vega 在接受采访时说。“我们发现,[SPIFFE 和 SPIRE]就在其中，人们来到 SPIFFE 和 SPIRE 开始做复杂的事情。在某种程度上，它是一块罗塞塔石碑，解开了所有这一切，弥合了现代做事方式与所有其他传统身份验证方式之间的差距，在这些方式中，您依赖于使用秘密。”

Vega 在一封电子邮件中发送了自去年 11 月以来更新的完整功能列表:

*   SPIRE Federation 用于组织间互操作性的用例，例如云提供商和其客户之间的互操作性
*   SPIFFE 与 SPIFFE 兼容系统的联合，比如对服务网格的 SPIRE 部署
*   OIDC 联盟到远程系统，如与 OIDC 联盟兼容的公共云提供商服务和秘密存储
*   支持嵌套 SPIRE 的多云拓扑
*   数据库 x509 身份验证
*   彻底检查现有的客户端库，以确保它们是惯用的(go-spiffe、java-spiffe 和 c-spiffe)
*   在 Kubernetes 中运行 SPIRE 时，提高自动注册条目管理的性能和可靠性

在这两个项目之间，SPIFFE 提供了一个安全识别软件系统的安全规范，而 SPIRE 是 SPIFFE APIs 的一个实现，提供了工作负载的验证。除了联邦身份的普遍可用性之外，自首次加入沙盒级别以来，这些项目还添加了许多功能，包括水平扩展、对非 SPIFFE 感知工作负载的支持、对裸机、AWS、GCP 和 Azure 等的支持，以及与 Kubernetes、Docker、Vault、MySQL、Envoy 等的集成。关于最后一点，SPIRE 维护者和惠普企业(HPE)的首席软件工程师 Andrew Harding 说，SPIRE 与 Envoy 的集成意味着 SPIRE 已经迈出了第一步，使采用变得快速和容易。

Harding 说:“有许多现有的部署和服务架构已经在使用 Envoy，因此能够无缝地插入 SPIRE 作为 Envoy 的身份源对于项目的普遍采用来说是一个巨大的好处。”

SPIRE 与 Envoy 合作的能力也使其被用于提供与 [Istio](https://istio.io/) 的身份，后者是使用 Envoy 为其数据平面构建的开源服务网格。哈丁指出了 IBM 的一个新兴的[项目，该项目使用 SPIRE 来提供身份平面，Vega 谈到了使用 SPIRE 所面临的挑战。](https://github.com/IBM/istio-spire)

“Istio 的挑战在于，Istio 的身份模型是特定于 Istio 的。如果您想给事物命名或标识，那么您必须使用 Kubernetes 对象。你可以说这个东西是由服务帐户或这个名称空间来表示的，但你不能通过谷歌或 AWS 从底层基础设施中对属性这样做，或者你不能从应用程序级元数据中这样做，而这正是 SPIFFE 提供的灵活性，”Vega 说。“IBM 和其他有类似努力的人的部分动机是，他们希望有一种更加平台不可知的方式来给出身份，并让网格上的东西与网格外的东西进行通信。”

除了新特性之外，还对许多东西进行了重构，比如 Go、C 和 Java 的客户端库，所有这些都经过了彻底检查，以简化采用。Vega 还指出，该团队已经重构了 SPIRE APIs，以偿还技术债务，并使其更容易解决未来计划的用例，如无服务器。他说，新的 API 将在即将到来的 7 月发布。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>