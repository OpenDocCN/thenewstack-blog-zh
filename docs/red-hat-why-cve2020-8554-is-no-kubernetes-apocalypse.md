# 红帽:为什么 CVE2020-8554 不是库伯内特启示录

> 原文：<https://thenewstack.io/red-hat-why-cve2020-8554-is-no-kubernetes-apocalypse/>

[](https://www.linkedin.com/in/alhandy/)

 [亚历克斯·汉迪

亚历克斯是红帽公司的技术营销经理。在他之前的生活中，他报道了第一台 iMac 的发布，然后开始了 20 多年的科技记者生涯。他的作品出现在《连线》、《亚特兰大宪法日报》和《奥斯汀美国政治家》上。](https://www.linkedin.com/in/alhandy/) [](https://www.linkedin.com/in/alhandy/)

上个月，围绕 Kubernetes 的外部 IP 服务路由漏洞 [CVE 2020-8554](https://access.redhat.com/security/cve/cve-2020-8554) 发生了一场混乱。一些人认为这不是一个简单的修补问题，而是这个问题已经融入了 Kubernetes 设计的[核心](https://thenewstack.io/unfixable-kubernetes-security-hole-means-potential-man-in-the-middle-attacks)。这是 Kubernetes 建筑的一个基本缺陷。[红帽](https://www.openshift.com/try?utm_content=inline-mention)愿意站出来为 Kubernetes 和[云计算原生计算基金会](https://cncf.io/?utm_content=inline-mention)为其解决这个问题的工作辩护。不幸的是，没有适合所有用户的单一解决方案。

正如新任 Stack security 记者 Steven J. Vaughan-Nichols [描述的漏洞](https://thenewstack.io/unfixable-kubernetes-security-hole-means-potential-man-in-the-middle-attacks):“如果恶意用户可以创建一个 ClusterIP 服务并设置 spec.externalIPs 字段，他们就可以拦截到该 IP 的流量。此外，如果用户可以修补负载平衡器服务的状态，他们也可以获取流量。现在，后者是一种特权操作，Joe 和 Jane 用户不应该有这种权利，但在实践中，错误是会发生的。”

有争议的是，Kubernetes 用户可以通过利用不受限制的服务属性，进入来往于 Kubernetes 集群的流量中间。

[David Eads](https://www.linkedin.com/in/david-eads-64b67212a/) ，Red Hat 高级首席软件工程师，也是 Kubernetes 项目的主要贡献者，他对这个安全缺陷解释如下:

“服务上有一个字段，允许您在每个节点上配置 iptables 的逻辑规则，它表示特定的 IP 应该路由到我的 pod。对于 OpenShift，Red Hat 的 enterprise Kubernetes 产品，我们必须找到一个解决这一缺陷的方案，这个方案将适用于我们的客户、我们的按需自管理解决方案以及用户自己处理的 OpenShift 安装。

我们的解决方案限制了对这个特性的访问，并且说‘不，普通用户不能设置这个。“集群管理员可以对此进行设置，并委托和设置允许的 IP 列表。”流量进来寻找目的地 192.168.0.2，这个服务可以说，‘是的，就是我。在上游的 Kubernetes 中，任何用户都可以自由使用任何 IP。"

虽然这个问题不仅仅是一个简单的一刀切的补丁，但它一直是 Red Hat 容器化应用基础设施架构师 Clayton Coleman 和 Red Hat 首席软件工程师 Maciej Szulik 的关注焦点。两人都是 Kubernetes 的贡献者，Coleman 是 CNCF Kubernetes 项目指导委员会的成员。

手头的问题在很多年前就被认识到了，并在极早期的 [OpenShift](https://www.openshift.com/) 版本中得到了修复，但是上游修复并不那么容易应用。事实证明，限制这一功能给一些用户带来了问题。每次提出这个问题，都找不到一个好的通用解决方案。

这总是一种不稳定的平衡——试图为社区驱动的项目的问题找到正确的解决方案。科尔曼说，他在 2016 年为 OpenShift 打开了关于该问题的[第一期，就连当时被引用的人们也就该问题的正确解决方案应该是什么进行了一些深入的讨论。即使是 Red Hat 的软件开发人员也对如何解决这个问题同时给用户带来最少的兼容性问题有不同的看法。](https://github.com/openshift/origin/pull/7810)

最后，Clayton 说，问题不一定是这个缺陷，就像之前的[新栈文章](https://thenewstack.io/unfixable-kubernetes-security-hole-means-potential-man-in-the-middle-attacks)暗示的那样，“无法修复”问题是这个问题的通用解决方案不容易找到。虽然 Red Hat 的解决方案本质上是控制对该功能的访问，但另一个上游解决方案是一个插件，完全充当外部 IP 服务的关闭开关。这是一个激烈的步骤，但肯定比允许任何人访问这些 IP 更安全。

科尔曼说:“为每个人找到合适的解决方案并不容易。“这并不意味着我们应该放弃。我们致力于与上游社区合作，并始终保持这种安全水平。”

这个特殊问题的上游解决方案还不完全确定。这并不是说没有解决办法，比如前面提到的关闭开关。

事实上，外部 IP 服务路由的问题在 GitHub 上仍未解决，关于最佳解决方案的争论仍在继续。虽然 CVE 可能是新的，[背后的问题](https://github.com/kubernetes/kubernetes/issues/22650)在过去的 Kubernetes GitHub 问题流中已经提到过，但已经被关闭了。

因此，虽然这个 CVE 听起来像是一个惊天动地的漏洞，可能会动摇 Kubernetes 的基础，但这已经是 Kubernetes 项目的一个长期问题。由于 CVE 的提交，唯一真正的变化是解决方案可能会比其他情况下更快地在社区内出现。

在 CVE 的背后是一个由非常有才华的人组成的非常健康的社区，他们每天都必须选择在他们有限的时间里关注项目的哪一部分。他们已经习惯性地解决了他们遇到的每一个重大问题，在这里也是如此。

毫无疑问，Kubernetes 未来将面临安全问题，但他们不太可能突然毫无预警地从深渊中跳出来。CNCF 有很多非常聪明的人在全球范围内夜以继日地工作，以确保 Kubernetes 尽可能可靠和安全，他们通常都知道棘手、复杂的部分在哪里。

开源开发的真正诀窍不一定是识别那些需要关注的复杂部分，而是找到合适的人并为他们找到时间来完成工作。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>