# SPDX 软件供应链规范成为 ISO 标准

> 原文：<https://thenewstack.io/spdx-software-supply-chain-spec-becomes-an-iso-standard/>

唉，你们很多人都没听说过[软件包数据交换(SPDX)](https://spdx.dev/) 。这很遗憾，因为 SPDX 将把我们从[软件供应链攻击](https://thenewstack.io/supply-chain-attacks-and-cloud-native-what-you-need-to-know/)的痛苦中拯救出来，比如[太阳风](https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/)。幸运的是，虽然我们大多数人都没有注意到，但 Linux 基金会和英特尔、微软和 VMware 等企业一直在推动它向前发展，现在 SPDX 已经成为国际标准化组织(ISO)的标准: [ISO/IEC 5962:2021](https://www.iso.org/standard/81870.html) 。

这一切都要追溯到 2010 年，当时作为[吉姆·泽姆林](https://www.linkedin.com/in/zemlin/)，当时也是现在的 [Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)的执行董事解释说[公司需要一种标准的方式来标准化他们的许可证和物料清单](https://www.computerworld.com/article/2468757/linux-foundation-launches-major-open-source-license-compliance-program.html)中的组件信息(元数据),以便于发现和标记他们产品中的开源组件。

当时，人们主要关注的是为开源许可创建一个供应商中立的、非商业的合规性计划。虽然这仍然很重要，但 SPDX 也已经成为在策略或工具中保护[软件材料清单(SBOM)](https://www.ntia.gov/SBOM) 信息的开放标准，以确保全球软件供应链的合规、安全开发。

“在整个供应链中，SPDX 在如何创建、分发和消费软件方面，在建立更多信任和透明度方面发挥着重要作用。从事实上的行业标准到正式的 ISO/IEC JTC 1 标准的过渡，使 SPDX 在全球舞台上的采用大幅增加，”Zemlin 在上周的一份声明中说。“SPDX 现在完全有能力支持整个供应链的软件安全性和完整性的国际要求。”

男孩，我们需要这个。开源软件尤其如此。而且，让我们面对现实吧，因为 90%的现代应用程序都是由开源软件组件组装而成的，这是至关重要的。此外，尽管 SPDX 的 SBOM 最初是为开放源代码和许可证设计的，但它同样适用于专有程序或其他第三方程序。

有了通用的 SBOMs，我们可以跟踪和追踪软件供应链中的组件。这让我们更容易识别软件组件问题和风险。它还为我们提供了一个解决他们的许可或安全问题的起点。

软件组合分析(SCA)供应商已经认识到了这一点，并一直在采用 SPDX。SCA 工具执行自动化的应用程序代码库扫描，以识别其开源组件、许可证合规性数据和安全漏洞。

正如 Gartner 最近在[的软件组合分析技术洞察](https://www.sonatype.com/2019-gartner-sca)中指出的那样，“组织应该通过强化软件供应链来降低风险。这包括检查内部和外部来源的代码(以及支持脚本、配置文件和其他工件)，以及创建可信组件的内部存储库。它还包括管理外部存储库的使用。”

因此，Gartner 预测，“到 2024 年，软件供应商提供详细、定期更新的软件材料清单将是至少一半企业软件购买者不可协商的要求，高于 2019 年的不到 5%。”我想会更快。SPDX 使之成为可能，网络安全管理软件产品用红色强调了了解我们的软件供应链中的内容是多么重要。

此外，正如[奥立佛·芬特](https://www.linkedin.com/in/oliver-fendt-9558a14/)所指出的，“SPDX[已经成为]标准是很自然的，因为它已经成为事实上的标准达十年之久。这将使供应链中的许可证合规性变得更加容易，特别是因为一些开源工具，如 [FOSSology](https://www.fossology.org/) 、ORT、 [scancode](https://github.com/nexB/scancode-toolkit) 和 [sw360](https://www.eclipse.org/sw360/) 已经支持 SPDX。”

除了帮助开发人员保护他们的代码，SPDX 还有很好的商业价值。正如 [Mark Gisi](https://www.linkedin.com/in/markgisi/) 、 [Wind River](https://www.windriver.com/) 开源项目办公室主任和 [OpenChain](https://www.openchainproject.org/) 规范主席所观察到的，“基于 SPDX 的标准化使我们能够以更低的成本交付更高质量的 SBOM。”

如果您也想从 SPDX 中受益，那么现在是时候在您自己的代码和测试中采用它了。你会很高兴你做了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>