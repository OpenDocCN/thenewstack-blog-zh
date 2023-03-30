# Kubernetes 部署中的容器安全性考虑

> 原文：<https://thenewstack.io/container-security-considerations-kubernetes-deployment/>

在深入 Kubernetes 的安全方面之前，我们必须首先了解容器基础设施本身的相关安全问题。(参见我们之前的文章，了解适用于所有 Kubernetes 部署的[威胁模型](https://thenewstack.io/4-threat-models-for-kubernetes-deployment-security/)和[Kubernetes 安全的四大原则](https://thenewstack.io/4-major-tenets-kubernetes-security/)。)

Kubernetes 支持 Docker 容器，并且实验性地支持 [rkt 容器格式](https://coreos.com/rkt/docs/latest/)。在这个博客系列的剩余部分中，所有关于容器的讨论都集中在 Docker 容器上。

## 节点安全性

 [王晨曦博士

王晨曦博士是网络安全战略咨询公司简·邦德项目的创始人。网络安全行业知名战略家、演说家、作家。Wang 博士还担任 OWASP 基金会董事会副主席，ClearSky security 和 630 Cyber 的投资顾问，以及各种安全初创公司和 IT Security Planet 的战略顾问。此前，陈曦是 Twistlock 的首席战略官，负责将 Twistlock 的品牌和业务从零发展到细分市场的领导者。](https://www.paloaltonetworks.com/prisma/cloud) 

为了以安全的方式运行容器，每个 Linux 节点都必须正确配置和加固。Docker 的互联网安全中心(CIS) [基准](https://www.cisecurity.org/cis-benchmarks/)和 Kubernetes 的相应 CIS 基准包含许多运营团队应该遵循的强化准则。

例如，推荐的做法之一是启用内置的 Linux 安全措施，如 [SELinux](http://man7.org/linux/man-pages/man8/selinux.8.html) 和 [Seccomp 概要文件](http://man7.org/linux/man-pages/man2/seccomp.2.html)。SELinux 是一种内核级功能，它控制对文件和网络资源的访问，而 Seccomp 配置文件限制应用程序可以发出的系统调用集。总之，这些功能允许对节点上运行的工作负载进行一定程度的细粒度控制。

通常，节点安全性的主要考虑因素包括:

*   使用 TLS 客户端证书保护节点通信，以确保所有关键 API 访问点通过端到端 TLS 得到保护。
*   启用相关的内核级安全控制，如 SELinux 或 Seccomp。这些功能有助于限制节点上的攻击面，从而更好地控制整个系统的安全性。
*   限制对 Kubernetes 节点的直接访问，例如安全外壳(SSH)访问:强制通过 Kubernetes 对节点的所有访问确保了适当的访问控制和日志记录。这有助于降低未经授权访问主机资源的风险。
*   遵循行业最佳实践，如 CIS Docker 基准，正确配置和强化运行容器的 Linux 节点。

### 集装箱图像安全

容器映像安全最重要的方面是管理漏洞。因为运行有漏洞的容器会使您的系统暴露于攻击和危害之下，所以您必须主动管理系统中使用的映像，以发现并消除已知的漏洞。

[cyclone slider id = " kubernetes-series-book-2-赞助商"]

许多商业和开源软件包可以执行容器图像扫描，以发现已知的[常见漏洞和暴露](https://cve.mitre.org/) (CVE)标识符。诀窍是不要停留在扫描上。相反，扫描功能应该与运行时实施和补救功能相集成。

对于运行时实施，考虑一个仅部署那些通过漏洞扫描的映像和那些遵守组织的强化策略的映像的流程。Kubernetes 提供了执行这种强制策略的机制。

要进行补救，请确保将漏洞扫描和安全评估功能与组织的持续集成/持续部署(CI/CD)渠道相集成。通过这种方式，扫描结果将直接反馈给管道，从而在部署之前启动补救工作流。反过来，这应该与 Kubernetes 的滚动更新功能相集成，确保易受攻击的容器离线，并替换为没有已知缺陷的新构建的映像。

### 集装箱登记管理

容器注册表是图像的来源。您必须管理您的组织可以使用哪些注册表来获取映像，因为从未知注册表下载映像会导致易受攻击和危险软件的扩散。

使用私人注册和批准的图像；也就是说，只有经过扫描和审核的图像才能被推送到您的私人注册表中。如果必须使用公共注册表，请在部署之前扫描映像。如果安全扫描过程未能清除映像，您肯定会因此导致部署失败。这是确保集装箱环境卫生的唯一方法。

在牢牢掌握了威胁模型、Kubernetes 安全性的四个主要原则以及现在的容器安全性考虑因素之后，您就可以更深入地探索 Kubernetes 部署安全性的四个主要原则了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>