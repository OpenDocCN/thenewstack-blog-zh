# VMware 面向平台工程师

> 原文：<https://thenewstack.io/vmware-targets-the-platform-engineer/>

基础设施软件提供商 [VMware](https://tanzu.vmware.com?utm_content=inline-mention) 的目标可能是开发人员，但在今天的市场上，它是该公司试图接触的平台工程师。

VMware 总经理兼现代应用高级副总裁 [Ajay Patel](https://www.linkedin.com/in/ajaypatel4/) 上周在旧金山的 [VMware Explore](https://www.vmware.com/explore/us.html) 活动上对 TNS 表示，VMware 的目标用户群是大型组织中的平台工程师。

“根据组织的不同，平台团队的章程可能非常侧重于开发人员体验和应用程序运营，并且可能足够宽泛，以涵盖运营方面的问题。”

Patel 说，VMware 的愿景是为开发人员提供一个单一的平台，让他们能够构建在任何云上运行和操作的应用程序，他们不再需要对所有的安全性、合规性和运营问题负责。平台工程师构建集成开发人员、安全团队和操作人员的平台。平台工程故事有助于创建一种叙事，即 VMware 正在推动一种开发人员至上的模型，该模型包含一种 DevOps 方法，其中包括运营工程师、应用工程师或具有系统资源工程背景的架构师。

Patel 举了一个开发人员的例子，他首先得到一个服务目录，一个调色板。然后定义管道，在那里他们编纂安全和供应链。

开发人员将从在 GitHub repo 中构建映像开始，但是从那里开始，需要进入阶段、测试和生产。存在依赖性——使应用程序成为现实的所有东西。这可能是一个消息服务，如 Kafka 和所有需要可用的依赖项。团队可能需要更多的安全性，例如将安全策略放入管道中。

一旦部署完成，就有两大挑战需要运营团队来应对。当一个应用程序关闭或服务不可用时，焦点就转向了问题的解决。然后，该平台集合在一起，集成开发、安全和运营。

## 开发体验

[Backstage](https://backstage.io/) 是 VMware 用来支持其开发者体验的开源项目。[由 Spotify](https://thenewstack.io/spotify-reboots-ospo-earmarks-109000-for-open-source-projects/) 开发，VMware 使用 Backstage 为其客户构建开发者门户。据 Backstage 网站称，Backstage 由一个中央软件目录、软件模板和技术文档提供支持，使用“像代码一样的文档”方法“使创建、维护、查找和使用技术文档变得容易”。后台是一个[云原生计算基金会](https://cncf.io/?utm_content=inline-mention)孵化项目。

“这可以追溯到我们谈到的所有不同的开发人员体验，”VMware 首席技术官 Kit Colbert 说。“所以这就像，你如何给他们(开发者)他们需要的那种原语？后台做了大量的编排自动化工作来设置云服务。”

Backstage 允许管理员为开发人员提供来自公共云或内部的选项目录。目标是让平台工程师能够轻松挑选他们需要的东西。

Patel 说，VMware 认为使用 Backstage 的平台团队非常注重开发人员。他们通常有一个正在进行的开发者体验计划。他们是应用架构师、云架构师——希望创建模式的人，加速器——他们可以交给开发人员的可重复的东西。他们正在管理服务目录，并寻找要使用的安全服务。

VMware 采取固执己见的方法，让人想起深深植根于 VMware 的 Pivotal 文化。Pivotal 是在从 EMC 和 VMware 分离出来后成立的，当时 EMC 拥有 VMware 的大部分股权。Pivotal 于 2018 年上市。2019 年，VMware 收购了 Pivotal。EMC 以前持有 VMware 的大部分股份。

Pivotal 支持最初由 VMware 项目发起的 Cloud Foundry。随着时间的推移，Cloud Foundry 成为 Pivotal 及其产品线的核心。VMware 随后收购了由 Kubernetes 创始人创办的公司 Heptio。Kubernetes 的遗产和 Cloud Foundry 的遗产已经成为 VMware 的云原生焦点的基础。根据[维基百科](https://en.wikipedia.org/wiki/Pivotal)的说法，“VMware 将 Pivotal 并入 Tanzu 应用程序套件，Pivotal Labs 咨询集团将于 2021 年 1 月更名为 VMware Tanzu Labs”。

Patel 说，VMware 的下一步是构建集成到 TAP 中的开箱即用产品。例如，VMware 可能会提供一个安全解决方案。

“我认为后台就是一个例子，”帕特尔说。“我想围绕后台门户创建一个成熟的开发者体验。我想使用 Tanzu Mission Control，一个运营门户，为审计平台运营提供经验，以提供高效的服务。我如何跨多个端点进行大规模管理？”

帕特尔说，VMware 增加了对亚马逊网络服务 EKS 的支持。接下来是 AKs (Azure Kubernetes 服务)，后续还会有更多的云服务。

VMware 关注开发人员是有原因的。

## 基础设施即代码

[RackN](https://rackn.com/) 的创始人兼首席执行官[罗布·希施菲尔德](https://www.linkedin.com/in/rhirschfeld/)说，在寻找开发人员的过程中，将需要可重复使用的代码，这是一个基础设施即代码软件(IaC)平台，其可重复使用的工作流可用于任何平台。

"那么在寻找难以捉摸的平台团队的过程中，团队在哪里呢？"希施菲尔德问道。“什么团队？”

希施菲尔德说，平台团队存在于整个组织中。团体已经在做平台决策了。团队已经有了他们的工具。他们需要的是一个决策结构。

“平台团队是要引入治理和过程，并帮助传播那些反对组织的东西，”希施菲尔德说。

基础架构即代码(IaC)功能非常适合 VMware 正在构建的管道。该公司在 IaC 有大量投资。VMware [在 2020 年收购了 SaltStack](https://blogs.vmware.com/management/2020/10/vmware-completes-saltstack-acquisition-to-bolster-software-configuration-management-and-infrastructure-automation.html) 。还有 [Concourse](https://concourse-ci.org/) ，是 [Chip Childers](https://www.linkedin.com/in/chipchilders/) 提到的开源项目，他是 VMware 的副总裁兼首席开源官。Childers 之前曾担任 Cloud Foundry Foundation 的执行董事。

VMware 有更多的支持者，主要是您在 VMware Explore 看到的那些人，例如运营经理和系统管理员。

“如果我退后一步，看看整个 VMware 产品组合，我们通过开源努力获得了不同的角色，”Childers 说。整个 Spring 产品组合中都有 Java 应用程序开发人员。有平台工程或平台操作人员。"

Childers 说，但也有通过收购 SaltStack 获得的更经典的系统管理员类型。因此，所有这些不同的角色都可以从各种形式的开源项目中获得一些价值。

“所以这是我关注的三个方面，”Childer 说。“是企业中的应用开发者。是平台工程师/操作员。然后是典型的系统管理员。”

VMware 开发人员关注的下一步将是未来一年感兴趣的话题。[博通计划收购 VMware](https://www.datacenterknowledge.com/business/vmware-ceo-says-broadcom-deal-track-touts-new-multi-cloud-products) 。我们知道博通希望专注于付费用户。这是否意味着对开发者和开源的持续关注？这将是有意义的，甚至可能是以解决方案为重点。这是否意味着开发者对开源的持续关注和承诺？有些人会说是的，但那是另一个故事。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>