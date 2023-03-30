# 今天的 CI/CD:从“胖牧羊犬”到“机器猫”

> 原文：<https://thenewstack.io/todays-ci-cd-from-fat-sheepdogs-to-robot-cats/>

基于软件管理的“[宠物与牛](https://thenewstack.io/pets-and-cattle-symbolize-servers-so-what-does-that-make-containers-chickens/)”类比，谷歌云的开发者倡导者[戴夫·斯坦克](https://www.linkedin.com/in/davidstanke/)本周早些时候在旧金山举行的[devo PS World | Jenkins World 2019](https://www.cloudbees.com/devops-world/san-francisco)上发表演讲时，又加入了几只动物来提及持续集成和部署(CI/CD)的现代化。

当然，宠物是云出现之前的服务器。我们单独照顾他们。在云中，它们是牲畜，只知道是大量存在的，而挑战在于管理畜群。对于 Kubernetes 来说，它们更像一群蝴蝶，他指出这被称为万花筒。

他将新兴平台比作“星际迷航”中的纯能量光束。

“当我与人们谈论他们的 CI/CD 系统时，他们说他们落后于他们的生产系统。他们没有高度进化，”他说。

他提出了这样一个场景:

即使你已经迁移到了云，你的办公桌下还有一个旧的 prod box，上面有 Jenkins。或者它曾经生活在你的书桌下，但你已经搬了几次家，它仍然在那里，在某个地方。

“我们在快速发展的现代生产系统上使用传统的 DevOps 系统。这些是牧羊犬。牧羊犬是管理家畜的宠物。当我们深爱他们时，他们却在拖我们的后腿。他们脆弱、缓慢、负担过重，他说。

构建被破坏了，你不能确定这是一个错误的提交还是 CI 系统的问题。长长的构建队列、溢出的硬盘驱动器怎么办？有这个 CI 系统，但是只有一个人知道怎么做，而且他们在度假。

CI/CD 在实现表现最佳的组织与其他组织之间的关键指标方面发挥着重要作用，这些指标在[devo PS Research and Assessment(DORA)](https://devops-research.com/assessment.html)报告中有所提及——周期时间、发布时间、变更失败率和平均修复时间。

“对于传统系统，您需要花费大量时间等待 CI 任务完成。他们很慢。他们很古怪。因此，我们需要快速且可扩展的竞争情报，”他说。

“部署也需要快速，但也需要可扩展性。我们需要与代码库一起发展的 CI/CD。快速、可扩展、可靠、适应性强、安全。这些是我们在生产系统中想要的东西。为了实现这些，我们也需要 CI/CD 中的这些品质。

“我们可以获得现代 CI/CD，但这意味着我们需要淘汰牧羊犬。我们需要更像机器猫的东西。”

这并不意味着抛弃你已经拥有的一切。他说，你可以使用渐进式步骤，指的是谷歌云和 CloudBees 之间的合作。

Google Cloud 的 Graphite 团队创建了与流行的开源工具的集成，以简化在 GCP 上的工作。他们负责 Turbo GCP 提供商、GCP 的 Ansible 模块、GCP 的 CloudFoundry 和 Logstack 插件。

他说，该公司的首要任务之一是制造一流的詹金斯插件，以连接到谷歌云。这包括用于身份验证的 OAuth 插件、用于构建工件的云存储、用于供应工人的计算插件以及用于部署 GKE 的 Kubernetes 引擎插件。

CI/CD 面临的一大挑战是可扩展性。当工程师们在白天工作时，系统变得超负荷，但当他们不工作时，系统就处于闲置状态。这既昂贵又低效。

在云中，您可以按需供应来构建模板。每当构建队列开始时，Jenkins 都会及时剥离一个工人。您可以一次根据需要并行运行尽可能多的实例，只有在实例实际工作时才会为它们付费。

Graphite 团队为 GCE 提供了一个插件，可以自动提供和终止计算实例。按需代理易于保持最新状态。如果有安全漏洞，不用一个一个绕过去。只需更新模板。每项工作都有一台干净的修补过的机器。

这样，詹金斯大师还能住在你的桌子底下。然而，它仍然更具可扩展性，也更安全。

Kubernetes 怎么样？

缺乏一致性是组织的一个共同点。他们有很多应用程序，在不同的时间构建，有很多技术。不同的语言，框架，大量的依赖。

“这是难为宋词了。每个应用程序都有不同的工具链，所以我们让员工使用各种工具，Java、Python、. NET。每种工具的多个版本都相互碰撞。我们给这些宠物吃得太多了，”他说。

有了 Kubernetes 上的 Jenkins，你可以得到定制的、容器化的工人作为代码。您的工人定义与他们构建的代码一起在版本中陈述，而不是有一个预烤的模板存在于云配置中。每个版本都有合适的工具。他说，不要再养胖宠物了。如果想使用一些特殊的语言，只需在 Docker 文件中添加一行，这个特殊的工具就会在需要的时候出现。建筑完工后就消失了。

在混合环境中，谷歌的答案是 Anthos，这是一个基于开源平台(如 Kubernetes 和 Istio)的托管基础设施堆栈。谷歌云和 [Cloudbees 刚刚开始与谷歌合作，整合 Jenkins 和 Anthos。](https://thenewstack.io/cloudbees-expands-into-software-delivery-management/)

他说，Anthos 提供了跨异构环境的一致基础，因此相同的软件可以在 GCP、数据中心甚至 AWS 上运行，所有这些都具有一致的控制平面。

“这对于 CI/CD 来说非常有趣。他说:“你可以在云中运行你的构建，利用可扩展的工作节点来处理那些尖峰工作负载，然后部署到本地的生产服务器上。

他继续倡导[持续交付基金会](https://thenewstack.io/the-cd-foundation-finds-a-challenging-environment-in-continuous-delivery/)，这是一个专注于减少碎片化和开发行业持久标准的组织。它的四个项目分别是[詹金斯](https://jenkins.io/)、[詹金斯 X](https://jenkins-x.io/) 、[大三角帆](https://www.spinnaker.io/)和[泰克顿](https://github.com/tektoncd)，他称之为我们要找的机器猫。

Tekton 是起源于 Google 的 CI/CD 开源框架。他说，它运行在 Kubernetes 上，因此它获得了云的固有优势，如可扩展性、封装和声明性配置。

JenkinsX 是 Cloudbees 对 Tekton 的实现。它在系统上本地运行，因此工作负载可以在任何可以运行 Tekton 的系统上移植，Tekton 可以是任何 Kubernetes 集群。

他说，有了现代 CI/CD，是时候让牧羊犬退休了。

CloudBees 赞助了这个故事，由 New Stack 独立撰写。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>