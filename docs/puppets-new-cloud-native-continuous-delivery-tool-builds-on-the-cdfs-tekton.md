# Puppet 的新云原生连续交付工具建立在 CDF 的 Tekton 之上

> 原文：<https://thenewstack.io/puppets-new-cloud-native-continuous-delivery-tool-builds-on-the-cdfs-tekton/>

Puppet 已经发布了其 [Project Nebula](https://puppet.com/project-nebula) 的公开测试版，这是一个云原生工具，将 DevOps 团队的现有工具集连接到一个端到端的连续交付平台。该公司旨在通过将基础架构供应、应用部署和通知的常用工具连接到一个自动化的工作流中，来简化微服务和基于无服务器的应用的部署。

“世界上有少数人相信一种工具可以解决所有问题。还有一些人相信最佳产品，相信用正确的人和正确的文化为正确的工作提供正确的工具，”[木偶](https://puppet.com/)的产品管理高级总监[马修·杨](https://www.linkedin.com/in/mattyoung/)说。“我们真正追求的是后者……我们并不是要取代所有其他工具。”

Project Nebula 目前支持包括 Terraform、Helm、Kubectl、Slack 等 20 多个工具。Young 说，随着 Puppet 瞄准主要的集成工具，如 GitLab 和 Jenkins，这个列表将继续增长。

由此产生的管道或工作流可以通过 [GitOps 方法](/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/)以声明方式进行管理。在 git 命令 git-push 的触发下，Nebula 启动部署工作流，并将来自各种工具的日志聚合到该过程的逐步可视化中，从而实现更加集中的调试和优化。例如，为了将应用程序部署到 Kubernetes，Nebula 将在 Google Kubernetes 引擎中提供一个 Kubernetes 集群，然后按照预定的步骤推出应用程序，然后通知 Slack 中的 DevOps 团队，并在完成后关闭吉拉的票证。Puppet 已经在其免费社区市场 [Puppet Forge](https://forge.puppet.com/) 上提供了一些 Nebula 工作流。

## CDF 之外的第一个商业 CD 工具

Project Nebula 建立在 Tekton 的基础上，Tekton 是一个开源项目，始于谷歌，并于去年三月捐赠给持续交付基金会。Puppet 的解决方案是 CDF 合作的第一个商业产品，其创始成员包括 CloudBees、Google、JFrog、网飞和其他公司。

“有许多公司在各种综合发展基金项目的基础上进行建设。这是公司在 Tekton 基础上开发产品的最早例子之一，这仍处于早期阶段，”[云计算原生计算基金会](https://www.cncf.io/)首席技术官/首席运营官、[Linux 基金会](https://training.linuxfoundation.org)开发人员关系副总裁 Chris Aniszczyk 通过电子邮件说道。“但随着项目的不断成熟，看到人们已经在 Tekton 上进行建设，这是令人鼓舞的。”

Puppet 凭借其开源自动化供应工具引领了基础设施代码运动，在过去几年中，它在管理云原生工作流方面取得了长足的进步。其 2017 年对 Distelli 的[收购导致了 Puppet Pipelines 的创建，这是其 Puppet Enterprise 产品的 CI/CD 功能的一部分。大约一年前，由于客户开始要求云供应功能，Puppet 也开始在内部开发自己的云原生 CD 工具。在 CDF 宣布前不久，Puppet 将内部云原生管道项目](https://puppet.com/blog/welcome-distelli-to-puppet-family) [Lyra](https://lyraproj.github.io/) 作为开源发布。

CDF 成立后，Puppet 停止了 Lyra 的工作，转而加入 CDF，开始在 Tekton 上构建一个新的 CD 工具。Young 说，Project Nebula 的首席工程师参加了 CDF 的技术监督委员会会议，并从其他成员那里学到了很多关于他们应该在 Project Nebula 中加入哪些功能的知识。例如，Tekton 不包括基于角色的访问控制(RBAC)、秘密管理或 GUI，所有这些 Puppet 都已集成到 Nebula 中，以区别于开源项目和基于它的其他解决方案。

“我们开始意识到 Tekton 在编排云原生工作流方面所做的事情与 Lyra 实际上计划做的事情之间有很多协同作用，”Young 说。“因此，与其有一个相互竞争的项目，一个人的社区与一个以上的社区，我们决定共同努力，让 Tekton 项目成为每个人更可行的选择。

“这是一种啰嗦的说法，我们在过去的 12 个月里学到了很多，”杨说。

## 建立在开源的基础上以走得更快

Tekton 最初是由 Google 为 Kubernetes 上的 Knative 无服务器应用程序开发的构建工具。作为工作流协调器，它位于堆栈的底部，在 Kubernetes 和团队的部署和管理工具之间形成一层。谷歌 Tekton 的软件工程师丹·洛伦茨(Dan Lorenc)说，它与 Kubernetes primitives 和各种工具进行交互，整合、管理和自动化将应用程序从笔记本电脑投入生产的所有步骤。

Puppet 产品管理总监 Eric Sorenson 表示，Nebula 中的所有计算繁重任务都由 Tekton 处理，从并行和排序，以便各个步骤可以同时运行或根据其依赖关系按顺序运行，到步骤和 pod 的生命周期管理以及跨步骤共享数据。

索伦森说:“[Tekton]提供的平台功能将我们的项目加速了 4 到 6 个月，因为它做了很多棘手的计算。”。“这些都是谷歌在内部使用它作为 Knative build 项目时想出来的东西。”

其他公司也在 Tekton 的基础上建立了 CD 产品，包括 Red Hat 的 [OpenShift Pipelines](https://blog.openshift.com/cloud-native-ci-cd-with-openshift-pipelines/) 、 [IBM 的 Kabanero](https://developer.ibm.com/open/projects/kabanero/) 和 CDF 的 [Jenkins X](https://jenkins.io/projects/jenkins-x/) 。但是 Puppet 的星云是第一个直接来源于 CDF 合作的。

“我对[Puppet]从他们第一次开始在 CDF 中提出问题所用的时间以及他们提出问题的速度印象深刻，”Lorenc 说，并指出 Nebula 对于这样一个新的倡议来说是一个功能相当丰富的产品。“他们在 Tekton 上构建的方式是有意义的，这是我们所预想的(当谷歌将 Tekton 捐赠给中国发展基金时)。]我们很高兴看到这次发布。”

Lorenc 说，通过在 Tekton 上开发 Project Nebula，Puppet 正在利用现有的插件和集成生态系统来更快地进入市场。最终用户还可以从市场上更多样化的产品中受益，这些产品满足不同的需求和使用情形，但都建立在相同的基础之上，从而提高了可移植性和互操作性。

“每个人似乎都在努力实现持续部署。他们引用的原因是因为很难以可重复的方式对环境建模，以便人们可以在将代码推出 GitHub repo 时进行测试，”Puppet 的 Young 说。“如果我们能够帮助解决这个问题，我们已经在[Puppet Enterprise]中为连续交付做到了这一点，而且我们可以在云原生空间中做到这一点，你知道，我认为这是互利的。”

Puppet 以配置管理为基础，将开源技术和基础设施的相同原则作为代码移植到云本地空间。凭借其自己的开源 Puppet 和 Puppet Enterprise 用户社区，该公司对企业在将云原生与传统企业基础架构集成并大规模集成时所面临的挑战有着独特的理解。

“我们将继续为开源做出贡献，并努力实现技术的民主化，”Puppet 首席执行官[伊冯娜·瓦森纳](https://puppet.com/company/leadership/yvonne-wassenaar)在本周于波特兰举行的该公司 [Puppetize PDX 2019](https://puppet.com/puppetize) 用户大会上说道。“我们将继续抽象复杂性。我们将确保它的可扩展性和安全性……我们跨越了从数据中心到云再到容器再到裸机的整个环境。”

CloudBees、Cloud Native Computing Foundation、Linux Foundation、Puppet 和 Red Hat 是新堆栈的赞助商。

特写:木偶公司的首席执行官伊冯娜·瓦塞纳尔在 PDX 木偶剧院的舞台上。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>