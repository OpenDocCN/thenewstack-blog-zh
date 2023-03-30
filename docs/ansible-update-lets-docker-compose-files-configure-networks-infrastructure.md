# 使用 Ansible Update，Docker 编写文件可以配置网络

> 原文：<https://thenewstack.io/ansible-update-lets-docker-compose-files-configure-networks-infrastructure/>

如果您正在非常大规模地部署容器，那么您很有可能同时使用各种自动化工具。自然，Docker 有它自己的，它的脚本简单易懂，易于理解。但是构图可能有多简单并不重要；如果您使用两个或更多的导体，您可能会在协调导体方面遇到比工作负载更多的麻烦。

去年三月，我们向开发人员询问了关于在他们的组织中管理和编排容器的方式的信息。我们给了他们五种编排方法的列表，并要求他们选择所有适用的方法。大约 21%在开发阶段而不是在生产中使用容器化的受访者表示，他们使用 shell 脚本和定制来集成多种工具。也许是巧合，但也许不是，另外 21%的受访者说他们使用配置管理(CM)工具，如 Chef、Ansible 和 Puppet。

[![Note drop when going from non-production use to production use](img/9978450d48991a9952f4327128439378.png)](https://thenewstack.io/wp-content/uploads/2016/05/chart_primary_method_of_managing_orchestrating_containers_-_differences_by_implementation_status_1024.png)

然而，当容器进入生产阶段时，CM 的数量减少得更快。在生产中使用容器的组织中，只有 10%的受访者使用 CM 工具，相比之下，16%的受访者乐于使用自己的脚本。

这是红帽公司希望填补的一个空白。

周三，就在[收购 Ansible](https://thenewstack.io/red-hat-ansible-staying-better-together/) 七个月后，红帽正式宣布对 Ansible 自动化平台进行重大变革。对于 2.1 版本，该公司正在添加一个模块，使 Ansible 的 YAML 自动化脚本(“剧本”)包括 Docker Compose 风格的语法。通过这种方式，DevOps 专家一直致力于手动编排容器的大部分工作 Reddit 上的一位科学工作流开发人员[将其描述为“欺骗”](https://www.reddit.com/user/omgbioinfo)——可以重新用于整个 it 基础设施的自动化。

从 Ansible 2.1 开始，这个级别的自动化还将包括网络基础设施。

## 新任务，同样的剧本

“docker-compose 文件和 Ansible playbook 都是 YAML 文件，语法几乎相同，”Ansible 社区副总裁 Greg DeKoenigsberg 在周三的一篇博客文章中写道，并指出这两个脚本解释器都是用 Python 编写的。“关键的区别在于， **docker-compose** 只能做一件事:管理 docker 容器。Ansible 也可以做到这一点，它还可以做 Ansible 做的所有其他事情，所有这些都在同一个剧本中。”

红帽周三表示，对 Ansible 现有的 Docker 支持模块进行彻底检查，将让 Ansible 使用 Docker 编写脚本，本质上就像它们是 Ansible 剧本一样。同时，Ansible 将保持对同时使用多个容器的应用程序的支持。

“只需从任何可翻译剧本中调用 **docker_service** 模块，”DeKoenigsberg 写道，“并指定一个外部 **docker-compose** 文件，或者将 **docker-compose** 语法直接放入可翻译剧本本身。”

这就是网络自动化功能可以为 Docker 用户改变的地方。早在二月份， [Red Hat 宣布](https://thenewstack.io/red-hat-ansible-will-handle-networking/)它打算不仅将网络配置而且将自动化集成到 Ansible 中，并在 2.0 版本中推出了该功能的预览版。

虽然 Ansible 中已经存在某种形式的网络自动化(网络顾问 [Jason Edelman 至少从 2014 年](http://jedelman.com/)就已经展示了这一点，并在去年 3 月为 O'Reilly 撰写了[关于该主题的广泛报告](https://www.oreilly.com/learning/network-automation-with-ansible)，但 2.1 版本现在正式添加了网络模块，使剧本更容易直接联系网络设备。

具体来说，Ansible 2.1 支持的设备属于这些平台:Arista EOS 思科 IOS、IOS-XR 和 NXOS 积云网络；HPE OpenSwitch 和 Juniper Junos。

Ansible 高级首席工程师 Peter Sprygada 在最近的公司网络研讨会上演示了新方法。该演示展示了 DevOps 专业人员如何使用数据中心实际拥有的实际物理基础架构，而不是该基础架构之上的虚拟化或分离的覆盖层，来有效地编排工作负载。

该演示为许多 DevOps 专业人员和开发人员带来了一线希望，即不需要仅仅为了应用而改造网络，大规模容器化在数据中心已经运行的网络中是可行的。

## 必要条件与理想状态

然而，反对这种方法的论点已经写好了。首先，显而易见的一点是，任何为公司自己的网络设备编写的自动化脚本都变得与这些设备有效地“结合”，不再是可移植的。

软件定义网络(SDN)的支持者，特别是网络功能虚拟化(NFV)的支持者，已经声明[这种类型的分离对于使工作负载可扩展是至关重要的](https://thenewstack.io/de-ossify-the-network-with-function-virtualization/)，并且一些人提出了有效的论点，即明确的自动化将使微服务不可能大规模实现。

基于云的 CI/CD 平台提供商[shipbable 认为](https://thenewstack.io/shippable-formations-is-a-container-cicd-without-devops-style-scripts/)配置应该像网络本身一样灵活；由于根据定义，SDN 通过设计使网络更加灵活，因此一个更适合容器化时代的配置系统将使 DevOps 能够指定*所需的状态*。

Ansible 会反驳这些观点，指出它也是一个理想的国家体系。正如它的文档所写的，“应该没有必要测试服务是否已经启动，软件包是否已经安装，或者其他类似的事情。Ansible 是一个系统，它将确保这些事情声明是真实的。相反，你应该在行动手册中强调这些东西。”

这实际上是一个相当有争议的问题，Ansible 断言的反对者认为 [Ansible 实际上是一个命令式系统](https://ifireball.wordpress.com/2015/01/03/comparison-of-puppet-and-ansible/)，因为它实现了指令序列，尽管首先有条件测试的空间；还有人说 [Ansible 有点像](https://www.upguard.com/blog/articles/declarative-vs.-imperative-models-for-configuration-management)，或者说是一个“混合体”，因为它不是完全抽象的。

直到今天，这场争论除了在开源会议上叫嚣比赛之外，并没有太大的意义。如果 Ansible 真正打算自动化真实的物理网络基础设施，使其适用于大规模的多容器工作负载，而不使用像 Weave 或法兰绒这样的网络覆盖层，那么它最好像其新母公司所说的那样是一个声明性系统。一个命令式的自动化模型在编排网络层的工作负载时是完全无效的，网络层就像某个候选人在解决国家债务问题上的立场一样坚定不移。

Ansible 的 DeKoenigsberg 写道，Docker Compose 是“一个很好的工具，可以让用户安全地依赖一个完全以 Docker 为中心的世界观。但是大多数用户并不生活在那个世界里——而且 **docker-compose** 并不是为解决非 docker 编排问题而设计的。这就是 Ansible 的用武之地。”

Docker 是新堆栈的赞助商。

特征图片:[电话总机接线员，大约 1975 年](https://commons.wikimedia.org/wiki/File:JT_Switchboard_770x540.jpg)，作者 Joseph A. Carr，通过知识共享获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>