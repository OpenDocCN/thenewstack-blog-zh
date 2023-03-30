# 软件供应链符合 Aqua 的链式工作台

> 原文：<https://thenewstack.io/software-supply-chain-compliance-with-aquas-chain-bench/>

我们今天都同意，我们真的需要知道你的软件供应链的情况。如果你不知道为什么我推荐你去看看网络安全管理软件产品安全事故和正在进行的 T2 垃圾站火灾。但是，一个好的、安全的软件链中有什么呢？云原生安全公司 [Aqua Security](https://www.aquasec.com/) 与[互联网安全中心(CIS)](https://www.cisecurity.org/) 联手创建了首个正式的软件供应链安全指南: [CIS 软件供应链安全指南](https://workbench.cisecurity.org/communities/142)。

该指南涵盖了五个软件供应链类别的安全基础知识。这些包括源代码、构建管道、依赖项、工件和部署。具体来说，例如，您的公共存储库必须有一个 SECURITY.md 文件，所有代码更改都必须由版本控制系统跟踪，并且第三方库必须经过验证。所有这一切都是为了支持一般的最佳实践，这些实践支持关键的新兴安全标准，例如[软件工件的供应链级别(SLSA)](https://slsa.dev/) 和[更新框架(TUF)](https://theupdateframework.io/) 。总共有 100 多条安全建议。

## 社区努力

除了这两家创作公司，该指南还受到了 Axonius、PayPal、CyberArk、Red Hat 和其他领先技术公司的安全专家的审查。这不是一个静态文档。它的创造者正在寻求反馈，以确保它保持准确和相关。

根据 CIS 开发团队经理 Phil White 的说法，长期计划是“建立一个有兴趣开发特定平台基准指南的充满活力的社区。”

## 链式工作台

但是假设你认真对待这些指导方针，并把它们融入到你的代码中。如何判断你的程序是否真的合格？带 Aqua Security 的[链台](https://github.com/aquasecurity/chain-bench)。这是一个开源工具，用于审计您的软件供应链，以确保遵循指导方针。

在 Apache 2.0 许可证的许可下，您可以将 Chain-Bench 作为命令行工具或在 Docker 容器中运行。它尽可能地实现了 CIS 软件供应链基准。您可以在[AVD–软件供应链 CIS–1.0](https://avd.aquasec.com/compliance/softwaresupplychain/cis-1.0/)下找到当前实施的检查。在这一点上，只有少数准则被检查。尽管如此，它每天晚上都会从链条工作台`metadata.json`文件中更新。希望它能很快变得更加全面。

Chain-Bench 的观点是，Aqua 的 Argon 技术安全总监 Eylam Milner 将“利用我们在软件供应链安全方面的专业知识，帮助为行业最紧迫的挑战之一建立关键的指导，以及帮助其他组织遵守它的免费、可访问的工具。”

指南和软件都在不断完善中。但这是一个好的开始。在认真对待软件供应链安全的其他人的帮助下，这可能最终为开源开发安全设置真正的标准。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>