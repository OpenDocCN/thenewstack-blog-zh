# 国家安全局可以帮助保护你的 Kubernetes 集群

> 原文：<https://thenewstack.io/the-nsa-can-help-you-secure-your-kubernetes-clusters/>

是的，[国家安全局(NSA)](https://www.nsa.gov/) ，又名“没有这样的机构”，又名世界密码破译大师，也可以帮助你保护你的 [Kubernetes 集群](https://thenewstack.io/what-does-it-take-to-manage-hundreds-of-kubernetes-clusters/)。不，这不是玩笑。它的“ [Kubernetes 硬化指南](https://media.defense.gov/2021/Aug/03/2002820425/-1/-1/1/CTR_KUBERNETES%20HARDENING%20GUIDANCE.PDF)”不仅能帮到你，而且非常好。

这并不像一开始听起来那么令人惊讶。除了大家从电视和电影中知道的密码破译方面，它的另一个任务是通过保护美国的安全来帮助保护国家安全。除了为中情局之类的机构编写代码之外，它还发布文件，告诉你——是的，就是你——如何更好地保护你的安全和隐私。这包括指南和一系列最常见的漏洞[威胁者用来在服务器上植入网络外壳](https://www.zdnet.com/article/nsa-shares-list-of-vulnerabilities-commonly-exploited-to-plant-web-shells/)以及[如何选择最安全的视频会议和协作系统](https://media.defense.gov/2020/Aug/14/2002477667/-1/-1/0/CSI_%20SELECTING_AND_USING_COLLABORATION_SERVICES_SECURELY_FULL_20200814.PDF)。

正如你们许多人所知，美国国家安全局创造了 SELinux。这是 Linux 可选的[强制访问控制](https://www.nsa.gov/Portals/70/images/resources/everyone/digital-media-center/publications/research-papers/flexible-support-for-security-policies-into-linux-jun2001-report.pdf) (MAC)架构。如果你真的想保证 Linux 的安全，SELinux 是你的首选。

因此，毫不奇怪，Kubernetes 硬化指南非常有用。坦白地说，我们需要一个简单明了的 Kubernetes 安全指南。正如 [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 在其 2021 年 7 月 [*Kubernetes 采用、安全和市场趋势报告*](https://www.redhat.com/en/resources/kubernetes-adoption-security-market-trends-2021-overview) 中所报告的那样，“55%的受访者因为安全问题而不得不推迟应用部署。”

这太高了。那么你能做什么呢？根据美国国家安全局的说法，Kubernetes 集群威胁主要来自三个来源:

*   供应链风险，带来多层次的危险。这些范围从容器或应用程序级别到底层基础设施。
*   **恶意威胁参与者**可以利用暴露的架构 API。这些包括控制平面、工作节点和容器化的应用程序。
*   **内部威胁**来自拥有特权或特殊知识的参与者，包括管理员、用户和云服务或基础设施提供商。

那么，你能做些什么呢？国家安全局有七条建议:

*   扫描容器和 pod 以查找漏洞或错误配置。
*   以尽可能低的权限运行容器和单元。
*   使用网络隔离来控制危害可能造成的损害程度。
*   使用防火墙来限制不必要的网络连接和加密以保护机密性。
*   使用强身份验证和授权来限制用户和管理员的访问，并限制攻击面。
*   使用日志审核，以便管理员可以监控活动并对潜在的恶意活动发出警报。
*   定期检查所有 Kubernetes 设置，并使用漏洞扫描来帮助确保适当考虑风险，并应用安全补丁。

然后，该报告对每个领域进行了深入研究。例如，为了保护容器，他们建议:

*   使用构建的容器作为非根用户运行应用程序。
*   只要有可能，运行具有不可变文件系统的容器
*   扫描容器映像，查找可能的漏洞或错误配置
*   使用 Pod 安全策略来实施最低安全级别。具体来说:防止特权容器发起；拒绝经常被利用的容器功能，如 hostPID、hostIPC、hostNetwork 和 allowedHostPath。拒绝作为根用户执行或允许提升到根用户的容器；以及使用 SELinux、 [AppArmor](https://apparmor.net/) 和 [seccomp](https://man7.org/linux/man-pages/man2/seccomp.2.html) 等安全服务来加固应用程序以防被利用。

除了一般指导之外，该指南还包括代码示例，使您能够更好地保护您的群集。这些策略包括 Pod 安全策略、网络策略和资源配额策略，以限制命名空间内的聚合资源使用。

将所有这些放在一起，我认为这是迄今为止我所见过的对 Kubernetes 安全性的最好介绍。它真的很好，我怎么推荐都不为过。如果您只是阅读本文档并将其策略付诸实践，您的集群可能会比现在安全一个数量级。哦，我说过这是免费的吗？下载、阅读并实现它。你会很高兴你做了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>