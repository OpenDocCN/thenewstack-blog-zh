# 如何扩展您的地形基础设施

> 原文：<https://thenewstack.io/how-to-scale-your-terraform-infrastructure/>

[](https://twitter.com/theseanodell)

 [肖恩·奥戴尔

肖恩是 Spacelift 的开发者关系主管。他相信每个 IT 组织都能够并且应该发展和实践 DevOps 的生活方式。Sean 是一名改革后的基础架构管理员和架构师，他热衷于帮助开发人员和应用团队在多云世界中取得成功。](https://twitter.com/theseanodell) [](https://twitter.com/theseanodell)

[HashiCorp 的](https://www.hashicorp.com/?utm_content=inline-mention)开源 [Terraform](https://www.terraform.io/) 在许多方面都是学习、供应和维护云基础设施的首选基础设施即代码(IaC)工具。

我与 Terraform 的个人旅程始于多年前，资源创造几乎是我的第二天性，但我在文档、繁荣的社区和奇妙的合作伙伴网络的帮助下走到了这一步。创建基础设施实际上只是 DevOps 等式的一部分，但由于其简单的性质，事情变得有点棘手。大规模运营暴露了一些挑战，包括部署的复杂性、内部和外部依赖性、安全性内置和可维护性。

本文将带您经历这一旅程，并确定大规模使用 Terraform 的一些最佳实践和解决方案。

## 当地建筑

仅使用 Terraform 二进制文件和对目标提供程序的访问，您就可以在代码库所在的计算机上本地使用您的资源。这种方法使得在 Terraform 上运行状态、导入、移动等日常活动变得更加容易。当与队友合作时，远程状态和状态锁定也是可用的。如果在没有持续集成的情况下运行版本控制，您可以使用`[pre-commit-terraform](https://github.com/antonbabenko/pre-commit-terraform)`，它在提交之前运行一组代码林挺工具。

尽管在本地工作很酷，但进行多个手动流程可能会导致错误和浪费时间。想象一个场景，其中多个开发人员在一个过程中工作。几年前，当我所在的团队在 AWS 上构建基础设施和资源时，我亲身经历了这种场景。我们要么不得不等待并重新确定每个拉请求的基础以应用变更，要么放弃团队工作的能力。当时的工具使我们让一个人负责基础设施的创建和部署。那个人竟然是我！为您的 Terraform 模块编写单元测试是一个最佳实践，但是对您的代码所做的每一个更改都运行测试可能会浪费时间，因为它必须是手动的。相信我，我跳过了这一步。

本地创建的另一个问题是安全性。即使使用像 Vault 这样的外部解决方案，也可以访问状态文件，简单的 terraform 状态拉取可能是灾难性的。还有一次，一位同事在本地创建了一些 IaC，但无法上传到我们的 GitHub 组织。我做了件好事，说我会创建存储库并上传代码。不幸的是，我不知道里面埋藏了硬编码的 AWS 访问和安全密钥。我承担了将同事的敏感数据上传到公共存储库的责任。

## 创建您自己的 CI/CD 渠道

旅程的下一步只是将 Terraform 代码添加到您现有的(有时是遗留的)[持续集成和持续部署](https://thenewstack.io/category/ci-cd/)工具中。使用 [CI/CD](https://thenewstack.io/a-business-perspective-on-ci-cd-pipelines/) ，可以避免上面讨论的特权访问问题，因为访问只能应用于执行层。

同时，开发人员只有读取级别的权限。CI/CD 管道生成系统日志，可用于跟踪每次运行的更改。拉式请求状态检查可以配置为运行林挺、合规性检查和自动化单元测试。

并发运行 [CI/CD 管道](https://thenewstack.io/3-ways-to-use-automation-in-ci-cd-pipelines/)会导致管道失效的竞争情况。当一个拉请求在另一个之前几秒钟被合并时，管道被触发，导致一些失败。当代码库包含状态锁定(一个关键的最佳实践)时，这是很常见的。第一个 pull 请求锁定状态，其他请求失败，因为它们是同时触发的。

这可以通过配置排队运行来解决，但是在大多数 CI/CD 工具中创建排队运行是有挑战性的。在为成功的集成和部署创建一个有效的 CI/CD 时，我们必须考虑，例如，单元测试、模块共享和定期漂移检测。

正如我之前所描述的，我所在的团队也经历了这种情况。您甚至可以在 YouTube 上找到一些视频，在这些视频中，我们详细描述了从基础设施到应用程序的整个流程。这对于演示来说非常有用，但是操作起来会非常困难。尽管定制你自己的弗兰肯斯坦 CI/CD 看起来很诱人，但请在走这条路之前仔细考虑。

## 使用开源软件

有许多开源工具可以帮助 Terraform 自动化。一整类工具被创造出来，叫做 TACOS，Terraform 自动化和协作软件。当规模成为一个问题时，可以利用它们向 Terraform 基础架构添加额外的功能。

例如，看看 Atlantis，它是与 Terraform 相关的最常见或最受欢迎的开源工具，用于增强自动化和协作层。这是一个开源工具，允许开发者更容易地管理任务和操作。

其他受欢迎的选项包括 Terratest、Terraformer 和 Terragrunt。根据您的需求，有许多[开源 Terraform 项目](https://github.com/shuaibiyy/awesome-terraform)可用。

虽然我热爱开源并继续倡导它，但有时它们只是填补了旅程中的一些空白，托管解决方案很快就出现了。

## 使用托管解决方案

### 地形云

第一个进入市场的是 Terraform 的创建者和维护者 HashiCorp。本质上，新开发的 Terraform 功能可以并将在 Terraform Cloud 中实现。借助 Sentinel 等高级安全遵从机制，它完全允许您在代码部署之前使用组织标准。

Terraform Cloud 提供的远程执行后端非常高效，因为它允许在您的计算机上使用 Terraform，因为您可以在本地上传代码库并对其运行 plan，这是一种验证您的配置是否有效的简单方法。

### 太空升降机

在 Terraform 支持和部署执行方面，Spacelift 和 Terraform 实际上具有与 Terraform 云相同的功能。你可以[比较太空飞船和地形云](https://spacelift.io/terraform-cloud-alternative)。

合规性是 Spacelift 具有优势的一个领域，部分原因是因为依赖于[开放政策代理](https://www.openpolicyagent.org/)(OPA)；跨云原生堆栈的统一开源工具集和策略框架。OPA 已经成为当今市场上许多安全解决方案的基础。选择 OPA 允许 Spacelift 在解决方案中提供策略，并与许多专门从事安全和合规性最佳实践的供应商集成。

## 结论

你从哪里开始？第一步是理解组织的最佳实践和技术需求。每个组织都是不同的，从不同的点开始，并以不同的原则和实践来确保 DevOps 的成功。在经历了几年的旅程并与业内同行交谈后，我了解到，从人类的角度来看，利用 Terraform Cloud 或 Spacelift 这样的平台来提供必要的功能并按代码扩展基础设施更具成本效益和理想性，这使我们所有人都有更多的时间与家人相处，享受我们的爱好并为我们最喜欢的非营利组织做志愿者，而不是担心我们的云资源。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>