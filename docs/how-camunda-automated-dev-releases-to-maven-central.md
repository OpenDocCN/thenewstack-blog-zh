# Camunda:我们如何将开发发布自动化到 Maven Central

> 原文：<https://thenewstack.io/how-camunda-automated-dev-releases-to-maven-central/>

[](https://lwille.xyz)

 [莱恩哈特威尔

莱恩哈特威尔是卡蒙达的高级软件工程师(基础设施)。](https://lwille.xyz) [](https://lwille.xyz)

将 DevSecOps 最佳实践和工具引入开源社区是一项挑战。可能很难理解要实现什么工具，在哪里宣传它们，以及如何让您的社区参与进来。通过使用 Terraform 和 Vault 来利用 GitHub secrets，开源社区不仅可以改善他们的开源开发者体验，还可以减轻基础设施团队的负担。

通过使用来自 [HashiCorp](https://www.hashicorp.com/?utm_content=inline-mention) 的 Terraform Cloud、 [Aqua Security](https://www.aquasec.com/?utm_content=inline-mention) 的 Trivy 和 GitHub Actions 等工具， [Camunda](http://camunda.com/) 的基础设施和开发人员体验团队合力构建了一个 [CI/CD 发布工具](https://github.com/camunda-community-hub/community-action-maven-release) ，该工具允许开发人员自动向 Maven Central 发布，同时还确保具有关键安全漏洞的项目能够实时获知测试失败。在本文中，我们将分享技巧、经验教训，并深入研究如何使用这些 DevSecOps 最佳实践来增强您的开源社区项目的能力并保护其安全。

## 专注于自动化和安全性

 [基兰·奥利弗

Rin 是 Camunda 的技术社区构建者。他们喜欢讨论开源的所有事情，特别关注改善技术行业中那些神经分裂的人的招聘渠道，以及改善新的和回归的开源软件贡献者的开发体验。](https://www.linkedin.com/in/ckoliver/) 

自动化 CI/CD 发布工作流不仅有益于开源社区的维护者，还允许开源项目的新贡献者以有意义的方式做出贡献。

当在 CI/CD 生态系统中使用自动化时，尤其是在开源环境中，安全性是任何项目的核心。有时，如果没有内置的安全特性或策略，组织和社区维护者可能会犹豫是否采用新的工作流。在 GitHub Actions、 [GitLab](https://about.gitlab.com/?utm_content=inline-mention) CI 和 Jenkins 中，有多种安全工具和改进可以添加到现有的 CI/CD 工作流中。

卡蒙达的团队选择了 [Aqua Security 的 Trivy](https://github.com/aquasecurity/trivy) 来实现它的 [GitHub 动作](https://github.com/features/actions)；尽管在实现的时候，他们面临着 GitHub Actions 不能运行并发操作的挑战。这导致团队结对编程在一个解决方案上，允许他们仍然利用 Trivy，这涉及到通过 Bash 脚本实现工具并通过 Sarif 文件返回扫描结果。任何使用自动发布 GitHub 动作的项目，如果发现其项目有高或严重的安全漏洞，将不能自动向 Maven Central 发布他们的项目。

## Terraform 给开源 DevSecOps 带来了什么

CI/CD 工作流需要秘密，以便将工件部署到目的地，如由 [Sonatype](https://www.sonatype.com/?utm_content=inline-mention) 管理的 [Apache Maven Central](https://central.sonatype.org/publish/publish-maven/) 或 [Docker Hub](https://hub.docker.com/) 。

高效、透明且安全地管理这些机密的需求，尤其是在大型组织中，通常会导致以下问题:

*   如果凭据需要轮换，该怎么办？
*   如何高效分发机密？
*   如何确保一个新项目快速有效地启动？

GitHub 可以部分解决分发方面的问题，它允许将秘密分配给一个组织，并允许将它们继承给所有或选定的项目。这就给我们留下了有效维护存储库列表的任务，以及在发生变化时更新实际的秘密值。

HashiCorp Terraform 是一款配置管理工具，在运营、开发运营和现场可靠性工程(SRE)社区广为人知。Camunda 的团队选择了 Terraform，将来自 Vault(一个“真实的单一来源”秘密商店)的秘密镜像到各自的目的地。

这方面的配置管理代码保存在一个 Git 存储库中。

由于 Terraform Cloud 提供的自动化，新项目的启动或添加新秘密变成了一项简单的任务:

项目名称只需添加到 Terraform 代码文件的现有列表中，然后检查并合并更改。Terraform Cloud 采用来自 HashiCorp 的官方 GitHub 提供者和 [`github_actions_secret`](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/actions_secret) 资源，更改立即反映在 GitHub 组织的配置中。这一过程确保秘密不被篡改，更改在应用前必须通过同行审查。

同样的技术可以用于 [管理存储库的应用安装](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/app_installation_repository) ，以及 [创建](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/repository) 和管理 GitHub 存储库的许多方面。

## 增强社区能力的最佳实践

安全性对每个人来说都不一样。适用于一个大型开源项目的方法可能不适用于专注于产品或平台的开源扩展的较小社区。鼓励您的社区走到一起，通过提供与他们配对的程序，或者通过提供 GitHub 发布模板，允许他们快速打开 pull 请求以修复 bug 或请求新功能，来协作和改进他们现有的自动化工具。另一种方法可能是鼓励他们构建一个他们建议的功能来改进您的项目的现有 CI/CD 工作流程，并与他们一起工作来完成这一过程。鼓励安全意识也是关键。告诉你的社区你为什么选择这些工具，它们是做什么的，为什么它们很重要。

**附加资源**:

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>