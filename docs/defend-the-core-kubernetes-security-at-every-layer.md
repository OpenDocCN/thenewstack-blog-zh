# 保卫核心:Kubernetes 每一层的安全性

> 原文：<https://thenewstack.io/defend-the-core-kubernetes-security-at-every-layer/>

[](https://twitter.com/jimmesta)

 [吉米·梅斯塔

吉米·梅斯塔目前是 Fastly(原 Signal Sciences)的安全研究主管，是一位拥有 15 年经验的资深应用和基础设施安全领导者。他在行业的进攻和防御方面都花了时间，致力于构建现代的、开发人员友好的安全解决方案。在加入 Signal Sciences 之前，Jimmy 维护着一个全球网络，为公司提供咨询，并在世界各地提供技术安全培训、研究和安全基础设施。他以前教过 Kubernetes、Docker、DevSecOps 和 Manicode 安全的高级 Web 应用程序安全课程。Jimmy 曾在各种全球会议上发表演讲，包括 KubeCon、LocoMocoSec、RSA、NDC、CactusCon 和 AppSec USA。](https://twitter.com/jimmesta) [](https://twitter.com/jimmesta)

容器正在改变软件开发。作为 CI/CD 的新基础，容器为您提供了一种快速、灵活的方式来部署应用程序、API 和微服务，以及数字化成功所依赖的可扩展性和性能。但是，容器和容器编排工具(如 Kubernetes)也是黑客的热门目标——如果它们得不到有效保护，它们会将您的整个环境置于风险之中。在本文中，我们将讨论容器栈每一层的安全最佳实践。

理解容器的安全含义很重要。作为一个依赖于共享内核的应用层构造，容器的启动速度比完整的虚拟机快得多。另一方面，容器的配置也比 VM 灵活得多，可以做从安装卷和目录到禁用安全特性的任何事情。在“容器突破”场景中，当容器隔离机制被绕过，并且在主机上获得了额外的权限时，容器甚至可以在黑客的控制下以 root 用户身份运行，这时您就真的有麻烦了。

这里有几件事你可以做，让坏人远离你的容器。

## 第 0 层——内核

Kubernetes 是一个开源平台，旨在自动化容器的部署、扩展和编排，正确配置它可以帮助您增强安全性。在内核级别，您可以:

*   检查允许的系统调用，并删除任何不必要或不需要的系统调用
*   使用类似于 [gVisor](https://gvisor.dev/) 或 [Kata 容器](https://katacontainers.io/)的容器沙箱来进一步限制系统调用
*   验证您的内核版本已打补丁，并且不包含现有漏洞

## 第 1 层–集装箱

### 静止

静态容器安全性关注于您将用来构建运行容器的 Docker 映像。首先，通过删除不必要的组件、包和网络工具来减少容器的攻击面——越精简越好。考虑使用仅包含您的应用程序及其运行时依赖项的[发行版](https://github.com/GoogleContainerTools/distroless)映像。

接下来，确保只从已知良好的来源提取图像，并扫描它们的漏洞和错误配置。在整个 CI/CD 管道和构建过程中检查它们的完整性，并在运行之前验证和批准它们，以确保黑客没有安装任何后门。

### 运行时间

一旦您的映像打包完毕，就该进行调试了。临时容器可以让你交互式地调试运行中的容器，包括无发行版或其他没有自己调试工具的轻量级映像。注意异常和可疑的系统级事件，它们可能是危害的标志，例如产生了一个意外的子进程、在容器中运行了一个 shell，或者意外读取了一个敏感文件。[Cloud Native Computing Foundation](https://cncf.io/?utm_content=inline-mention)的 [Falco 项目](https://falco.org/docs/)开源运行时安全工具，以及已经创建的许多 [Falco 规则文件](https://github.com/falcosecurity/falco/blob/master/rules/falco_rules.yaml)，对此非常有用。

## 第 2 层–工作负载(Pod)

Kubernetes 内部的部署单元 pod 是可以共享公共安全定义和安全敏感配置的容器的集合。 [Pod 安全上下文](https://kubernetes.io/docs/tasks/configure-pod-container/security-context/)指定给定 Pod 的权限和访问控制设置，例如:

*   舱内的特许集装箱
*   进程和卷的组和用户 id
*   粒度 Linux 功能(删除或添加),如 Sys.time
*   沙盒和强制访问控制(seccomp、AppArmor、SELinux)
*   文件系统权限
*   权限提升计划权限

为了加强 pod 级别的基本防御，您可以实施严格的 Pod 安全策略，以防止危险的工作负载在集群中运行。为了更加灵活和精确地控制 pod 安全性，可以考虑使用[开放策略代理(OPA)项目](https://github.com/open-policy-agent/gatekeeper)实现一个[开放策略代理(OPA)](https://www.openpolicyagent.org/) 。

## 第 3 层–网络

### 妥协的工作负载

默认情况下，所有的 pod 可以不受限制地与集群中的所有其他 pod 通信，从攻击者的角度来看，这非常有趣。如果工作负载受到威胁，攻击者可能会尝试探测网络，看看他们还能访问什么。Kubernetes API 也可以从 pod 内部访问，提供了另一个丰富的目标。如果您看到来自集群中一个容器的流量到达一个以前没有接触过的外部 IP，这不是一个好现象。

严格的网络控制是容器强化的一个关键部分——从容器到容器、从集群到集群、从外向内和从内向外。使用内置的网络策略来隔离工作负载通信，并构建精细的规则集。考虑实现一个服务网格来控制工作负载之间的流量以及入口/出口，例如通过定义名称空间到名称空间的流量。

### 应用层(L7)攻击–服务器端请求伪造(SSRF)

我们最近听到了很多关于 SSRF 袭击的消息，这并不奇怪。对于 API 与其他 API 对话的云原生环境，SSRF 可能特别难以停止；客户提供的 webhooks 尤其臭名昭著。一旦发现目标，SSRF 可用于提升权限和扫描本地 Kubernetes 网络和组件；命中云元数据端点；转储 Kubernetes metrics 端点上的数据，以了解关于环境的有价值的信息——并有可能完全接管它。

### 应用层(L7)攻击–远程代码执行(RCE)

RCE 在云原生环境中也非常危险，它可以在容器中运行系统级命令来抓取文件，访问 Kubernetes API，运行图像处理工具，并危及整个机器的安全。

### 应用层(L7)防御

保护的第一条规则是坚持安全的编码和架构实践——这可以减轻您的大部分风险。除此之外，您还可以沿着两条轴线部署网络防御:南北向，监控和阻止恶意的外部流量进入您的应用程序和 APIs 和东-西，以监控从容器到容器、从集群到集群、从云到云的流量，以确保您不会成为被入侵的 pod 的受害者。

## 第 4 层–节点

节点级安全性没有网络那么激动人心，但也同样重要。为了防止虚拟机或其他节点上的容器突破，请限制对节点和控制平面的外部管理访问，并注意打开的端口和服务。保持您的基本操作系统最小化，并使用 [CIS 基准](https://www.cisecurity.org/cis-benchmarks/)强化它们。最后，确保像其他虚拟机一样扫描和修补您的节点。

## 第 5 层–集群组件

Kubernetes 集群中有各种各样的事情在进行，并且没有一体化的工具或策略来保护它。总体而言，您应该关注:

*   **API 服务器**——检查您的访问控制和认证机制，并对您的动态 webhooks、Pod 安全策略和 Kubernetes API 的公共网络访问进行额外的安全检查；
*   **访问控制**——使用基于角色的访问控制(RBAC)来对您的 API 服务器和 Kubernetes 秘密实施最小特权原则
*   **服务帐户令牌**–为了防止未经授权的访问，限制对服务帐户以及存储服务帐户令牌的任何机密的权限
*   **审计记录**–确保该功能已启用
*   **第三方组件**–小心您将什么带入您的集群，以便您知道什么在那里运行以及为什么运行
*   **Kubernetes 版本**–Kubernetes 和任何其他系统一样可能存在漏洞，必须及时更新和修补
*   **kube lets 错误配置**——kube lets 负责容器编排和与容器运行时的交互，可能会被滥用和攻击，试图提升权限

Kubernetes 的安全性似乎令人望而生畏，但是通过为您的堆栈的每一层制定最佳实践，您可以将您的容器带到与您的环境的其余部分相同的高保护级别——因此您可以享受快速、敏捷开发的好处，而不会将您的环境或业务置于风险之中。

*有关 Kubernetes 安全性的深入讨论，请查看本次[网络研讨会](https://info.signalsciences.com/defend-core-kubernetes-security-web-ty?submissionGuid=f6da7755-9fe0-471a-aee8-c84e7959abc2)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>