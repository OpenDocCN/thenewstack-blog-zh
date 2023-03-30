# Kubernetes 1.14 为 Windows Server 带来了 Docker 编排

> 原文：<https://thenewstack.io/kubernetes-1-14-brings-docker-orchestration-to-windows-server/>

最新发布的 [Kubernetes](https://github.com/kubernetes/kubernetes) ，版本 1.14 **，**推出了对 Windows 节点的生产级支持，并有 10 项增强功能转移到稳定版。

“我最引以为豪的是，这个版本拥有 Kubernetes 所有版本中最稳定的增强功能，”发布负责人 [Aaron Crickenberger](https://github.com/spiffxp) 说，他是谷歌的高级测试工程师。“你已经听到人们谈论 Kubernetes 专注于稳定性和成熟度，我认为你已经开始看到这个版本的结果了。”

Crickenberger 支持 Windows 特别兴趣小组组长 Michael Michael 和微软以及其他公司在 Windows 节点上的工作，这项工作始于三年前。

现在，您可以在 Kubernetes 之上使用 [Docker 来调度 Windows Server 容器。](https://thenewstack.io/kubernetes-vs-docker-swarm-whats-the-difference/)

“这项工作实际上是围绕着修改 Kubelet 和 Kube 代理来进行的，这样 Windows 就可以作为一个操作系统得到支持，Windows 上的 Docker 功能也可以得到适当的考虑，”Michael 说。

第二大部分是围绕网络基础设施。随着[容器网络接口(CNI)](https://thenewstack.io/kubernetes-and-cni-whats-next-making-it-easier-to-write-networking-plugins/) 的加入，网络基础设施也必须在 Windows 上良好工作。这包括与许多网络提供商和网络插件集成，以确保他们的 CNI 版本也能在 Windows 上工作。这一努力正在进行。

[Kubernetes 1.14](https://kubernetes.io/blog/2019/03/25/kubernetes-1-14-release-announcement/) 包括:

*   支持面向工作节点和容器的 Windows Server 2019
*   支持与 Azure-CNI、OVN-库伯内特和法兰绒的树外联网，工作继续包括 Calico 以及其他流行的网络提供商
*   改进了对 pod、服务类型、工作负载控制器和指标/配额的支持，以紧密匹配为 Linux 容器提供的功能

Michael 说，大多数企业都有 Windows 和 Linux 工作负载的组合，这推动了对 Windows 支持的需求。

“如果您是一家企业，并且同时拥有 Linux 和 Windows 应用程序，您不会希望使用两个不同的协调器。你希望在两个生态系统中都采用云原生方法，”他说。

增强功能包括:

*   kubectl 的文档已经重写，重点是使用声明性资源配置来管理资源。在这里可以找到这本书的[，它有一个来自 Kubernetes](https://kubectl.docs.kubernetes.io/) [主文档的链接](https://kubernetes.io/docs/home/)。还有一个 kubectl 的标志和吉祥物叫做*kubee-cudding*。
*   kubectl 中通过 apply 等命令的 **-k** 标志提供了 [kustomize](https://github.com/kubernetes-sigs/kustomize) YAML 配置工具的声明性资源配置创作功能。Kustomize 帮助用户使用 Kubernetes-native 概念编写和重用资源配置。这里提供了这些新功能的文档。
*   kubectl 插件机制逐渐稳定。它允许开发人员将他们自己定制的 kubectl 子命令作为独立的二进制文件发布。
*   永久本地卷现已正式发布。它们使本地连接的存储可用作永久卷源。
*   进程 id(PID)正在向 beta 迁移。该功能解决了达到任务限制并导致主机不稳定的问题，使管理员能够通过默认每个 pod 的 PID 数量来提供 pod 到 pod 的 PID 隔离。一个额外的 alpha 特性是能够为用户 pod 预留多个已分配的 PID。
*   [Pod 优先级和抢占](https://github.com/kubernetes/enhancements/issues/564)使 Kubernetes 调度程序能够根据优先级安排工作，并根据需要删除不太重要的 Pod。
*   [Pod 准备就绪门](https://github.com/kubernetes/enhancements/issues/580)引入了一个扩展点，用于 Pod 准备就绪的外部反馈。
*   默认强化 [RBAC 发现集群角色绑定](https://github.com/kubernetes/enhancements/issues/789)。这在很大程度上是由去年 11 月发现的 Kubernetes 漏洞引起的。它从默认情况下允许未经身份验证的访问的 API 集中删除发现。

总的来说，这个版本包括 31 个增强功能:10 个升级到稳定版，12 个测试版，7 个全新的。

“将 Windows 作为潜在的工作负载意味着我们必须更准确地定义 Kubernetes 在某些环境中支持和不支持什么，”Crickenberger 说。

“我相信，诸如 pod 就绪门、优先级和先发制人等功能将真正有助于人们协调高级工作负载。一些应用程序可能需要非常具体的方式来表明它们是否准备好处理流量，而 pod 就绪门允许这样做。”

Kubectl 的增强提供了一种 kube-native 的方式，通过一个定制的子命令，允许他们更有效地管理资源以及指定自己工作负载的插件。

他说，将 Windows 支持引入 Kubernetes 确实迫使该项目就普遍可用意味着什么展开了一场对话。

“这鼓励我们在发布过程中引入更多的形式主义和流程，”他说。

“我认为我们已经达到了与 Kubernetes 的状态，如果我们更好地记录我们所有的期望，那将非常有帮助。我们现在称它们为增强功能，而不是特性。我们有整个改进过程，”他说。“我们已经确保此次发布的所有内容都是根据一致的标准进行衡量的。你能证明阿尔法、贝塔或稳定遗传的含义吗？我们希望确保我们以交叉的方式审查 API 设计原则是否得到了一致的使用，这样最终用户就不必完全重新学习一些操作方式。有一种适用于所有地方的 Kubernetes 做事方式。”

迈克尔补充说:“这个过程和成熟度确实给了我们一种方法，以统一的方式与每个 SIG 交谈，从一开始就设定期望，并让各个 SIG 独立运作，并在发布结束时满足这些期望。”

Crickenberger 说，Kubernetes 指导委员会不控制项目的方向，但确保社区在前进的方向上保持一致。

“我们一直对不在 Kubernetes 中添加厨房水槽很感兴趣。我们对添加大量的功能不感兴趣，我们感兴趣的是 Kubernetes 非常稳定，定义非常明确，我敢说这是一个非常无聊的东西，具有非常清晰和明显的扩展点。例如，允许审计的动态扩展就是一个明显的扩展点，”他说。

展望未来，他预见到更多从 Kubernetes 核心到更多可扩展组件的提取，存储，CSI，DNI 和容器网络，以及更多云提供商的工作。

管理 Kubernetes 的云本地计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>