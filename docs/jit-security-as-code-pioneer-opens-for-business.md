# Jit:作为代码的安全先锋开始营业

> 原文：<https://thenewstack.io/jit-security-as-code-pioneer-opens-for-business/>

任何人都可以制定计划。把计划变成现实，那很难。Jit 是一家获得了 3850 万美元种子资金的初创公司，它有一个神奇的技巧，可以将复杂的安全计划从书面文件和电子表格转换成代码。

Jit 的首席技术官 [David Melamed](https://www.linkedin.com/in/mlmd/?originalSubdomain=il) 解释说，这背后的想法是“安全领导者正在添加更多的工具，比他们的团队能够实现、调整和配置它们的速度更快，以至于风险支出效率变得不一致。”

因此，与合规性复选框的实践相比，Jit 简化了工程团队的技术安全性，同时降低了开支。我们提供了实施 DevSecOps 的最简单方法，其中产品安全作为服务交付到 CI/CD 管道中，产品安全计划遵循 Git 原则，翻译成开发人员理解的语言:代码。"

### 使用 GitOps

怎么会？Jit 通过采用 [GitOps](https://thenewstack.io/getting-started-with-gitops/) 原则并将你的[产品安全计划](https://docs.jit.io/docs/the-plan-as-code-concept)存储在你的源代码管理平台中来做到这一点。您的安全计划是用 YAML 语言编写的，您可以在自己喜欢的 IDE 中查看和编辑它们。

每个计划都有一个指定的结果，并规定了实现该结果的具体安全措施。因此，您不必浪费时间重新发明轮子，您可以根据 Jit 的计划模板制定一个安全计划，并在您的环境中实现它。一旦你掌握了窍门，你就可以添加你自己的计划了。

### 最低可行安全

受[最小可行产品(MVP)](https://www.productplan.com/glossary/minimum-viable-product/) 概念的启发，Jit 使用最小可行安全性(MVS)作为一种精益、迭代的方法来添加“即时安全性”在 MVS 中，这是一个声明性的安全计划，您可以指定实现结果所需的安全工具和工作流。

但是你不能自己挑选工具。Jit 安全研究小组没有要求您成为一名开源安全专家，而是管理和选择了将为您的应用程序提供第一道防线的工具。

编排框架的插件架构采用了同类最佳的开源安全工具，如 [OWASP](https://owasp.org/www-project-dependency-check/) 依赖性检查、 [npm-audit](https://docs.npmjs.com/cli/audit/) 、 [GoSec](https://github.com/securego/gosec) 、 [Gitleaks](https://github.com/zricethezav/gitleaks) 和 [Trivy](https://github.com/aquasecurity/trivy) ，并将它们统一到一个简单一致的开发人员体验中。简而言之，Jit 提供了一个编排层来统一开源安全工具，同时将安全性作为代码体验原生集成到开发人员工作流中。

### 轻松自由

Jit 旨在像其他 as-code 工具一样简单，如[terra form Plan/terra form Apply](https://www.terraform.io/cli/commands/apply)。一旦为黄金时段做好准备，增加安全性将变得前所未有的简单。

该计划最终将自动编排安全工具和工作流程。目前，它还是测试版，各部分仍在整合中。Jit 的最终计划是提供一个简单的入口，将安全性引入开发人员和 DevOps 工作流。

在资金和增加有经验的专家到管理层之间，Jit 也许能够兑现它的承诺。例如， [Abby Kearns](https://www.linkedin.com/in/abbykearns/) ，前[傀儡](https://puppet.com/?utm_content=inline-mention) CTO 兼 Cloud Foundry Foundation 首席执行官正在为公司提供建议。

Jit 是免费的，可以作为一种[自助服务，让你今天就着手保护你的项目](https://platform.jit.io/login?distinctID=1802f8292b32e5-07795a84014b09-35736a03-13c680-1802f8292b4bf1&items=)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>