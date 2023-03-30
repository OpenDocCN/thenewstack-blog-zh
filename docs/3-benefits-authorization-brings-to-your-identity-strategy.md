# 3 授权给你的身份策略带来的好处

> 原文：<https://thenewstack.io/3-benefits-authorization-brings-to-your-identity-strategy/>

如今的组织正在采用[云原生技术](https://blog.styra.com/blog/why-we-need-to-rethink-authorization-for-cloud-native?utm_medium=pr&utm_source=new_stack&utm_campaign=awn&utm_content=blog)来加快上市时间、提高可扩展性和节约成本。云原生转变的一大部分是[将遗留系统和架构迁移到云](https://blog.styra.com/blog/styra-accelerates-cloud-migration-with-cloud-native-entitlements?utm_medium=pr&utm_source=new_stack&utm_campaign=awn&utm_content=blog)。

随之而来的是复杂性和新的风险，因为现代[应用](https://blog.styra.com/blog/using-open-policy-agent-for-cloud-native-app-authorization?utm_medium=pr&utm_source=new_stack&utm_campaign=awn&utm_content=blog)通常由数十个微服务组成，存放在容器中，托管在不可变的、动态扩展的平台上，如 Kubernetes。适用于遗留系统的安全措施和授权系统不再适用。身份和授权尤其如此。

 [杰夫·布罗伯格

Jeff 是一位拥有 30 多年经验的产品管理总监。在加入 Styra 之前，Jeff 曾在 SecureAuth、OneLogin 和 CA Technologies 工作，负责他们的身份认证和身份管理解决方案。](https://www.linkedin.com/in/jbroberg) 

身份和访问(IAM)团队经常面临的挑战是引导许多传统身份解决方案向云的过渡，提供各种内部和外部系统之间的集成，并专注于用户的身份验证。

身份认证标准和工具，如单点登录(SSO)、多因素身份认证(MFA)和 SAML，是为解决这些挑战而开发的，并已发展到提供允许用户或服务登录或身份认证的模式，以确定用户声称的身份。

IAM 团队可以使用这些工具和框架来高度肯定地确保用户身份验证是他们所声称的身份。另一方面，授权、理解和控制用户或服务可以访问的动作或资源还没有达到相同的成熟度或理解水平。应用程序团队每周仍要花费大量时间来维护新的和现有的应用程序并向其添加授权。

这种授权挑战就是为什么 Styra 创建了开源项目[开放策略代理(OPA)](https://blog.styra.com/blog/what-is-open-policy-agent?utm_medium=pr&utm_source=new_stack&utm_campaign=awn&utm_content=blog) 和不久之后的 [Styra 声明式授权服务(DAS)](https://blog.styra.com/blog/what-is-styra-declarative-authorization-service?utm_medium=pr&utm_source=new_stack&utm_campaign=awn&utm_content=blog) 。

OPA 是策略即代码的一个例子，它是一个通用的策略引擎，将策略决策从应用程序的其他职责中分离出来。由于其单一的统一策略语言，OPA 在为 Kubernetes、微服务、功能应用授权等做出决策时同样表现出色。

策略的一个例子——可以把它想象成一组规则——可能是在系统中执行操作需要什么角色，或者是授权，这是一种规定谁或什么在系统中做什么的策略。

毫不奇怪，组织已经能够在其基础架构(Kubernetes、Terraform 等)中通过 OPA 和一般的策略即代码实现优势和控制。)开始引起组织的注意，特别是 IAM 团队和大量负责在其应用程序中实现授权的工程师。

## **身份认证解决方案中授权的优势**

将策略作为代码应用到身份验证或身份解决方案中可以提供许多好处，包括:

*   **利用现有的数据源** (LDAP、AAD、SCIM 等。)来利用您对 IAM 的现有投资。当丰富的上下文与声明性策略相结合时，您可以根据需要将它大规模复制到任意数量的云、大陆、地区和可用性区域。此外，您将能够在部署策略或数据更改之前很久就了解其影响，这将有助于停机时间、测试等。
*   拥有**集中式策略创作**、数据管理和决策日志，而不牺牲物理上的分布式实施，在确保您确实可以大规模运行时，无疑可以节省时间。
*   运行授权服务(IAM + authorization) **实例的可用性，尽可能靠近需要它们的应用程序**。此外，保持最新的分布式策略/数据提供了单点故障本地解决方案的替代方案，这可能意味着全功能应用程序和故障应用程序之间的差异。

虽然将身份验证和授权完美地结合在一起还有很多好处，但最简单的方法是扩展 IAM 的现有记录系统，关联声明性策略，并在所有部署模型中实施授权决策。这允许您回答一个简单的问题，“谁可以在哪个上下文中访问什么？”

但是，直到最近，对于 IAM 团队来说，使用行业最佳实践来更新现有的授权解决方案，或者基于行业标准和策略库从头开始创建新的解决方案，都不是一件容易的事情。

[面向云的 Styra 声明式授权服务(DAS)](https://www.styra.com/das-free?hsLang=en?utm_medium=pr&utm_source=new_stack&utm_campaign=awn&utm_content=website) 可以引入原生授权，以满足需要更广泛控制的组织的需求。人们的理解是，这些控制将渗透到系统或组织的其他领域。例如，使用身份供应商和 Styra DAS 使组织能够扩展授权环境，以合并来自不同系统的不同类型的数据源。

然后，组织可以获取这些信息，并将其用于他们需要控制的不同领域，而不仅仅是一个应用程序(如基础架构)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>