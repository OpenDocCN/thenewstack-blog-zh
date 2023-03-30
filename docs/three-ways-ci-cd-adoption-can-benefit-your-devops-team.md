# 采用 CI/CD 有三种方式可以让您的 DevOps 团队受益

> 原文：<https://thenewstack.io/three-ways-ci-cd-adoption-can-benefit-your-devops-team/>

在过去的十年中，许多组织在采用 DevOps 方面取得了长足的进步，以更快地交付更好的软件。自动化是在 DevOps 中取得成功的关键因素，而在 DevOps 实践中自动化的关键实现之一是 [CI/CD](https://thenewstack.io/category/ci-cd/) (持续集成/持续交付)，它自动化软件开发工作流，以帮助团队减少手动任务，并快速将软件交付给客户。

随着开发人员[更快地编写和发布代码](https://octoverse.github.com/writing-code-faster/#merging-pull-requests)，多云采用的[增加](https://services.google.com/fh/files/misc/state-of-devops-2021.pdf)，以及工作场所环境在新冠肺炎的影响下处于显著的变革时期，组织和软件团队越来越多地探索新的方式来构建更好的软件发布系统，并在新的分布式工作世界中进行大规模协作。

在 GitHub，我们将 [CI/CD 工具直接集成到我们的核心平台](https://github.com/features/actions?utm_medium=referral&utm_source=outreach&utm_campaign=actions_cicd&scid=edium=content&utm_campaign=actions_cicd)——在与开发人员和公司的合作中，我们看到了将 CI/CD 作为任何工作流的核心部分的好处。使用自动化 CI/CD 平台的组织可以[将合并的拉式请求数量增加 36%，并将合并时间缩短 33%](https://octoverse.github.com/writing-code-faster/#scale-through-automation) 。当团队自动化重复性任务时，如环境设置、数据操作 ui 或应用程序部署脚本，他们报告说[在开源环境中性能提高了 27%,在工作环境中性能提高了 43%](https://octoverse.github.com/writing-code-faster/#scale-through-automation)。

有鉴于此，这里有三种组织可以从投资 CI/CD 和 DevOps 中受益的方式，以更快地构建更高质量的软件，并在这样做的同时更有效地协作。

## **确保流程一致**

最基本的是， [CI/CD 自动化](https://thenewstack.io/3-ways-to-use-automation-in-ci-cd-pipelines/)用于开发运维实践中，通过减少手动任务并使软件开发生命周期(SDLC)中的每一步都一致且可重复，来帮助团队更快地将代码交付到生产中。

 [布莱恩·道格拉斯

Brian Douglas 领导 GitHub 的开发人员宣传工作，他致力于通过互联网上发布的技术内容来增加 GitHub 平台特定功能的使用。除此之外，Brian 对开源充满热情，喜欢指导新的贡献者。](https://github.com/bdougie) 

在企业环境中，CI/CD 管道通过自动化整个 SDLC(从构建到测试和交付)建立在这样的实践之上，因此组织可以系统化软件开发，并为每个阶段及其相应的输出带来一致性。这意味着组织可以更快地交付软件，开发人员可以专注于更重要的工作，并通过自动执行重复和耗时的任务来消除人为错误的风险，这些任务最好由计算机来完成。

除了自动化之外，成功的 CI/CD 实践中还有一个文化因素。CI/CD 实践鼓励开发人员更频繁地提交较小的更改，而不是等待一个版本，而不是发布需要时间来集成和测试代码库的较大代码更改。这有助于软件团队更快地发布迭代更新，因为与较大的更新相比，较小的代码更改更容易集成、测试和部署。当这种文化实践与自动化代码集成、测试、打包和交付的 CI/CD 管道相结合时，它可以帮助组织更加一致地交付问题更少的更好的软件。

例如，在我自己的开源工作中，我使用一个简单的自动化工作流程，称为 [PR Compliance Action](https://github.com/marketplace/actions/pr-compliance-action) 来确保每一个贡献都符合我的项目标准。如果他们没有，我会有一条自动消息告诉他们为什么他们的贡献失败了。

## **船上更安全的软件**

几乎每个开发人员都知道在发布之前测试他们的代码有多重要。在整个 SDLC 中定期测试代码有助于组织更快地发现错误、安全缺陷和问题，从而更容易修复它们，并有助于减轻对软件供应链的下游影响。

但是这里有一个真理:开发人员并不总是像关注构建新代码那样关注测试他们的代码。这就是 CI/CD 的用武之地。当它被成功实现时，CI/CD 可以通过应用一套一致的测试并提供一个反馈循环来帮助以高速度产生无错误的代码。

对于已经投资或正在考虑投资 CI/CD 的组织来说，这意味着确定其 SDLC 中的关键测试点并设计测试套件以确保所有交付的代码都是安全的，这一点至关重要。许多 CI/CD 平台都有预构建的测试，组织可以使用这些测试开始工作。但是，确定何时以及如何应用测试——以及需要利用定制单元测试、应用测试以及静态和动态安全测试的什么组合——取决于组织的独特需求和要求。

任何自动化测试套件的目标都是确保代码库保持稳定、安全和发布就绪。通过将代码审查和批准集成到 CI/CD 工作流中，团队可以提高他们的代码质量，通过集成开发环境或结对编程鼓励协作，并帮助所有背景的开发人员做出更好的提交。日志、可视化工作流构建器和深度集成的工具使开发人员更容易排除故障、理解复杂的工作流，并在构建失败时与更大的团队共享他们的状态。

最好的 CI/CD 管道对代码和权限进行安全检查，同时为审计失败、安全漏洞和不合规事件提供虚拟的书面记录。一些 CI/CD 管道甚至自动开发发布说明，为客户创建变更和安全更新的日志(我使用 GitHub release API[为我的项目生成自动发布说明](https://docs.github.com/en/repositories/releasing-projects-on-github/automatically-generated-release-notes)，这使事情变得更加简单)。

## **打破孤岛，实现更好的协作**

在 DevOps 实践中，每个人都对产品的成功负责——跨 SDLC 的协作是 DevOps 的文化核心。

设计和执行良好的 CI/CD 管道有助于鼓励跨团队协作，减少手动任务的数量，并使开发人员更容易合作开发更高价值的软件功能和更新。事实上，最近的一项调查发现，在没有干扰或干扰很少的日子里，开发人员[度过愉快一天的几率是 82%，相比之下，当开发人员在一天的大部分时间里面临干扰](https://github.blog/2021-05-25-octoverse-spotlight-good-day-project/#patterns)时，这一几率仅为 7%。

随着团队一起工作和共享工具，自动化支持整个组织的一致性、可靠性和效率，使发现和解决问题变得更容易。CI/CD 可以通过创建实时反馈循环来帮助打破障碍和消除孤岛，在反馈循环中可以立即标记问题以进行故障排除。这有助于将传统上孤立的团队(如开发、IT 和运营)聚集在一起，成为一个有凝聚力的团队，提前计划并实时解决问题。

## **##带上这个**

随着越来越多的组织开始采用 DevOps，设计和构建 CI/CD 管道以更快地交付更高质量的软件已经成为一种共同的推动力。但是最成功的 CI/CD 实现也确保了一致的最终产品，提高了应用程序的安全性，并促进了团队之间的协作和交流。获得正确的 CI/CD 意味着为工作采用最好的工具，拥抱 DevOps 文化，并通过 SDLC 进行战略性思考，以使开发人员能够专注于他们最喜欢做的事情:构建优秀的代码。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>