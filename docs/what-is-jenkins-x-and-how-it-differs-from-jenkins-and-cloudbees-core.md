# 困惑的终结:詹金斯还是詹金斯 X

> 原文：<https://thenewstack.io/what-is-jenkins-x-and-how-it-differs-from-jenkins-and-cloudbees-core/>

早在 Kubernetes 和运行在云原生平台上的分布式系统出现之前，Jenkins 就已经作为一个持续集成(CI)工具。将 Jenkins 作为一个独立的开源工具来使用——正如开发人员和运营人员首先会说的那样——也是极其困难的。

现在，最近，向云原生和 Kubernetes 的转变给组织带来了更多特定于管理的挑战。因此， [Jenkins X](https://jenkins.io/projects/jenkins-x/) 成为了一种改善和自动化向 Kubernetes 和云原生环境持续交付管道的方式。然而，对于许多人来说，Jenkins 和 Jenkins X 管道之间的兼容性是一个问题。在 Reddit 和其他渠道的论坛帖子和评论中，每个人的角色也是一个令人担忧的问题。

事实上，随着企业继续使用管道进行内部部署、云原生部署或两种类型的组合部署，了解每种部署的作用、Jenkins 不断变化的环境以及 cloud bees(Jenkins 的商业发行版)所扮演的角色也成为了困惑的来源。

简而言之，Jenkins X 确实适合 Kubernetes 部署——但这并不意味着它一定需要替换现有的 Jenkins 配置，至少目前是这样。这也不意味着 Jenkins X 无法管理内部或非云生产管道的 Jenkins 管道。同时，CloudBees 对两者都适用。因此，很难理解每个人所能扮演的角色。

“对于人们来说，理解是一个很大的飞跃——基本上，我们看到了很多困惑。此外，很多事情都在发生变化，我们看到了(甚至更多的)混乱，” [Jenkins X](https://github.com/jenkins-x) 项目负责人 [CloudBees](https://www.cloudbees.com/) 的高级架构师[詹姆斯·斯特拉坎](https://www.linkedin.com/in/jstrachan/)说。“在 CloudBees 内部和我们的客户之间存在很多误解。我希望我们能把这一点说得更清楚一点。我觉得应该表现出来，比如你可以用詹金斯 X 来编排詹金斯。”

[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 说，在很多方面，“几乎每次你重命名知名软件项目时”，都会出现混乱。“还记得当 Docker 将其软件的社区版本改名为莫比时引起的强烈抗议吗？这里的问题是 CloudBees 首先提出了 Jenkins Enterprise 和 CloudBees Suite 产品名称，而 Jenkins Enterprise 已经开始支持容器了，”Volk 说。“然后将所有这些乱七八糟的东西打包到 CloudBees 核心产品中总是很难，但必须完成。”

Strachan 说，现在的想法是将经典的 Jenkins 世界和 Jenkins X 世界融合为一种体验，“因此，如果一个组织，例如，将 Jenkins 服务器结合用于无服务器和自动化管道，例如，具有单一用户界面(UI)和命令行界面(CLI)的内部部署，这真的无关紧要”。"这两个用例都得到了解决，因为一些团队两者都在使用，对吗？"斯特拉坎说。“一些团队正在构建新的微服务，但他们仍然拥有传统的虚拟机。”

斯特拉坎没有出来，并形容詹金斯 X 为“詹金斯 2.0。”然而，人们希望 Jenkins X 在最近发布后，将最终覆盖所有 Jenkins 管道的基础，包括经典管道和 Kubernetes 管道。“我认为，我们还没有真正向社区传达足够好的信息:Jenkins X 实际上是每个人在某个时候将如何使用 Jenkins，”Strachan 说。

## 使用案例

至少从表面上看，采用 Jenkins X 作为 Kubernetes 生产管道的论点显然是有道理的。正如 Jenkins X 的作者所定义的:

“Jenkins X 是 Kubernetes 上现代云应用的 CI/CD[连续交付]解决方案… Jenkins X 提供管道自动化、内置 GitOps 和预览环境，以帮助团队协作并加速任何规模的软件交付。”

对于那些开始一个新的绿地项目的人来说，“你没有 CI，你只需要直接去 Jenkins X，这很容易——你只需要自动化所有的东西，你就完成了，”Strachan 说。

但是在云本地管道的使用范围之外，事情可能变得模糊不清——至少从一开始是这样。例如，在许多人的心目中，Jenkins X 仍然不是很明显，如前所述，它也旨在为那些仅具有内部生产管道需求的组织服务，无论他们最终是否决定部署到云原生平台。

斯特拉坎说，他接触过的大多数组织都已经为 Jenkins 建立了管道，并希望将它们扩展到 Jenkins X 中。这可能对你更好…但从长远来看，我们希望摆脱你手写的詹金斯文件，因为我们认为我们的管道可以做得更好。"

在 Jenkins X 最终产品发布后的几个月里，这些工具被认为在融合 GitOps 概念和利用 Kubernetes 作为编排和目标平台方面做得很好， [AppDynamics](https://www.appdynamics.com/) 的技术宣传员[Ravi lach man](https://www.linkedin.com/in/ravilachhman)说。“通过利用 Kubernetes 作为运行 Jenkins X 的平台，CI/CD 解决方案在资源放置方面可以更加强大，例如工作节点和可用性。”

最后，“无论开源平台是什么，每个组织在考虑构建还是购买时都是不同的，”Lachhman 说。“CloudBees 在其领域/堆栈中提供了大量专业知识，并提供可扩展性、安全性和支持方面的功能。对于精通 GitOps 的团队来说，Jenkins X 是在 Kubernetes 上运行 CI/CD 堆栈的现代处方，”Lachhman 说。“Jenkins 系列作为许多 DevOps 管道的主干继续发展，并随着云原生架构的推进而继续发展。”

“CloudBees 是一家商业开源软件公司，编写了绝大多数的 Jenkins 代码。Redmonk 的分析师和联合创始人 [James Governor](https://www.linkedin.com/in/jamesgovernor/) 说:“这种结构在商业开源领域并不罕见。“Jenkins 是一个比 CloudBees 更知名的品牌，但在开源分发远远领先于商业客户收购的情况下，这也是非常常见的。”

## 战略暴露

Volk 说，CloudBees 自 2010 年以来已经吸引了 1.12 亿美元的资本，因此需要尽快达到终端速度。“他们设法为他们的各种詹金斯支持产品注册了数百名付费客户，但同时他们需要向詹姆斯·斯特拉坎这样的优秀人才支付费用，他是詹金斯和詹金斯 X 项目的主要贡献者之一，”沃尔克说。“当然，他们需要支持大量 Jenkins 与所有基础设施和中间件的集成。”

Volk 说，Jenkins X 项目也是必要的，以便在 Kubernetes 支持方面不落后于 Xebia Labs、Atlassian 和 Electric Cloud 等竞争对手。

“这就是为什么他们决定将 Jenkins、Jenkins X、Codeship 和他们的 DevOps 分析产品整合到一个跨越整个企业的 DevOps 管理平台中，”Volk 说。“他们现在需要做的是宣传 CloudBees Core，并解释他们参与了 Jenkins 和 Jenkins X，这很难。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>