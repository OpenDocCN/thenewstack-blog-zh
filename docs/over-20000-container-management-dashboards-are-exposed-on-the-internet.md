# 超过 20，000 个集装箱管理仪表板在互联网上公开

> 原文：<https://thenewstack.io/over-20000-container-management-dashboards-are-exposed-on-the-internet/>

尽管非常不鼓励将任何类型的管理仪表板直接暴露在互联网上，但仍有许多用户继续忽视这一建议，基础设施管理员似乎也不例外。

[云安全公司 Lacework 最近的一项研究](https://info.lacework.com/hubfs/Containers%20At-Risk_%20A%20Review%20of%2021,000%20Cloud%20Environments.pdf)发现了超过 22，000 个公开的容器编排和 API 管理系统，其中约 300 个可以在没有任何凭据的情况下访问，并给予攻击者对容器的完全控制或远程代码执行能力。

Kubernetes 仪表板占公开界面的 75%以上，其次是 Docker Swarm (Portainer 和 Swarmpit)占 20%，Swagger API UI 占 3%，Mesos Marathon 和 Red Hat OpenShift 各占不到 1%。

绝大多数被暴露的系统(超过 95%)托管在亚马逊 AWS 上，55%位于美国的 AWS 地区。

“在研究过程中，我们注意到数量惊人的系统没有任何认证，”Lacework 的研究人员在他们的报告中说。“有些显然正在筹备之中，但有些已经全面投产。在完全访问权限可用的情况下，用户可以执行添加和部署自己的应用程序、删除基础架构、更改凭据等操作，还可能泄露数据。”

这甚至可能发生在拥有大量 IT 预算的大公司身上。今年早些时候，来自 [RedLock](https://redlock.io/) 的研究人员发现了数百个可公开访问的 Kubernetes 管理控制台，其中一些属于英国跨国保险公司 Aviva 金雅拓，全球最大的 SIM 卡制造商和汽车制造商特斯拉。他们中的许多人被滥用于在这些公司的云计算实例中运行加密货币挖掘软件。

虽然 Lacework 发现的 22，000 个管理接口中的绝大多数确实需要身份验证，但它们直接暴露在互联网上是不必要的，并使它们成为各种攻击的目标，包括凭据填充(使用在其他违规中泄露的凭据)和更常见的基于字典的密码猜测尝试。

“此外，仅仅通过公开，你就有可能泄露信息，从而给攻击者提供关于他们目标的敏感信息，”Lacework 研究人员说。在大多数发现的系统中，即使没有访问权限，公司名称也可以从证书和主机名中获得

有意保持容器管理仪表板公开意味着您还需要致力于跟踪所有可能影响软件堆栈的漏洞或错误，并在它们可用时尽快为它们部署补丁。

过去，攻击者需要数周时间才能开始利用新公布的漏洞，而现在，他们在漏洞公开后的几天甚至几小时内就可以开始利用。还存在零日漏洞利用的可能性，即针对还没有补丁的漏洞的漏洞利用，这一点您需要加以考虑。

“在有意向外界开放管理用户界面的情况下，目前还不清楚使用情形是什么，这些公司的管理员和安全操作员应该意识到，他们的暴露是透明的，这对他们的数据和云基础架构构成了巨大的潜在风险。”

Kubernetes 不断增加新的安全功能，最近的版本提供了 SSL 通信和认证。应该打开这些功能，如果需要远程管理，可以通过 VPN 连接和多因素身份验证来增强这些功能。

有关加强 Kubernetes 抵御各种攻击的更多深入信息，您可以在 kube con+CloudNativeCon North America 2017 上[观看独立顾问](https://www.youtube.com/watch?v=vTgQLzeBfRU) [Brad Geesaman](https://www.linkedin.com/in/bradgeesaman/) 的演示。

[https://www.youtube.com/embed/vTgQLzeBfRU?feature=oembed](https://www.youtube.com/embed/vTgQLzeBfRU?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>