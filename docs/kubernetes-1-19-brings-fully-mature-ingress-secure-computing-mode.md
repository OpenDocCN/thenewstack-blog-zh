# Kubernetes 1.19 带来了完全成熟的入口安全计算模式

> 原文：<https://thenewstack.io/kubernetes-1-19-brings-fully-mature-ingress-secure-computing-mode/>

虽然 Kubernetes 最新版本的发布有点延迟，但是 [Kubernetes 发布团队](https://github.com/kubernetes/sig-release/blob/master/releases/release-1.19/release_team.md)刚刚推出了 Kubernetes 版本 1.19，其中有几处更新增强了 Kubernetes 的生产就绪性。这些改进包括 Ingress 和 seccomp 功能的全面推出、安全性改进(如 TLS 1.3 支持)以及其他功能增强。

虽然 Kubernetes 团队历史上每年发布四个更新，但由于疫情的条件，今年将只发布三个版本。1.19 版本很可能是今年的最后一次更新。

## GA 改进:Ingress 和 seccomp

 [希拉里·本森

作为 StackRox 的产品主管，Hillary Benson 负责产品战略、产品设计和产品管理。她在安全行业和情报界拥有超过 10 年的经验。在加入 StackRox 之前，她带领团队为国家安全局执行技术情报收集任务，并在私营企业担任红队操作员和安全工程师。希拉里拥有乔治城大学沃尔什外交学院安全研究硕士学位和麻省理工学院管理学学士学位。](https://www.linkedin.com/in/hillary-benson/) 

[入口](https://kubernetes.io/docs/concepts/services-networking/ingress/)最初是在 Kubernetes 版本 1.1 的测试版中作为 API 引入的。此功能使用户能够控制对群集中服务的外部访问，以公开 HTTP 和 HTTPS 路由。它还可以帮助管理负载平衡，终止 SSL/TLS，并提供基于名称的虚拟主机功能。为了使入口资源发挥作用，必须使用入口控制器。Kubernetes 目前支持和维护 GCE 和 nginx 控制器。

在版本 1.19 中，Ingress 升级到正式发布，并被添加到网络 v1 APIs 中。这次更新带来了 v1 入口对象的一些关键变化，包括模式和验证变化。

[seccomp](https://kubernetes.io/docs/concepts/policy/pod-security-policy/#seccomp) (安全计算模式)在 Kubernetes 版本中也毕业于 GA。seccomp 是 Linux 内核中的一个安全设施，它限制了应用程序可以进行的系统调用的数量。它最初是作为 Kubernetes 版的一个特性引入的，但是有一些限制。以前，将 seccomp 配置文件应用于 pod 时，需要对 PodSecurityPolicy 进行注释。

在此版本中，seccomp 引入了一个新的`seccompProfile`字段，添加到 pod 和 container securityContext 对象中。为了确保 Kubelet 向后兼容，seccomp 配置文件将按优先顺序执行:

1.  容器特定字段。
2.  特定于容器的注释。
3.  豆荚宽的领域。
4.  Pod 范围的注释。

在本次更新中，pod 沙盒容器现在也配置了单独的`runtime/default` seccomp 配置文件。

## 支持 TLS 1.3

根据去年安全审计期间收集的建议，Kubernetes 版增加了对可用于 orchestrator 的新 TLS 1.3 密码的[支持](https://github.com/kubernetes/kubernetes/pull/90843)。

## 介绍节点调试

Kubernetes 1.19 引入了`kubectl alpha debug`命令，现在在 alpha 中可以使用。此命令将在主机操作系统命名空间中创建和运行一个新的 pod，以排除节点故障。用户现在无需重启即可检查正在运行的 pod。此外，用户不再需要进入容器本身来检查系统或启动操作，如调试实用程序或从 pod 网络名称空间发出初始网络请求。这一增强消除了节点维护和调试对 SSH 的依赖

## 入场网钩中的警告

在 Kubernetes 1.19 引入的 beta 版中，Admission webhooks 可以向发出请求的 API 客户端提供非致命警告。这种增强使得识别有问题的 API 使用变得更加容易。

## 其他变更和弃用

本着包容性的精神，Kubernetes 1.19 还对其使用的术语进行了修改，以反映更具包容性的语言，例如用 allowlist 替换 whitelist。

对 [Pod 拓扑分布](https://kubernetes.io/docs/concepts/workloads/pods/pod-topology-spread-constraints/#spread-constraints-for-pods)进行了额外的[更改](https://github.com/kubernetes/kubernetes/pull/90475)，它会自动对拓扑进行加权，并在节点和区域之间应用更好的区分，以在各种约束条件下产生更平衡的结果。该功能在 1.18 版本的测试版中发布，为复杂的窗格布局创建简单的定义。此外，1.18 中引入的不可变秘密和配置映射特性在 1.19 中升级为 beta 版。

另一个值得注意的[更新](https://github.com/kubernetes/kubernetes/pull/89193)确保为服务帐户凭证创建的默认卷挂载具有文件权限，这将在运行非根容器时提高安全级别。版本 1.19 现在也支持来自 Kubernetes 组件的 JSON 日志输出，方法是传递标志`–log-format = JSON。

hybercube[现在被弃用](https://github.com/kubernetes/kubernetes/issues/81760)，并且不会由 Kubernetes 项目继续构建。在 1.19 版中，一些较旧的测试 API 版本也已被弃用。它们将在 1.22 版本中被删除，这可能会成为许多用户的突破性版本。

## 库伯内特的未来

那些密切关注 Kubernetes 更新周期的人可能会意识到，对 sidecar 容器的支持预计将在 1.19 中发布，但由于 Kubernetes SIG-node 的额外考虑，[已被推迟](https://github.com/kubernetes/enhancements/issues/753)。这项开发工作将对其他项目产生重大影响，如 [Istio](https://istio.io/) 。

无论如何，Kubernetes 背后的团队在 1.19 版本中引入了几个关键的增强功能，这些功能继续改善了 Kubernetes 的安全性并扩展了其功能。这些更新是社区努力实现这些新功能的结果。完整的变化列表，请查看[官方发布说明](https://kubernetes.io/docs/setup/release/notes/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>