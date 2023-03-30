# 如何帮助您的安全团队帮助您

> 原文：<https://thenewstack.io/how-to-help-your-security-team-help-you/>

来自帕洛阿尔托网络公司的 KubeCon + CloudNativeCon 和 [Prisma](https://www.paloaltonetworks.com/prisma/cloud) 赞助了这篇文章，期待虚拟的 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) ，8 月 17-20 日。

在我交谈过的一些组织中，将运营和开发纳入信任的合作关系中所带来的生产力和工作流优势在安全团队中无法复制。

我认为，这对所有相关人员都不利。

## 安全漏洞在许多层面上都代价高昂

 [罗伯特·海恩斯

从一个卑微的服务台操作员到 Unix 系统管理员的崇高职位，然后又回到市场营销，Robert 喜欢认为他的职业生涯主要包括犯错误，然后在任何人注意到之前迅速纠正错误。他目前正在与 Palo Alto Networks Prisma Cloud 团队一起执行这一有缺陷的策略，在那里，他非常喜欢讲述有关安全性、技术和人员的技术细节。](https://www.linkedin.com/in/robert-haynes-7aa95a/) 

这对开发人员不利，因为安全性是软件质量的固有组成部分。可能在开发的早期阶段就被发现的漏洞，当它们不可避免地暴露出来时，可能意味着大量的返工，影响开发人员的注意力、流程和快乐。

这对安全团队来说是不利的，因为他们知道他们没有成功地完成为组织降低风险的任务。他们明白，试图在管道的错误一端检测和补救问题会使他们成为价值流中的瓶颈。

这对企业及其客户都是不利的，因为功能会延迟，数据会丢失，头条会被写出来。这对于卑微的安全供应商来说也不理想，他们只想让世界变得更好(养活我们的家人只是一个快乐的副产品)。

我们可以确定的一件事是:[由于错过了这些机会，有大量不安全的配置漏网](https://unit42.paloaltonetworks.com/cloud-threat-report-intro/)。

## 由三部分组成的解决方案

在一个组织中找到这个问题的解决方案需要改变思维方式、流程和技术。

### **心态**

当我与努力与开发团队有效合作的安全运营团队交谈时，我鼓励双方建立一些共同的理解。

在过去，对工具的大量安全关注一直处于边缘——无论是从拓扑结构(例如，防火墙)还是从工作流的角度来看，安全团队在管道的末端介入，对已经构建的东西进行评估，或者对正在运行的系统提出更改建议。

对于一个开发团队来说，这只是冰山一角，并不是他们关注的焦点所在。此外，对于使用 Kubernetes 的团队，尤其是使用托管云 Kubernetes 服务的团队，传统的安全工具似乎无关紧要(尽管我认为这完全不是真的)。

因此，我鼓励安全团队通过构建 Kubernetes 集群(遵循优秀的“ [Kubernetes the Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way) ”)与他们的开发/开发人员同事建立共鸣，此外还有[阅读一些书籍](https://itrevolution.com/the-unicorn-project/)和观看“ [10 在 Flickr](https://www.youtube.com/watch?v=LdOe18KhtT4) 部署一天”

### **流程**

但是开发团队如何更好地处理安全团队关心的问题呢？我认为重要的一点是联合开发威胁表面区域模型以及控制和缓解措施的参考架构。

从最初的软件开发到在 Kubernetes 集群上运行 pod，工作流中的弱点在哪里？在不破坏现有工作流程的情况下，可以实施哪些控制措施来帮助消除它们？

您的安全团队是寻找所有可能危及您安全的方式的专家；从恶意的模块域名仿冒和欺骗粗心的人，到更普通的[过度特权](https://unit42.paloaltonetworks.com/non-root-containers-kubernetes-cve-2019-11245-care/)和[错误配置](https://unit42.paloaltonetworks.com/github-data-exposed/)错误。您是寻找方法的专家，通过与您的自动化构建和测试管道集成的方式来检测和修复它们。

当然，谈判是要进行的——什么程度的风险应该破坏一个构建？可以使用的库应该有多少限制？如果云数据库未加密，补救措施应该是什么样的？在提交基础设施即代码(IaC)模板并(可能)中断构建之前，如何确定它是否通过了检查？

如果你能设法把正确的心态带到工作坊，这就是乐趣的开始。向安全团队传授一些使 DevOps 成为如此有效的运营模式的文化特征，将会带来回报。

你能把无责备的事后思考转化为无冲突的安全计划吗？尽管安全性是一个严肃的问题，但是在现代软件开发过程中识别和修复威胁所需的问题解决方案可能是一个每个人都喜欢的有趣的挑战。

### **技术**

一旦您掌握了威胁和补救措施，接下来就是工具的选择了。

我们发现，成功的工具允许安全团队管理策略，但直接向开发人员提供反馈——例如，提供一条 Slack 消息，说明您现有的容器映像(安全地存放在受信任的注册表中)在 Node.js 包中有一个新发现的漏洞。

考虑“认知负荷”也很重要除非您希望安全性转移得太远，以至于全部变成您的责任，否则保持工具数量较少是值得的，并寻找可以针对不同用户以多种模式驱动的平台。安全团队必须提供报告和审计，将这种功能整合到平台中的解决方案将使他们的生活变得更加轻松，希望在流程结束时，您会倾向于这样做。

*要想了解更多将安全性与云原生开发联系起来的方法，请考虑参加 8 月 17 日至 20 日在 T4 举行的[kube con+CloudNativeCon Europe【】(因此可以在任何对您来说安全方便的地方举行)。](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)*

[![](img/75815f6c9d934e86ec6fa33b77909e39.png)](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>