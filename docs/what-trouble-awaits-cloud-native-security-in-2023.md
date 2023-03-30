# 2023 年云原生安全有什么麻烦等着？

> 原文：<https://thenewstack.io/what-trouble-awaits-cloud-native-security-in-2023/>

[Gartner](https://www.gartner.com/en) 预测，到 2025 年，我们将最终看到[一半的 IT 支出将最终从传统 IT 基础设施转移到公共云](https://www.gartner.com/en/newsroom/press-releases/2022-02-09-gartner-says-more-than-half-of-enterprise-it-spending)。与 2022 年的 41%相比，这是一个相当大的跳跃。但是，我确信它会发生。我还确信，随着时间的推移，云的原生安全问题只会随着它的整体增长而增长。

为什么？并不是说在 [Kubernetes 1.26](https://kubernetes.io/blog/2022/12/09/kubernetes-v1-26-release/) 的核心部分潜伏着什么令人震惊的安全问题。或者，[亚马逊网络服务(AWS) Lambda](https://aws.amazon.com/lambda/) 会突然开始修改你的代码。要是有那么容易就好了！

不，技术问题可能非常烦人——我们正在看着你，[Log4j](https://thenewstack.io/one-year-of-log4j/)——但真正的云原生安全问题是坐在键盘和座位之间的活生生的人。您的技术支持人员可能会认为:椅子和键盘之间存在问题(PEBAK)。

不相信我？2020 年 [Ponemon](https://www.ponemon.org/) 和 [IBM](https://www.ibm.com/us-en) 的一项研究发现，仅[配置错误的云服务器就导致了 19%的数据泄露](https://www.capita.com/sites/g/files/nginej291/files/2020-08/Ponemon-Global-Cost-of-Data-Breach-Study-2020.pdf)。这不是火箭科学。只是简单地建立一个云并不容易。

并不是我怀疑你的云人们聪明识路，比如 [Azure](https://azure.microsoft.com/en-us/) 的 [Kubernetes 事件驱动](https://keda.sh/)[auto scaling](https://keda.sh/)[【KEDA】](https://keda.sh/)； [Kyndryl 云原生服务](https://www.kyndryl.com/us/en/about-us/news/2022/12/kyndryl-cloud-native-services-digital-modernization)；或者[谷歌 Kubernetes 引擎(GKE)](https://cloud.google.com/kubernetes-engine) 。如果您正在使用云原生服务进行实际工作，这是一个很大的挑战。

不，问题是理解如何构建和维护云原生应用已经够难了，更不用说保护它们了。现在，和往常一样，开发人员和 IT 人员在紧张的时间期限内工作。这种执行压力导致了安全疏忽。

你可能会说，“你已经知道了。”为了不打扰你。我不能。您知道，您可能知道安全性很重要，但这并不意味着您的团队对此很重视。口惠而实不至。

当然，您可能会将安全性转移到开发管道中，但这并不意味着已经完成了。最近苏黎世大学的一项研究显示，现代代码评审期间的软件安全:开发人员的观点大多数开发人员在代码评审期间仍然没有关注安全问题。他们会说他们是，但他们不是。在尽可能快地推出可交付成果的过程中，安全性常常被忽视。

这种情况仍在发生，因为第一个问题是管理层仍然没有足够重视安全性。直到一家公司或一个项目被打得鼻青脸肿，他们似乎都拒绝认真对待。

云原生安全公司 [Oxeye Security](https://www.oxeye.io/) 希望"[领导者希望了解【安全风险】](https://pix11.com/business/press-releases/ein-presswire/607242954/oxeye-reveals-application-security-predictions-for-2023/)以便他们能够相应地分配资源，从而降低他们的整体风险暴露。”我希望。

诚然，Gartner 预测云安全将在 2023 年快速增长，增长率为 26.8%。毕竟，正如 Gartner 的高级主管分析师 Ruggero Contu 所观察到的，“疫情加速了混合工作和向云的转移，挑战着(首席信息安全官)CISO 保护日益分散的企业。”因此，2023 年安全服务将达到 765 亿美元。

会花更多的钱，但我不确定会花在需要的地方。正如麦肯锡的一项网络安全研究所说，“许多(如果不是大多数)首席信息安全官的预算资金不足。”

此外，抛开纯粹的安全资金，没有足够的资金用于程序员和 IT 安全。这表明在实践中许多公司仍然没有提供安全培训。尽管如此，他们认为开发人员会神奇地知道如何在他们的程序和管道中构建安全性。

太多时候，C 套件和 IT 团队仍然认为安全性是一个神奇的黑匣子，你可以在里面填充代码和进程，然后——哒——哒！—他们变得安全。没有什么比这更偏离事实了。

安全培训必须成为现代云开发的一部分。我担心在 2023 年，直到我们遇到更大的云灾难，我们才会看到这一天的到来。

一个相关的问题是，我们都知道云原生计算是复杂的，但我们没有认识到这使得保护云原生程序变得多么困难。正如德勤咨询公司(Deloitte Consulting)首席云战略官 David Linthicum 最近所说的，“多云和其他复杂的异构平台部署[加速了过于复杂的部署](https://www.infoworld.com/article/3682134/complexity-is-the-enemy-of-cloud-security.html)。同时，安全预算、方法和工具保持不变。随着复杂性的增加，违规风险也以大致相同的速度增加。”

没错。

Linthicum 建议，在您将最新的、闪亮的新云原生工具添加到您的工作台之前，您应该“考虑将如此多的移动部件添加到已经复杂的 IT 环境中的影响。”他是对的。我以掌握技术为生，对[云原生计算基础(CNCF)](https://www.cncf.io/) [云原生交互格局](https://landscape.cncf.io/)几乎没有肤浅的了解。在使您的基础架构变得更加复杂之前，坚持使用您最了解的东西并掌握它。

此外，正如 Oxeye 的首席技术官兼联合创始人 Ron Vider 所说，“就业务灵活性而言，云原生应用程序是游戏规则的改变者，但这些平台的保护带来了新的挑战、限制和要求，限制了传统应用程序安全解决方案在这些环境中的有效运行。由于这是一个快速发展的领域，向云原生应用程序安全性的转变需要一种全新的方法，从整体上审视所有软件组件和底层基础架构，以确保弹性运营。”

说起来容易做起来难。

现在，一些安全进步确实在 2023 年成为现实。根据身份和访问管理(IAM)巨头[Okta](https://www.okta.com/sites/default/files/2022-09/OKta_WhitePaper_ZeroTrust_H2_Campaign_.pdf)的数据，97%的公司要么已经实施了零信任计划，要么将在 2023/24 年实施。据零信任公司 [Zscaler](https://www.zscaler.com/) 称，这将使云安全变得更加容易，而不是依赖于不适合云的安全机制，如防火墙和虚拟专用网络(VPN)。零信任除了简单地帮助保护最终用户云访问之外，还将有助于 API 安全和基于上下文的访问策略。

我们将不得不等待其他技术云安全改进。例如，正如 [Spiceworks](https://www.spiceworks.com/) 所指出的，简单地管理[多个云安全仪表板是一个大问题](https://www.spiceworks.com/it-security/cloud-security/guest-article/cloud-security-predictions-for-2023/)。有多糟糕？“由于不同平台之间的应用程序安全性不一致，69%的组织经历过违规或数据泄露。”那么糟糕。

还记得我说过的复杂性吗？又来了。

为了解决这个问题，我们确实拥有比以前更有用的自动化安全工具。例如，众所周知，由于不安全的第三方库，软件供应链问题已经成为主要的安全问题。感谢[左移安全软件流程](https://thenewstack.io/shift-left-where-cloud-native-computing-security-is-going/)，比如[软件工件的供应链层级](https://security.googleblog.com/2021/06/introducing-slsa-end-to-end-framework.html) (SLSA，发音为“莎莎”)；[软件包数据交换(SPDX)](https://spdx.dev/) / [软件物料清单(SBOM)](https://thenewstack.io/sboms-are-great-for-supply-chain-security-but-buyers-beware/)；静态应用安全测试(SAST)和交互式应用安全测试(IAST) 我们对代码安全问题有了更好的自动化控制。

但是，今天，所有这些领域的工具涵盖了供应链的多个部分。再一次，我们正在处理大量的复杂性。

那么，你能做些什么呢？首先，安全性必须成为高管团队的首要问题。他们还必须通过投入更多资金来支持这一点，不仅是在大写“S”的安全方面，而且要培训战壕中的每个人如何保护他们的云部分。也就是说，你还必须投资零信任和软件供应链安全工具。

所有这些，一点都不容易。尽可能地，我敦促你简化你的云基础设施，这样你就可以掌握它。做到这一点，通过大量的艰苦工作，我希望你能在没有任何重大安全问题或中断的情况下度过下一年。

祝你们好运，伙计们。黑客会追杀我们。我们所有人。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>