# Log4j:疼痛持续不断

> 原文：<https://thenewstack.io/log4j-the-pain-just-keeps-going-and-going/>

对此不要有任何误解。Apache Log4j 的 Log4Shell 安全漏洞是一个空前可怕的代码灾难。我的意思是，根据[国家漏洞数据库(NVD)](https://nvd.nist.gov/)的统计，它的得分为[10.0 cvss v3](https://nvd.nist.gov/vuln/detail/CVE-2021-44228)。那是在 0.1 到 10 的范围内。

作为安全公司 [Nextron Systems 的](https://www.nextron-systems.com/)研究主管， [Florian Roth](https://www.linkedin.com/in/floroth/) 在推特上写道，“这个 [#](https://twitter.com/hashtag/Log4Shell?src=hashtag_click) [Log4Shell](https://twitter.com/hashtag/Log4Shell?src=hashtag_click) 漏洞不仅仅是一个 RCE【远程代码执行】0day。这是一个在各种软件产品中造成成百上千天的漏洞。这是一枚 0 天集束炸弹。

但是，嘿，几个月前就修补好了。的确，第一个 Log4j 补丁出现了一个[安全问题，但是很快就被修复了。所以，我们现在都没事了，对吧？对！？](https://thenewstack.io/another-day-another-log4j-vulnerability/)

不对。

## 剥削持续存在

正如美国[网络安全和基础设施安全局(CISA)](https://www.cisa.gov/) 和美国海岸警卫队网络司令部(CGCYBER)最近[在一份联合网络安全咨询(CSA)通知](https://thenewstack.io/log4shell-hacks-on-and-on/)中报告的那样，包括国家支持的高级持续威胁(APT)行为者在内的黑客[仍在利用](https://www.cisa.gov/uscert/ncas/alerts/aa22-174a) [VMware Horizon](https://www.vmware.com/products/horizon.html) 和[统一访问网关(UAG)](https://docs.vmware.com/en/Unified-Access-Gateway/index.html) 中的 CVE-2021-44228 (Log4Shell】。

但是你猜怎么着？还有呢！

美国国土安全部(DHS) [网络安全审查委员会(CSRB)关于 Log4j 的报告](https://www.cisa.gov/sites/default/files/publications/CSRB-Report-on-Log4-July-11-2022_508.pdf)，发现“Log4j 事件并没有结束。Log4j 仍然深深嵌入在系统中，即使在我们审查的短暂时间内，机构群体利益相关者也发现了新的妥协、新的威胁因素和新的知识。”

袭击不断发生。正如 VMware 全球安全技术专家 [Chad Skipper](https://www.linkedin.com/in/chadskipper/) 所言，“自 2022 年 1 月以来， [VMware NSX 网络检测和响应](https://www.vmware.com/products/nsx-network-detection-response.html)已经跟踪了超过 2500 万次针对 Log4j 的漏洞利用尝试。”还有更多的组织没有任何安全系统来保护和跟踪他们的问题。

## Log4j 无处不在

为什么 Log4j 如此令人头疼？首先，它是一个非常流行的、开源的基于 Java 的日志框架。所以它已经被嵌入到成千上万的其他软件包中。那不是打字错误。Log4j 在成千上万的程序中。雪上加霜的是，由于被间接依赖调用，Log4j 经常被深深地嵌入到代码中并隐藏起来。

因此，CSRB 指出，“维权者面临着特别具有挑战性的处境；该漏洞几乎影响了所有联网的组织，威胁的严重性要求采取快速行动。”更糟糕的是，根据 CSRB 的说法，“Log4j 没有一个全面的‘客户列表’，甚至没有一个它作为子系统集成到哪里的列表。”

欢迎来到我们如何使用开源代码。这是[软件材料清单(SBOM)变得对保护软件供应链](https://thenewstack.io/securing-the-software-supply-chain-with-a-software-bill-of-materials/)至关重要的一个重要原因。

因此,“企业和供应商争相发现他们在哪里使用 Log4j。速度、压力和宣传加剧了防御挑战:安全研究人员很快在 Log4j 中发现了额外的漏洞，导致了混乱和“修补疲劳”；CSRB 说:“防御者很难区分真正的研究人员进行的漏洞扫描和威胁行为者，响应者发现很难找到关于如何解决这些问题的权威信息来源。”。

来自开源社区的最佳响应者在周末和 12 月的假期工作时进行合作。他们很大程度上成功地找到并修复了漏洞。然而，CSRB 声称，“很少有组织能够按照需要的速度或效率执行这种反应”。问题的一部分是，部署补丁“也是一个风险决策，迫使在可能的操作中断与及时性、完整性和补偿控制之间进行权衡。”

## 你能做什么

那么，我们能做什么呢？CSRB 有很多如何保护自己的好建议。其中大部分，你已经——或者至少你应该——知道了。

但是如果你还没有这样做——我知道你们中的一些人还没有——现在是时候了。毕竟，正如 CSRB 委员会所言，Log4j 是一个“地方性漏洞”，“Log4j 的易受攻击实例将在未来许多年内留在系统中。”

目前，我的最后一句话来自谷歌基础设施副总裁埃里克·布鲁尔。“如果你使用开源，你不能指望其他人神奇地为你修复安全问题，”如果你使用开源代码——谁没有呢？—你也必须帮助维护和修补它的问题。我们都在一起。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>