# 利用 DevSecOps 平台建立软件供应链信任

> 原文：<https://thenewstack.io/build-software-supply-chain-trust-with-a-devsecops-platform/>

大型组织的软件开发人员不断面临新的安全性和合规性要求的挑战，这些要求旨在提高他们的应用程序开发和交付流程的安全性。

然而，这些新的和不断变化的安全性和合规性要求是由安全团队编写和实现的，这些团队没有考虑到他们的[开发人员的工作流程](https://tanzu.vmware.com/content/ebooks/securing-cloud-applications?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS6)。作为处理这一问题的一种方式，[将安全转移到左边](https://thenewstack.io/golden-paths-start-with-a-shift-left/)的想法已经得到普及，但即使这样，如果没有正确实现，它也会导致开发人员生产力的损失和软件安全性的降低。

很明显，仅仅“向左转移安全性”是不够的，因为这样做通常会将额外的负担或决策转移给开发人员，这会分散他们编写代码的注意力。

专注于由平台和安全工程师设置的自动化控制和工具[的端到端方法可以帮助减少工作量，让开发人员专注于创建推动业务和收入的应用。](https://thenewstack.io/vmware-targets-the-platform-engineer/)

我们需要改进[软件供应链安全](https://tanzu.vmware.com/what-is-a-secure-software-supply-chain?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS6)流程的自动化，以帮助开发人员从构建时间到生产管理这些需求。企业开发人员需要有工具来提供清晰和智能的护栏，这些护栏可以持续应用，无需人工干预，使他们能够专注于[业务价值](https://thenewstack.io/vmware-to-be-acquired-by-broadcom-in-a-61-billion-deal/)。

当谈到建立一个安全的软件供应链时，我们应该关注以下五个期望的结果。

## 以开发人员为中心的漏洞管理

在构建应用程序时，开发人员、平台运营商和安全专业人员希望监控整个软件供应链中的漏洞。当在管道的不同阶段使用多个漏洞扫描器，并且不同的团队被通知并被要求在没有适当协调的情况下采取行动时，挑战就来了。

注重安全的[应用程序平台](https://thenewstack.io/vmware-tanzu-application-platform-a-portable-paas-for-kubernetes/)可以内置扫描流程，不仅可以检测漏洞，还可以将这些发现映射到工作负载。这个特性允许开发人员在应用程序的整个生命周期中识别问题，并帮助他们解决问题，将责任转移到更高程度的自动化上。此外，该平台可以通过展示应用程序开发人员的表现并帮助他们了解团队面临的风险，来建立与安全分析师的信任。

> 通过正确的自动化，应用平台可以帮助组织通过建立对应用及其运行时环境的更丰富的理解来减少噪音。

一旦平台在构建时和运行时检测到这些漏洞，它需要帮助开发人员筛选和修复它们。这反过来又减少了所有安全扫描器所带来的麻烦，并将分析和工具推给最了解他们软件的人，即开发人员。工程团队可以对供应链中发现的漏洞进行分类，并利用平台自动化来重建其映像，从而减少任何潜在的可利用问题。

由于缺乏协调和警报映射，所有企业的工程团队都[淹没在安全警报](https://tanzu.vmware.com/content/blog/cloudnativesecuritycon-2023-takeaways?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS6)中。然而，通过正确的自动化，应用程序平台可以帮助组织通过建立对应用程序及其运行时环境的更丰富的理解来减少噪音。拥有这种自动化可以从根本上减少开发人员的工作量，并改善团队的安全状况。

## 可证明的软件供应链完整性

自从大型软件供应商披露多个软件供应链漏洞以来，很明显，作为一个行业，我们需要改进我们的应用程序完整性流程。

安全框架 [SLSA](https://slsa.dev/) 和 [sigstore](https://www.sigstore.dev/) 的发布和越来越多的采用已经帮助开发团队改进了他们的完整性工作。也就是说，创建一个满足 [SLSA](https://slsa.dev/spec/v0.1/levels) 要求并从开发到生产实现严格签名的软件供应链仍然是复杂的。

平台团队可以创建自动化供应链，帮助开发者实现 SLSA 合规。特别是，希望实现这一目标的工具和[平台工程师](https://tanzu.vmware.com/platform-engineering?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS6)可以专注于对他们的构建过程进行基本控制，例如:

*   拥有完全脚本化和可复制的交付管道(像 [Jenkinsfile](https://www.jenkins.io/doc/book/pipeline/jenkinsfile/) 或 [GitHub Actions workflow](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions#create-an-example-workflow) )
*   使用生成认证出处信息的构建服务
*   要求对所有变更进行两人审核(这只是 SLSA 第 4 级的一项要求，但这是一项通用的最佳实践)

有了这些控制，团队就可以实现 SLSA 第二级，而[提升到第三级](https://slsa.dev/spec/v0.1/requirements)，构建系统可以验证出处信息。

SLSA 仍在开发中，社区也在不断改进实施方案。

## 证明

供应链证明使开发人员能够展示他们的软件从构建时到运行时的完整性。它是关于软件工件集合的经过验证的元数据，可以用来验证它们的出处。SLSA 为软件认证创建了一个[模型，平台团队可以用它来帮助开发者证明他们代码的来源。](https://slsa.dev/attestation-model)

[toto](https://in-toto.io/)是 SLSA 使用的证明模型的实现。它可以与 GitHub Actions 等构建工具一起使用，来创建和验证关于应用程序构建过程的证明。

一旦团队实现了经过身份验证的证明，他们就可以使用它们来验证构建过程中的多个步骤。例如，他们可以证明构建发生在可信的构建系统中，或者工件通过了企业批准过程。

创建所有证明后，生产环境可以自动验证在部署应用程序之前是否采取了所有必需的步骤，而无需手动干预，并且具有加密验证提供的信心。

## 安全集成是关键

应用平台需要与多种不同的工具协同工作，从漏洞扫描器到[监控解决方案](https://www.vmware.com/products/aria-operations-for-applications.html?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS6)。与其他工具的集成对于帮助团队交付安全的系统至关重要。

集成需要成为平台的核心特性。安全是一项团队运动，当构建自动化来帮助开发、运营和安全团队时，您希望所有的参与者一起工作。

> 一个以安全为中心的应用程序平台应该集成和协调诸如漏洞扫描、动态应用程序扫描、运行时应用程序保护等工具。

根据最新的 [Panaseer 安全领导者同行报告](https://panaseer.com/reports-papers/report/2022-security-leaders-peer-report/)，安全团队平均使用 76 种不同的工具。这些工具中的一些需要开发团队的输入和交互，但是企业很少具有编排能力来在正确的时间为工程师提供正确的信息。即使有了“左移”计划，开发人员也不得不使用多种工具和仪表板，这最终会增加工作量。

以安全为中心的应用平台应该集成和协调漏洞扫描、动态应用扫描、运行时应用保护等工具，以便在正确的时间为开发人员提供正确的信息。此外，让集成提供有关应用程序安全状况的信息可用于创建策略和执行自动化防御任务，从而提高整体安全性并减少合规性负担。

## 具有跨环境策略、合规性工作流的智能护栏

像 [OPA](https://www.openpolicyagent.org/) 和 [Kyverno](https://kyverno.io/) 这样的工具已经帮助将应用环境的合规性管理提升到了以前从未考虑过的水平。这些工具帮助平台运营商为开发人员设定界限，以确保他们遵守监管框架和企业要求，而无需手动审查。

平台团队可以利用这些工具来创建足够灵活的护栏，以便开发人员在其中工作，同时为组织中所有不同的团队提供适当的信任级别。

基于以前的工具，如漏洞管理、完整性检查、证明和集成，平台团队可以创建一组丰富的策略，为在给定环境中部署的工件提供很大程度的信心。拥有这些工具可以增加开发人员、[平台工程师](https://tanzu.vmware.com/content/analyst-reports/technology-trends-for-2023-platform-engineering?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS6)和安全团队之间的信任，而不必使用手动流程。

有了这些适应性强的规则，团队可以将精力集中在交付应用程序上，而不必手动证明应用程序的安全性和合规性。

## 了解更多信息

在他的书《保护云应用》中，Adib Saikali 提供了根据开发人员的经验编写的见解、示例代码和架构。你可以在这里免费阅读和下载这些章节。虽然这里没有详细提及，但内部开发人员门户被证明是平台工程、安全和运营团队确保开发人员使用最安全和最新工具的一个好方法。

要了解更多关于内部开发者门户的价值，请查看这个 [Gartner Tech Insights 报告](https://tanzu.vmware.com/content/analyst-reports/innovation-insight-for-internal-developer-portals?utm_source=thenewstack.io&utm_medium=referral&utm_content=TNS6)。与此同时，有多种工具可以通过应用程序级的可观察性和漏洞数据来增强应用程序开发过程中的安全性。

虽然这些工具是必要的，但它们应该包含在应用平台中，更重要的是提供可操作的数据，正如 Kara Yimoyines 在[这个 KubeCon 演讲中强调的](https://www.youtube.com/watch?v=4dg7jJDo9tU.)。

如果平台工程的想法对你来说是新的，看看这篇关于如何构建一个平台的白皮书，它将真正帮助你的开发者更快地交付高质量的软件。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>