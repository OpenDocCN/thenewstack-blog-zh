# OSPO 如何帮助保护您的软件供应链

> 原文：<https://thenewstack.io/how-an-ospo-can-help-secure-your-software-supply-chain/>

如今，不使用开源代码来构建软件几乎是不可能的。但是所有这些自由软件都带有额外的安全风险。

组织努力解决[如何最好地保护他们的开源软件供应链](https://thenewstack.io/the-challenges-of-securing-the-open-source-supply-chain/)。但是还有另一个问题:许多公司甚至不知道他们有多少开源应用——或者里面有什么。

最糟糕的情况包括像 2021 年的 [Log4j 安全漏洞](https://thenewstack.io/log4j-is-one-big-i-told-you-so-for-open-source-communities/)或发生在[网络安全管理软件产品](https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/) ' [专有猎户座网络监控产品](https://www.fireeye.com/blog/products-and-services/2020/12/global-intrusion-campaign-leverages-software-supply-chain-compromise.html)的崩溃，该产品在 2020 年感染了恶意软件。

根据 VMware Tanzu 的开源营销和战略总监 Suzanne Ambiel 的说法，对于构建和发布软件的公司来说，最佳实践是“发布你所知道的和你所知道的”。“发货清单”同样适用于开源代码和专有代码。

“你的顾客和用户群体相信你提供给他们的是好的、干净的和安全的，”她说。“他们相信你已经完成了艰苦的工作，并且你知道你的软件里有什么。”

为了控制使用开源软件的潜在风险，公司需要清楚地了解在他们的环境中使用了什么开源代码，及时更新补丁，甚至在必要时进行他们自己的漏洞扫描和评估。

一个开源项目办公室(OSPO)——一个由你组织内的开源专家组成的局，专门监督你的公司如何使用、创造和贡献自由软件——可以帮助协调所有这些努力。

Constellation Research 的副总裁兼首席分析师 Liz Miller 说，OSPO 可以帮助一家公司掌握它所使用的开源代码，并建立对开源项目和工具的可见性。

“从根本上说，开源项目办公室的目的是在整个企业范围内集中对开源代码的依赖性、实现和利用的理解，”米勒说。" OSPO 具有显著的安全优势."

## 你的开源代码里有什么？

今天的软件是由各种来源的组件组成的。“从来都不是 100%的一件事，”VMware 的 Ambiel 说。

“有些代码是你第一次写的，所以你显然知道里面有什么。但是你可能用过一些容器化的软件。你将会重用一些代码。而且大家都用开源代码。”

最近的研究在企业到底使用多少开源代码的问题上存在分歧，但确实很多:

可怕的是:在 Synopsys 的分析中，84%的代码库至少有一个漏洞。在过去的两年中，91%的开源组件都没有维护过。

米勒说，即使是已经流传多年、被数百万人看到和使用的开源代码，也可能包含隐藏在代码深处的漏洞。

“开源的现实是，对于安全专业人员来说，听到软件供应链充满了未经检查、未知和完全看不见的开源代码是噩梦的素材，”她说。

这就是为什么软件需要有一个[“材料清单”，](https://thenewstack.io/securing-the-software-supply-chain-with-a-software-bill-of-materials/)Ambiel 说，这是一个软件包中所有组件的完整清单，以及它们的版本和许可条款。

在这方面发生了很多事情。她说，T2 OSPO T3 可以帮助公司掌握最新的建议。

例如，去年 5 月，拜登总统发布了一项行政命令[，要求向联邦政府提供软件的供应商提供软件材料清单(通常称为 SBOM](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/) )。

两天后，[云本地计算基金会(CNCF)](https://cncf.io/?utm_content=inline-mention) 发布了一份最佳实践白皮书，建议[所有供应商尽可能提供一个 SBOM](https://www.cncf.io/announcements/2021/05/14/cncf-paper-defines-best-practices-for-supply-chain-security/)，并提供清晰直接的依赖关系链接。

CNCF 白皮书还建议公司用软件合成分析工具扫描他们的软件，以检测易受攻击的开源组件，并使用渗透测试来检查基本的安全错误或漏洞以及对标准攻击的抵抗力。

> 公司需要清楚地了解他们的环境中使用了哪些开源代码，及时更新补丁，甚至在必要时进行自己的漏洞扫描和评估。OSPO 可以帮助协调这些努力。

最近，Linux 基金会[发布了一份报告](https://www.linuxfoundation.org/tools/the-state-of-software-bill-of-materials-sbom-and-cybersecurity-readiness/)，为软件供应链的最佳实践管理提供了额外的见解和建议。

有了内部 OSPO，该办公室的专业人员可以帮助开发人员了解创建 SBOM 的最佳实践，还可以帮助建立[软件数据包交换(SDPX)标准](https://thenewstack.io/spdx-software-supply-chain-spec-becomes-an-iso-standard/)，这是 SBOM 信息交流的方式。

它还可以帮助开发者跟上新出现的概念，如软件供应链完整性的新框架，称为软件工件的供应链水平，或由谷歌与 OpenSSF 合作于 2021 年推出的 [SLSA](https://slsa.dev/) 。

Ambiel 说，跟上这些最佳实践是一项挑战。“作为一名开发人员已经够难了，让他们接受这一挑战会让他们远离他们试图构建的应用程序或产品。”

Ambiel 说，OSPO“可以带来最佳实践，并以可能的最佳方式应用它们，考虑到你所在的公司和你所做的软件开发”。

## 保护开源软件免受攻击

根据 9 月份发布的 Sonatype 公司的软件供应链状况报告，与 2020 年相比，去年对开源软件供应链的攻击增加了 650%。

这是在 Log4J 漏洞曝光之前，被安全研究人员称为多年来最危险的 Java 漏洞。

OSPO 可以帮助开发人员跟上开源安全领域的新发展，构建更安全的应用程序，同时还能及时获得所需的更新和补丁。

软件是不断变化的，对于公司来说，跟上这些变化是一个持续的挑战。OSPO 还可以帮助创建和维护与开源社区的联系，这些社区跟踪软件的最新变化，这些联系可以帮助公司保持领先地位。

“今天的当前是明天的技术债务，”Ambiel 说。“这是一项大工程。但当涉及到这些大的生态系统挑战时，这就是开源社区真正闪光和可以加强的地方。”

保持对代码变化的掌控是每个人都有的问题，她说:“没有人被排除在外。每个人都必须注意这一点。”

她补充说，当公司对来自公司边界之外的新想法敞开心扉时，就是最好的解决方案产生的时候。

例如，开源社区多年来一直致力于供应链安全性和合规性。Linux 基金会的 [Tern](https://github.com/tern-tools/tern) 项目检查集装箱图像，是其[自动化合规工具计划](https://www.linuxfoundation.org/press-release/the-linux-foundation-to-launch-new-tooling-project-to-improve-open-source-compliance/)的一部分。

> “今天的电流就是明天的技术债务。这是个大工程。但当涉及到这些大的生态系统挑战时，这就是开源社区真正闪光和可以加强的地方。”

—Suzanne Ambiel，VMware Tanzu 开源营销和战略总监

OSPO 还可以通过 OpenSSF 利用外部专业知识，OpenSSF 正在研究系统解决方案和方法，以打击日益增多的攻击，如域名抢注和恶意代码。

所有这些都很重要，因为攻击者变得更加主动，Linux 基金会开源供应链安全主任 David Wheeler 说。

他们直接将恶意软件注入软件源代码或可安装包中——有时，只是提交一个带有恶意软件的更新，并希望没有人注意到，或者通过窃取开发人员的密码。

“恶意代码注入是大多数人认为的一种攻击，但在实践中，它在开源软件中并不常见，”Wheeler 说。"尽管如此，当它发生时，可能是毁灭性的."

用恶意代码替换合法代码的最常见方法是在不同的存储库上创建一个重复的包。开发人员可能认为他们正在从自己的内部存储库中加载一个受信任的包，但是却从不同的公共存储库中加载了一个同名的包，因为它的发布日期更晚。

“域名抢注是另一种常见的攻击，”Wheeler 说。这是恶意包与真实包几乎同名的时候。"开发者使用了恶意的软件包——通常是因为开发者打错了字."

## OSPOs 和开源社区

为了防范这类攻击，Wheeler 建议公司更多地参与开源社区。

拥有 OSPO 有助于公司做到这一点。在 Linux 基金会的调查中，56%的参与者认为与开发人员社区合作是 OSPO 的主要责任，几乎 69%的人认为在内部推广开源文化是 OSPO 的主要责任。

如果一个开源项目对一个公司来说很重要，但是这个项目没有很多人审查代码升级，那么加入这个项目可能是有意义的。

“这样做的成本通常比试图独立开发和维护自己的软件要低得多，”惠勒说。

他还建议公司参与 OpenSSF，这是一个由许多致力于系统解决方案的组织组成的联盟，例如向软件开发人员分发多因素认证令牌。

“不同的组织可能会选择不同的方式来解决这些挑战，”惠勒说。“但 OSPOs 通常很适合提供帮助。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>