# 身份和访问管理是 Kubernetes 的一个难点

> 原文：<https://thenewstack.io/identity-and-access-management-is-a-pain-point-in-kubernetes/>

来自帕洛阿尔托网络公司的 Prisma Cloud 赞助了这次播客。

身份和访问管理(IAM)以前相对简单。设置分层数据访问权限的过程通常作为低级管理任务委派给局域网(LAN)或广域网(WAN)管理员，绝对不是更具挑战性的安全相关职责之一。然而，在当今高度分布式和相对复杂的计算环境中，网络和相关 IAM 的复杂程度成倍增加。

[https://www.youtube.com/embed/Vv_zndiYYWg](https://www.youtube.com/embed/Vv_zndiYYWg)

视频

管理分布式 IAM 是这一集[新堆栈分析师](/podcasts/analysts)播客的主题，为 [KubeCon + CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/) 与会者录制。在我们最新的“虚拟煎饼和播客”中，TNS 创始人兼发行人 [Alex Williams](/author/alex/) 和嘉宾讨论了为什么 IAM 变得更加难以管理，并提出了他们对潜在解决方案的看法。

[为什么 IAM 是 Kubernetes 的痛点](https://thenewstack.simplecast.com/episodes/why-iam-is-a-pain-point-in-kubernetes)

IBM 的高级技术人员、Istio 的主要发明者[孙林](https://www.linkedin.com/in/lin-sun-a9b7a81/)；以及帕洛阿尔托网络公司高级威胁研究员 [Nathaniel "Q" Quist](https://www.linkedin.com/in/qquist) (公共云安全部门 42)。TNS 执行主编[乔布·杰克逊](https://thenewstack.io/author/joab/)担任共同主持人。

有效的 IAM 中的缺口已经成为攻击者进入网络和数据库的一个有吸引力且相对容易的入口。通常只需窃取一组开发者登录凭证，在 GitHub 上上传代码，就能造成真正的破坏。通过这种方式，攻击者可以获得云环境的典型用户通常不具备的网络访问权限和特权。

Quist 指出，Palo Alto Networks 的 Unit 42 云威胁报告称，23%的受访组织在其环境中遇到过针对存储在终端上的云服务提供商凭据的加密挖掘操作。“然后，[访问]只是被‘模板化’，只是让他们更容易获得整个系统的访问权限，而是更进一步，获得对实际环境本身的访问权限，”奎斯特说。

当然，Kubernetes 的高度分布式特性带来了一系列新的 IAM 挑战。然而，好消息是，服务网格越来越被视为管理 Kubernetes 环境和相关微服务的关键，它也可以适用于 IAM。在 Istio 的服务网格标准化中，IAM 属于服务网格能力的安全保护伞，与可观察性和连接性并列。

Sun 说，服务网格“提供更加面向服务的认证和授权策略”。“他们可以利用第 7 层数据做出明智的决定，”她说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>