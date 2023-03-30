# CircleCI Orbs 提供开箱即用的 CI/CD 配置

> 原文：<https://thenewstack.io/circleci-orbs-offer-out-of-the-box-ci-cd-configuration/>

公司的钟摆一直在摆动:自由与标准化。护栏对大门。开发与运营。工作流程与灵活性。DevOps 和持续集成/持续交付(CI/CD)系统的自动化主干必须经常调整，以便在这些二分法之间找到正确的平衡。

“你想要自由，但你想要在一个明确的途径内的自由，使组织仍然能够在决策上富有成效，”circle ci T1 的业务发展副总裁 T2 Tom Trahan T3 说。他说，大约七年前，微服务的爆炸是由开发人员主导决策的文化变化支持的——一种想用什么就用什么的哲学。但这种情况越滚越大。

这可能在荒谬复杂的[云原生计算基础图中得到最好的说明，该图展示了云原生环境](https://landscape.cncf.io/)，在本文发布时，该环境拥有不到 1300 个专用于定义和部署、编排和管理以及供应的工具和平台。对于快速发展的组织来说——它们通常也从合并和收购中继承堆栈——选择太多了。

本周，CircleCI 发布了一组新的软件包，称为“orbs”，将推荐的护栏和自动化带到使用其 CI/CD 软件和服务的组织的部署端。

orb 来自行业中的许多合作伙伴，如允许测试和部署 Salesforce 定制的 Salesforce orb。还有一个 Google CloudRun orb，它允许 CloudRun 无服务器容器在云中运行，而无需考虑底层基础设施。另一个受欢迎的补充将是 Kubernetes orbs，它为运行私有 Kubernetes 集群的组织创建了一个通用基础，可部署到亚马逊 EKS、Azure Kubernetes 服务、谷歌 Kubernetes 引擎和 Red Hat OpenShift。

## 可重用性减少了选择

随着钟摆回到组织主导的软件开发选择，像所有 CI/CD 和 DevOps 一样，这种趋势也反映在运营方面。

Trahan 说，“这是一个相对较新的现象，软件开发人员和操作人员一直在寻求在软件交付中实现相同的实践。”

首先也是最重要的，新版本是关于尽可能自动化，包括自动化部署。这种程度的自动化允许工程师的创造潜力，快速发布，同时减少停机时间和安全风险。

这种趋势已经发展到创造护栏，允许选择的工具明显更少，而不是所有可能的选项。这反过来防止了你所谓的意大利面条式代码的分布式版本，并允许团队重用、回收和学习他人的工作。

“许多人为代码的质量做出了贡献，”Trahan 说。

考虑到这些好处，[一年多前](https://circleci.com/blog/optimizing-open-source-projects-on-circleci/)，CircleCI 推出了“orbs”一个 orb 是一个配置包——非常类似于 Ruby gem 或者 NPM 库为 Node.JS 工作的方式

一旦一个组织在 orb 中创建了某个集成的工作流，它就在一个公开的、完全可搜索的注册表中发布。一旦 orb 被创建，它保证了可变性，这意味着你的依赖不能删除它。

Trahan 说，这种可重复执行的代码在开发领域很常见，但是“在 CI/CD 中是相对独特的”

这并不是说组织希望完全限制工程师的选择，他们只是希望将选择限制在现有的最佳工具上，如语言、安全、林挺和云提供商。他们希望他们的团队能够使用正确的工具，这包括在一个空间内标准化一个、两个或三个数据库、源代码控制系统和安全工具。

Trahan 继续说，使用 CircleCI orbs，“你通过学习曲线的上升来工作，并决定你希望它如何工作，”根据需要进行调整。

他将 CircleCI orbs 称为“一个中心，在这里组织可以将所有这些东西整合到一个 CI/CD 平台中，使用现成的用例，而不需要复杂的配置。”

## 作为代码部署

CircleCI 目前拥有超过 115 个来自 Heroku、Kubernetes 和 Helm 等服务的认证和合作伙伴 orb，在 [CircleCI orb 注册表中列出了超过 1200 个 orb。](https://circleci.com/orbs/registry/)

最流行的 orb 用例是作为代码进行部署。这些部署 orb 允许开发人员根据他们当前的设置和工作流选择他们想要部署到的位置，并使用预打包的配置在几分钟内创建一个集成。

Trahan 将这种“代码部署”称为“自动化流程以获得性能水平的正确方法，即在您的组织中尽可能多的验证时间，以便您可以尽快将想法传达给客户。”

“当一项新技术问世时，想要利用它的人会有很多机会，”Trahan 解释道。

[正如我们已经知道的](/how-much-time-do-developers-spend-actually-writing-code/)，开发人员花在维护、测试和保护现有代码上的时间比他们写或改进代码的时间要多。迁移到无服务器是一种非常耗时的情况，需要花费几个小时甚至几天来编写部署 CircleCI 部署 orb 解决的无服务器平台所需的集成。

orb 成为一个模板，通过共享最佳实践的信心来加速该过程。

平台即服务提供商 [Convox](https://convox.com/) 已经与谷歌、Salesforce 和 VMWare 合作的 orbs 合作。

Convox 联合创始人卡梅伦·格雷说:“与 CircleCI 合作建造 Convox orb 是如此简单和强大。借助 Convox CircleCI orb，我们的客户能够构建应用程序、运行测试并部署到运行在多个云上的 Kubernetes 集群，所有这些都只需一个工作流程，这将为用户节省时间来做最重要的事情。”

切尔莱西和 CNCF 是新堆栈的赞助商。

来自 Pixabay 的 CJ 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>