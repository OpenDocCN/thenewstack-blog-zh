# 普鲁米平台达到 1.0

> 原文：<https://thenewstack.io/pulumi-reaches-1-0/>

Pulumi 平台来自西雅图的同名初创公司，专注于使用熟悉的编程语言管理基础设施，它已经达到了 1.0 的里程碑。该公司吹嘘该平台能够为寻求实现基础设施现代化和转向云计算的公司提高生产率、可靠性和安全性。

“我们已经与足够多的公司合作，我们觉得我们涵盖了端到端的解决方案，真正投入生产，并解决了客户的一系列难题。首席执行官[乔·达菲](https://github.com/joeduffy)说道，同时也提到了其在稳定性、性能和兼容性方面的工作。

Pulumi 为容器、无服务器功能、API 和基础设施提供了一种一致的方法，使用“真正的”编程语言，如 JavaScript、TypeScript、Python 和 Go。达菲之前称该公司为“ [YAML 终结者](https://thenewstack.io/pulumi-uses-real-programming-languages-to-enforce-cloud-best-practices/)，因为它有能力浓缩成千上万行代码。

它还可以跨云提供商(包括 AWS、Microsoft Azure、Google Cloud、Kubernetes、Digital Ocean 等)保持基础架构的最新版本，并提供通用工具、工作流和策略，使开发、基础架构和运营团队保持一致。

对于 1.0 版本，“我们已经将所有这些语言提升到彼此平等的水平。Duffy 说:“尽管我们从 TypeScript(JavaScript)开始，但我们实际上发现 Python 的采用越来越多，特别是在运营团队中，他们可能已经在日常工作中使用 Python 了。

“我们也很好地融入了这些生态系统。因此，我们已经确保测试能够在您最喜欢的测试框架中开箱即用。随着我们与越来越大的客户合作，这一直是我们非常感兴趣的领域。”

Pulumi 1.0 的新功能包括:

*   与现有基础设施或 Terraform、CloudFormation、Azure Resource Manager 或 Kubernetes 和 Helm config 配合使用的基础设施即代码 SDK。
*   团队可以在现有的生态系统中使用 NPM 和 Pip/PyPI 来分享最佳实践和测试框架。
*   生产力框架，用于共享和重用自动化云架构最佳实践的组件。
*   跨多个环境自动管理状态的能力。
*   内置的秘密管理和加密，包括与 AWS KMS、Azure KeyVault、谷歌云 KMS 和 HashiCorp Vault 的集成，使团队能够使用现有的密钥和策略。
*   身份提供商与 GitHub、GitLab、Atlassian 或 SAML/SSO 的集成，包括 Active Directory、Okta、Google G Suite 等。基于角色的访问控制(RBAC)用于细粒度的团队访问和权限管理。
*   CI/CD 与 Azure DevOps、AWS 代码服务、CircleCI、Codefresh、GitHub、GitLab、Google Cloud Build、Jenkins、Travis 等的集成。
*   对于希望在自己的防火墙后或在自己的云帐户中运行的组织，Pulumi SaaS 的自托管功能。

拉丁美洲最大的电子商务平台 [Linio](https://www.linio.com/sell-in-latinamerica) 的 DevOps 主管 [Harrison Heck](https://www.linkedin.com/in/harrison-heck-0846a212/) 说:“有了 Pulumi，我们能够以前所未有的速度和可靠性开发新的基础设施、改变现有的基础设施等。“Pulumi 使我们能够简化和自动化我们的工作流，确保所做的更改以与我们的应用程序相同的方式得到审查。”

5 月，Duffy 在巴塞罗那的 KubeCon + CloudNativeCon 大会上与 New Stack 的 Alex Williams 谈论了开发人员和运营人员[与 Kubernetes](/pulumi-ceo-on-the-challenges-with-kubernetes/) 和多云环境的关系。

[普鲁米 CEO 直截了当地描述了你与 Kubernetes 的真实关系](https://thenewstack.simplecast.com/episodes/pulumi-ceo-cuts-through-the-chafe-describes-your-real-relationship-with-kubernetes)

但是他说至少一半的顾客还没有到达那里。对许多人来说，仍然有许多虚拟机，可能还有一些容器，但他们仍然在处理非常单一的体系结构。

他说:“我们在这里投入了大量资金来与现有系统集成，这样客户就可以在他们所在的地方与他们见面，然后带领他们前进，帮助他们实现自动化交付的目标。”。

其中一部分是学习如何在复杂的环境中做到这一点。

“您知道，许多人一开始可能要管理一、二、三个生产环境。与我们的客户 Tableau Online 相比，这是一个非常不同的世界。他们在全球范围内管理和扩展了几十个生产环境。…这非常复杂，”他说。

他称 Kubernetes 是 DevOps 运动的加速器。

“DevOps 作为一种文化转变，旨在让运营团队更好地实现自动化，并更像开发人员一样工作。我们现在发现的是，团队真的想打破运营团队和开发团队之间的孤岛。Kubernetes 是一种催化剂，它使人们后退一步，意识到他们需要这样做，但真正使开发商和运营商能够合作，”他说。

他表示:这确实是许多顾客试图实现的主要文化转变。

“这一直是 Pulumi 擅长的事情，但由于我们选择使用通用语言，我们越来越多地发现采用 Pulumi 的客户希望将其扩展到他们的组织。”

“我们并不试图抽象出是什么让每个云变得伟大，我们正在接受差异，但实际上只是允许团队拥有一种跨越所有这些不同云的方法，而不是…不同的工具、服务和工作流集，”他说。

6 月，Pulumi 宣布了亚马逊 Web 服务的 Crosswalk，这是一个开源框架，它打包了在 AWS 上创建和部署应用程序的最常见模式。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>