# Veracode:第三方代码如何影响软件安全性

> 原文：<https://thenewstack.io/veracode-how-third-party-code-impacts-software-security/>

如果看起来每一天都有另一个公告，威胁行为者已经成功地利用开源代码中发现的漏洞发起了网络攻击——想想 log 4 shell——这不只是你的想象。

现实是，企业和政府越来越认识到如果软件开发人员没有正确管理开源软件会带来的[挑战。随着这种意识的传播，我们可以期待看到更多的公司和组织试图以各种方式超越这些漏洞。](https://thenewstack.io/the-stone-ages-of-open-source-security/)

但是，即使组织在处理开源代码的方式上做出了急需的改变，理解第三方代码如何影响软件开发也是至关重要的。通过使用开源代码，开发人员可以获得由每一位长期贡献的开发人员所创造的创新。

这种社区感是一种相当大的吸引力，因为成百上千的开发人员可以为增强特性、功能甚至安全性献计献策。最重要的是，利用开源降低了前期成本，使企业能够更快地创新。

尽管 Log4Shell 和其他攻击引起了负面关注，但这些好处继续推动开源的采用。事实上，根据开源倡议， [在过去的一年中，所有规模的组织和行业对开源的使用增加了 77%](https://www.openlogic.com/resources/2022-open-source-report)——其中 37%的人说他们显著增加了开源的使用。

然而，一项对 700 名软件开发人员和专家的调查显示，安全性是一个至关重要的问题，57%的人说安全性是应用程序开发团队在构建开源软件时面临的最常见的挑战。同样，30%的人说安全性也是他们面临的最紧迫的挑战。

我们在 [软件安全状态第 12 版](https://www.veracode.com/state-of-software-security-report) 中的研究同样表明，开源对于所有规模和行业的组织来说都是一个关键问题。因此，深入研究开源挑战如何影响开发人员和整个软件开发是值得的。

## 开放源代码的风险

在软件开发中利用开源代码有很多好处，使它受到开发人员的普遍欢迎。也就是说，理解它的风险也是值得的。以下是我们所知道的:

*   组织通常不会保存他们正在使用的所有开源代码的准确、最新的清单。如果他们不知道他们的软件中有什么代码，他们怎么可能知道什么需要修补呢？
*   虽然开发团队可以从使用开发人员社区贡献的代码中受益，但他们并不总是认为这些贡献可能包含漏洞——尽管事实上用开源代码构建的应用程序平均包含七个[漏洞。](https://www.veracode.com/security/dangers-open-source-risk)更令人担忧的是， [44%的公司存在可能导致重大违规的严重漏洞](https://www.veracode.com/security/dangers-open-source-risk)。
*   第三方库被视为一个潜在的攻击媒介，因为许多开发人员在代码编写和运行后会不经意地跳过更新库。事实上， [79%的时间](https://www.veracode.com/blog/research/announcing-state-software-security-v11-open-source-edition) ，开发者在将第三方库包含在一个代码库中之后，从来不会更新它们。毫不奇怪，开发人员希望尽可能快速、轻松地创建代码，然后继续下一个项目，因此没有太多的动力来更新已经发布的代码库。这就是潜在的安全风险。今天的大部分代码源自第三方库，但是在这些库中发现的漏洞被广泛忽视。然而，开源软件库不会消失。事实上，据估计今天超过 90%的代码可能来自开源库，这个数字预计还会继续增长。

## **开发者习惯如何改变**

在最新的 [软件安全状态](https://www.veracode.com/state-of-software-security-report) 中，我们查看了历史数据，以确定第三方代码与自主开发代码的数量，我们了解到大多数应用程序要么几乎全部由第三方代码组成，要么几乎全部由内部开发的代码组成。

[【SoSS v 12(第 21 页)](https://info.veracode.com/report-state-of-software-security-volume-12.html) 表明开发者倾向于使用久经考验的库，很少尝试重构他们的代码库来评估最新的贡献。然而，开发者现在面临着基于 [拜登政府关于改善国家网络安全](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/) 的行政命令(EO)应该对程序做出的改变，该命令概述了旨在改善软件供应链安全的措施。

虽然行政命令专门针对联邦政府使用的软件，但毫无疑问，它将很快渗透到私营部门。EO 呼吁建立严格的机制来确保软件供应链的安全性和完整性，特别是对于关键软件。具体来说，政府机构现在被要求提供软件材料清单(SBOM)，这是一个应用程序中涉及的所有组件和软件依赖关系的清单，包括开放源代码。

尽管毫无疑问，EO 中列出的建议和要求是迫切需要的，但开发人员不能在不了解需要什么、他们的责任以及如何确保他们符合要求的情况下，就只是打个响指并遵守这些更改。

## **降低风险**

像我们的 [Veracode 安全实验室](https://info.veracode.com/webinar-shift-application-security-knowledge-left-to-deliver-secure-code-on-time.html?utm_source=kuma&utm_medium=paid-search&utm_campaign=VER012T000001pJymQAE&utm_term=brand-security-labs&utm_content=deliver-secure-code-on-time) 这样的资源可以帮助开发人员更好地了解如何修复出现的缺陷，以及如何避免在未来产生新的问题。该培训平台为开发人员提供了使用各种编程语言的实际应用程序来利用和修复常见漏洞的实践经验。

事实证明，体验式学习是有效的！我们的分析表明，至少完成了其中一门课程的开发人员比没有受过培训的开发人员修复缺陷的速度更快。具体来说，使用 Veracode 安全实验室培训的组织修复缺陷的速度平均快了约两个月，补救时间减少了 35%。

Veracode 的 Continuous Software Security Platform 已得到增强，以进一步帮助开发人员降低与开源代码相关的风险，并满足保护软件供应链安全的新法规。该平台现在具有 SCA(软件成分分析)中的 SBOM API，使开发人员能够生成 CycloneDX JSON 格式的 SBOM，这是 EO 中注明的合规性的批准格式之一。

Veracode 的 SBOM API 提供了应用程序中组件的清单，可以洞察组件之间的关系并识别哪些组件来自第三方。然后，Veracode 的 SCA 提供补救指导并帮助管理许可证风险。

利用 SBOM API 可以帮助开发人员更好地了解组成他们的应用程序的“要素”,以确认他们使用的代码(包括开放源代码)没有漏洞。

随着组织和开发人员继续利用第三方代码，毫无疑问，我们将继续看到由于代码中的漏洞而可能发生的网络攻击。没有公司想成为下一个网络攻击的受害者，但所有公司都有成为受害者的风险。理解第三方代码重要性的精明组织必须在今天与开发人员合作，以确保他们理解潜在的危险以及如何减轻这些危险。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>