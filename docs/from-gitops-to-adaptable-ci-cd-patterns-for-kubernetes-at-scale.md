# 从 GitOps 到大规模 Kubernetes 的适应性 CI/CD 模式

> 原文：<https://thenewstack.io/from-gitops-to-adaptable-ci-cd-patterns-for-kubernetes-at-scale/>

本文是第三篇

[a three-part series](https://thenewstack.io/the-road-from-local-development-to-cloud-native-kubernetes/)

由 Kubernetes 赞助的 CI/CD

[Google](https://cloud.google.com/)

。本文对原始版本进行了更新，以阐明 GitOps 中推和拉模型之间的差异。先前对拉模型的描述是不正确的。

[](https://cloudplatformonline.com/TNS-CI-CD-with-Kubernetes.html?utm_source=google&utm_medium=email&utm_campaign=FY18-Q3-americas-nurture-email-wd-icb_tns&utm_content=cicd&utm_term=tns)

 [吐温泰勒

吐温在谷歌开始了他的职业生涯，在那里，他参与了 AdWords 团队的技术支持工作。他的工作包括审查堆栈跟踪，解决影响客户和支持团队的问题，以及处理升级。后来，他建立了品牌社交媒体应用程序和自动化脚本，以帮助初创公司更好地管理他们的营销业务。如今，作为一名技术记者，他帮助 IT 杂志和初创公司改变团队构建和发布应用程序的方式。](https://cloudplatformonline.com/TNS-CI-CD-with-Kubernetes.html?utm_source=google&utm_medium=email&utm_campaign=FY18-Q3-americas-nurture-email-wd-icb_tns&utm_content=cicd&utm_term=tns) [](https://cloudplatformonline.com/TNS-CI-CD-with-Kubernetes.html?utm_source=google&utm_medium=email&utm_campaign=FY18-Q3-americas-nurture-email-wd-icb_tns&utm_content=cicd&utm_term=tns)

GitHub 改变了开发团队管理代码变更的方式，从“提交”到“合并”都带来了改进的协作。从以 Jenkins 为中心的持续集成开始，许多组织现在正试图通过仔细研究他们的 GitHub 工作流来优化和改进次优管道。

最初创造了术语 GitOps 的组织 Weaveworks 将其描述为“ [通过拉请求](https://www.weave.works/blog/gitops-operations-by-pull-request) 的操作。”GitOps 最有价值的部分是它支持“将环境作为代码”，这意味着 GitOps 允许您在编写代码的同时定义策略和环境配置。

虽然这种方法有很多优点，但是 GitOps 的某些方面不一定适合企业环境。谷歌云平台 DevOps 部门的产品经理 Andrew Phillips 详细阐述了这一点，他解释说，GitOps 的常见实现主要有两个挑战:“首先，主要通过源代码存储库运行发布流程和批准在较大的组织中并不理想。第二，选择“拉”的方法使环境像代码一样真实并不总是最好的；“在许多情况下，‘推’的方式可能更合适。”这些问题随着组织的复杂性而突然出现，这也是 GitOps 的简单实现的不足之处。

因此，必须保留 GitOps 的最佳部分，并用更适合您的环境的替代方案替换它的某些部分。在这篇文章中，我们讨论了一种更好的方式来考虑使用 Kubernetes 的 GitOps，这样您就可以应用一组可行的模式，同时记住您自己组织的复杂性和约束。

## 应对企业复杂性

大型组织通常有多个开发团队，每个团队都有自己独特的实践。他们必须赋予每个团队必要的自主权来构建、部署和维护团队拥有的代码和应用程序，以保持速度和质量。同时，组织必须对其应用程序和集群的扩展进行优先排序和规划。

扩展 CI/CD 管道有两个方面。第一种是当您的组织扩展到包括新的团队和新的团队成员时。第二种情况是当应用程序的使用量增加，需要额外的资源支持时。额外的 Kubernetes 集群和更大的环境意味着部署过程中的复杂性和失败风险更大。您的应用程序扩展得越多，失败的代价就越大。对于生产中的应用程序来说，每秒有一百万次查询比只有十次查询更危险。

自治和规模这两个目标似乎相互矛盾。这正是 GitOps 适合的地方，因为它在不牺牲一方或另一方的情况下对双方都有利。

“GitOps 提供了一套最佳实践，以自动化的方式组织应用程序和环境的代码和配置，”谷歌云软件工程经理 [丹·洛伦茨](https://www.linkedin.com/in/danlorenc) 说。

如果基础设施作为代码以实例为中心，那么 GitOps 以环境配置为中心。在 GitOps 模型中，对生产环境的所有更改和更新都是通过对代码库的更改来实现的。GitOps 不是手动配置环境，而是将对环境的更改作为代码更改的副产品。通过这种方式，GitOps 在您的存储库和环境之间创建了一个链接，并实现了“环境即代码”

“集成存储库和环境的力量在于，你现在可以将你的访问控制、测试策略和授权从你的代码扩展到你的环境配置，”Lorenc 说。这有助于统一您的 CI/CD 管道，同时仍然实施适应您的组织的开发模式。

## 每个团队一个存储库

GitHub 使得从多个代码仓库进行维护和部署成为可能，但是每增加一个仓库，管理开销就会增加。在一个拥有多个开发团队的组织中，两难的问题是创建尽可能多的存储库还是更少的存储库。在有多个存储库的场景中，每个团队都有单独的存储库用于开发、试运行和生产。这导致了存储库蔓延的问题。

谷歌的安德鲁·菲利普斯推荐了一个替代方案。他建议，“尽可能减少存储库的数量。您可以在该存储库中为每个环境创建三个分支，而不是创建额外的存储库——例如，一个分支用于开发，一个用于试运行，另一个用于生产。这样，每个环境都有自己的提交历史和配置，因此您仍然可以获得隔离的好处，同时避免维护开销。”

通常情况下，组织最终会得到一个非常细粒度的、不必要的复杂系统，这个系统很容易创建，但很难维护。Phillips 的建议与这种趋势相反，提供了一种管理和扩展代码库的实用方法。

通过遵循这种模型，您可能会以每个团队一个存储库而告终，这比每个团队多个存储库要好，但是在拥有许多团队的大型组织中，这仍然很难管理。进一步考虑减少存储库的想法，您可以为每个环境共享一个存储库。例如，五个团队部署到的临时集群可以将其配置托管在单个存储库中。这样，您可以获得两全其美—关注点分离和易于管理。

## “推”超过“拉”

GitOps 的另一个重要考虑是，当许多开发人员一天多次贡献代码时，运行时如何同步。GitOps 通常被描述为在“拉模式”下运行，在这种模式下，运行在动态集群中的进程在提交了对它的更改之后，试图实现所需的环境配置。这是有问题的，因为团队只有在存储环境配置的存储库被更新之后才意识到失败。当这种情况发生时，团队可以回滚提交，但是它被记录在提交历史中，而提交历史不再是良好状态的干净记录。

依赖拉模型来部署变更的另一个问题是，任何拥有提交权限的人都会成为生产部署者。这不是一个好的安全实践，因为您的存储库变成了您的安全表面，并且围绕存储库的安全控制不如围绕运行时的安全控制强大。

“一个更好的选择是完全避免‘拉’模式，而是使用‘推’模式来部署配置和代码，”Phillips 说。在这种模式下，不是让群集“监视”更新，而是调用 API，这允许您在部署前后应用检查和自定义安全控制作为管道的一部分

在“推送”命令之前，新代码要经过一个“试运行”或“预览环境”，如果测试失败，就不会执行部署。但是如果它成功了，那么配置将被推送，并使用冒烟测试或其他验证步骤进行验证，然后您将它提交到您的主存储库。这增加了对每个部署的信心，并产生了一个稳定的主分支，它具有成功部署的提交历史。您仍然可以将手动批准作为管道的一部分，以在需要时获得更多控制，但目标是尽可能实现批准和验证过程的自动化。

支持这些特定 GitOps 模式的工具尚未成熟，但已经有一些有希望的选项。詹金斯 X 在实现 GitOps 模型方面最接近现实。它专注于各种环境的自动化管理，并在代码变更被合并到 master 之前提供快速反馈。 [Weave Flux](https://www.weave.works/oss/flux/) 是另一个开源工具，它基于在 Git 中声明部署所需状态的思想。然后 Flux 会确保在您的实时集群中达到期望的状态。虽然工具仍在发展，但这里讨论的模式可以应用，而不管实施它们的工具是什么。

## 关键要点:

在本系列中，我们详细介绍了如何为云原生应用程序创建和优化 CI/CD 管道。

*   在 [的第一篇文章](https://thenewstack.io/the-road-from-local-development-to-cloud-native-kubernetes/) 中，我们讨论了如何使用 Skaffold 快速启动本地环境，并使用 Google Cloud Build 在云中自动部署。
*   在 [第二篇](https://thenewstack.io/integrate-security-and-compliance-into-your-ci-cd-pipeline) 中，我们讨论了如何使用元数据 API Grafeas 来加固和保护您的 CI/CD 管道。我们还介绍了使用容器注册表进行漏洞扫描，以及使用 Kritis 和二进制授权实施安全策略。
*   最后，在这篇文章中，我们讨论了优化和扩展 GitOps 风格工作流的特定模式和修改。

无论您是刚刚开始构建 CI/CD 管道，还是正在修复一个过时的管道，这里讨论的工具、最佳实践和模式都可以应用。这样，您将改变构建和发布现代云原生应用的方式。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>