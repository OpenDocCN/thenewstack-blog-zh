# 一年的 Log4j

> 原文：<https://thenewstack.io/one-year-of-log4j/>

你可能会认为我们已经解决了这个臭名昭著的 bug。你错了。

一年前，如果你问某人什么是开源 Java 日志库 [Apache Log4j](https://logging.apache.org/log4j/) ，你会得到很多茫然的目光。当然，它被用于数百甚至数千个应用程序，从 [Apache](https://www.apache.org/) 项目，如 [Flink](https://thenewstack.io/apache-flink-for-unbounded-data-streams/) 、 [Flume](https://thenewstack.io/apache-streaming-projects-exploratory-guide/) 、Hadoop、 [Kafka](https://thenewstack.io/apache-kafka-cornerstone-iot-data-platform/) 、Solr、 [Spark](https://thenewstack.io/the-good-bad-and-ugly-apache-spark-for-data-science-work/) 和 [Struts](https://thenewstack.io/critical-vulnerability-apache-struts-puts-thousands-web-applications-risk/) ，到苹果 iCloud、Elastic LogStash、Twitter，以及众多的 [VMware](https://tanzu.vmware.com/?utm_content=inline-mention) 程序。见鬼，这甚至是我的孩子们最喜欢的《我的世界》游戏。但是想想看？求你了。它只是一些深入代码的无害日志程序。哦，好吧，我们学会了。

Apache 基金会在 2021 年 12 月 4 日悄悄地发布了 Log4j 漏洞的补丁。没人太在意它。但是，零日漏洞[CVE-2021-44228](https://nvd.nist.gov/vuln/detail/CVE-2021-44228)——又名 [Log4Shell](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/) ，在 2021 年 12 月 10 日从 Mojang Studios 的《我的世界》游戏补丁中曝光。事实很快证明，它很容易被利用，可以轻松地完全控制易受攻击的服务器。呸！

## 0.1 至 10 分

有多糟糕？通过[国家漏洞数据库(NVD)](https://nvd.nist.gov/) 统计，它的 CVSSv3 得分为 [10.0。那是在 0.1 到 10 的范围内。一整个家族的攻击，](https://nvd.nist.gov/vuln/detail/CVE-2021-44228)[log 4 shell](https://www.lunasec.io/docs/blog/log4j-zero-day/)，让这次零日攻击变得足够糟糕，以至于引起了[白宫的注意](https://thenewstack.io/open-source-security-at-the-white-house/)。现在，我的朋友们，这是一个错误！

根据 [Check Point](https://blog.checkpoint.com/2021/12/13/the-numbers-behind-a-cyber-pandemic-detailed-dive/) 的数据，2021 年 12 月 13 日，在最初披露后仅 72 小时，就有超过 80 万次使用它的攻击尝试。作为安全公司， [Nextron Systems 的](https://www.nextron-systems.com/)研究负责人， [Florian Roth](https://www.linkedin.com/in/floroth/) 在推特上写道，“ [#](https://twitter.com/hashtag/Log4Shell?src=hashtag_click) [Log4Shell](https://twitter.com/hashtag/Log4Shell?src=hashtag_click) 漏洞不仅仅是一个 RCE【远程代码执行】0day。这是一个在各种软件产品中导致成百上千个 0 天的漏洞。[是 0 天集束炸弹。](https://twitter.com/cyb3rops/status/1469671300285222917)

是的，是的，它是。但是很快就解决了。到 2021 年 12 月 20 日， [Log4j 2.17.0](https://www.zdnet.com/article/apache-releases-new-2-17-0-patch-for-log4j-to-solve-denial-of-service-vulnerability/) 库修复了代码的主要和次要问题。所以，这应该是结束了。我们希望！

## 到处都是

结果是 Log4J 在代码中到处都是异常。那很糟糕。但是，更糟糕的是，即使是现在，许多人也不知道 Log4j 的一个易受攻击的版本仍然隐藏在他们的代码中。

到 2022 年 1 月，[微软警告说，民族国家行为者](https://securityaffairs.co/wordpress/126333/breaking-news/log4j-flaws-attacks.html)和[网络罪犯](https://thenewstack.io/as-geopolitical-tensions-rise-so-do-opportunities-for-cybercriminals/)继续试图利用 Log4j 中发现的漏洞在易受攻击的系统上部署恶意软件。与此同时， [Check Point 的研究人员发现了](https://duo.com/decipher/apt35-deploys-powershell-based-malware-in-log4j-flaw-attacks)一个与伊朗有关联的威胁参与者 APT35，它利用 Log4j 漏洞来部署基于 [PowerShell](https://thenewstack.io/microsoft-open-sources-powershell-ports-cli-linux/) 的模块化恶意软件。这种策略一直沿用至今。微软的研究团队还发现了一个总部位于中国的组织[利用了 VMware Horizon](https://duo.com/decipher/china-based-actors-using-log4shell-bug-for-ransomware-deployment) 某些版本中的漏洞。这里的目标是安装[夜空勒索软件](https://www.avertium.com/resources/threat-reports/everything-you-need-to-know-about-night-sky-ransomware)。

当然，这个漏洞也被普通的骗子用来植入加密挖掘恶意软件。如今，如果不试图窃取计算能力来赚钱，安全漏洞是什么？

2022 年 12 月早些时候，最近，[网络安全和基础设施安全局(CISA)](https://www.cisa.gov/) 披露，不仅黑客仍在使用 Log4Shell，伊朗政府特工也曾用它来[撬开联邦政府机构 VMware systems](https://www.cisa.gov/uscert/ncas/alerts/aa22-320a) 。

不过，这肯定是个例外，对吧？我们终于解决了这个问题，不是吗？不是吗！？

没有。

## 72%的组织仍然易受攻击

据安全公司 Tenable 称，“截至 2022 年 10 月 1 日， [72%的组织仍然易受 Log4Shell 漏洞的攻击。”为什么！？“在完成全面补救后，这些资产中有近三分之一(29%)再次出现 Log4Shell。”](https://www.tenable.com/press-releases/tenable-research-finds-72-of-organizations-remain-vulnerable-to-nightmare-log4j)

所以，是的，代码是固定的，然后有人引入了“新”代码，引入了 Log4J 的旧版本。然后，很快！实例漏洞！

正如 Tenable 首席安全官 Bob Huber 所说，“对于一个如此普遍的漏洞来说，完全修复是非常困难的，重要的是要记住漏洞修复不是一个‘一劳永逸’的过程。虽然某个组织可能在某个时候已经得到了充分的补救，但是随着他们向其环境中添加新的资产，他们很可能会一次又一次地遇到 Log4Shell。根除 Log4Shell 是一场持续的战斗，需要组织不断评估其环境中的缺陷，以及其他已知的漏洞。

## 依赖，依赖，依赖

这怎么可能呢？Tenable 没有深入探讨，但是 [Endor Labs 的](https://www.endorlabs.com/) Station 9 研究[依赖性管理的状态](https://www.endorlabs.com/state-of-dependency-management)给了我们一个巨大的提示。在很多厂商[开源代码库](https://thenewstack.io/add-it-up-competing-estimates-of-open-source-composition/)中，95%的漏洞都不是开发者选择的，而是间接拉到项目中的。

Endor Labs 的联合创始人兼首席执行官 [Varun Badhwar](https://www.linkedin.com/in/vbadhwar/) 说:“根据某些标准，对于开发人员带入软件项目的每一个依赖，平均有 77 到 78 个可传递的依赖。因此，“发现的 95%的漏洞都存在于那些可传递的依赖关系中，即你带来的东西带来的东西。我们需要跟踪我们环境中的所有这一切，并了解这些包正在哪些应用程序中使用。”

对[软件物料清单(SBOM)](https://www.cisa.gov/sbom) 和软件工件供应链[(SLSA)](https://slsa.dev/)的需求从未如此清晰。显然，公司在部署代码之前仍然不知道代码中有什么。

即使根据 Tenable 的统计，截至 2022 年 10 月 1 日，全球 28%的组织已经完全修复了 Log4Shell，比 2022 年 5 月提高了 14 个百分点，这一事实也不能令人放心。

## 地方性脆弱性

这意味着什么？鲍勃·伯恩斯(Bob Burns)首席产品安全官说，Log4j 被证明是一个“地方性漏洞，因为它将在未来几年内留在系统中。”这也引起了人们对开源软件本质安全性的担忧。当然，正如[网络安全管理软件产品惨败](https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/)所显示的，专有软件也有自己的问题。

关于专有软件的安全问题，安全公司 ReversingLabs 的软件保证布道者 Charlie Jones 预计 Log4Shell 的影响可以与 MS-17-10 相媲美。这就是驱动 NotPetya 和 WannaCry 雨刷恶意软件攻击的“[永恒之蓝](https://www.hypr.com/security-encyclopedia/eternalblue)”微软中小企业漏洞(MS-17-10)。但是“Log4Shell 提出了一个比 MS-17-10 更复杂的挑战，因为它往往深深地嵌套在应用程序依赖关系中，因此更难以用标准工具快速识别。”

Log4j 的真正教训是，即使我们努力最终结束它，也迫切需要知道我们在程序中放入了什么。直到我们用自动化工具解决了这个基本的[软件供应链](https://thenewstack.io/nsa-software-supply-chain-guidance/)，我们可以期待看到更多 Log4j 问题的出现。让我们只希望它们都没有 Log4j 被证明的那么糟糕吧！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>