# Kubernetes:对主要攻击的检查

> 原文：<https://thenewstack.io/kubernetes-an-examination-of-major-attacks/>

[](https://www.linkedin.com/in/manojahuje/)

[Manoj AHU je](https://www.linkedin.com/in/manojahuje/)

[Manoj 是 Tigera 的高级威胁情报研究工程师，他密切关注云安全行业的趋势，特别关注针对 Kubernetes 环境的威胁。Manoj 在漏洞分析、漏洞开发和恶意软件逆向工程方面拥有丰富的经验。](https://www.linkedin.com/in/manojahuje/)

[](https://www.linkedin.com/in/manojahuje/)[](https://www.linkedin.com/in/manojahuje/)

在一场永无止境的猫捉老鼠游戏中，威胁参与者正在利用、控制和维护受损云基础架构中的持续访问。虽然云从业者拥有一流的知识、支持和安全实践，但从统计数据来看，不可能为全球所有云实例提供一个通用的安全态势。攻击者知道这一点并加以利用。通过应用进化的策略、技术和程序(TTP)，攻击者正在利用边缘案例。因此，像 [Capital One](https://www.theverge.com/2019/7/31/20748886/capital-one-breach-hack-thompson-security-data) 、 [Jenkins](https://www.csoonline.com/article/3256314/hackers-exploit-jenkins-servers-make-3-million-by-mining-monero.html) 、 [Docker](https://www.eweek.com/security/docker-hub-breached-impacting-190-000-accounts) 和许多其他组织都经历了引人注目的违规事件。

TTP 被定义为“与特定威胁行为者或威胁行为者群体相关的活动模式或方法”TTP 描述了威胁参与者(坏人)如何组织、执行和管理他们的操作攻击。对 TTP 的分析可以提供威胁参与者如何执行攻击的描述，从而有利于安全操作。Kubernetes 对 TTPs 并不免疫。让我们来看看 Kubernetes 生态系统中最近的一些案例。

## 案例 1:错误配置的 Docker

如果您是一名攻击者，正在寻找错误配置的 Docker 实例来利用，那么在互联网上探测开放端口 2375、2376、2377、4243 和 4244 就很容易了。易受攻击的实例也可以使用像 Shodan 这样的搜索引擎来定位。已经观察到像 [TeamTNT](https://www.tigera.io/blog/teamtnt-latest-ttps-targeting-kubernetes/) 这样的有组织的威胁参与者使用合法的 Kubernetes 监控工具，如 Weave Scope，来后门这些 Docker 实例。

此外，Docker 配置缺陷正被像[塞特斯](https://unit42.paloaltonetworks.com/cetus-cryptojacking-worm/)和 [Graboid](https://resources.infosecinstitute.com/malware-overview-graboid/) 这样的加密劫持恶意软件所利用，利用 CI/CD 工具的精心策划的活动也是一种威胁。易受攻击的 Docker 实例也成为 DDoS 恶意软件的目标，如 [XORDDoS 和 Kaiji](https://www.trendmicro.com/en_us/research/20/f/xorddos-kaiji-botnet-malware-variants-target-exposed-docker-servers.html) ，它们使用这些资源来增加其 DDoS 容量。

对于使用 Docker 的组织来说，部署像 AWS 安全组这样的云提供商防火墙作为防御措施是必不可少的。考虑投资可观察性工具来监控运行的容器、CPU 利用率和网络活动。安全团队还可以受益于将威胁情报嵌入云中并监控风险阈值。

## 案例 2:恶意的 Docker 图片

公共图像存储库已经成为分发伪装成定制配置的恶意图像的简单工具。说明这种攻击媒介范围的一个例子是 Docker Hub 的[事件，其中一个恶意图像在被删除之前被提取了 500 万次。这强调了检查您的基本图像源的需要，无论您是创建自己的图像还是使用来自公共存储库的图像。像](https://arstechnica.com/information-technology/2018/06/backdoored-images-downloaded-5-million-times-finally-removed-from-docker-hub/) [dive、](https://github.com/wagoodman/dive)这样的取证分析工具以及 Docker 本身，都可以帮助你检查图像历史。

## 案例#3:无意的集群错误配置

云提供商代表我们配置、修补和管理 Kubernetes 安全性，这一点得到了相当大的信任。然而，有时事情可能会被遗漏。即使是最受信任的云服务也容易受到无意中启用权限提升和促进集群接管的配置的影响。

Christophe Tafani-Dereeper 的一篇博客文章展示了如果没有明确阻止对实例元数据服务(IMDS)的访问，损害集群中的 pod 可能会对 AWS 帐户中的资源造成的灾难性后果。不幸的作者从一个受损的 pod 到达元数据服务以检索身份和访问管理(IAM)角色凭证。不幸的是，默认情况下，IAM 角色拥有太多的权限，导致权限提升。事后看来，这本来可以通过对托管环境的持续审核和对安全漏洞的早期检测来避免。

## Kubernetes 对 Kubernetes

有时候，Kubernetes 可能是它自己最大的敌人。像 kubelet、controller-manager 和 etcd 这样的组件可以被利用，目的是在集群中获得更高级别的特权和持久性。容器内的远程代码执行可以使用 [kubelet 的未认证、未记录的 API](https://securityboulevard.com/2020/08/using-kubelet-client-to-attack-the-kubernetes-cluster/) 来完成。Kubernetes 的威胁演员 TeamTNT 被视为在野外利用这一缺陷。犀牛安全实验室展示了一个[攻击者如何以一个假的工人节点](https://rhinosecuritylabs.com/cloud-security/kubelet-tls-bootstrap-privilege-escalation/)加入。

以下是 Kubernetes 可以用来对付自己的一些其他方法:

*   第二个 kubelet 可以在一个节点上运行，这样同一个节点将成为两个不同集群的一部分，其中一个集群将由攻击者控制。
*   **Privileged pods** 可以通过滥用 CGROUPs 之类的 Linux 功能来逃避容器并提供对主机的根访问。
*   如果有一个**支持主机网络的 pod** 存在，它可以攻击 Kubernetes 上的底层网络。
*   **恶意的 webhook** 可以拦截和修改对 Kubernetes API 的请求。这在生产集群中是难以察觉的。
*   **pod 网络**可用于开发 Kubernetes 集群中的 VXLAN 和 IPIP 网络。
*   **使用不安全的根挂载**，可以在 pod 内部访问主机文件系统。
*   **Kubernetes cron jobs/jobs**可用于集群后门。
*   如果配置错误，Pod 默认令牌可用于获取特权资源。
*   Kubernetes ExternalIPs 可用于中间人攻击。

## 摘要

需要时刻保持警惕，以确保锁定云基础架构，并确保 DevSecOps 团队拥有合适的工作工具。云增加了一个新的维度，增加了组织的攻击面，为攻击者创造了潜在的机会。当云被纳入考虑范围时，即使是典型的漏洞也可能成为更大的威胁。为了有效应对这种新的安全模式，云安全团队必须了解每种常见漏洞和暴露(CVE)的影响，并准备好在检测到漏洞和暴露时采取缓解措施。

威胁参与者正在使用进化的 TTP 来利用、控制和维护受威胁的云基础设施中的持久访问。异常行为的早期检测至关重要，可以大大加快检测、调查和缓解威胁的速度。利用数据科学和机器学习技术的最新进展，组织必须增强其云观察能力，定期审计其环境，并在最新的安全补丁可用时应用它们。

想了解更多关于 Kubernetes 的网络威胁保护战略和战术？阅读[最新 eBPF 漏洞，它对 Kubernetes 的影响，以及如何缓解它](https://www.tigera.io/blog/cve-2021-31440-kubernetes-container-escape-using-ebpf/)，并查看这个针对 Kubernetes 安全的[实践研讨会的重播。](https://www.tigera.io/event/hands-on-workshop-for-kubernetes-security/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>