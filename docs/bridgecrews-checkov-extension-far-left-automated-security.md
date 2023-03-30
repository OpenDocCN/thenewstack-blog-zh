# Bridgecrew 的 Checkov 扩展:“极左”自动化安全

> 原文：<https://thenewstack.io/bridgecrews-checkov-extension-far-left-automated-security/>

帕洛阿尔托网络公司(Palo Alto Networks)最近同意收购的 DevSecOps 公司 Bridgecrew 已经扩展了其安全工具 [Checkov](https://www.checkov.io/) ,从开发周期的一开始就扫描代码和应用程序。

该公司声称，凭借其新的 [Visual Studio Code (VS Code)](https://code.visualstudio.com/) 扩展，Checkov 将自动提示开发人员代码是否不符合政策要求、配置错误或显示其他安全异常。Bridgecrew 说，这些自动通知会在“尽可能早的时刻”到达开发人员，例如，在代码上传到 git 之前，他们正在自己的机器上编写代码。

Bridgecrew 的首席技术官和联合创始人[巴拉克·肖斯特](https://il.linkedin.com/in/barakschoster)说，通过这种方式，VS 代码扩展缓解了开发人员编码下游的许多瓶颈和摩擦点。

“假设您确实在上游部署了基础架构代码扫描和/或云安全监控，如拉式请求、CI/CD 和运行时，基础架构配置错误和违反策略的情况最终会以某种方式回到开发人员那里。所以，问题就变成了:开发者想怎么打发时间？，”肖斯特问道。“我可以告诉你，这不是在构建失败后重新运行构建，也不是在 JIRA 票证和日志文件中进行梳理。因此，在某种程度上，这既是一个安全解决方案，也是一个生产力解决方案。”

Schoster 说，如果没有扩展，扫描会在提交前阶段停止，而扩展会“直接在 IDE 中编写代码时”提供扫描。

Schoster 说，Bridgecrew 的 Checkov 代码扫描因此可以嵌入到拉请求检查中，即 CI/CD 管道的测试和构建阶段，并且还可以在预提交时进行本地扫描。“这是 Checkov 能走的‘最左’了，”Schoster 说。提交前，代码仍在本地工作站上，尚未集成到共享存储库中，但此阶段的扫描需要在命令行中手动临时触发扫描

## 极右翼也在更新

当然，会出现新的漏洞和其他因素，因此在某些情况下，在生产周期开始时经过正确扫描后，糟糕的代码可能会被部署。Schoster 说，虽然将 VS 代码扩展描述为“有点像 Bridgecrew 的平台和开发工具套件中最后一个缺失的拼图”，但在 IaC 的上下文中，该扩展在开发周期中进一步编译时会继续扫描相同的代码。"因此，扫描可以引用其他模块和模板，这些模块和模板可能包含以前没有发现的错误."

> 在应用程序部署阶段发现的坏代码的补救成本是在维护阶段发现的 5 到 100 倍。

“Checkov 仅在 CI/CD 管道允许的范围内‘向右’扫描，并带有定制功能。Schoster 说:“另一方面，Bridgecrew 的 SaaS 平台在云环境中监控和扫描已经在生产中运行的代码，这是你能得到的最正确的结果。“这就是为什么在基础设施开发过程中的每一点都进行测试非常重要——无论您使用的是 Checkov 等所有开源工具和运行时工具，如 [Prowler](https://github.com/toniblyx/prowler) ，还是 Bridgecrew 的一体式平台，既可以进行 IaC 扫描，也可以进行云监控。

根据 Bridgecrew 引用的 IBM 系统科学研究所的一份[报告，修复代码中的一个缺陷的成本与缺陷在生产管道中被检测到的正确程度成比例增加。例如，与在开发阶段修复错误相比，在应用程序部署阶段发现的坏代码的修复成本是在维护阶段发现的 5 到 100 倍。](https://gist.github.com/Morendil/ebfa32d10528af04e2ccb8995e3cb4a7)

简而言之，在开发生命周期的更长时间里，错误的分类和修复变得更加昂贵和耗时。新的 VS 代码扩展背后的想法是在开发人员将代码集成到共享存储库或部署它之前，直接在开发人员的 IDE 中自动修复和违反策略的行为，”Schoster 说。“在现代分布式环境中，这并不意味着新问题不会在开发生命周期的后期出现，这就是为什么我们在整个 SDLC 中都有解决方案。但这里的想法是，你越早发现和补救问题，你浪费的时间(作为开发人员和组织的资金)就越少。”

[Bridgecrew](https://bridgecrew.io/?utm_content=inline-mention) 传达了该扩展提供的以下功能:

*   500 项内置政策，涵盖针对亚马逊网络服务、Azure 和谷歌云的安全性和合规性最佳实践。
*   [HashiCorp](https://www.hashicorp.com/?utm_content=inline-mention) 的 Terraform，以及 Terraform Plan，CloudFormation，Kubernetes，Helm，Serverless 和 ARM 模板扫描。
*   检测 EC2 用户数据、Lambda 环境变量和 Terraform 提供程序中的 AWS 凭据。
*   在 Terraform 中，检查支持对变量和远程模块中表示的参数进行评估，以得到它们的实际值。
*   策略描述的链接，包括修复已知错误配置的说明。
*   修正常见错误配置的地形和云结构属性的建议。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>