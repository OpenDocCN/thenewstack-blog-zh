# Veracode 的 SBOM API 简化了开发者的软件安全性

> 原文：<https://thenewstack.io/veracodes-sbom-api-simplifies-software-security-for-devs/>

[Veracode](https://thenewstack.io/adding-security-to-the-developers-workflow/) 通过新的集成、对[软件材料清单(SBOM)](https://thenewstack.io/securing-the-software-supply-chain-with-a-software-bill-of-materials/) 的支持和其他关键改进，增强了其云原生应用安全测试平台。

Veracode 的连续软件安全平台的新功能包括支持软件组合分析(SCA)的扩展集成、SBOM 应用程序编程接口(API)以及静态分析的附加语言和框架支持。使用 Veracode 等工具频繁扫描代码可以降低来自专有和开源漏洞(如 Log4j)的风险。

## 丢弃 SBOMs

“联邦政府 2021 年 5 月的行政命令强调了保护软件供应链的重要性以及软件材料清单在这一过程中的作用，”弗雷斯特研究公司的分析师[珍妮特·沃星顿](https://www.forrester.com/analyst-bio/janet-worthington/BIO18144)说。“从那以后，我们看到越来越多的政府机构和私营公司询问我们如何申请 SBOM。软件提供商也不甘落后，他们中的许多人现在主动生成 SBOMs。将 SBOM 生成工具集成到开发 CI/CD 流程中，使软件提供商能够在整个产品生命周期中灵活地生成和更新 SBOM。”

Veracode 的 SBOM API 使开发人员能够轻松地生成 [CycloneDX](https://cyclonedx.org/) JSON 格式的 SBOM，这是符合美国行政命令的[批准格式之一。这将有助于确认正在使用或构建的代码没有漏洞。](https://www.veracode.com/executive-order)

Veracode 的首席技术官兼联合创始人 Chris Wysopal 告诉 The New Stack:“随着开发人员今天构建大量开源代码，手动流程会降低开发人员和安全团队的速度。“引入 Veracode SBOM API 是为了在使用第三方组件时更容易提供可见性。通过从软件组合分析中去除手动清点步骤，资源和时间可以转而用于更快的更新和漏洞响应。”

此外，Veracode 的首席产品官 Brian Roche 表示，现代应用程序是组装的，而不是从头开始编写的。开源代码在审计的代码库中占很大比例，增加了安全风险和识别供应链风险的需要。他说，例如，97%的典型 Java 应用程序都是由开源库组成的。

罗氏在一份声明中说:“我们的 SBOM API 旨在使开发者更容易清点他们的代码库，包括第三方组件，使他们能够在新的漏洞出现时迅速采取行动。”“自从我们的持续软件安全平台在 5 月份推出以来，我们已经引入了一些额外的功能来满足开发人员的工作需求:集成开发环境(IDE)、代码存储库和命令行界面。这些创新旨在通过使平台对开发者更加友好来推动采用。”

沃星顿说，通过将 SBOM 一代整合到软件开发生命周期中，软件供应商获得了他们组装和打包的组件和库的可见性。

“当客户在销售和采购过程中要求 SBOM 时，这些做法使他们在竞争中获得了优势，”她指出。

## 新集成

与此同时，Veracode 引入了集成，使开发人员能够在他们熟悉的环境中工作，或者在他们工作的地方与开发人员见面。例如，Veracode Azure DevOps 扩展有一个新的 SCA 缺陷导入器，可以自动将缺陷导入 IDE，这使得查找和修复任何静态或 SCA 安全缺陷变得很容易。

Roche 表示，该公司还将发布 Visual Studio 代码扩展的 Veracode，该代码将提供关于漏洞、许可风险以及开源库和可传递依赖项的推荐版本的详细信息。

Veracode 的平台支持 100 多种语言和框架，包括用于云原生应用程序开发的语言和用于遗留资产的旧语言，如 COBOL。该平台的新版本增加了对 [Rails 7.0、Ruby 3.x](https://guides.rubyonrails.org/7_0_release_notes.html) 和 [PHP Symfony](https://symfony.com/) 的支持。

在一份声明中， [QAD 精密 GTTE](https://www.precisionsoftware.com/qad-precision-gtte) 的工程总监 [Peter Evans](https://www.linkedin.com/in/peter-evans-174367109/?originalSubdomain=ie) 说:“Veracode 为我们带来了一个完整的平台，将安全工具构建到我们的开发管道中，并帮助我们增长知识，以不断提高安全性。“Veracode 也非常适合，因为该平台可以在我们开发软件的 Spring 框架中扫描 Java 代码。我们已经从审查代码到将连续扫描集成到我们的日常管道中。安全威胁不会一成不变，Veracode 为我们提供了跟上最新漏洞和规则的工具。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>