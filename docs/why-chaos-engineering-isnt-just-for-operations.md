# 为什么混沌工程不仅仅是为了操作

> 原文：<https://thenewstack.io/why-chaos-engineering-isnt-just-for-operations/>

开发人员创建代码或应用程序，上传，然后让运营工程师接管其余工作的时代已经一去不复返了。

随着高度分布式 [Kubernetes](https://thenewstack.io/category/kubernetes/) 和[微服务](https://thenewstack.io/category/microservices/)环境的大规模采用，动态已经发生了变化。现在， [DevOps](https://thenewstack.io/category/devops/) 团队越来越多地分享任务，并参与到以前由运营或软件可靠性工程师(SREs)负责的工作流程中。

最终的结果是，开发人员要做的工作并不一定与应用程序开发紧密相关。除此之外，开发人员将经常直接参与测试——并且越来越多地，通过[持续集成/持续开发(CI/CD)管道](https://thenewstack.io/category/ci-cd/)与运营和其他团队进行混乱工程。

“在过去的两到三年里，我的评估是[云原生](https://thenewstack.io/category/cloud-native/)的活力正在迫使其他角色，如开发人员，将混沌工程集成到他们的工作流中”连同运营和 QA 团队和 sre， [Uma Mukkara](https://twitter.com/Uma_Mukkara) ， [ChaosNative](http://cloud.chaosnative.com/?utm_content=inline-mention) 的首席执行官和 [LitmusChaos](https://thenewstack.io/chaosnative-litmus-enterprise-supports-more-experiments/) 的维护者，在 1 月份 ChaosNative 的年度用户大会[混沌嘉年华](http://chaoscarnival.io)之前告诉新的堆栈

在这里，我们探讨为什么和如何混沌工程涉及整个生产管道与开发人员的支持，以及它应该如何正确地实施和集成到 CI/CD。

## 什么是混沌工程？

[混沌工程](https://thenewstack.io/chaos-engineering-progressively-moves-to-production/)可以描述为发现并修复分布式应用及其与不同组件(如微服务和 API)的交互中的弱点，当故障被故意引入作为实验时。

Mukkara 说，通过实验引入“随意的混乱”,有可能帮助避免失败，并为失败的最终结果做好更好的准备。停电后同时改善恢复(MTTR)是混沌工程提供的好处的一个例子。

作为混沌实验的第一步，故障被注入到应用程序、服务、网络甚至硬件中，以便导致应用程序或服务以某种方式出现故障。“这是一门防止大范围损失的艺术，”穆卡拉说。

三部分流程的第二部分也是最重要的一部分是稳态假设验证，以查看一旦出现故障，服务是否能正常工作。

例如，如果网络连接只正常运行 80%的负载，服务提供的事务应该继续保持一定的任务完成率。该实验用于确认所谓的“稳态假设验证”

混沌工程的第三部分由[可观测性](https://thenewstack.io/category/monitoring/)组成。“这涉及到许多对业务至关重要的服务的监控系统，当你引入混乱时，你可以看到是否有足够的恢复，以便以可行的方式维持服务，”Mukkara 说。

在混沌嘉年华的一次会议演讲中， [Dynatrace](https://www.dynatrace.com/?utm_content=inline-mention) 的高级工程师 [Henrix Rexed](https://www.linkedin.com/in/hrexed/?locale=en_US) 展示了可观测性在混沌工程中的重要作用。通过使用 [LitmusChaos](https://thenewstack.io/chaosnative-litmus-enterprise-supports-more-experiments/) 和其他工具，他展示了 [Prometheus](https://prometheus.io/) 和 Dynatrace 如何有助于收集 Kubernetes 集群所需的指标。

“混沌工程需要适当的可观测性，”Rexed 说。

## 开发人员在混沌工程中的角色

开发人员在为 Kubernetes 和微服务环境创建应用程序时的角色可以涵盖许多任务，包括对集群的直接和间接访问。例如，对于 CI/CD 工作流，[开发人员可能会使用 Jenkins CI](https://thenewstack.io/why-chaos-engineering-for-jenkins-is-easier-than-you-think/) 来定期更改和提交他们的代码以供同行评审。

一旦审查和批准，代码与 Git 合并，开发人员更新 Kubernetes YAML 文件，以引用用 Jenkins 构建的最新工件或图像。

开发人员可能会进行更多的测试，例如确定应用程序如何在与微服务高度依赖的环境中运行。如果失败，应用程序将被委托给开发团队。

应用程序或新特性更新也可能在生产中失败，Kubernetes 允许您将应用程序回滚到以前的版本。在这两种情况下，开发人员可能需要能够对 Kubernetes 的日志和性能数据进行故障排除和监控，以修复代码。

开发人员的测试不仅包括测试应用程序在堆栈中的执行情况，还包括测试整个堆栈以及新代码如何与不同环境、API 和接口中的其他服务进行交互。这就是混沌工程开始变得相关的地方。

测试通常仅限于评估单个组件或服务的性能。另一方面，混沌工程超越了传统测试。Mukkara 说，它涉及到交付服务所需的依赖组件的验证，如在网络中运行的应用程序或微服务组合。

混沌工程还包括观察当网络中引入故障时会发生什么，以查看应用程序或微服务是否继续正常运行。

一个例子可能涉及观察当在模拟环境中的条带支付系统 API 中引发故障时会发生什么。chaos 实验将测试服务是否能在 99.99%的时间里继续运行，同时保持必要的事务处理速度，前提是如果 Stripe 系统出现故障，服务能正确地切换到替代 API。

“混沌工程有助于确保无论发生什么，都不会因为网络、微服务、API 或环境中可能中断服务的其他故障而产生财务责任，”Mukkara 说。

一旦将可执行代码添加到容器映像并集成到不同的环境中，开发人员就可以从开发过程的一开始就集成混沌工程。Mukkara 建议，这可以通过测试代码在谷歌云平台、微软 Azure 或其他网络中的故障表现来实现。

“云原生开发者需要在生产周期的开始就开始考虑混沌工程，”他说。一旦部署在不同的环境中，在进行混乱测试之前，你要编写代码并进行测试，以发现是否有任何弱点。

## 所有利益相关者的混乱

虽然开发人员通常会从混沌工程中获益良多，但它仍应是一项团队工作。许多 DevOps 团队可能会选择让开发人员和 QA 团队联合进行混沌实验，或者由 SRE 来领导这个过程。

一旦部署了服务，运营团队通常会发现性能问题，并使用混沌工程解决这些问题。“实际上很难定义哪些团队必须绝对使用混沌工程，”Mukkara 说。“但每个人都能受益。”

虽然从一开始实现混沌工程看起来令人生畏，但是开发人员以及 QA 和运营团队需要接受这种实践。简而言之，混沌工程确保了可靠性。

“混沌工程可以帮助开发团队在尝试新事物时有一种安全感，”云本地咨询公司 Container Solutions 的工程经理夏洛特·马赫(Charlotte Mach)在混沌嘉年华的新堆栈煎饼早餐会上说。

“当某些东西损坏或我们损坏某些东西时会发生什么，我们真的得到了我们想要的结果还是发生了其他事情？”

马赫说，混沌工程“就像是一个安全网，你可以在生产周期的开始或 CI/CD 期间的任何地方给人们提供安全网”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>