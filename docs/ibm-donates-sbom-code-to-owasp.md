# IBM 向 OWASP 捐赠 SBOM 代码

> 原文：<https://thenewstack.io/ibm-donates-sbom-code-to-owasp/>

软件材料清单现在对程序安全性至关重要，IBM 正在通过向开放 Web 应用程序安全性项目捐赠两个开源项目来提供帮助。

IBM 为开放 Web 应用安全项目(OWASP)T1 贡献了两个开源项目，SBOM 实用程序和许可证扫描器。在那里，它们将被集成到 [CycloneDX](https://cyclonedx.org/) ，OWASP 的旗舰[软件物料清单(SBOM)](https://thenewstack.io/how-to-create-a-software-bill-of-materials/) 标准中。

SBOM 实用程序是一个 API 平台，旨在根据发布的模式验证 CycloneDX 或[软件包数据交换(SPDX)](https://spdx.dev/) 格式的 sbom。它还可以帮助验证需要更严格数据要求的衍生、“定制” [SBOM](https://thenewstack.io/sbom-everywhere-the-openssf-plan-for-sboms/) 模式。它可以评估和报告组件软件、服务和数据许可信息，以帮助组织根据可配置的使用策略进行风险评估。

## SBOM 公用事业和许可证扫描仪

SBOM 实用程序也可用于使用正则表达式(regex)对 CycloneDX SBOM 内容运行查询，并生成自定义报告。此外，它还支持 OWASP [软件组件验证标准(SCVS)](https://owasp.org/www-project-software-component-verification-standard/) 的工作，该标准定义了一个 BOM 成熟度模型(BMM)来帮助识别和降低软件供应链中的风险。最后，它可以用于处理[漏洞披露报告(VDR)](https://cyclonedx.org/capabilities/vdr/) 和[漏洞可利用性交换(VEX)](https://thenewstack.io/combining-sboms-with-security-info-chainguards-openvex/) 文档。

另一方面，许可证扫描程序扫描文件中的许可证和法律条款。它可用于从完整发布的 [SPDX 许可证列表](https://spdx.org/licenses)中识别文本匹配许可证和许可证例外。License Scanner 旨在集成到现有的 SBOM 软件中，[持续集成/持续交付(CI/CD)](https://practical-tech.com/2018/07/10/continuous-integration-and-delivery-tool-basics/) ，或者单独用作命令行实用程序。该工具根据 SPDX 许可证模板集扫描许可证文本，并返回包含三种表示许可证方式的 CycloneDX LicenseChoice 数据:SPDX 许可证 ID、SPDX 许可证表达式和许可证名称。

IBM 一直在自己的 [CI/CD](https://thenewstack.io/ci-cd/) 服务、 [IBM Cloud 的持续交付](https://www.ibm.com/cloud/continuous-delivery)和 DevOps 工具链中使用许可证扫描仪。它还被用于 IBM 的开源软件和公司软件的法律许可过程中。简而言之，它已经过实战考验，随时可以部署。

这两个工具都是用 [Go](https://thenewstack.io/go-1-18-the-programming-languages-biggest-release-yet/) 编写的，以利用该语言内置的类型强制和内存安全特性，以及为广泛的目标平台和架构编译并与云原生平台兼容的能力。

OWASP 的执行董事 Andrew van Der Stock 感谢 IBM 的捐赠。Van Der Stock 说，“根据定义的模式进行验证是一项重要的完整性控制，扫描代码以识别许可证的能力对于一些用例来说至关重要。对于许多合并和收购，能够快速准确地识别代码中存在的许可证决定交易的成败。

因此，这些捐赠不仅有助于希望通过 SBOMs 保护其代码的开发人员，也有助于高层的合并和收购。这是一对开源捐赠，会帮助到大家。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>