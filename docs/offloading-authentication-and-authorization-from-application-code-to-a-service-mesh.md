# 将认证和授权从应用程序代码卸载到服务网格

> 原文：<https://thenewstack.io/offloading-authentication-and-authorization-from-application-code-to-a-service-mesh/>

[](https://www.linkedin.com/in/zack-butcher-339a2180/)

 [扎克·布彻

扎克是一名工程师。他是 Istio 贡献者和 Istio 指导委员会成员，也是《Istio:启动并运行》(O'Reilly: 2019)的合著者](https://www.linkedin.com/in/zack-butcher-339a2180/) [](https://www.linkedin.com/in/zack-butcher-339a2180/)

在我与 NIST 的 [Ramaswamy Chandramouli](https://www.linkedin.com/in/ramaswamy-chandramouli-64b8446/) 合著的[美国国家标准与技术研究院](https://www.nist.gov/) (NIST)即将出版的特别出版物中，我们将围绕安全可靠地将认证和授权从应用代码卸载到服务网格提出建议。我们将讨论这种方法的优缺点。这篇文章概述了将于本月晚些时候在[举行的为期一天的服务网格安全会议](https://www.tetrate.io/event/nist-tetrate-virtual-conference-devsecops-and-zero-trust-architecture-for-multi-cloud-environments/)上提交的论文，Tetrate 将与 NIST 合作主办该会议。1 月 27 日的会议将涵盖围绕 DevSecOps 和使用服务网格的多云中零信任架构的各种主题。

服务网格为您的组织构建一组操作保证提供了一个框架。该框架包括

*   服务的可认证运行时身份；
*   验证应用程序(用户)凭证的能力；
*   服务间通信传输中的加密；
*   可从应用程序独立部署和控制的策略执行点(PEP)——服务网格的边车代理；和
*   用于监控策略实施的日志和指标。

使用这些网格功能，您可以为属于网格一部分的所有应用程序构建一组控件(“所有流量都被加密”)；“应用程序的所有流量都通过边车(PEP)”；等等)。这些控制为部署在服务网格中的组织中的应用程序提供了一组操作保证。

## **为什么要使用服务网格？**

服务网状架构的一大好处是，允许您构建这些控制的关键部分——部署在每个应用程序旁边的 sidecar 代理——与将这些操作保证构建到您的应用程序代码中的传统方法相比，具有相当多的安全好处。这些好处是:

1.  边车的生命周期独立于应用程序，因此更容易管理您的车队。例如，您可以推送更新，并确保在任何地方部署一致的版本。
2.  现代实现(如 Istio)允许动态配置；更新策略很容易，而且更新会立即生效，无需重新部署应用程序。
3.  网格的集中控制允许您的安全团队构建、管理和部署适用于整个组织的策略，因此构建业务价值的应用程序开发人员在默认情况下是安全的。他们“开箱即用”，无需做额外的工作。

服务网格提供了对附加到请求的最终用户凭证进行身份验证的能力，就像 JWT 一样。许多服务网格——例如 Istio——更进一步，为网格的 sidecar 提供了代表应用程序调用外部认证和授权系统的能力。这使您能够将请求级策略实施移出应用程序代码；取而代之的是信任网格的保证，即到达服务的请求已经被认证并被授权执行请求所采取的动作。网格甚至可以被配置为将这种证明传递给应用程序。这一点，再加上服务网格的集中控制，意味着中央团队可以授权和管理整个组织的应用程序级安全性，只需委托给单个应用程序团队来指定应用程序中每个操作所需的权限。

最后，使用服务网格架构，我们可以将我们的身份验证和授权系统部署为网格中的服务。像网格中的任何其他服务一样，它们受益于网格提供的操作保证:传输中的加密、身份、PEP、最终用户身份的认证和授权，等等。这使得安全可靠地运行您组织的身份验证和授权系统更加便宜。

[多云中虚拟会议 DevSecOps 和零信任架构的注册](https://www.nist.gov/news-events/events/2021/01/devsecops-and-zero-trust-architecture-zta-multi-cloud-environments)已开放。会议将邀请来自美国空军、商务部(DoC)和国土安全部(DHS)以及食品药品监督管理局(FDA)的 NIST 科学家和 IT 领导者，以及来自 RSA、Flexport、马里兰大学和 Tetrate 的网络安全专家和工程师参加。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>