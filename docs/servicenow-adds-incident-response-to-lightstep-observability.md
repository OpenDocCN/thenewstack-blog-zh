# ServiceNow 将事件响应添加到 Lightstep 可观察性中

> 原文：<https://thenewstack.io/servicenow-adds-incident-response-to-lightstep-observability/>

本周，ServiceNow 向该公司去年收购的 [Lightstep](https://lightstep.com/) observability 平台引入了一项新的事件解决功能。

随着 [Lightstep 事件响应](https://lightstep.com/incident-response/)的发布，ServiceNow 在单一平台上将可观察性与事件解决结合起来，帮助开发人员和[现场可靠性工程师(SREs)](https://thenewstack.io/building-sre-teams-with-specialization/) 监控、警报、协作和响应事件，以实现快速恢复。

ServiceNow 的副总裁兼新兴业务总经理 Rohit Jainendra 说:[我们的目标是通过向这些人提供他们有效应对软件错误、停电或网络中断等事件所需的服务环境和自动化来减少停机时间。](https://www.linkedin.com/in/rohitjainendra/)

## 消除上下文切换

Jainendra 说，开发人员和 sre 不得不在各种工具之间进行大量的手动上下文切换，以跟上他们所有的系统。

“我们从开发人员和 sre 那里听到的是，消除‘上下文切换’——在可观察性、随叫随到、协作和事件管理工具之间切换——将减少人为错误，加快响应时间，”他在一份声明中说。“借助 Lightstep 事件响应，我们为团队提供了一个单一平台，可协调电话呼叫上报、警报分组、事件分析和补救，同时与协作和事件管理工具无缝集成，以消除‘上下文切换’并快速解决事件。”

## 收购后的主要新功能

[ServiceNow 于 2021 年收购了 Lightstep](https://thenewstack.io/servicenows-lightstep-buy-moves-observability-up-the-stack/) ，以扩展跨业务功能的可观察性优势，并使企业能够增加其云原生能力。该公司计划将 Lightstep 的功能扩展到可观测性之外，其使命是成为应用开发组织的端到端平台。Lightstep 事件响应的全面上市标志着这一使命迈出了重要的第一步。

Lightstep 总经理、CNCF [OpenTelemetry](https://thenewstack.io/why-opentelemetry-is-the-future-of-instrumentation/) 项目的联合创始人 Ben Sigelman 表示，Lightstep 如果单独作为一家初创公司提供这一功能，将会受到很大压力，但它在 ServiceNow 的支持下加快了开发速度。

## 它是如何工作的

Lightstep Incident Response 通过将随叫随到员工的时间表同步到共享日历上来工作，并根据事件的性质和受影响的服务，使用特定的标签来指示谁需要参与。从那里，合作者被邀请到基于预构建的合作集成的专用通道，以进行快速补救。Jainendra 说，此外，如果问题再次出现，他们可以创建自动分类和自我修复的功能。

新工具集成了领先的监控、可观察性和协作工具，包括 LogicMonitor、Postman、Slack、Sumo Logic、Zoom 和 [more](https://lightstep.com/integrations) 。

对于 ServiceNow 客户，Lightstep 事件响应与 Now 平台进行了本机集成，允许用户在一个平台上快速响应事件或将事件上报给适当的团队，并将事件响应与核心运营联系起来。

“ServiceNow 已经意识到 IT 运营模式现在已经发生了变化。现代敏捷和 DevOps 团队不能等待多层次的支持，如 L1、L2 和 L3，或者等待通过一个基于票的系统来工作，”星座研究副总裁兼首席分析师[安迪·图雷](https://www.linkedin.com/in/andythurai/)说。“CloudOps 正在转向基于事件/事故的工作流，并由服务所有者而不是随叫随到的支持工程师立即上报/解决问题，这是一种较新的模式。ServiceNow 的这一举措旨在创建工具集来迎合这一模式。”

然而，ServiceNow 的第一版功能有限，但他们有一个很好的路线图和方向，他指出。

“事件响应的心态过去是唤醒某人，这是下一个升级链，在半夜是升级问题的唯一方式，”Thurai 说。“新模型是基于事件/事件的。您可以并且应该直接将事件上报给服务所有者，他们将掌握解决此问题的第一手知识。DevOps 模型是关于您的变更的所有权和责任的。”

快速反应的能力使新的 ServiceNow 工具与众不同。

## 速度和效率

Sigelman 在一份声明中说:“随着 Lightstep 事件响应的推出，我们正在为开发人员和 SREs 提供一体化解决方案，以必要的速度和效率采取行动，为使用他们的应用程序和服务的客户提供卓越的体验。”“结合 OpenTelemetry，一个由 Lightstep 部分创建的[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)沙盒项目，组织现在将拥有成功运营高度分布式云本地服务所需的数据平台、工作流和开放标准方法。”

像[装配](https://www.joinassembly.com/)、[精益](https://www.withlean.com/)和 [Roambee](https://www.roambee.com/) 这样的早期使用(测试版)客户已经看到了 Lightstep 事件响应的好处。

当谈到监控 DevOps 基础设施和服务时，有许多开源工具可以提供良好的覆盖，并且可以在典型的团队中找到，例如 [Grafana](https://thenewstack.io/will-grafana-become-easier-to-use-in-2022/) 、Prometheus、[influence](https://www.influxdata.com/?utm_content=inline-mention)等。Roambee 的工程副总裁 Shailesh Mangal 说。

“Lightstep 帮助我们解决了两个问题:处理基础设施和服务警报，”他告诉新堆栈。"他们本质上帮助(迫使)我们通过添加额外的元数据来区分警报类型的优先级."

他说，Roambee 面临的另一个问题是需要建立一个升级路径并自动跟进。

“鉴于团队规模较小，我们不可能 24 小时都有人值班。我们通过与常规(非 DevOps)团队成员兼职和依靠警报来分担责任来实现这一点。如果这些警报由于任何原因被遗漏，我们就没有办法检测到它们，直到为时已晚。有了 Lightstep，我们建立了适当的升级路径，如果警报没有得到确认，就会升级到食物链上。”

在一份关于 Lightstep 事件响应功能的声明中， [Assembly](https://www.joinassembly.com/) 的首席技术官和联合创始人 Muthu Gurumoorthy 表示，“它已经改变了我们随叫随到的工程师和开发人员的游戏规则。有了 Lightstep 事件响应，我们的团队获得了授权并积极参与，因为他们知道自己拥有快速解决事件所需的关键环境……”

## 新定价模式

Jainendra 说，Lightstep 事件响应有免费和付费两种版本，并引入了基于使用量的定价模式，该模式基于被管理的活动服务的数量。顾客不按座位付费，只为他们使用的东西付费。这允许整个团队参与事件响应流程，并推动服务所有权文化。顾客可以立即开始 30 天的免费试用。

“ServiceNow 有优势，因为他们是许多大型企业的 SOR(记录系统)，拥有他们的 ITSM 解决方案，”Thurai 说。“如果可观察性和事件管理的结合起作用，追加销售会更容易，但还有很长的路要走。这是一个好的开始，但我们必须等待，看看他们是否能正确执行。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>