# Synopsys 快速扫描现在可以安全检查专有代码

> 原文：<https://thenewstack.io/synopsys-rapid-scan-can-now-security-check-proprietary-code/>

如果你从解决 Y2K 问题开始就没有编程，你可能不知道我们在供应链软件安全漏洞和攻击方面遇到了多大的麻烦。仍然不确定我的意思，去读读关于[太阳风安全惨败](https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/)。我会等的。明白了吗？因此，当 [Synopsys](https://www.synopsys.com/) 宣布在其 [Coverity 静态应用安全测试(SAST)](https://www.synopsys.com/software-integrity/security-testing/static-analysis-sast.html) 和[黑鸭软件组合分析(SCA)](https://www.synopsys.com/software-integrity/security-testing/software-composition-analysis.html) 解决方案中发布新的[快速扫描](https://www.synopsys.com/blogs/software-security/rapid-scan-appsec-testing-for-developers)功能时，这是一件大事。

快速扫描为您的开发人员带来的是针对您的专有代码和开源代码的更快、轻量级的漏洞检测。特别是，快速扫描针对开发的早期阶段进行了优化，在 bug 嵌入程序之前，仍然很容易捕捉到它们。Synopsys 还表示，快速扫描对于云原生应用程序和基础架构即代码(IaC)尤其有用。

当然，我们知道全面彻底的安全测试对于在软件开发生命周期(SDLC)的后期管理风险是至关重要的。但是，让我们现实一点。我们中有多少人真正做到了我们应该做到的始终如一？更好的是，正如高级 Linux 内核维护人员 Shuah Khan 所观察到的，“在开发过程的早期更容易检测和修复问题”

这就是快速扫描的用武之地。它补充了传统的应用程序安全测试活动，使开发团队能够在每次代码签入或早期构建时执行快速的 SAST 和 SCA 扫描，而不会降低它们的速度。这使得开发人员能够有效地向左转移，并防止安全问题传播到 SDLC 的后期阶段。如果你想要[持续集成/持续交付(CI/CD)](https://thenewstack.io/how-continuous-integration-and-continuous-delivery-ci-cd-enhances-devops/) ，在开发管道的早期建立测试是必要的。

正如 Synopsys 软件完整性集团总经理 Jason Schmitt 在一份新闻稿中所说:“对于采用 DevSecOps 的组织来说，应用程序安全测试也需要效仿。借助快速扫描，Coverity 和 Black Duck 用户可以在开发人员编写和提交代码时运行快速预防性扫描来检测和消除表层漏洞，并且可以在部署应用程序之前，使用相同的解决方案在 SDLC 中运行深度扫描。”

听起来不错，但是他们具体在谈论什么呢？

新功能包括:

在 [Coverity 快速扫描 SAST](https://www.synopsys.com/blogs/software-security/rapid-scan-sast/) 中，您可以在开发人员的桌面和持续集成(CI)管道(如 GitLab 和 GitHub Actions)中获得专有代码的快速安全分析。Coverity Rapid Scan 针对构建在 Kubernetes、Terraform 和 CloudFormation 等 IaC 框架上的云原生应用程序以及 GraphQL、Kafka 和 Postman 等微服务进行了优化。除了快速检测许多常见的安全弱点，它还可以发现配置错误和 API 错误。

要使用它，您只需将快速扫描 SAST 指向一个目录或 Git 存储库，它就会在命令行或即将推出的 Microsoft Visual Studio Code，Code Sight IDE 插件中提供相关的可操作反馈。它已经包含了对 Java、JavaScript 和 Typescript 的支持，更多的语言正在开发中。它对标记语言的广泛支持使得扫描 IaC 应用程序变得很容易。

在 [Black Duck Rapid Scan](https://www.synopsys.com/blogs/software-security/black-duck-rapid-scan) 中，开发人员和管理人员可以执行比以往更快的依赖性分析，在将代码合并到发布分支之前，查看他们的任何开源组件是否违反了您组织的安全和许可政策。它通过跳过资源密集型 SCA 活动(如多因素开源检测)并为 SDLC 流程的后期生成完整的软件物料清单来实现这一点。

Coverity 和 Black Duck 快速扫描功能均可与 Synopsys 的[智能编排解决方案](https://c212.net/c/link/?t=0&l=en&o=3239777-1&h=1242642689&u=https%3A%2F%2Fwww.synopsys.com%2Fsoftware-integrity%2Fpolaris%2Fintelligent-orchestration.html%3Fcmp%3Dpr-sig%26utm_medium%3Dreferral&a=Intelligent+Orchestration+solution)一起使用，根据持续集成(CI)管道中的事件自动触发快速 SAST 和 SCA 扫描。同样，目标是在开发和测试的早期阶段做需要做的事情，而在后期阶段延迟完全覆盖和黑鸭扫描。

简而言之，这里的游戏名称是平衡敏捷性和风险管理。当然，如果你需要，你可以运行一个完整的扫描。但是有了快速扫描，您可以做您需要做的事情来满足您的计划，同时保护您的代码免受安全漏洞和开源许可问题的影响。对我来说，这听起来像是一个值得的妥协，有这个选择当然很好。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>