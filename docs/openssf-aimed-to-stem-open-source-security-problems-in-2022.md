# OpenSSF 的目标是在 2022 年阻止开源安全问题

> 原文：<https://thenewstack.io/openssf-aimed-to-stem-open-source-security-problems-in-2022/>

2022 年是开源安全问题重重的一年，但与此同时，[开源安全基金会(OpenSSF)](https://openssf.org/) 尽最大努力帮助保护重要的编程基础设施。

在 2021 年，而不是 2022 年，开源软件安全出现了大问题。当然，我指的是 [Log4J 漏洞](https://thenewstack.io/one-year-of-log4j/)。已经一年多了，还在徘徊。这反过来让开发人员和安全世界之外的人意识到软件供应链的危险。我曾预测，2022 年，开源和 Linux [开发者会更加重视安全性。看来我是对的。](https://www.zdnet.com/article/in-2022-security-will-be-linux-and-open-source-developers-job-number-one/)

## 国家安全问题

为了满足这些安全需求， [OpenSSF](https://thenewstack.io/the-open-source-security-foundation-looks-to-unite-and-conquer/) 和众多其他开发者，包括 Apache、Google、Apple 和 AWS，在白宫与美国政府的行政部门会面。正如白宫国家安全顾问杰克·沙利文(Jake Sullivan)在召集会议时所说，志愿者维护基础开源软件是一个“国家安全问题”。

好吧。是的，我们开源社区知道这一点。当然，这并不像专有软件开发公司已经给自己披上了荣耀。

随后，IBM 的企业安全主管杰米·托马斯说:“政府和行业可以共同努力来改善开源软件的安全实践。”这始于“鼓励广泛采用开放和合理的安全标准，确定应满足最严格安全要求的关键开源资产，并促进国家合作努力，以扩大开源安全方面的技能培训和教育，并奖励在该领域取得重要进展的开发者。”

这就是谷歌和 Alphabet 全球事务总裁肯特·沃克(Kent Walker)在博客中写道:“(T2)开源软件是网络世界的一个结缔组织(T3)——它值得我们给予道路和桥梁同样的关注和资助。”鉴于 T4 总统拜登的建设美国更好的基础设施法的缓慢推出，这让我感觉并不好。

## 2022 年的举措

尽管如此，OpenSSF 在 2022 年通过众多举措迎接了挑战。

例如，当 OpenSSF 在 5 月举办了第二届[开源软件安全峰会](https://www.linuxfoundation.org/press/press-release/linux-foundation-openssf-gather-industry-government-leaders-open-source-software-security-summit)时，它将来自公司的高管和美国联邦政府领导人聚集在一起，就提高开源软件的弹性和安全性的关键行动达成共识。这就是[开源软件安全动员计划](https://openssf.org/oss-security-mobilization-plan/)。这列出了十个投资流，以立即改善开放源码软件的安全。它为此认捐了 3000 万美元。这不是一个完整的计划，但这是一个良好的开端，它详细说明了实现开源安全所需的资金，而不仅仅是好听的话。

在此之前，2022 年 2 月，OpenSSF 启动了 [Alpha-Omega 项目](https://openssf.org/community/alpha-omega/)。它的目标是“通过与项目维护者合作，系统地寻找开源代码中新的、尚未发现的漏洞”，然后修复它们，从而提高全球 OSS 供应链的安全性。特别是，“Alpha”旨在通过与最关键的开源项目维护者合作，帮助他们识别和修复安全漏洞，从而提高全球 OSS 供应链的安全性。“Omega”部分关注开放源码软件项目的长尾，帮助系统地发现和修复至少 10，000 个广泛部署的开放源码项目中的漏洞。到目前为止，[阿尔法-欧米茄](https://thenewstack.io/eclipse-plunges-into-oss-supply-chain-security/) [已经赞助了几个项目](https://thenewstack.io/alpha-omega-dishes-out-cash-to-secure-open-source-projects/)的关键安保工作。这包括给 [Rust 基金会](https://foundation.rust-lang.org/)的 46 万美元拨款，给 [Node.js](https://nodejs.org/) 的 30 万美元拨款，以及给 [Eclipse 基金会](https://www.eclipse.org/org/foundation/)的 40 万美元拨款。不管项目的细节如何，顶层的目标总是相同的:提高安全性。

动员计划的一个关键组成部分是使用软件材料清单(SBOM)作为基础构建模块，以改善 OSS 所有项目的安全态势: [SBOM 无处不在](https://github.com/ossf/sbom-everywhere)。它的第一个努力是资助一个[软件包数据交换(SPDX)](https://spdx.dev/) [Python 库的工作，以支持 SBOM](https://spdx.dev/an-update-on-the-spdx-python-tools/) 的创建和处理。鉴于 [Python 几乎每天都有成功的软件链安全攻击的列表](https://thenewstack.io/poisoned-lolip0p-pypi-packages/)，Python 可以使用它所能获得的所有安全帮助。

另一个工作组[漏洞披露工作组](https://github.com/ossf/wg-vulnerability-disclosures/security)正在起草一份新的漏洞披露指南。目前，追踪漏洞与其说是科学，不如说是艺术。最终，[漏洞利用交换(VEX)](https://www.cisa.gov/sites/default/files/publications/VEX_Use_Cases_Aprill2022.pdf) ，一个[网络安全和基础设施安全局(CISA](https://www.cisa.gov/sbom) )的工作规范，将提供机器可读的安全建议。

## 纯技术性的

纯技术方面，[安全工具 WG](https://github.com/ossf/wg-security-tooling) 发布了 [Fuzz 内省器](https://github.com/ossf/fuzz-introspector)。现在我们都有自己最喜欢的模糊工具——好吧，在我的圈子里，人们都有最喜欢的模糊工具，我的是[OSS-模糊](https://github.com/google/oss-fuzz)。你不能模糊一切——这是一种通过向程序提供意外输入来发现 bug 的自动化技术——因为你可能会遇到阻碍有效模糊化的路障(又名阻塞器)。Fuzz Introspector 为开发人员提供了可操作的见解，以识别阻塞，从而解决它们。

OpenSSF 供应链完整性工作组也致力于细化软件工件的供应链层次[(SLSA，发音为“salsa”)](https://github.com/slsa-framework/slsa)。这是一个标准和控制的清单，以防止篡改，提高完整性，并保护包和基础设施。草案已经公开，工作继续完善它的“版本 1.0”发布。

## 还有更多的事情要做

我认为在这里需要注意的是，尽管每个人都说，他们支持 SBOMs，在较小的程度上，也支持 SLSA，但我们还远远没有完善它们。在一个公司或团体的 SBOM 中的东西在另一个公司或团体中却不是。在它们像我们希望的那样有用之前，我们需要大量的标准化工作。

这实际上概括了 OpenSSF 的努力。他们有进步吗？哦，是的。他们到了吗？没有。我们有了一个好的开始。考虑到我们——这里的我们，我指的是所有参与编程的人——一直以来都把保护代码放在次要位置——这是一件好事。但是，还有更多的工作要做。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>