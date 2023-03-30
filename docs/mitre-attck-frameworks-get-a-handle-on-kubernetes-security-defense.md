# 米特 ATT 和 CK 框架处理 Kubernetes 的安全防御

> 原文：<https://thenewstack.io/mitre-attck-frameworks-get-a-handle-on-kubernetes-security-defense/>

我们都知道保护 Kubernetes 是一件痛苦的事。我们的一个问题是，虽然我们知道如何保护这个或那个组件，但要防范对容器和 Kubernetes 的所有可能的攻击真的很难。这就是为什么美国政府致力于安全的非营利公司 [Mitre](https://www.mitre.org/) 正在为集装箱和 Kubernetes 建立一个 [ATT & CK](https://attack.mitre.org/) 知识库。

米特 ATT 和 CKs 是全球可访问的基于观察真实世界攻击的对手战术和技术知识库。ATT 和 CK 知识库是在私营部门、政府以及网络安全产品和服务社区开发特定威胁模型和方法的基础。

最初，Mitre 和它的合作伙伴，花旗集团、摩根大通和微软，打算着手建立一个 ATT & CK 的容器知识库。然而，他们很快意识到，他们需要[在 ATT & CK](https://medium.com/mitre-engenuity/att-ck-for-containers-now-available-4c2359654bf1) 的单个[容器平台中涵盖编排级(例如 Kubernetes)和容器级(例如 Docker)对手行为](https://attack.mitre.org/matrices/enterprise/containers/)。

在创建这个知识库的过程中，安全研究人员发现，尽管对容器和 Kubernetes 集群的绝大多数攻击都与加密挖掘有关。但是，有证据表明，对手也将容器用于更“传统”的目的，如渗透和收集敏感数据。更糟糕的是，这类攻击被低估了。因此，如果您看到您的集群中发生了一些奇怪的事情，并且您并不太担心，因为您没有在您的容器中看到诸如 Monero[Cryptojacking](https://thenewstack.io/untrusted-docker-hub-images-found-with-monero-cryptojacking-malware/)[恶意软件之类的](https://thenewstack.io/untrusted-docker-hub-images-found-with-monero-cryptojacking-malware/)[加密挖掘攻击，那么请三思。你可能仍然受到攻击。](https://thenewstack.io/untrusted-docker-hub-images-found-with-monero-cryptojacking-malware/)

在构建知识库的同时，Mitre 团队还添加了其他类型的攻击。其中包括利用软件漏洞来帮助[逃到底层主机](https://attack.mitre.org/techniques/T1611/)的对手；与容器部署相关的[安全工具被攻击者禁用](https://attack.mitre.org/techniques/T1562/001/)的情况；以及[网络安全攻击者在 Kubernetes 网络](https://attack.mitre.org/techniques/T1046/)内扫描。

至于恶意软件，MITRE 已经将针对特定容器的恶意软件程序——[kin sing](https://attack.mitre.org/software/S0599/)、 [Doki](https://attack.mitre.org/software/S0600/) 和[hilde gard](https://attack.mitre.org/software/S0601/)——植入 ATT & CK。他们希望这将有助于系统管理员和安全负责人更好地了解容器矩阵技术的抽象层次，并与 Linux 和基础设施即服务(IaaS)进行比较。

想到抽象，您可能想知道 Kubernetes 和容器安全威胁的这种高级抽象对 Kubernetes 开发人员和该领域的管理员有什么好处。在思科公司从事新技术和云应用安全工作的 Ariel Shuper 解释说，虽然“通用的 Kubernetes 风险评估框架是基于 Kubernetes 公司广受欢迎的 CIS 基准。该框架由一组全面的测试组成，涵盖了所有 Kubernetes 元素的配置安全性最佳实践。"

Shuper 继续说，这很好，但是[它没有解决“不是基于安全错误配置的攻击媒介”](https://www.ciscotechblog.com/blog/mitre-security-framework-containers-kubernetes/)毕竟，“恶意攻击可以从安全误配置之外的多种因素开始。但是还有其他推动新框架的操作要素。受欢迎的托管 Kubernetes 服务，如[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)、EKS、Azure AKS 或谷歌的 GKE，都不提供对 CIS 基准测试元素的访问，因此很难评估这些服务的安全状态。"

因此，舒伯认为 ATT&CK 矩阵作为一种新的风险评估框架非常有效，因为它验证了所有其他攻击方法、步骤和阶段。此外，ATT&CK 矩阵“仅基于真实攻击中使用的战术和技术，使其非常具体。”

此外，正如 Shuper 非常正确地指出的，“并不是所有的开发人员都完全意识到他们正在使用的就是这个！这一切都使得 Kubernetes 很难管理安全性。”你觉得呢？我见过太多的 Kubernetes 专家，他们什么也不是。

Shuper 总结道:“理解 Kubernetes 的安全性始于理解 Kubernetes 是如何被攻破的。因此，安全团队需要全面了解保护您组织的 Kubernetes 集群安全所涉及的每个角色。这就是高水平的米特 ATT&CK 安全知识库的用武之地。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>