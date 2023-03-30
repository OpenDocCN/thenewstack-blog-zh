# 背景:12 因素无服务器应用，费城云计算峰会

> 原文：<https://thenewstack.io/context-12-factor-serverless-apps-cloud-foundry-summit-philly/>

KubeCon + CloudNativeCon 和 [InfluxData](https://www.influxdata.com/) 赞助了这个播客。

[12 因素无服务器应用，费城云铸造峰会](https://thenewstack.simplecast.com/episodes/12-factor-serverless-apps-cloud-foundry-summit-philly)

欢迎来到[新的堆栈环境](https://thenewstack.io/podcasts/context)，这是一个总结本周新闻的每周播客。本周，我们将与无服务器软件提供商 [Stackery](https://www.stackery.io/) 的社区开发者 [Toby Fee](https://twitter.com/TobyFee) 讨论如何将 [12 因素应用模型](https://12factor.net/)的原则应用于无服务器应用。在节目的后半部分，我们与 [Grape Up](https://grapeup.com/) 的云研发副总裁 [Roman Swoszowski](https://twitter.com/romswo?lang=en) 就本周在费城举行的[云铸造峰会](https://www.cloudfoundry.org/event/nasummit2019/)进行了交谈。

在过去的几周里，费已经为我们写了一系列的文章，通过一个无服务器的镜头探索了 12 因素应用中的每一个原则。她写道:

没有两个无服务器应用是完全相同的，你做出的设计决定会极大地影响你让开发者的生活变得容易或困难。无服务器应该是一个使开发体验更容易而不是更困难的选择，遵循这些指南会有所帮助。

在播客的后半部分，我们将讨论云铸造峰会。今年的活动值得注意的是开源平台即服务已经接受了多少外部合作者。

本周最大的新闻是一个新的 Cloud Foundry 沙盒项目的消息，[称为 Project Eirini](https://thenewstack.io/with-project-eirini-cloud-foundry-adapts-to-a-new-open-source-ecosystem/) ，它可以用于管理和扩展 Kubernetes 环境中的 Cloud Foundry 服务。IBM 和 SUSE 的企业发行版都已经包含了 Eirini。

Cloud Foundry 也开始与 Heroku 合作扩展构建包。基于开放容器接口(OCI)，新的构建包将允许更大的模块化，允许开发人员将额外的构建包添加到一个链中以捕获依赖关系。“我真的很兴奋这对未来意味着什么，”Cloud Foundry 首席执行官艾比·科恩斯[本周在推特上写道。](https://twitter.com/ab415/status/1113433857796268032)

该组织还与开源 Istio 和 Envoy service mesh 合作。该组织已经表明，这些服务网格技术可以支持多达 20，000 个应用程序相互通信，Cloud Foundry 首席技术官 Chip Childers [在其主题演讲](https://twitter.com/thenewstack/status/1113448530650259456)中指出。由于这项工作，该平台现在可以提供加权路由，开发者可以指定每个版本的服务可以获得的流量百分比——这对 A/B 测试非常有用。

其他组织也伸出了援手。移动电话运营商 T-Mobile 发布了一款面向 Cloud Foundry 的开源应用级混沌工程工具，这款名为 Monarch 的工具[引入了延迟，甚至完全终止了一项服务，以检查弹性。](https://github.com/TMobile/monarch)

本周的节目由《新书库》编辑部主任利比·克拉克主持，TNS 出版商亚历克斯·威廉姆斯和 TNS 执行主编约阿布·杰克逊提供帮助。

## 讨论的帖子:

[借助 Project Eirini，Cloud Foundry 适应了一个新的开源生态系统](https://thenewstack.io/with-project-eirini-cloud-foundry-adapts-to-a-new-open-source-ecosystem/):Cloud Foundry 的年轻时代已经过去。这一点在本周费城举行的云铸造峰会上显而易见。现在，从用于启动 12 因素应用程序的开源平台到尊重其根源但继续通过 Project Eirini 扩展的平台的持续过渡正在进行，这是一个用于 Cloud Foundry 的 Kubernetes 后端，它使用 OCI 映像和 Kubernetes 部署将 Cloud Foundry 应用程序部署到 Kubernetes 后端。

[12 因素应用#1:为什么无服务器版本控制至关重要](https://thenewstack.io/12-factor-app-1-why-serverless-version-control-is-critical/):12 因素应用中描述的原则已经开始指导大多数现代开发和运营，无论它们是否受到 it 的直接影响。符合 12 因素原则的应用程序应该更可靠，更易于维护，并为新开发人员和团队过渡提供更清晰的路径。

[12 因素应用程序#2/#3:无服务器依赖和配置](https://thenewstack.io/12-factor-app-2-3-serverless-dependencies-and-configuration/):没有两个无服务器应用程序是完全相同的，您做出的设计决策会极大地影响您让开发人员的生活变得简单还是困难。无服务器应该是一个使开发体验更容易而不是更困难的选择，遵循这些指南会有所帮助。

Cloud Foundry Foundation 和 Stackery 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>