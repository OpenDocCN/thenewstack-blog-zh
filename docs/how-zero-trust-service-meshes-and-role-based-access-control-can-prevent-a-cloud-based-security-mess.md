# 零信任、服务网格和基于角色的访问控制如何防止基于云的安全混乱

> 原文：<https://thenewstack.io/how-zero-trust-service-meshes-and-role-based-access-control-can-prevent-a-cloud-based-security-mess/>

零信任。这听起来肯定不符合我们自组织、敏捷的软件开发文化。只有建立在信任基础上的组织才能成功。毕竟，工作中的快乐与生产力和利润直接相关。那么，如果我们知道所有这些，为什么零信任是一个趋势话题？

因为我们在安全方面一次又一次地失败。随着我们的系统变得越来越分散和复杂，恶意攻击者也是如此。

事实上，技术服务提供商 [Probrand](http://probrand.co.uk) 最近的一份报告发现，在过去的一年中，43%的英国企业遭受了数据泄露，其中 72%的入侵来自不安全的无线设备，包括连接到 Wi-Fi 网络的打印机、扫描仪、电话和笔记本电脑。自带设备的世界只会让它更具挑战性。

真正重要的是谁和什么可以访问什么数据。

然而，越来越多的人接受零信任作为替代防火墙的[企业运作方式。基于角色的访问控制(RBAC)、服务网格等正在幕后工作，以阻止数据泄露和系统中断。当然，自动化和流程编排可以加快开发运维流程。](/beyondcorp-google-ditched-virtual-private-networking-internal-applications/)

通过实现零信任代码库，也许你可以开始培养信任文化。

## 什么是零信任？

“所有数据泄露都是对旧的不信任模型的利用。几乎所有的网络安全事件都利用了信任模式，”零信任模式的创始人约翰·金德瓦格说。

信任模型是以边界为中心的安全方法。受防火墙保护，默认情况下您信任内部流量。作为一名前渗透测试人员，Kindervag 认为，对于大多数组织来说，一旦你进入第三层网络——他说总有办法——那么你就可以访问几乎所有东西，因为“那种破碎的信任模式”

零信任的座右铭是“永远不要信任”。始终验证。”每个访问网络资源的请求都必须经过身份验证和授权。在所有七个安全层。

您首先要确定您的敏感数据，然后绘制这些数据是如何流动的。您构建 Kindervag 所称的保护面，然后用微参数封闭攻击面的最小子集。他说你移动你的控制尽可能靠近保护表面。然后很少有人被给予多因素认证访问以进出微周界仪。

所有数据和访问都必须得到政策的批准。零信任包括:

*   避免默认配置
*   持续监控用户和日志记录活动
*   监控所有网络通信
*   双因素认证
*   安全自动化和流程编排

Kindervag 表示，如果您是本地遗留系统，或者使用公共云或私有云，情况也是如此。

然后，当您重新审视和调整您的零信任策略时，它们应该与整体业务成果保持一致，以确保零信任加快而不是减慢您的安全发布速度。这种实践还确保您关注于识别和保护业务关键元素。基本上，[你的现场可靠性工程师](/the-evolution-of-the-site-reliability-engineer-sre/)应该总是在这张桌子旁边。

重要的是要记住，所有这些政策和实施必须由一个跨组织的工作组来定义。负责服务器、虚拟化和合规性的人员应该从一开始就加入您的 SRE、您的开发人员和您的组织领导层。

零信任策略归根结底就是定义细分。Kindervag 认为，许多组织在网络分段方面失败了，因为他们以一种特别的方式进行网络分段，这使得网络不太可用，不太强大，并且增加了延迟。这就是为什么他提倡对分段网关背后的基础设施进行抽象。

如果分割正确，您将获得更好的性能。

## Kubernetes:默认情况下不那么安全？

毫无疑问，微服务和容器自然有助于细分。但是，再说一次，系统越分散，厨房里的厨师越多，保持锁定就越困难。

[云原生开发者](https://twitter.com/Ben_Hall) [Katacoda 学习平台](http://katacoda.com/)创始人 Ben Hall 在 [CloudNative London](https://skillsmatter.com/conferences/11723-cloudnative-london-2019#program) 分享了他主动攻防 Kubernetes 和 Docker 集群的经验。他希望提供一些团队在运行云原生系统时需要了解的最新安全方法。

Hall 表示，错误配置是安全问题的主要原因之一，[就像去年在特斯拉发生的事情](https://redlock.io/blog/cryptojacking-tesla)，当时有人因 Kubernetes 仪表板缺乏密码保护而入侵了数据中心的控制平面。

“Kubernetes 可能是世界上最安全的平台，但如果你把你的东西向外界开放，人们会发现并利用它”，如果你使用不正确的配置，霍尔说。

一个例子是，当你发出一个没有令牌的 Kubernetes 请求时，它会认为这个请求是匿名的。Hall 警告说，如果在集群设置期间使用了以下配置，那么任何人都可以访问集群。

```
apiVersion:  kubelet.config.k8s.io/v1beta1

authentication:
  anonymous:
    enabled:  true
authorization:
 mode:  AlwaysAllow

```

当用户仍在学习系统如何运行时，错误配置的风险会增加。很多用户在 Kubernetes 论坛上寻求建议。有人可能会建议你采取行动来克服错误。但是，虽然这是一种变通办法，但您现在已经将您的系统置于风险之中，例如删除您的 RBAC 策略以减轻您的即时痛苦，其副作用是删除所有安全保护。

霍尔说，RBAC 肯定是一个更强大的出路，但警告说，它仍然在 Kubernetes 混乱。通过在 Kubernetes 中使用 RBAC，您将它更改为“所需的最低特权”

Hall 强调了在不了解受影响的安全性的情况下利用底层容器功能的风险，他说:“特权容器是不好的，如果我设法利用您的应用程序，我就可以映射磁盘，我可以访问所有秘密，甚至编写自己的秘密。”

例如，如果您需要访问 Kubernetes API，您可以创建具有所需角色和权限的服务帐户。但是，如果不需要访问，应该完全禁用默认装载的令牌。只是要小心[确保 RBAC 权限](https://www.cyberark.com/threat-research-blog/securing-kubernetes-clusters-by-eliminating-risky-permissions/)没有提供太多的信息，比如下面的示例代码，如果应用于服务帐户，可能会泄露比预期更多的秘密:

```
kind:  Role

apiVersion:  rbac.authorization.k8s.io/v1

metadata:
   namespace:  default
  name:  read-secrets

rules:

-  apiGroups:  [“*”]
   resources:  [“secrets”]
  verbs:  [“lists”]

```

但是 Hall 提醒你，如果你不需要访问 API，你应该禁用它。

实际上，这是一条零信任的经验法则——如果有人不需要访问某个东西，就切断它。马上就去。然后自动执行安全策略，并使用 PodSecurityPolicy 和 OpenAgentPolicy 应用保护层，确保不会意外应用错误配置。

Hall 提供了来自 Aqua Security 的 Kube-Bench 作为自动安全扫描的有用工具，以确保您的集群已根据最佳实践进行了配置。基于一个 CIS 报告，它将报告结果转换为 Kubernetes 集群的一组可执行规则。

云本地计算基金会[最近对 Kubernetes 的核心漏洞进行了评估](/cncf-open-sources-security-audit-of-core-kubernetes-components/)。其中包括:

*   策略可能无法应用，导致错误的安全感。
*   默认情况下使用不安全的 TLS。
*   大多数组件接受入站 HTTP。
*   大多数组件不强制出站 HTTPS。
*   凭据在环境变量和命令行参数中公开。
*   秘密的名字在日志中被泄露。
*   没有证书吊销。
*   默认情况下，seccomp 不启用。

## 安全自动化、服务网格和零信任网络

[在 New Stack Makers](/how-service-meshes-and-kubernetes-will-close-gap-between-speed-and-security/) 播客的一次采访中，安全公司 [Tufin Technologies](https://www.tufin.com/) 的联合创始人兼首席技术官[鲁文·哈里森](https://www.linkedin.com/in/reuvenharrison/)表示，尽管零信任是一个很好的想法，但手动维护几乎是不可能的。

服务网格——位于服务之间的覆盖网络——作为澄清零信任的解决方案出现。从开发者的角度来看，它是透明的。这意味着这种安全逻辑构建在他们的应用程序中，但这些开发人员仍然能够看到所有的业务逻辑。服务网格通常带有对安全性之间性能的监控和可见性。最重要的是，这种 sidecar 服务充当安全屏障，对服务之间的流量进行加密，并提供可见性和监控，所有这些都在微分段级别上进行。

[Istio](https://istio.io/docs/concepts/security/) 是最受欢迎的实现方式，因为它允许控制:

*   运输流量
*   安全性
*   可观察性
*   Kubernetes 上的服务部署

当然，Harrison 提醒我们，基础设施必须由安全策略驱动，“控制谁可以与谁交谈，什么是允许的，什么是不允许的。”

然后，使用 Tufin 等安全策略管理工具将这些自动生成的策略集成到服务网格中。

[服务网和 Kubernetes 将如何拉近速度和安全性之间的差距](https://thenewstack.simplecast.com/episodes/how-service-meshes-and-kubernetes-will-close-gap-between-speed-and-security)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>