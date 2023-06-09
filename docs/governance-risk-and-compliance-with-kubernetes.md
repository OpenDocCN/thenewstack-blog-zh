# Kubernetes 的治理、风险和合规性

> 原文：<https://thenewstack.io/governance-risk-and-compliance-with-kubernetes/>

[](https://www.linkedin.com/in/cristianklein/)

 [克里斯蒂安·克莱恩

克里斯蒂安·克莱恩是 Elastisys 的高级云架构师。他在 Compliant Kubernetes 上工作，这是一个 Kubernetes 发行版，旨在促进多云遵守各种法规。他于 2012 年获得法国 INRIA 大学的博士学位。Cristian 对云安全和法规遵从性充满热情，扮演过顾问、从业者、教师和研究人员等不同角色。](https://www.linkedin.com/in/cristianklein/) [](https://www.linkedin.com/in/cristianklein/)

有没有晚上醒来觉得自己做的不够“安全”的时候？您是否曾经因为您的组织“安全性太高”而无法完成任何事情而感到沮丧？在这篇博文中，我们采访了一位风险管理人员，让这场有争议的讨论变得更加清晰——并且睡个好觉。

2020 年是不同寻常的一年。如果有什么积极的结果，那就是我们学到了平衡各种风险的困难。“ [Schrems II](https://iapp.org/news/a/the-schrems-ii-decision-eu-us-data-transfers-in-question/) ”裁决结束了 PrivacyShield，导致我们如何选择云提供商的混乱和不确定性。以防万一，我们希望这是一个我们可以忽略的问题， [GDPR 的罚款](https://www.enforcementtracker.com/)以惊人的速度执行 **—** 提醒我们，缺乏数据隐私和安全可能会产生直接的财务后果。

同时，在[kube con+CloudNativeCon NA 2020](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)上，安全性是参与人数最多的赛道之一。本已拥挤的[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)在安全方面的前景变得更加拥挤；例如[法尔科被孵化](https://www.cncf.io/blog/2020/01/08/toc-votes-to-move-falco-into-cncf-incubator/)和[开放政策代理毕业](https://blog.styra.com/blog/open-policy-agent-graduating-in-the-cncf-proves-need-for-cloud-native-authz)。Kubernetes 本身也陷入了[“默认安全”vs .“默认工作”](https://searchitoperations.techtarget.com/news/252487963/Kubernetes-security-defaults-prompt-upstream-dilemma)的争斗。

随着风险和技术领域的快速发展，工程焦虑达到了前所未有的高度。我们是否应该像其他人一样采用 tech X？我们应该将我们的工作负载转移到云 Y 吗？我们做得足够安全吗？我们是否在安全性方面做得“太多”,失去了市场份额？我晚上睡得好吗？难道你不希望自己能安全、诚实地与风险管理人员交谈吗？

 [莎拉·克拉克

Sarah 是数据保护和网络安全 GRC 专家。她为自己的公司 Infospectives Ltd 工作，为众多客户提供建议和支持。她还是 ForHumanity AI Institute 的研究员，支持他们开发 AI 审计和治理机制，并且是曼彻斯特大学 it 治理硕士课程供应商安全治理的客座讲师。](https://www.linkedin.com/in/infospectives/) 

为了澄清这个复杂的问题，我们向数据保护和网络安全 GRC 专家莎拉·克拉克提问。她在 IT 风险管理方面拥有超过 17 年的经验，见证了许多法规和新技术的浪潮。她对技术术语和产品名称不感兴趣，并且很快就知道你实际上做了什么来保护数据。这是我和她的一段对话(她完全保证不会解雇我！)

Sarah，架构师和开发人员什么时候应该让像你这样的人参与进来？

昨天。

***“打碎玻璃”呢？我应该如何在被锁在外面和滥用紧急访问之间找到正确的平衡？***

签署层级结构，并访问审计和监控。这不是要阻止你，而是要展示你的工作方式。始终相信，但要核实。

***我得跟你说实话。我们确实走了一些“捷径”,只是为了出货和获得市场反馈。现在他们被收养了，我们被他们缠住了。我们要花几个月的时间才能堵住那些漏洞。我们应该如何推理特权访问的最小化？***

又一样。如果在下一次冲刺或者下一次冲刺中还不能修复。如果它有可能成为你的 MVP，记录下来。我们都会忘记事情。您需要快速迭代不是您的风险，但是没有跟踪为此做出的妥协绝对是风险。升级(给我或你的 CISO 打电话，或者把它记在你知道我们会审查的日志里)。除了基本的 CVSS 之外，要有明智的标准。

***那么我需要在发货前把所有东西都修好吗？***

不需要追求完美，但你需要不断地管理风险。管理风险可以包括什么都不做，但你必须记录下你这样做的原因，并让与游戏有利害关系的人参与进来。

***但是我需要推送功能。我怎么能挤出时间来呢？***

有有效的反馈回路吗？推动的需要来自负责任的人。没有时间做你的工作本身就是一种风险。订婚风险。

这是一种风险，您应该尽可能早地记录下来，并让管理层看到它以及漏洞和其他控制漏洞。

我们还没有人正式为此负责。我该怎么办？

浮出水面的最好方法是做一个 RACI——事先就谁负责、负责、咨询或了解一个有用的任务和输入的粒度列表达成一致。记录你对每个人的需求，你所有的依赖、限制和时间约束。事先做好，这是风险管理。在发布前一周完成，这是一个借口。

但是我们会变得非常没有竞争力。我们做什么呢 

董事会的核心工作是不断管理风险。如果他们想用安全或隐私来换取某个功能或发布日期，他们需要在上面签名；但你需要清楚严格的监管和法律界限，以及其他风险的变化范围，然后确保所有这些都记录在案。

***我应该如何选择我的供应商？***

他们自己的下游供应商尽职调查，他们的隐私和安全控制和事件响应能力，他们的内部专业知识。他们的透明度和反应能力。在我们主要基于云的供应链中，快速可见性对一切都至关重要，不仅仅是性能和吞吐量。

***我应该如何看待我的客户？***

比如你的朋友和家人。如果你的商业模式依赖于模糊事物，依赖于运送一个危险的有洞的工具包，依赖于仔细措辞你打算如何处理个人数据，依赖于黑暗的模式来混淆他们的同意——这可以吗？

***如果我“需要合规”，但我的经理为了快速发货而催促我跳过安全检查，我该怎么办？***

如果在迭代开发、发布前或发布后的早期迭代变动中存在可能无法解决的安全或隐私问题，并且存在大量风险的可能性(您是否为弱势群体的需求提供服务？)那么你很可能没有站在历史的正确一边，但是你有责任吗？您的第一步总是定义责任，分类风险，从不同利益相关者的角度记录危险，并上报。

他们不想在上面签名吗？你猜怎么着？他们已经做了。问责制只能属于那些拥有知识和影响力来实现变革的人。我们有责任提供这些知识。他们要对自己做出的决定负责。

*要了解更多关于 Kubernetes 和其他云原生技术的信息，请考虑参加 5 月 4 日至 7 日举行的[kube con+CloudNativeCon Europe 2021–Virtual](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>