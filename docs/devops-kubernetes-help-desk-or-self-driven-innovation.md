# DevOps: Kubernetes 帮助台还是自我驱动的创新？

> 原文：<https://thenewstack.io/devops-kubernetes-help-desk-or-self-driven-innovation/>

采用云原生技术是一个需要时间来[](https://github.com/cncf/cartografos/blob/main/reference/prologue.md)成熟的旅程。在大多数情况下，团队开始在小项目中使用容器、Kubernetes 和采用微服务。但是随着项目的增长，复杂性也在增加。Kubernetes 仍然是一项相对较新的技术，许多开发者现在[才开始跟上它的速度](https://thenewstack.io/data-on-kubernetes-how-we-got-here-whats-next/)。

DevOps 团队越来越多地选择、部署和管理 Kubernetes。他们在 Kubernetes 上简化部署和[扩展微服务，为平台的成功做了很多工作。DevOps 团队成为安全、财务和开发团队之间的桥梁。他们是所有事情的中心，他们的任务是将所有事情整合在一起并使之成功。虽然他们开始创新，并希望继续尝试新技术或使平台更好，但他们往往成为 Kubernetes 的服务台，即他们不断响应开发人员和组织其他人员的基本询问。](https://thenewstack.io/scaling-microservices-on-kubernetes/)

这些基本的查询可能是检查应用程序停机的原因，并发现没有人设置活跃度和就绪性探测。它还可能是对开发人员关于为什么应用程序的构建会中断的问题做出响应，并且必须停止一切工作来正确配置它，然后重新部署它。这可能是因为开发团队从未设置容器安全性，或者因为存在其他缺失的配置(如果策略引擎正在 CI 管道中工作)。

## **运营一个 Kubernetes 帮助台有什么错？**

完全没有。在一些组织中，可能有足够的人员和资源来专门为此组建一个团队。但这通常是例外，而不是规律。DevOps 和 SRE 团队人手不足，工作过度，花了太多时间在战术救火或支持开发人员上。

这从 DevOps 的创新方面带走了——战略性地推动新工具和技术的实现，以改进开发过程。想想一家公司的 DevOps 团队如何在每次开发人员想要推向生产时放弃一切:有一个必须遵循的手动清单，并且花了一周时间来完成它。它减缓了 DevOps 团队的冲刺和开发项目。对所有参与者来说都是双输，因为“我们把所有的时间都花在审计上，而不是创新上。”

这还没有考虑到，作为 Kubernetes 的帮助台， [DevOps 团队成员](https://thenewstack.io/embrace-devops-culture-to-transform-your-business/)通常无法进行创新或找到解决问题的创造性解决方案，这导致了单调的工作和高度的倦怠。

## **没事，我拿到 CI/CD 了**

许多阅读这篇文章的人不会认为这是一个问题，因为 CI/CD 管道已经到位。毕竟，它有助于自动化构建、测试和部署代码的过程。这是云原生工具包的重要组成部分，但它并没有解决 DevOps 帮助台的问题。

Kubernetes 在默认情况下是[不安全的，](https://thenewstack.io/6-kubernetes-security-best-practices/)必须小心确保适当的护栏到位以保护环境。虽然 Kubernetes 是为动态扩展而构建的，但如果容器配置不当，自动扩展可能会被滥用，如果没有人跟踪成本优化和云支出，就会造成 FinOps 灾难。此外，如果没有正确的配置，它可能会有性能和可靠性问题。CI/CD 管道不能解决这些问题。

## **Kubernetes 从开发到生产的治理**

DevOps 团队提供的许多帮助台服务都是围绕配置问题的，这些问题可以而且应该自动化。开发人员需要的不是简单地带来需要开发人员解决的问题，而是提供即时反馈的能力，告诉他们什么不工作，为什么以及如何解决。

这就是 Kubernetes 治理和护栏对于 DevOps 团队和开发人员的理智变得必不可少的地方。服务所有权文化——设置防护栏和可操作的反馈——可以帮助开发人员在部署中自助修复。

它首先从理解需要遵循什么政策开始。Kubernetes 的最佳实践包括对安全性、可靠性和成本的考虑，例如，不以 root 身份运行容器，设置活跃度探测器，以及根据实际使用情况调整 CPU 和内存。将这些最佳实践转化为策略即代码(或护栏),然后从开发到运行时强制执行它们，减少了开发运维团队需要花费的时间。

通过合并服务所有权模型，您可以授权开发人员，而无需他们了解 Kubernetes 的来龙去脉。通过在他们已经使用的工具中为他们提供护栏(即，将策略作为代码合并到 CI/CD 检查中)以及如何修复问题的建议，开发人员将不会陷入困境，不会有长达一周的等待 DevOps 资源的延迟，并且将更快地交付应用程序。

是时候解放 DevOps 团队，使用先进的自动化 Kubernetes 治理工具完成他们想要的项目和冲刺了。是时候让他们不再是发展的服务台了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>