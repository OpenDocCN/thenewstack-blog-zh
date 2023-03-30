# 安全设置 Kubernetes 集群的最佳实践

> 原文：<https://thenewstack.io/best-practices-for-securely-setting-up-a-kubernetes-cluster/>

[](https://twitter.com/DMBisson)

 [大卫·比森

大卫·比森是一名信息安全作家和安全迷。他是 IBM 安全情报、Tripwire 安全博客的特约编辑，也是 Bora 的特约撰稿人。他还定期为 Zix 和数字安全领域的许多其他公司撰写书面内容。](https://twitter.com/DMBisson) [](https://twitter.com/DMBisson)

组织越来越依赖容器来推动数字化转型。到 2020 年， [Gartner](https://www.gartner.com/en/newsroom/press-releases/2020-06-25-gartner-forecasts-strong-revenue-growth-for-global-co) 预测四年后全球集装箱管理收入将从 4.658 亿美元增长到 9.44 亿美元。这家全球研究和咨询公司表示，到 2022 年，75%的全球组织将在生产中运行容器化应用程序，而 2020 年这一比例不到 30%。

这些预测证明了组织对容器的使用正在增长的事实。根据部署中容器的数量，一些组织可能无法手动管理其容器。因此，对容器管理解决方案的需求越来越大。

组织尤其转向 Kubernetes。Kubernetes 是一个可移植的开源平台，使组织能够使用声明式配置和自动化来管理其容器化的工作负载和服务。如 Kubernetes 的[文档](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)中所述，该平台为组织提供了多种优势:

*   **负载均衡。**组织求助于 Kubernetes 来确保他们支持容器的应用程序保持运行。这里的风险是高网络流量可能会影响容器的可用性。使用 Kubernetes，组织可以自动分配网络流量，以确保其应用程序继续运行。
*   **管理容器的展开状态。**作为其容器安全性的一部分，组织需要描述其部署的容器的期望状态。Kubernetes 可以在这方面提供帮助，它可以以可控的速度将组织容器的实际状态自动更改为指定的期望状态。
*   **自愈。** Kubernetes 自动监控组织部署的容器的健康状况。为了支持这一点，该平台可以重启失败的容器，替换容器，以及杀死不符合用户定义的环境健康检查中指定的要求的容器。

所有上述好处的存在都归功于[红帽](https://www.redhat.com/en/topics/containers/what-is-a-kubernetes-cluster)所描述的 [Kubernetes 的一个关键优势:集群](https://thenewstack.io/what-does-it-take-to-manage-hundreds-of-kubernetes-clusters/)。组织不能运行 Kubernetes 而不运行一个。每个集群包含两个元素:一组运行应用程序和工作负载的节点；和控制平面，这有助于保持集群的期望状态。这两个组件一起帮助集群在组织的环境中调度和运行容器。

## 安全性:获得 Kubernetes 好处的必要条件

如果想要获得 Kubernetes 的全部好处，组织需要了解如何建立集群。作为这些考虑的一部分，他们需要保护他们的集群。[黑暗阅读](https://www.darkreading.com/cloud/why-kubernetes-clusters-are-intrinsically-insecure-(and-what-to-do-about-them)/a/d-id/1338747)注意到管理员可能会不小心以不安全的方式部署他们的集群。根据其性质，这些安全弱点可能会使组织面临各种数字风险，如数据泄露和拒绝服务(DoS)攻击。

考虑到这些类型的威胁，Kubernetes 建议组织从问自己一系列问题[开始，找出哪种类型的集群管理最适合他们的需求。例如，组织需要确定他们是打算使用托管的 Kubernetes 集群还是托管他们自己的集群。他们还需要确定他们的群集是位于云中还是内部，如果是后者，他们需要选择一个适用于其环境的网络模型。](https://kubernetes.io/docs/concepts/cluster-administration/)

然后，组织可以继续深入研究其集群组件的安全性。以节点为例，或者以托管称为“pod”的容器组的元素为例。默认情况下，这些 pod 是非隔离的，它们接受来自任何来源的流量。这给组织带来了一个问题，因为恶意行为者可以利用单个 pod 的危害横向移动到 Kubernetes 环境的其他部分。

作为回应，组织可以使用[网络策略](https://kubernetes.io/docs/concepts/services-networking/network-policies/)来加固他们的豆荚。这些服务选择命名空间中的 pod，并拒绝与策略规范中不允许的那些 pod 的任何连接。使用网络策略，管理员可以通过创建拒绝所有入站流量的网络策略，为命名空间内的所有 pod 创建默认隔离策略。他们同样可以通过创建网络策略来增强安全性，这些策略会拒绝在名称空间中创建的所有 pod 的所有出口流量或入口和出口流量。

组织也可以考虑保护 [Kubernetes API 服务器](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-apiserver/)，它是控制平面的前端，公开 Kubernetes API 并促进所有其他组件之间的交互。为了防止恶意参与者获得对 API 服务器的访问，组织可以在主节点中运行命令“`ps -ef | grep kube-apiserver`”，并检查“`--authorization-mode`”是否存在，以及是否被设置为包含 Kubernetes 基于角色的访问控制(RBAC)的值。这将有助于管理员根据组织内的用户角色来控制谁可以访问 Kubernetes 环境。此外，他们可以使用[准入控制](https://kubernetes.io/docs/concepts/security/controlling-access/)模块拒绝未经批准的访问 Kubernetes 资源的请求。

## CKS 如何加深对 Kubernetes 安全性的了解

安全地建立一个集群只是一个元素，人们可以通过成为认证 Kubernetes 安全专家(CKS)学习。由[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)提供的 CKS 认证证明了个人在集群强化、系统强化和 Kubernetes 供应链安全等主题方面的知识。

在成为认证 Kubernetes 安全专家，候选人可以使自己成为其组织的安全劳动力的宝贵成员。以下是 StackRox 的更多信息:

*CKS 是由云计算原生计算基金会(CNCF)支持的第三个基于 Kubernetes 的认证。CKS 将加入现有的[认证 Kubernetes 管理员](https://www.cncf.io/certification/cka/) (CKA)和[认证 Kubernetes 应用开发者](https://www.cncf.io/certification/ckad/) (CKAD)项目。所有这三种认证都是在线、监考、基于表现的考试，需要从命令行解决多个 Kubernetes 安全任务。随着过去五年对 Kubernetes 的大量投资，这些认证继续受到许多寻求 Kubernetes 技术知识的人的高度追捧。CKS 特别关注 Kubernetes 基于安全的特性，如基于角色的访问控制(RBAC)和网络策略，并利用现有的 Kubernetes 功能来保护您的集群。*

感兴趣的人可以通过访问 CNCF 的网站[这里](https://www.cncf.io/certification/cks/)了解更多关于 CKS 和认证程序的信息。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>