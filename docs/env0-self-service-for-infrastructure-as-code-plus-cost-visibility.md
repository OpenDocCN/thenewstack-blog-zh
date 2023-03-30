# Env0:基础架构即代码的自助服务，以及成本可见性

> 原文：<https://thenewstack.io/env0-self-service-for-infrastructure-as-code-plus-cost-visibility/>

去年在旧金山举行的 [DevOps World|Jenkins World](https://www.cloudbees.com/devops-world/san-francisco) 大会上，[毕马威](https://home.kpmg/xx/en/home.html)咨询公司的软件工程总监[杰夫·阿迪利奥](https://www.linkedin.com/in/jeff-ardilio-b36b5217/)谈到了基础设施即代码 (IaC)的[优势，以及它为不同环境所做的准备。](https://thenewstack.io/what-kpmg-learned-about-infrastructure-as-code-tools-people-and-process/)

以色列初创公司 [env0](https://www.env0.com/) (发音为“env zero”)通过帮助组织自动化部分工作来应对这一挑战。它在 IaC 框架之上提供了一个层，为开发人员提供自助服务，同时企业保持对成本的控制和可见性。

在公测中，env0 旨在帮助开发者组织实现自由和治理之间的平衡。

它允许开发人员在为每个项目、团队甚至个人用户定义策略和成本控制的模板范围内提供他们自己的云环境。每个环境的模板——主要是亚马逊 Web 服务、Azure 和谷歌云平台(GCP)——使管理员能够管理变量和云凭证；为用户定义策略，如访问控制、环境生存时间和预算限制。

它还能让组织深入了解云资源的使用方式和使用者。

## 在公开测试中

几年前，在经营一家 DevOps 服务公司时， [Ohad Maislish](https://www.linkedin.com/in/ohadmaislish/?originalSubdomain=il) ，env0 首席执行官发现他的一位客户在管理多区域环境时遇到了困难，其中一个是美国客户，另一个是欧盟客户。

“尽管他们在技术上实施了 IaC，但他们仍然缺少一个支持多环境的解决方案。这一具体问题促使我对转向 IaC 的差距和机遇进行了更多的市场研究，”他说。

该公司在 4 月份宣布了一项公开测试和 330 万美元的种子投资，由纽约市的 Boldstart Ventures 和特拉维夫的 Grove Ventures 牵头，天使投资人包括[Snyk](https://twitter.com/guypod?lang=en)的联合创始人[Guy Podjarny](https://snyk.io/)。

Boldstart Ventures 的创始人兼管理合伙人 Ed Sim T1 谈到这笔投资时说:“从我们第一次见面开始，我们就被他们的愿景所吸引，即把 IaC 的力量带给每个人，并自动、主动地将基础设施的使用与业务和应用联系起来。”。

预计 env0 将于 2020 年秋季正式上市。

## 模板提供控件

默认情况下，env0 与开源 IaC 供应工具 [Terraform](https://www.terraform.io/) 一起工作。您还可以使用[定制流](https://docs.env0.com/docs/templates#section-custom-flows)来插入任何部署工具，例如 AWS CloudFormation 或 Ansible *、*甚至普通的 bash 脚本。

模板在组织级别进行管理，需要特定权限才能进行更改。如果未在模板中定义，则不会提供它。

最长生存时间和默认生存时间等可定制策略可确保开发和其他非生产环境不会超出需求。它还增加了时间安排，因此非生产环境可以在晚上和周末无人使用时自动关闭，然后在需要时自动重新配置并准备就绪。

除了定义策略之外，env0 还允许管理员根据使用情况、用途和成本来跟踪环境，不仅提供了资源消耗方面的信息，还提供了谁在使用什么以及为什么使用的信息。

它的控制面板提供了查看活动内容并根据需要自动关闭、暂停、恢复或销毁环境的能力。预算限制可以应用于项目、用户或用户组的给定时间段。

## 成本可见性

该公司旨在提供云使用和成本的可见性和可预测性。

在 Flexera 和 RightScale 的 2019 年[云报告](https://www.flexera.com/about-us/press-center/rightscale-2019-state-of-the-cloud-report-from-flexera-identifies-cloud-adoption-trends.html#:~:text=A%20few%20key%20highlights%20from,from%2058%20percent%20in%202018)中，云治理和管理预算是巨大的挑战，该报告估计 35%的云支出被浪费了。云“宿醉”已经成为一个如此令人担忧的问题，以至于一个名为 FinOps Foundation 的非营利贸易协会被创建来帮助组织控制他们的云成本。

[451 Research](https://get.cloudability.com/ebook-cost-management-in-the-cloud-age.html) 发现，超过一半的大型企业每天都在担心云成本，80%的企业表示糟糕的云财务管理对其业务有负面影响。

Maislish 坚持认为，行业对不断增长的云成本的反应一直是创建基础设施与其业务用途脱节的工具。将两者结合在一起通常需要大量的手动标记来适当地报告每个资源的使用情况。

env0 自助服务引擎平台会自动标记每个资源及其部署环境。这消除了人为错误，测试和维护的需要，并提供了使用任何模块或扩展(甚至是开源的)的灵活性，而不管其本机标记支持。

它了解每个环境的设置、谁部署了它、来自哪个团队、用于哪个项目、使用哪个代码、哪个模板、部署时间等等。

然后，它使用云提供商的 cost API 将支出数据拉入 env0，并将其关联回 env0 已经拥有的关于特定环境的数据(基于您的编排平台)。

该公司最近首次推出了[随时间推移的成本](https://www.env0.com/blog/introducing-cost-over-time)，这是一个跟踪随时间推移的成本的功能，但会在基础设施发生变化时添加进来，因此您可以看到这些变化如何影响预算。对于多云用户，新的成本图表将显示每个云提供商的成本。

据该公司称，提供自助供应和预算可见性可以帮助团队更好地掌控他们的项目。

基于云的钱包解决方案 [Curv](https://www.curv.co/) 在使用 Terraform 和 CloudFormation 配置 GCP 和 AWS 后采用了 env0。像许多快速发展的公司一样，当它的工程团队试图提供基础设施时，它不断遇到瓶颈。

Curv 遵循 Gitflow 分支模型，分支开发、发布和补丁。它雇用 Jenkins 来编排测试，以及跨开发、试运行和生产进行监控和发布。它依靠 Datadog 和 GCP 账单来控制成本。

为了提高透明度、审计能力以及开发人员和 DevOps 之间更好的沟通，It 部门转向了基础设施即代码模型，但发现还需要更多。

它发现了 env0 在管理不需要的环境方面的更多优势，了解了在任何给定时间有多少设置正在运行，哪些模板正在使用，以及每个模板的相关成本。车队还发现 env0 比 Jenkins 更直观，根据 [Shaked Shauli](https://www.linkedin.com/in/shaked-shauli-996619ab/?originalSubdomain=il) ，DevOps 在[弯道](https://www.curv.co/)领先。

“当我们转向基础设施即代码时，很明显，拥有一种灵活的方式来协调我们的环境是必不可少的，使用 Jenkins 是不够的，”Shauli 说。“env0 解决了我们的一些问题，但它最大的优势是其自动化 TTL(生存时间)环境策略。它让我们的团队能够控制和管理环境，同时降低成本。”

亚马逊网络服务和 Snyk 是新堆栈的赞助商。

*目前，新堆栈不允许在该网站上直接发表评论。我们邀请所有希望讨论某个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>