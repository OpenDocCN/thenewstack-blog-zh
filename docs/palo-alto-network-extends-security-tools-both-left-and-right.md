# Palo Alto Network 左右扩展了安全工具

> 原文：<https://thenewstack.io/palo-alto-network-extends-security-tools-both-left-and-right/>

为了加快部署速度，开发团队还必须面对意想不到的安全风险。当开发速度比安全性更重要时，如果没有采取适当的措施来实现安全策略和监控，这个问题会更加突出。

一种解决方案是在生产周期的开始就嵌入安全流程和检查，以不降低部署速度的方式实现自动化。这主要是通过自动化和策略以及使用正确的工具和插件来完成的。与此同时，部署后的漏洞仍然可能发生，当然，包括 CVEs 或其他问题，因此强调了自动化和改进安全监控的需要。

帕洛阿尔托网络公司(Palo Alto Networks)本周向其 Prisma Cloud 原生安全平台(Prisma Cloud Native security platform)推出的工具和更新可以在生产周期的最开始(左移)以及应用程序的整个部署和运营周期中作为安全代码的潜在解决方案，该公司表示。

Palo Alto Networks 希望通过多种方式帮助减轻当今“快速失败，经常失败”环境中固有的风险。这包括“在 Kubernetes 和 Multicloud 的时代，联合扫描基础设施和应用程序代码对于高效的开发至关重要，因为应用程序和基础设施之间的接口是黑客入侵和破坏这一天的绝佳来源，”[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 说。

Volk 说:“手动验证基础设施代码是一项棘手的工作，非常耗费人力，因为您需要考虑每个潜在部署平台的细节。

Palo Alto Networks 计划在 4 月下旬添加或更新特定工具和插件，以帮助开发运维团队提升左移和部署后安全功能，包括:

*   基础架构代码(IaC)扫描:使用现成的可定制策略扫描 IaC 模板，以发现不安全的配置。
*   集中 CI/CD 策略管理:直接从 Prisma Cloud dashboard 设置策略来管理持续集成(CI)和持续交付(CD)工作流，以实现云原生安全性和整合云风险管理。
*   Amazon 机器映像(AMI)扫描:在部署 AMI 之前扫描 AMI 中的安全问题，同时提供对云应用程序安全状况的可见性。
*   AWS Lambda 的自动无服务器保护:通过自动无服务器应用程序保护来保护 AWS Lambda 功能。

Palo Alto Networks 负责产品管理、容器和无服务器安全的副总裁 [John Morello](https://www.linkedin.com/in/john-morello/) 表示，以下版本中描述的云原生安全平台(CNSP)的这些更新对 DevOps 非常重要，主要是为了帮助“可能不像安全团队那样拥有安全的 DevOps 团队”。

Morello 说:“许多开发人员和 DevOps 工程师希望发布高质量的代码，尽可能避免重大的安全问题。随着 Prisma Cloud 的最新发布，Palo Alto Networks 正在扩展其对 IaC 扫描的支持-与领先的 IDEs、GitHub 和 CI 工具集成-以使“DevOps 团队能够更好地了解其云基础设施资源的安全状况，作为其常规部署工作流的一部分，”Morello 说。“这些功能扩展了我们现有的扫描主机、集装箱图像和功能的覆盖范围，”Morello 说。

具体到主机，Palo Alto Networks 正在扩展 Prisma Cloud 的功能，以扫描 Amazon 机器映像，就像扫描任何容器注册表或无服务器 repo 一样。Morello 说:“这使开发运维团队和安全团队能够在部署前和生产中更好地了解他们的非盟特派团的安全状况。" AMIs 的新功能扩展了我们现有的主机漏洞管理、合规性和运行时安全性解决方案."

Morello 说，Palo Alto Networks 还将其 CI/CD 策略启用功能扩展到其控制台中，以帮助简化安全团队实施管理 DevOps 工作流的策略的流程，而无需配置 Jenkins 插件或 CI 脚本。“这将使开发人员和 DevOps 团队能够更轻松地发布和查看他们代码的安全状态，而不必在他们的工具中配置安全策略，”

用户还可以使用 Prisma 云控制台或 API 通过 Lambda 层自动部署 Defender。它通过“无需开发人员或 DevOps 团队将此代码作为其功能或部署工作流的一部分来实现”来实现这一点

“对于 AWS Lambda 上的无服务器，我们正在减轻 DevOps 团队的额外安全负担，”Morello 说。“这使安全团队能够轻松保护功能，而不会给开发人员带来不必要的要求和步骤。"

Volk 说，Lambda 的自动无服务器保护有助于解决一个关键的痛点，即通过“工具”一致地监控和保护无服务器代码。Volk 说:“如果没有自动插装，那么对于那些急于在截止日期前忘记插装包装的开发人员来说，大门永远是敞开的，这样就产生了一个盲点，这个盲点可能会在阴影中存在很长一段时间，只是为了在最方便的时候露出丑陋的一面。”。

Volk 说，如上所述，集中 CI/CD 策略管理解决了频繁应用程序发布更频繁且更安全地完成的主要原因。Volk 说:“每一种方法都伴随着安全性和合规性的开销。“在一个仪表板中集中 CI/CD 策略报告和执行是一件棘手的事情，因为有许多特定于领域的技术和业务需求需要考虑，但如果 Palo Alto Networks 能够实现这一点，这将是朝着能够持续发布软件而不是通常的预发布狂潮迈出的重要一步。”

Palo Alto Networks 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>