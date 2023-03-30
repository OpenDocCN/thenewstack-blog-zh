# 在容器领域，Chef 面临着配置管理格局的变化

> 原文：<https://thenewstack.io/in-container-world-chef-faces-shifting-landscape-for-configuration-management/>

随着 4000 万美元的新投资，开源配置管理和自动化平台背后的商业实体 Chef 似乎准备好了席卷 DevOps 世界。

“对于 Chef 公司来说，这是一个转折点。我们的创新正在成为企业中传统 IT 和新 IT 之间的主要桥梁，”首席执行官 Barry Crist 在声明中说。“今天，我们进入了一个新时代，成为各地数字优先组织的自动化控制平台，这一新资本将帮助我们将 DevOps 纳入主流。”

Chef 首席执行官 Barry Crist 告诉 ZDNet，[容器和合规性](https://www.zdnet.com/article/devops-firm-chef-rustles-up-40m-to-feed-container-focus-and-expansion-plans/)将是投资的两个重点领域，尽管它对其计划保密。该公司通过发言人告诉 New Stack，它还不准备谈论其容器计划。

似乎其他新兴公司在集装箱领域领先一步。SaltStack 在 Kubernetes 中的角色反映了在寻求不变的基础设施(T5)的过程中，与现有的配置管理环境(T3)的决裂，新 Stack 的 Alex Williams 之前写道。

Blue Box Group 的云工程师 Paul Czarkowski 并不认为容器本身对 Chef 构成威胁。他说，Chef 既可以用于编排容器的运行，也可以用于配置容器内部的软件，还可以成功地用于以协调的方式构建、部署和运行 Docker 容器。

“我认识的大多数在生产中成功运行 Docker 的人都在使用这种方法。这一点尤其重要，因为很少有地方可以在 Docker 容器中运行他们所有的应用程序，他们也不应该觉得有必要这样做，”他说。

> “通过使用 Chef，他们可以使用相同的工具管理他们的 Docker 化和传统工作负载，这允许您在不中断所有现有工具的情况下引入 Docker。

“也就是说，”他补充道，“更大的容器生态系统开始提供方法来做 Chef 目前会做的[大多数]事情。像 Mesos 和 Kubernetes 这样的容器运行时编排系统以及像 Deis 和 CloudFoundry 这样的平台对 Chef 来说是一个威胁，因为更高级的云原生应用程序可以在容器中愉快地运行。尽管如此，还是需要安装和管理这些系统/平台。”他预测，目前使用 Chef 的组织可能会继续这样做。

## 强劲增长

4 月，Chef 宣布这是公司历史上增长最强劲的一个季度。它还推出了 DevOps 工作流服务 [Chef Delivery](http://techcrunch.com/2015/04/01/chef-launches-chef-delivery-devops-workflow-service-for-the-enterprise/) ，旨在加速基础设施、运行时环境和应用程序(包括容器)的交付。这最初是一个只有邀请才能参与的项目，该公司表示计划慢慢开放这项服务。同时，它宣布了 DevOps 平台与 Canonical 的 Ubuntu 企业发行版的[集成。](https://www.zdnet.com/article/canonical-to-integrate-chef-devops-into-ubuntu/)

它公布了与微软的合作伙伴关系，以开发与 Azure 的集成，并计划在网络层与思科和 F5 进行集成，以及与 Splunk 和 Sumo Logic 进行分析集成。去年，惠普在其[“协调数据中心”](http://www.enterprisetech.com/2014/05/21/hp-orchestrates-datacenters-openstack-chef/)产品中采用了 Chef 配置管理工具。

然而，Chef 面临着多方面的竞争——来自 Puppet、Ansible、Salt 和其他公司。 [SaltStack 也被微软 Azure 用作 Kubernetes 中的核心编排管理引擎](https://thenewstack.io/saltstacks-big-role-in-google-kubernetes-and-why-immutable-infrastructure-makes-the-cloud-a-giant-computer/)，CoreOS 有自己的配置 Kubernetes 的方法，称为 [Cloud-Config](https://coreos.com/docs/cluster-management/setup/cloudinit-cloud-config/) 。

与此同时，今年早些时候，竞争对手 Puppet Labs 推出了其企业平台的最新版本 Puppet Enterprise 3.8，其中包括管理 Docker 和 Docker 容器。它也在第一季度宣布了有史以来最强劲的季度。

该公司指出，最初的 Puppet Docker 模块大约与 Docker 同时发布，社区努力已经记录了超过 200 个拉请求，仅从 Puppet Forge 就有近 [10 万次下载。](https://forge.puppetlabs.com/garethr/docker)

Puppet 也将与思科在其 [NX-OS 平台](http://www.fierceenterprisecommunications.com/story/cisco-boosts-sdn-strategy-puppet-automation-nexus-switches/2015-08-05)上合作，以加速软件定义的网络基础设施的部署。

## 方向不同？

然而，一年前，New Stack 的 Chris Dawson 注意到 Docker 开发人员中似乎有一种[的趋势，他们倾向于 Ansible](https://thenewstack.io/are-docker-users-migrating-to-ansible-and-away-from-puppet-and-chef/) ，而不是厨师和木偶。

在那篇文章中，来自 Chef 的科林·坎贝尔区分了 Chef 和 Ansible 这两种工具处理的两种职责:创建容器和配置容器。他说 Ansible 第一个做得好，第二个不行，而 Chef 擅长配置。Chef 服务器在容器内部运行，并将配置放入其中。Ansible 使用 SSH 来编排映像，SSH 守护进程通常不在容器上运行。

Dawson 还注意到 Docker 开发人员明显偏爱 Python 语言，而 Chef 和 Puppet 是用 Ruby 编写的。(最近的 [RedMonk 编程语言排名](http://redmonk.com/sogrady/2015/07/01/language-rankings-6-15/) 把 Python 放在第 4 位；鲁比三人并列第五；继续，码头工人的语言，快速上升到第 15 位。

Dawson 指出，Docker 的主要承诺之一是帮助开发人员将复杂的 ops 任务迁移为可行的任务。

“今天，Chef 实际上仍然是 IT 部门的定制工具，很难让开发人员在意。这就是 Docker 真正的威胁所在，”分析师 Chris Riley 说。

他说，为了让 Chef 大量参与 DevOps，它需要超越编排，真正成为整个管道的一部分，这是通过专注于 Chef 交付来实现的。

> “事实上，Chef 在 Docker 上面临的技术挑战似乎很小，也不太复杂。相反，他们需要更好的回答何时以及如何一起使用 Docker 和 Chef，这也可能意味着更好的管理工具——这是 Docker 非常薄弱的地方，”Riley 说。

他说他希望看到更多更好的与云提供商的整合。云基础设施提供商 ProfitBricks 刚刚宣布了 Ansible 和 Chef 的这种集成。

“我认为底线是 Chef 可能会陷入一个大量使用但没有发展的 IT 工具的陷阱，所以从我们用来构建服务器的东西过渡到交付链中具有更好集成和更全面管理工具的关键部分是必要的，”Riley 说。

Czarkowski 希望看到 Chef 提供更多的工具，可能以社区食谱的形式来构建和运行各种系统，如 Mesos 和 Kubernetes，以及与这些系统交互的资源。

他说工作流程可能是这样的:

**Operations / DevOps** :使用 Chef 构建和维护 OpenStack。
**Operations / DevOps** :使用 Chef 在 OpenStack 之上部署和维护 Mesos。
**Operations / DevOps** :使用 Chef 来部署和维护监控、日志记录和有状态服务——比如数据库——它们可以被应用程序使用。
**Operations / DevOps** :使用 Chef 部署和维护 CI/CD 基础设施(Jenkins、Docker Registry 等。).

**开发者**:使用 Docker Compose 开发应用。
**开发者**:将代码(包括 dockerfile)推送到 Git。
**开发者(或 Git hook)** :调用 Jenkins 测试代码，构建 Docker 镜像，推送到 Docker 注册表。

发布工程师:告诉詹金斯部署新代码。Jenkins 使用 Mesos 工具或 Chef 来部署代码。

思科、CoreOS、Docker、惠普和 ProfitBricks 是新堆栈的赞助商。

特征图片: [Patrick Emerson](https://www.flickr.com/photos/kansasphoto/) 制作的[梭织](https://www.flickr.com/photos/kansasphoto/4682126666/in/photolist-88K88Q-bS7SWp-c1RiB5-4CGEb-nYuE4A-dZc21E-Tk5Bf-kZtKo-o5Lbiz-5pnHHs-ojrwjj-57mibP-5rCjjT-5pZZ4s-rykL7Y-2fw6sG-c1KHKq-oLCz5-dYMs1i-9u3TG9-7QiKjC-7QfoWB-HaBPH-2fw6rd-okqcqb-9tZRPc-cuaZj-MzvQV-dYMvgM-FR9ZK-o781aG-5AcCbs-iat43T-inuyhn-o4967d-6VNKXh-6wh6KX-kmBbWx-8pAZ3N-6cwnrY-fQhQb9-6qUYz-asNixR-qF6yX-7rLrWp-ceRpr-iRpH6N-DPXTs-ef6WRN-64QzZn)在 [CC BY-ND 2.0](https://creativecommons.org/licenses/by-nd/2.0/) 下获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>