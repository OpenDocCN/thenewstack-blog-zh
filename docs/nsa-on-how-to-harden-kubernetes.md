# 美国国家安全局如何强化 Kubernetes

> 原文：<https://thenewstack.io/nsa-on-how-to-harden-kubernetes/>

国家安全局，是的，国家安全局有两项工作。你从我的间谍电影和类似的电影中知道的一个是窃听美国以外的通信。然而，他们工作的另一半不太为人所知。他们的另一项工作是保护通信免受其他潜在的窥探。所以，就是 NSA 做出了最初的[安全 Linux(SELinux)](https://www.redhat.com/en/topics/linux/what-is-selinux)；撰写了关于如何[保护视频会议、文本聊天和协作工具](https://www.zdnet.com/article/heres-the-nsas-guide-for-choosing-a-safe-text-chat-and-video-conferencing-service/)的指南；现在解释如何[强化 Kubernetes 对抗攻击者](https://media.defense.gov/2021/Aug/03/2002820425/-1/-1/0/CTR_Kubernetes_Hardening_Guidance_1.1_20220315.PDF)。

这不是 NSA 第一次帮助我们保护 Kubernetes。他们新的 [Kubernetes 强化指南](https://media.defense.gov/2021/Aug/03/2002820425/-1/-1/0/CTR_Kubernetes_Hardening_Guidance_1.1_20220315.PDF)已经更新，现在更有用了。例如， [NCC 组](https://www.nccgroup.com/us/)发现第一个版本关于 [Kubernetes 认证的信息“很大程度上是不正确的](https://research.nccgroup.com/2021/09/09/nsa-cisa-kubernetes-security-guidance-a-critical-review/)”,因为它声称 Kubernetes 在默认情况下不提供认证方法。然而，NCC 集团指出，Kubernetes 本身支持令牌和证书认证。

这些改进很重要。我们需要尽可能多的帮助来保护库伯内特。根据[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)的 [2021 年云原生调查](https://www.cncf.io/reports/cncf-annual-survey-2021/)，96%的组织现在使用或评估 Kubernetes。事实上，全球已经有 560 万开发者在使用 Kubernetes。在所有后端开发人员中，这一比例高达 31%。

## 正确保护 Kubernetes

在这庞大的数字中，你认为有多少人在妥善保护库伯内特？根据对 Kubernetes 开发人员在工作中的交谈和观察，我的猜测是，太少了。正如[红帽](https://www.openshift.com/try?utm_content=inline-mention)最近指出的，[人为错误是导致 Kubernetes 安全事故](https://thenewstack.io/red-hat-human-error-a-leading-cause-of-kubernetes-security-mishaps/)的主要原因。事实上，94%的被调查者承认他们在过去 12 个月中经历过 Kubernetes 和 container environments 安全事件。

这是一个现实问题。黑客和我们一样清楚，我们现在生活在一个所有 IT 工作都在尽可能快地转向容器和 Kubernetes 的世界。正如 NSA 指出的，这意味着 Kubernetes 集群是数据窃取、计算能力窃取和拒绝服务攻击的主要目标。让我们不要忘记，在[网络战的时代，Kubernetes 是一个有希望的目标。](https://thenewstack.io/kubernetes-is-a-high-value-cyberwar-target/)

目前，数据盗窃是头号目标。但越来越多的网络参与者试图劫持 Kubernetes 集群进行加密货币开采。简而言之，有很多人在你的 Kubernetes 装置后，你应该尽你所能进行防御。

具体而言，国家安全局建议:

*   扫描容器和 pod 以查找漏洞或错误配置。
*   以尽可能低的权限运行容器和单元。
*   使用网络隔离来控制危害可能造成的损害程度。
*   使用防火墙来限制不必要的网络连接，并使用加密来保护机密性。
*   使用强身份验证和授权来限制用户和管理员的访问，并限制攻击面。
*   捕获和监控审计日志，以便管理员能够对潜在的恶意活动发出警报。
*   定期检查所有 Kubernetes 设置，并使用漏洞扫描来确保适当考虑风险并应用安全补丁。

这些都很好，但也很普通。我希望无论你运行的是一个简单的 Linux、Apache、MySQL、PHP/Perl/Python (LAMP)服务器还是一个数千个节点的复杂 Kubernetes 集群，你都已经做到了。

## Kubernetes 一点都不简单

当然，在 Kubernetes 环境中打补丁是困难的。除了 Kubernetes 本身之外，许多其他程序也在它上面运行，并在其中完成实际工作。运行 Kubernetes 并不简单，所以可悲的是，它也很难得到保护。

例如，我们都知道不应该以 root 用户身份运行应用程序，但是默认情况下，许多 Kubernetes 容器服务以 root 用户身份运行，应用程序以 root 用户身份在其中执行，即使它们不需要特权执行。尽管如此，NSA 警告我们，开发人员构建以 root 身份执行的容器应用程序的情况太多了。为什么？因为太简单了。但这也很危险。

当然，Kubernetes 也有自己的安全问题。例如，NSA 在本指南中的合作伙伴[网络安全和基础设施安全局(CISA)](https://www.cisa.gov/) ，最近警告了一个严重的问题，CVSS 严重度评分高达 8.8， [Kubernetes 胶囊运营商反向代理权限提升漏洞，CVE-2022-23652](https://www.cisa.gov/uscert/ncas/bulletins/sb22-059) 。

[保护库伯内特可能是一份全职工作。](https://thenewstack.io/6-kubernetes-security-best-practices/)NSA 提到有第三方安全程序可以提供帮助。当然，这些也有其自身的安全问题。另一方面，考虑到 Kubernetes 的复杂性，你可以从诸如 [Calico Cloud](https://thenewstack.io/tigera-tightens-cloud-native-container-security/) 、 [JetStack Secure](https://thenewstack.io/jetstack-secure-promises-to-ease-kubernetes-tls-security/) 和 [Falco](https://thenewstack.io/falco-lock-down-kubernetes-from-the-kernel-on-up/) 和[等程序中获得的任何帮助都是受欢迎的，比如零信任](https://thenewstack.io/securing-access-to-kubernetes-environments-with-zero-trust/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>