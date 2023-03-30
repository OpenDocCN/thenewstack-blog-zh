# HotJar 如何使用 DevOps 将其部署速度提高 50%

> 原文：<https://thenewstack.io/how-hotjar-sped-up-its-deployments-by-50-using-devops/>

[GitLab](https://about.gitlab.com/) 赞助本帖。

 [布雷因·马特罗

Brein 是 GitLab 的高级内容营销经理和客户，是一位经验丰富的软件技术作家和编辑。她与丈夫和两个儿子住在新罕布什尔州，教授 Vinyasa 瑜伽，并拥有一家 Ben & Jerry's。](https://www.linkedin.com/in/brein-matturro-081a801/) 

随着越来越多的公司采用远程友好的工作场所结构，拥有一个灵活且有凝聚力的 DevOps 堆栈比以往任何时候都更加重要。

对于 [HotJar](https://www.hotjar.com/) ，一个在 20 个国家拥有 100 多名员工的完全偏远的公司来说，这不仅重要，而且势在必行。

HotJar 是一个行为分析软件产品，它超越了传统的 web 分析，并了解用户在网站上真正在做什么。通过定量和定性的行为分析工具，HotJar 概述了如何改善客户体验、绩效和转化率。该公司成立于 2014 年，目前有超过 50 万客户使用它来改善他们的网站。

## 依赖太多，生产力不够

由于 HotJar 的全远程文化，随着公司的发展扩展其通信成为其最大的挑战之一。

“100 人和 18 人之间的交流是难以置信的不同，”HotJar 的人力运营专家[萨拉·本特](https://www.linkedin.com/in/sara-bent/)说。“现在有了更多的信息。有一个要素是要确保我们有团队需要的可用信息，但不要让每个人都淹没在有时不相关的信息中。”

> 开发人员现在可以专注于生产，而不是错误和修复。

作为一家公司，HotJar 的核心价值观之一是透明。然而，有时成为一家透明的公司意味着进出公司的大量信息让每个员工都能看到。最初，没有真正的方法将所有这些信息储存或过滤给正确的接收者。Bent 经常被不相关的信息淹没，导致她错过了她需要关注的重要信息。

HotJar 开发人员最初在已经存在的笨重的遗留系统上构建他们的工作。他们不得不使用那些遗留的工具来处理代码库，这降低了生产率，并且阻碍了向正确的团队成员交付相关信息。

“我们试图解决的问题是如何从这种[遗留系统]转向更多样化的设置，”hot jar SRE 团队负责人 Vasco Pinho 说，“我们仍然有一些基础设施遗留部分，但也有一些新的微服务部署。然后是如何整合所有的新事物，这样我们就可以在不降低生产率的情况下继续增加内部开发人员的数量。”

HotJar 的开发人员使用 BitBucket 托管其源代码，使用 Jenkins 托管其持续集成和持续交付(CI/CD)。由于一些遗留应用程序的限制，他们不得不开发和维护大量特定于 Jenkins 的代码来支持他们的管道。这消耗了大量资源，并且是对他们时间的无效利用。

HotJar 还使用 Kubernetes 作为他们所有微服务和一些构建管道的平台。他们需要一个能够提供 [Kubernetes 集成](https://about.gitlab.com/solutions/kubernetes/)和 Jenkins CI/CD 替代品的解决方案。虽然他们也尝试过将 BitBucket 用于 CI/CD 和 Concourse，但都没有提供他们所寻求的完整集成解决方案。

“就提供整个生命周期的 Kubernetes 本地产品而言，我们没有发现太多竞争对手，”Pinho 说。“我们看到的一些应用程序可能需要自己托管。Jenkins X 是 Kubernetes-native，但我们发现它不成熟，仍然有很多 bug。”

### 自然地找到正确的匹配

在尝试了各种工具来满足他们的需求后，HotJar 进入了 GitLab 的试用阶段。在本地运行之后，很快就清楚 GitLab 提供了团队需要的一切，甚至更多。

“虽然我们的痛点是开始寻找詹金斯的替代品，但一旦我们尝试了 GitLab 的管道，看到他们将开发体验完全集成到一个工具中的方式——以及满足我们所有的 CI/CD 要求——我们就开始考虑将我们的代码也迁移到 GitLab，”Pinho 说。“我们的开发人员认为 GitLab 的界面和功能优于 Bitbucket，例如代码审查流程。所以我们决定拥抱整个平台。”

HotJar 最初在 Jenkins 中创建了许多自定义代码，现在他们可以通过 GitLab 原生地做许多相同的工作。他们曾经使用云版本的 Bitbucket 进行代码管理，现在他们使用 GitLab.com 进行所有开发工作，并托管他们的 [CI/CD 运行](https://about.gitlab.com/stages-devops-lifecycle/continuous-integration/)。

“这不是很多其他供应商提供的东西，”皮尼奥说。“我们不必担心托管网站，但它仍然允许我们灵活地运行我们自己的构建基础架构，”。

Hotjar 想要保持的灵活性的一部分是远程工作的能力，并且做得很好。

本特说，创始人“从一开始就远程工作，因此必须围绕远程工作建立所有这些流程”。“这确保了我们有一个非常坚实的基础，确保我们的远程通信和协作运行良好。”

GitLab 对工作流程的端到端可见性使开发人员可以随时看到每个人在做什么。对信息的访问有助于维持 HotJar 的远程通信。

### 结果:增加部署，更好的 AWS EKS，和改进的开发工作流程

如今，HotJar 的每个工程团队——以及它的一些客户支持团队——都在使用 GitLab。他们都说整体用户体验比 BitBucket 有了很大的改进，GitLab 的审查环境对于任何需要视觉审查的工作来说都是一个改变。HotJar 的开发人员还可以在管道中更早地捕捉错误，这样他们就不会像以前那样遇到 stage 环境。

GitLab 与 Kubernetes 的原生集成也让开发团队高枕无忧。现在，他们可以相信该工具会自动工作，无需持续维护。开发人员现在可以专注于生产，而不是错误和修复。此外，HotJar 的构建 CI 时间比之前在 Jenkins 中的实现减少了 30%,这要归功于每个节点的构建密度更高，所需的扩展操作更少。

GitLab 项目也连接到 HotJar 的 [AWS EKS 集群](https://about.gitlab.com/handbook/marketing/product-marketing/technical-marketing/howto/eks-cluster-for-demo.html)。测试在集群中运行，使用 Kubernetes 操作符，然后报告覆盖率。然后工件被上传到 AWS ECR/S3。审查环境随后在审查期间在 EKS 集群内旋转。在合并之后，工件被再次部署到生产环境中。

“我们从部署到生产只用了一半的时间，”Pinho 说。

现在，HotJar 团队成员不用托管源代码管理和他们自己的工作流，或者试图找出为什么他们的 [Git 库](https://about.gitlab.com/blog/2019/10/28/optimize-gitops-workflow/)关闭，而是能够看到哪些更新正在计划过程中。这使他们能够重新帮助客户为自己的用户提供更好的体验。

今天，HotJar 的远程文化继续蓬勃发展。

“大多数人同时在线，因此你可以期待(一个合并请求)在几小时或几分钟内得到审查，并能够进行视频通话以调试问题、讨论项目等。”皮尼奥说。“我们绝对不会遭受完全远程办公室通常带来的痛苦，在那里，查询有时要到第二天早上才能得到答复。”

正如 GitLab 提高了 HotJar 的通信和开发协作能力一样，它也有助于提高其透明度水平。在看到 [GitLab 的 1000 多页员工手册](https://about.gitlab.com/handbook/)也可以在网上获得后，HotJar 最近在网上公开发布了其公司[手册](https://hotjar.atlassian.net/wiki/spaces/REC/pages/269942983/Team+Manual+Public)。

“我们看到了(HotJar 和 GitLab 之间的)相似之处，看到什么对我们双方都非常有效，这是一件令人欣慰的事情，”布伦特谈到 GitLab 对 HotJar 的 DevOps 工作流程和远程文化的影响。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>