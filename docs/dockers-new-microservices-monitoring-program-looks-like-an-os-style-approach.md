# Docker 的新微服务监控程序看起来像一种操作系统风格的方法

> 原文：<https://thenewstack.io/dockers-new-microservices-monitoring-program-looks-like-an-os-style-approach/>

大量的更正告诉我们，Docker 是一个容器主机，而不是一个操作系统。但“容器主机”朝着看起来像操作系统的方向又迈出了一大步，因为 Docker Inc .本周正式推出了似乎是几个生态系统技术合作伙伴计划中的第一个，这一计划旨在认证监控系统。

通过合作伙伴计划，第三方根据支持方发布的规范构建其支持产品。当这些产品达到或超过给定的标准时，主人同意帮助促销活动。这一切都让人想起那个时代，当时商业操作系统祝福支持厂商，给他们联合赞助标志，并认证他们进行产品推广。人们预见到供应商的未来会有一个“为码头工人制造”的鲸鱼徽章。

## 应该和不应该进行什么样的监控

监控是微服务管理的一项关键功能，也是 Docker Inc .希望市场自行解决的服务领域之一。尽管公司高管周二上午发表了正式声明，称合作伙伴关系的目的是确保监控产品与 Docker 正确集成，但显而易见的事实是，该合作伙伴关系的创始成员——[app dynamics](https://www.appdynamics.com/)、 [Datadog](https://www.datadoghq.com/) 、 [New Relic](http://newrelic.com/) 、 [Scout](https://scoutapp.com/) 、 [SignalFx](https://thenewstack.io/signalfx-a-saas-to-monitor-apps-at-any-scale/) 和[Sysdig](http://www.sysdig.org/)——都因已经与 Docker 进行了令人钦佩的集成而闻名。

这种伙伴关系所创造的，不仅仅是一种规范或一个目标，而是一种真正的经济。在一项技术的一个细分市场中出现六个坚实的品牌，所有这些品牌都在一个平等的竞争环境中呈现，这向潜在的采用者表明，健康和竞争的市场正在得到鼓励和培育，底层技术平台的未来道路永远不会如此之深，以至于这条道路上的乘客无法改变路线。

然而，六个宪章成员在多大程度上能够指导 Docker 中微服务监控的实际标准，还有待确定。

在上月的一篇博客文章中，AppDynamics 的市场开发副总裁 Jonah Kowall——新组织的创始成员之一——提出了任务监控绝对不应该被采用的问题。他列举了三个由社区中声誉良好的建筑师概述的例子，称它们是“破碎的”和“有缺陷的”，并引用了 Twitter 标签 **#monitoringsucks** 。

关于 Quicklizard Ltd .的首席技术专家提供的概念模型，Kowall 写道:“存在于筒仓中的视图不提供理解端到端事务路径所需的可见性。如果一个服务故障级联到其他服务故障，由于微服务的异步特性，确定根本原因实际上是不可能的。服务经常调用附加服务，这意味着服务之间存在 *n* 到- *n* 的关系。”

Kowall 提倡一种显示单个端到端可视化面板的模型，他说这种模型优化了服务之间所有交互的可追溯性。“拓扑和应用路径是管理复杂架构的关键，”他写道，“随着微服务和 Docker 的加入，每个人都将需要这些能力。”

值得注意的是，就在宣布 Docker 监控生态系统的几周前，Kowall 引用的三个模型都不是来自新伙伴关系生态系统的创始成员。

相比之下，SignalFx 强调其监控平台的分析能力，揭示服务交互背后的潜在趋势。

在上个月与新堆栈的 Alex Williams 进行的视频演示中，SignalFx 首席执行官 Karthik Rau 展示了深入了解有关性能和互连数据的实时启发式指标图的能力。SignalFx 并没有将服务显示为通过线条连接到其他节点的节点，而是倾向于通过算法组合的聚合视图。

你可能会认为 AppDynamics 的 Kowall 对这种可视化进行了长时间的抗议。同样，很难忽视 AppDynamics 和 SignalFx 现在共享一个公共主机的事实。

## 开放一个公平的竞争环境

Docker Inc .发誓不会在太大程度上推行首选解决方案，而是选择其首席执行官 Ben Golub 称之为“包含电池但可拆卸”的模式，让客户自由选择其支持的产品的替代品。

在去年 3 月接受 New Stack 采访时，Docker 产品副总裁 Scott Johnston 被问及他的公司是否计划采用任何类型的合作伙伴生态系统计划，类似于操作系统供应商过去交叉推广其支持者的方式。

“无论你的规模如何，Docker 的政策从一开始就是让它成为一个公平的竞争环境，”Johnston 告诉我们。“我们的治理模式是这样的，你不能花钱进去，也不能强行进去。它是开放的，各种想法在社区中进行公开的严格辩论，有 750 到 800 名不同的贡献者，大概有 10 倍于整个事情的旁观者。”

Johnston 试图在人们心目中描绘的不同画面将让整个社区来决定成员资格和认证的标准，而不是由主机供应商闭门造车来制定这些规范。

显然，公众正在讨论监测的真正性质。Docker Inc .未来面临的挑战将是缓和这种讨论。坏主意需要被排除在外，而不要让它们的创造者受到惩罚。好的想法需要得到鼓励和积极的讨论，而不是表现出与各种各样的参赛者一起扮演“山中之王”，并授予获胜者骑士头衔。

Datadog 和 SignalFx 是新堆栈的赞助商。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/mtaphotos/7704403154/in/photolist-5Sdnud-8r8yiH-73ugX8-75mrRg-bzRRqX-74nXyn-73aoqp-8rcSmN-8rdh6q-5J94NT-cJP7ib-j6NQxG-8ra5FP-6fJ5wA-oMkbn-5r39UM-78LZAy-6VbGSB-a1Qyt7-74sMDU-oEdggz-5CgsNA-oo2cea-cJP5Xy-eHzHt4-74nUiK-ASiEZ-neDxRD-73xW8m-8yG6yX-668H8K-oMk4y-cJP7GN-8yK6P3-cJP5D9-cJP5Qm-cJP653-dYmuNU-73Jh7E-73uE9Z-bubove-73fqp3-5mwjz9-a1xtoP-a1xtbX-a1AmKf-a1Amt7-a1AmDf-5y3msx-fmyV3j)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>