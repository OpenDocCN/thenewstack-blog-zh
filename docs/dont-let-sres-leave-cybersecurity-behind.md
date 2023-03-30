# 不要让 SREs 把网络安全抛在后面

> 原文：<https://thenewstack.io/dont-let-sres-leave-cybersecurity-behind/>

VMware 赞助了这个播客。

Alex Delgado 是 Gremlin chaos 测试服务公司的安全工程师，他指出了许多企业存在的脱节现象。这并不是说开发人员没有使用最新的技术，比如 Kubernetes 和微服务。只是安全和法规遵从性甚至没有听说过这些东西。这增加了风险。

“如果你不知道它是如何工作的，你就无法保护它，”他在这一集的[新堆栈制造商](https://thenewstack.io/podcasts/makers)中说道，在这一集中，Delgado 回顾了他在一家安全和国防企业的过去，以及他在纵向扩展 Gremlin 的现状。他的职业生涯始于客户支持，然后是客户问题的补救。这让他陷入了一个有趣但经常令人沮丧的境地，因为他进入了安全领域，这让他不得不越过可能在三个月后发布的代码。

[别让 SREs 把网络安全抛在后面](https://thenewstack.simplecast.com/episodes/dont-let-sres-leave-cybersecurity-behind)

但是在这里，Delgado 了解到，根据业务目标管理安全风险最好来自于理解客户的困难。它来自于理解如何传达这些风险，即使是对我们这些勒德分子。当然，这可能是一个挑战，因为他在我们的采访中指出，这在很大程度上是定性决策，是对以下问题的平衡:

*   企业想要达到什么目的？
*   为什么降低风险很重要？
*   降低该风险的成本是多少？
*   该风险对业务目标有多重要？

Delgado 说，尽管整个安全方法随着技术的发展而发展，但这些问题仍然存在。在他的第一个雇主那里，像许多运行在单一架构上的人一样，安全性被定义为用外围防火墙屏障来防止根访问。由于您完全信任网络中屏障后的所有设备和人员，因此数据不是主要问题。

这与现代云支持的分布式系统完全相反，由分布式团队运行，连接到许多外部服务。Delgado 建议企业环境运行云访问安全屏障或云访问安全代理( [CASB](https://www.netskope.com/about-casb) )来监控他们的流量和数据如何在云中运行。他认为他们会惊讶地发现成百上千的请求在这些云资源中运行，使得三级安全性不够。

在这个新的[零信任世界](/beyondcorp-google-ditched-virtual-private-networking-internal-applications/)中，每个人和所有东西现在都必须被授权访问任何分段部分，这通常是在[服务网](/how-service-meshes-and-kubernetes-will-close-gap-between-speed-and-security/)后面的[微服务或迷你服务](https://thenewstack.io/miniservices-a-realistic-alternative-to-microservices/)。对于每次访问，在授权访问之前，谁在访问什么数据以及数据的完整性都要经过身份验证。

Delgado 说，基于角色的访问控制或 RBAC 是必不可少的，正如最近在 Gremlin 系统中升级的[。它甚至允许非 It 人员参与安全实践，因为每个人都有分配角色和访问级别的基本技能，但只有获得授权的人才能做出这些决定。公司中的每个人都与公司的安全息息相关。](https://www.gremlin.com/blog/announcing-advanced-role-based-access-controls-for-gremlin/)

Delgado 担心安全团队已经停滞不前了，特别是对于那些具有旧的体系结构和层次结构的更符合法规的行业。他引用了 Square 的移动安全负责人 Dino Dai Zovi 在 8 月的黑帽信息安全活动上的讲话，他认为“现在每个安全团队都是软件团队”

像其他技术团队一样，Delgado 说安全正在明显左移。事实上，在 Gremlin，每个团队中至少有一名安全工程师。

### 在这个版本中:

[1:22:](https://thenewstack.simplecast.com/episodes/dont-let-sres-leave-cybersecurity-behind?t=1:22)  ，你为什么不告诉我们更多关于你的网络安全之旅？
[5:48:](https://thenewstack.simplecast.com/episodes/dont-let-sres-leave-cybersecurity-behind?t=5:48) 管理风险在分布式团队和遗留系统中是如何工作的？
[10:19:](https://thenewstack.simplecast.com/episodes/dont-let-sres-leave-cybersecurity-behind?t=10:19) 那你怎么分段？很多零信任都归结于细分。你如何决定，尤其是在一个复杂的系统中，你如何将它映射到商业目标中？
[11:47:](https://thenewstack.simplecast.com/episodes/dont-let-sres-leave-cybersecurity-behind?t=11:47) 那么我们来谈谈基于角色的访问控制。你刚刚在 Gremlin 设置的。你能告诉我们更多关于它和它是如何工作的吗？
[16:07:](https://thenewstack.simplecast.com/episodes/dont-let-sres-leave-cybersecurity-behind?t=16:07) 您认为目前公司面临的主要安全问题是什么？
[23:54:](https://thenewstack.simplecast.com/episodes/dont-let-sres-leave-cybersecurity-behind?t=23:54) 我们的听众可以做什么来帮助某人在科技行业获得成功？

来自 Pixabay 的 Simon Matzinger 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>