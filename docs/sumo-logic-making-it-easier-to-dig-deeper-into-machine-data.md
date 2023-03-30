# 相扑逻辑:更容易深入挖掘机器数据

> 原文：<https://thenewstack.io/sumo-logic-making-it-easier-to-dig-deeper-into-machine-data/>

日志管理和分析供应商 [Sumo Logic](http://www.sumologic.com/) 希望将更多数据——甚至是旧的日志数据——放到客户手中，添加新功能以实现这一点，并深入挖掘对 Docker 和 Kubernetes 的支持。

它上周在旧金山举行的 [DockerCon 2018](https://2018.dockercon.com/) 上宣布了这些增强，以及它委托 451 Research 进行的[调查](https://www.sumologic.com/resource/white-paper/machine-data-analytics-economy/)的结果，该调查概述了企业越来越多地使用机器数据，不仅用于 It 运营，还用于帮助推动其核心任务。

在接受调查的 250 家企业中，54%表示他们的公司已经使用机器数据工具进行业务洞察，50%专门使用这些工具来支持最终用户体验。

机器数据——产品营销总监 Ben Newton 称之为“数据排气”——来自 it 环境中的服务器、路由器、应用程序和传感器。

受访者表示，他们正在使用它来解决问题，以免影响客户体验，执行更有效的合规性审计，更好地了解用户行为，更明智地进行产品开发。

贷款生命周期软件供应商 [Simnang](https://www.simnang.com) 的软件开发总监 Cesar Olea 表示:“通过 Sumo Logic，我们可以利用机器数据洞察来了解我们的客户如何使用我们的不同服务以及贷款请求的其他趋势数据，从而更好地了解我们的业务，并确保每个客户的需求都得到充分满足。

增强功能包括对 Kubernetes(亚马逊 EKS) 的 [亚马逊弹性容器服务的本地支持，以及通过开源标准](https://www.sumologic.com/application/aws-eks/) [Prometheus](https://thenewstack.io/exploring-whats-new-prometheus-2-0/) 对性能指标和元数据的本地支持。

“我们还在与 Kubernetes 进行更深入的集成，以便能够获取更多关于如何设置 Kubernetes 的信息，并利用这些信息从您的 Kubernetes 部署中获得更多价值。他们使用信息来描述他们正在运行什么，以及它是如何根据元数据进行配置的，”牛顿说。

该公司还致力于帮助客户更有效地使用元数据。

“如果你要从机器数据中获得商业价值，日志和性能指标通常与你运行的平台密切相关，除非你描述它们与业务的关系，否则它们可能很难解释，”他说。

新功能使用户能够从非结构化日志中提取性能指标和关键性能指标，同时仍然保留这些日志用于根本原因分析。该公司表示，与 Sumo Logic 时间序列引擎配合使用，可以大幅提高非结构化日志数据搜索的分析性能，并支持指标的长期趋势。

从该公司长期的[日志和指标计划](https://www.sumologic.com/blog/it-operations/logs-to-metrics/)中，它使客户能够提取关键绩效指标，并将现有的【Graphite 格式的绩效指标实时转换为元数据丰富的 [Metrics 2.0](http://metrics20.org/) 格式。

“客户没有时间重组他们的应用程序来利用这些新的遥测方法，所以我们现在有一个实时流引擎，它将转换非结构化应用程序日志，允许他们从这些日志中提取这些性能指标，”他说。该公司几年前专门为这些时间序列性能指标构建了一个引擎，但用户必须重组应用程序才能利用性能提升。

“[现在]他们可以利用这些保存多年的日志，从中提取信息，并以这种新的高性能格式存储。对于客户来说，这种互动有多慢？这个交易花了多长时间？

“他们将能够使用这个工具说，‘这是我的 KPI，去提取它，这是我想要的粒度’——每分钟或每 30 秒，无论它是什么——然后它将被转储到我们的时间序列引擎中，他们将能够就此进行长达一年的培训，”牛顿说。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>