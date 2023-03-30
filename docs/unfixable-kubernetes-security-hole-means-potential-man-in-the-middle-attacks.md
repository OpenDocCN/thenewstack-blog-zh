# 不可修复的 Kubernetes 安全漏洞意味着潜在的中间人攻击

> 原文：<https://thenewstack.io/unfixable-kubernetes-security-hole-means-potential-man-in-the-middle-attacks/>

嗯，它最终还是要发生的。时不时地——我看着你[英特尔和你的融合安全管理引擎(CSME)一团糟](https://techxplore.com/news/2020-03-unfixable-flaw-intel-chipset.html#:~:text=The%20bad%20news%3A%20A%20security,install%20malware%20such%20as%20keyloggers.)——一个无法修复的安全漏洞出现了。现在，轮到[库伯内特](https://kubernetes.io/)了。苹果软件工程师 Tim Allclair 也帮助监督 Kubernetes 的安全，他宣布,[发现了一个影响多租户集群的安全问题。](https://groups.google.com/g/kubernetes-announce/c/GPpZzVtGwiI/m/mN2nRETUAgAJ)如果潜在的攻击者已经可以创建或编辑服务和 pod，那么他们可能能够拦截来自集群中其他 pod(或节点)的流量。”

确切地说，如果恶意用户可以创建一个 [ClusterIP](https://kubernetes.io/docs/concepts/services-networking/service/) 服务并设置 [spec.externalIPs](https://kubernetes.io/docs/concepts/services-networking/service/) 字段，他们就可以拦截到该 IP 的流量。此外，如果用户可以修补负载平衡器服务的状态，他们也可以获取流量。现在，后者是一个特权操作，Joe 和 Jane 用户不应该有这个权利，但是，在实践中，错误是会发生的。

正如软件开发人员 Markus Jevring 在 Twitter 上提问的那样，“这就是 Kubernetes 的用途吗？[同一个集群中的多租户是设计时的问题吗](https://twitter.com/jevring/status/1336014804029501440)？不不不是的。但是，正如 Allclair 回答的，“当然不是。但不管怎样，它现在就是这样被使用的，我们不得不适应。”

不幸的是，正如 Jerving 在他的后续文章中指出的，我“只是觉得像这样的问题不是安全问题。这就像把房子的钥匙留在锁里，当你被盗时感到惊讶。”这是非常正确的。

而且，前方还有更坏的消息。正如 [CVE-2020-8554:中间人使用负载平衡器或 ExternalIPs](https://github.com/kubernetes/kubernetes/issues/97076) 报告所述:“所有 Kubernetes 版本都受到影响。允许租户创建和更新服务和单元的多租户集群最容易受到攻击。”

你问这个问题的答案是什么。你不会喜欢这样的，但是没有补丁。相反，“目前只能通过限制对易受攻击功能的访问来缓解。”为什么！？“由于树内修复需要突破性的改变，我们将开启关于长期修复或内置缓解的对话。不知道什么时候会有修正。看来，它不会赶在下一个 Kubernetes 发布之前发布。Kubernetes 1.20 变更日志中对此只字未提。

你能做的就是用一个准入 webhook 容器来限制外部 IPs 的使用:这里是它的[源代码和部署指令](https://github.com/kubernetes-sigs/externalip-webhook)。这可以防止服务使用随机的外部 IP。或者，您可以使用 [OPA Gatekeeper](https://github.com/open-policy-agent/gatekeeper) 锁定外部 IP，使用以下示例[约束模板 can](https://github.com/open-policy-agent/gatekeeper-library/tree/master/library/general/externalip)

Kubernetes 没有为负载平衡器 IPs 提供缓解措施，因为授予用户补丁服务/状态权限从来都不是一个好主意。如果出于某种原因，您必须这样做，Kubernetes 安全团队建议您使用与外部 IP 缓解相同的一般方法来锁定负载平衡器 IP。

由于很少使用外部 IP 服务，Kubernetes 团队建议您手动审核集群的外部 IP 使用情况。除了确保用户不能修补服务状态之外，您还应该留意用户的修补服务状态请求。

把所有这些放在一起，这有可能成为一个真正的安全混乱。但是，[它只是被评定为中等严重程度，6.3](https://www.first.org/cvss/calculator/3.0#CVSS:3.0/AV:N/AC:L/PR:L/UI:N/S:U/C:L/I:L/A:L) 。这主要是因为没有那么多多租户集群。

尽管如此，我还是会留意这个。我不想作为系统管理员发现我的集群对租户之间的窥探敞开大门。你会吗？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>