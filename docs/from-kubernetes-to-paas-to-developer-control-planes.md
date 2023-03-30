# 从 Kubernetes 到 PaaS 再到开发者控制平面

> 原文：<https://thenewstack.io/from-kubernetes-to-paas-to-developer-control-planes/>

[](https://www.linkedin.com/in/danielbryantuk/)

 [丹尼尔·布莱恩特

丹尼尔是大使实验室(前身为 Datawire)的开发者关系总监。Daniel 是一名 Java 拥护者，是 TechBeacon DevOps 100 的影响者，并为几个开源项目做出了贡献。](https://www.linkedin.com/in/danielbryantuk/) [](https://www.linkedin.com/in/danielbryantuk/)

已经花费了大量的时间和精力来讨论云技术如何改变传统的软件开发体验。在过去的 20 年里，我们已经逐渐经历了许多不同的技术和软件发布方式。然而，对于云原生开发，我们正在见证一场巨变，它从根本上改变了[开发者体验](https://thenewstack.io/how-the-developer-experience-is-changing-with-cloud-native/)。随之而来的浪潮也震撼了[站点可靠性工程师](https://thenewstack.io/how-the-sre-experience-is-changing-with-cloud-native/)、[平台架构师和团队](https://thenewstack.io/how-the-platform-experience-is-changing-with-cloud-native/)，甚至是技术领导者。

以前的文章已经关注了这些转变，集中在几个主题上:一个“左移”正在进行，Kubernetes 已经成为默认的编排系统，云原生生态系统是强健的。现在的挑战是通过大量的工具来实现支持新的云原生常态的平台即服务(PaaS)方法。[云原生计算基金会](https://www.cncf.io/) (CNCF)已经成为构建云原生软件可持续生态系统的领导者，并且是包含全球技术基础设施关键组件的平台的天然跳板。

## 20 年的软件开发:爆炸式的认知负荷

在现代软件开发的早期(2000 年代中期)，开发人员有很多东西要学，但最终使用的是一个具有良好开发流程的单一整体代码库。他们编写代码并交付，却不知道或者不需要知道从那里发生了什么。后来，这演变成了一个简单的 PaaS 阶段，仪表板变得普遍，现代源代码控制(git)和应用程序性能监控(New Relic)等技术占据了主导地位。跳到 2015 年左右，我们到了微服务时代，开发者开始参与全生命周期。随着 Docker、Jenkins、Terraform、Chef 等工具以及各种插件的加入，认知负荷变得日益沉重。快进到今天，认知负荷进一步增加。

## 平台即产品

在我 20 年的开发生涯中，出现了几个关键的收获，我在最近 KubeCon North America 的 DevX Days 演示中探讨了这些收获:“从 Kubernetes 到 PaaS，再到开发人员控制平面”我在这里总结一下:

monolith 提供了一个较轻的认知负荷，支持 PaaS 的解决方案如 Heroku for Ruby on Rails 应用程序，提高了开发人员的工作效率。我们正处于类似转变的边缘，开发者的生产力和体验可以通过引入一个[平台作为产品](https://itrevolution.com/team-topologies/)来提高，也就是说，集中用户体验/用户界面(UX/UI)并以分散的方式标准化自以为是的做事方式，套用[Upchieve](https://www.youtube.com/watch?v=2mDakOMgITM)首席技术官戴夫·苏迪亚的话。

这会是什么样子呢？在很大程度上，这取决于组织。相反，一个潜在的问题是:应该如何提供平台，提供什么样的平台？对平台的投资为快速工作、小周期工作、迭代发布等提供了结构，但是这对开发人员的日常工作意味着什么呢？

## 没有好的 UX 就没有好的发展

构建一个平台需要了解用户如何承担他们的日常任务(使用*你的*工具)，这意味着用户研究开发人员如何工作，以及他们将如何具体使用该平台是至关重要的。

从[“机械同情”的角度来看，](https://mechanical-sympathy.blogspot.com/2011/07/why-mechanical-sympathy.html)这是马丁·汤普森的一个术语，也就是说，开发人员越了解事物如何运行，他们就越擅长编码。然而，如果从“[移情工程](https://www.youtube.com/watch?v=w6Dj2zf-39M)”的角度来看，你可以用自己的产品来理解最终用户的感受。如果他们不能完成他们的目标，那么软件需要改变，或者你的平台需要考虑开发人员的体验。

## 工作流和互操作性

理解如何提供平台是另一个关键。什么样的平台，应该有多“集中”？组织及其开发人员的成熟度水平如何？例如，一些像网飞这样的组织处于[先锋](https://www.infoq.com/news/2017/06/paved-paas-netflix/)，授权[全生命周期开发者](https://netflixtechblog.com/full-cycle-developers-at-netflix-a08c31f83249)。没有多少组织处于这一阶段，但一个减少摩擦和提高生产力的平台会让你在成熟的道路上走得更远。提供一个自助式平台，开发人员可以轻松访问该平台以获得自己的解决方案——SDK、API、完成工作的 UI——所有这些都无需在 Slack 中开罚单或提问，这将为更大的开发人员自主权和责任铺平道路。

## 统一云原生开发体验的下一个阶段:开发人员控制平面

“现在不只是 Kubernetes，这只是一个通用框架。现在最难的是所有其他东西:将所有东西连接在一起，并让它发挥作用。”— [月球银行首席平台架构师 Kasper Nissen](https://www.getambassador.io/developer-control-plane/dcp-insights-kasper-nissen-from-lunar/)

转向基于 Kubernetes 的、对开发人员友好的 PaaS，并使体验标准化，并不意味着取消选择和使用开发人员或更广泛的团队喜欢的工具的自由。相反，它提供了一个自以为是的或“铺设”的路径，帮助开发人员更快地达到速度和编码，减少认知负荷。在生产环境中，平台采用提供了一组有用的抽象，并为两个重要的成熟标志创造了条件:

*   **可预测性:**关注工作流、工具互操作性以及内部和外部开发循环的能力。也就是说，让云原生代码、发货、运行流程更流畅、更简单、更可预测。
*   **透明性:**工程团队更高效地协作和工作的可靠方式，获得整个软件生命周期的透明性，并使事情正常运行。

随着工作流和可互操作的工具围绕标准融合，以及随着开发人员的体验已经发展到包括对整个软件生命周期的了解，开发人员控制平面(DCP)的概念几乎成为了一种默契。不管开发人员是否需要在发布和运行阶段管理代码，DCP 都提供了一个公共平台来管理代码、开发环境、源代码控制、CI/CD、清单和容器管理、API 管理、Kubernetes 运行时和可观察性。

## 摘要:聚合 DCP 作为下一阶段云本机最佳实践

DCP 可以是平台的“单一平台”,无需完全集中管理，让开发人员能够以 DCP 为起点，自由定制他们的视图并进行部署。[工程大使实验室的 SVP Bjorn Freeman-Benson](https://www.getambassador.io/developer-control-plane/developer-control-planes-a-leadership-point-of-view/)解释道:“一个[开发人员控制平面](https://www.getambassador.io/developer-control-plane/)增强了您现有的技术堆栈，使您的开发团队之间能够协作，而不需要开发人员担心管理配置。”

我们已经达成共识，我们需要一个通用平台，用于在云原生空间中编码、运输和运行软件。开发人员控制平面传递了这一理念，提供了一个集中的地方来聚集共享标准并确定通用工作流，还鼓励技术集成/互操作性，这最终可以推动云原生成熟度的下一个阶段。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>