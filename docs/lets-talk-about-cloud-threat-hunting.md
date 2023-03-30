# 我们来谈谈云威胁追踪

> 原文：<https://thenewstack.io/lets-talk-about-cloud-threat-hunting/>

威胁搜寻是一种主动寻找和补救未检测到的网络攻击的方法。这是一个包括寻找危害指标(IoC)、调查、分类和补救的过程。

[当猎人调查外部或内部来源提供的指标时，威胁狩猎](https://www.crowdstrike.com/cybersecurity-101/threat-hunting/)可以是代码驱动的基础设施。当搜寻从最初的假设或问题开始时，它也可以是假设驱动的。例如，我们是否受到了新闻报道的最近一场运动的影响？

## 最好假设你已经妥协了

寻找威胁是必要的，因为没有网络安全保护总是 100%有效。需要一种积极的防御，而不是依赖“设置好就忘了”的安全工具。由于[的对手已经踏上了云之旅](https://www.crowdstrike.com/resources/white-papers/crowdstrike-security-cloud-guidebook/?utm_campaign=blog&utm_medium=syn&utm_source=cont)，因此需要进行威胁搜寻，以检测和破坏源自、运行和持续存在于云中的高级威胁。

今天，超过 70%的应用程序代码是开源的。攻击者希望将他们的恶意代码包含在 GitHub 等常见项目中。在下毒之后，他们耐心地等待新版本进入你的云应用。保持不被发现对这次和大多数攻击的成功至关重要。不幸的是，大多数攻击都没有被发现。发现和遏制违规行为所需的平均时间为 280 天。

威胁搜寻包括使用手动和软件辅助技术来检测躲避了其他安全系统的可能威胁。这些威胁搜寻任务可能包括搜寻您帐户中的恶意活动。攻击者会尽其所能隐藏他们的行动，但通常会留下一些他们活动的痕迹——就像面包屑一样，只有你[找对了地方才能看到。](https://www.crowdstrike.com/resources/reports/threat-landscape-cloud-security/?utm_campaign=blog&utm_medium=syn&utm_source=cont)

## 寻找威胁的过程

要有效地搜寻威胁，您需要做三件事:

### **第一步:收集质量数据**

[收集的数据](https://www.crowdstrike.com/resources/white-papers/not-so-secret-weapon-for-preventing-breaches/?utm_campaign=blog&utm_medium=syn&utm_source=cont)可以来自日志文件、服务器、网络设备、数据库和端点。在云中，一些最有用的威胁搜索数据将来自流量日志和事件活动日志。

### **步骤 2:在已知威胁的背景下分析这些数据**

威胁猎人必须搜索模式和潜在的危害指标(IOC)。您应该始终查看您的日志，以便进行适当的监控。很多时候，组织没有足够的资源和人力来进行持续的入侵检测监控。

### **第三步:分析工具，了解一切**

存在某些潜在恶意活动的明显迹象。您是否有到 Tor 出口节点的出站流量？访问令牌被新源滥用？你真正想要的是一个能够自动提醒你这些事情的云安全解决方案。如果明显的恶意活动被隐藏在堆积如山的云日志中，即使是最熟练的威胁猎人也可能无法发现。

## 发现并调查错误配置的迹象、危害和攻击的迹象

威胁搜寻需要一个范围来寻找什么，以及一种方法来识别任何不适合的东西，例如不规则的流量、异常的帐户活动、注册表和文件系统更改，以及以前没有看到的远程会话中使用的命令。

为了发现异常，首先对常规活动有一个基本的了解是很重要的。一旦发现迹象，就追踪。这通常是通过建立一个假设，然后确定每个错误配置或 IoC 指标是否是一个威胁来实现的。

一些 IOC 可能会使用直言不讳的方法，并提出明显的证据。例如，到某个组织没有任何业务往来的国家的流量增加。强烈建议使用能够自动扫描您环境中已知恶意软件签名或 IOC 的安全系统。

企业环境通常具有不同的流量，这使得检测变得更加困难。大多数安全解决方案对于已经被映射和分析的恶意代码往往是有效的，而全新的恶意代码更难以检测。

## 有效搜寻云威胁的技巧

复杂的恶意软件通常隐藏在其他东西中，以渗透到服务主机中，例如您的系统始终运行的 Windows 进程。如果他们设法注入[恶意代码](https://www.crowdstrike.com/cybersecurity-101/malicious-code/)，他们就能以一种无法察觉的方式执行恶意操作。Windows 注册表是恶意软件可能隐藏的另一个重要位置。与默认系统注册表进行比较，并调查任何更改。

在过去一年的许多重大入侵中，都使用了 Microsoft Active Directory。考虑让您的组织远离该系统，以防止横向移动和其他攻击技术。

您对[威胁搜索](https://www.crowdstrike.com/services/managed-services/falcon-overwatch-threat-hunting/cloud-threat-hunting/?utm_campaign=blog&utm_medium=syn&utm_source=cont)的详细程度取决于您组织的优先级和每个系统的自由度。检查始终处于活动状态的关键系统进程的完整性是威胁搜寻取证方面的一个重要部分。

拥抱云对于数字化转型计划至关重要，但要想取得成功，安全性必须与业务同步转型。很简单，现在是企业[重新思考云安全](https://www.crowdstrike.com/resources/white-papers/crowdstrike-security-cloud-guidebook/?utm_campaign=blog&utm_medium=syn&utm_source=cont)的时候了，以便跟上不断变化的风险形势。

CrowdStrike 云安全通过统一云安全状态管理 [(CSPM)](https://www.crowdstrike.com/products/cloud-security/falcon-horizon-cspm/?utm_campaign=blog&utm_medium=syn&utm_source=cont) 以及针对云[工作负载](https://www.crowdstrike.com/products/cloud-security/falcon-cloud-workload-protection-complete/?utm_campaign=blog&utm_medium=syn&utm_source=cont)和[容器](https://www.crowdstrike.com/products/cloud-security/falcon-cloud-workload-protection/container-security/?utm_campaign=blog&utm_medium=syn&utm_source=cont)以及我们的[人类威胁检测引擎的违规保护，超越了临时方法。](https://www.crowdstrike.com/services/managed-services/falcon-overwatch-threat-hunting/cloud-threat-hunting/?utm_campaign=blog&utm_medium=syn&utm_source=cont)当威胁猎手作为您团队的延伸来无情地识别和阻止云中的威胁时，您可以放心地保护您的云环境以及您的发展潜力。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>