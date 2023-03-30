# 新遗迹 AI:警惕疲劳的解毒剂

> 原文：<https://thenewstack.io/new-relic-ai-an-antidote-to-alert-fatigue/>

[新遗迹](https://newrelic.com/)赞助本帖，由新栈独立创作。

在上个月的 FutureStack New York 会议上，New Relic 推出了 [New Relic AI](https://newrelic.com/products/applied-intelligence) ，这是今年早些时候[重大收购](/new-relic-signifai-and-the-shifting-view-of-monitoring-technologies/) New Relic 的部分成果。SignifAI 提供了一个技术超集——它运行在 Prometheus、OpenShift 和大约 60 个监控工具上。新遗迹服务包含了重要的技术。它现在处于测试阶段，将于 2020 年初正式上市。New Relic 目前正在将 UI 功能集成到 SignifAI 团队开发的现有后端中。

新遗迹人工智能服务是为网站可靠性工程师(SREs)、开发人员和待命团队提供的，SignifAI 首席技术官 Guy Fighel 说，他目前正在领导新遗迹人工智能工作。新遗迹人工智能定制了不同的重要技术。Fighel 说，该服务是一套解决方案，主要是为了在 New Relic 已经拥有的时间序列数据(如应用性能监控(APM)数据)的基础上提供更深入的异常检测和预测分析。

从一开始，Fighel 和他的团队就意识到了负责监控 IT 环境的人员所面临的一个尖锐问题:警惕疲劳。

到今年早些时候 [New Relic 收购重要的](https://thenewstack.io/new-relic-signifai-and-the-shifting-view-of-monitoring-technologies/)公司时，这项服务提供:

*   Chewie，一个管理监控平台的 API，其目的是减少团队事件管理报告中的噪音。
*   与云计算原生计算基金会的 Prometheus 和 Red Hat 的 OpenShift 集成，用于监控警报和指标与相关日志和事件的可见性和相关性。
*   重大决策——SRE 和 DevOps 团队的关联引擎，使用关联来提供对生产系统的洞察。

Fighel 说，使用 SignifAI，New Relic AI 服务可以插入事件管理平台。这些信息由 New Relic One 和其他第三方服务整合而成，这些服务使用了之前开发的技术。使用 New Relic AI，用户可以使用现有管理平台和 New Relic One 中的信息。

值得注意的是，New Relic One 代表了该公司如何将其未来视为其所谓的可观测性平台。愿景是通过其用户界面和在一个地方管理日志的能力来交付上下文，并在其平台上提供可编程能力。在 [FutureStack](https://newrelic.com/futurestack) 上，New Relic 公布了其对可观测性的整体看法，将其视为加深其在企业中影响力的一种方式，并提供了 New Relic AI 等先进工具。

例如，SRE 告诉人工智能服务开始分析哪些来源。如果是新遗迹警报，就要检查政策了。可以集成来自事件管理平台的 API 或来自其他服务的预认证 API，以自动与服务同步，并开始发送到新的 Relic API。为用户提供了更多的上下文，他们收到的页面得到了丰富和简化。

就信号而言，收集的每一种类型的数据都会在 New Relic AI 中进行分类。该平台着眼于历史上的 SRE 黄金信号，如延迟、饱和度、错误率和可用性。还对子组件进行分类，以帮助确定可能导致事件风暴的原因。

然后，将所有这些数据关联起来，以减少噪声量，然后用可能的根本原因丰富噪声。例如，它查看哪些组件受到了影响。然后添加其他信息，显示异常情况，如特定指标中的峰值。向用户发送一个带有所有信息或洞察的特定事件，以提供上下文。

![](img/74fc9fb1ea61f8e965bbb058b018ebd2.png)

通用电气的鲍里斯·格林伯格。

[GE Digital](https://www.ge.com/digital/) 正在使用 New Relic AI 寻找减少过多警报噪音的方法， [Boris Grinberg](https://www.linkedin.com/in/boris-grinberg-a872975/) 在 FutureStack 的一次采访中说，他是 GE Digital 的监控产品负责人和全球监控开发经理。格林伯格对 New Relic AI 迄今为止的结果感到满意。他希望看到新遗迹系统做出推荐的能力，特别是对那些经验较少的新遗迹用户。衡量技术比衡量人更有效。这将特别有助于继续减少人们现在收到的可能需要很长时间才能解决的警报。经过更有资格的工程师分析后，它们甚至可能根本不是问题。

“噪音污染是生产力的杀手，”格林伯格说。“这是企业面临的头号挑战。”

### 机器学习意味着语境

New Relic AI 中的上下文是基于机器学习的，例如通过动态标题。历史上，事件的标题是静态的。每个事件都有不同的名称。CPU 使用率可能超过 80 %,或者连接服务器或容器时可能出现故障，每个事件都有不同的标题。既然问题已经汇总，系统就会动态地创建标题。

在 New Relic AI 中，事件被动态分类以包括上下文。分类是系统元能力的一部分。新遗迹人工智能使用专家系统来决定标题和评估不同的信号。在标题中，他们将自动填充特定事件中涉及的最相关的实体。

“你们是怎么关联的？”菲格尔问道。“你是基于时间进行关联的吗？你是基于相似性来关联的吗？你是基于不同的分类器吗？所以我们应用了多种不同的技术。我们有一个算法来选择自动关联的最佳技术。稍后，在正式发布之前，我们将向用户公开所有这些功能。所以作为用户，你实际上可以打造自己的逻辑。”

工艺逻辑将意味着用户实际上可以添加到新的遗迹人工智能关联引擎。它将根据用户的输入进行调整。通过其下拉用户界面，用户可以定义标准，如 CPU，网络连接和频率或时间段。然后，引擎将获取结果，并根据输入更新模型。

New Relic 正在开放其人工智能平台，允许用户添加他们的输入。在 FutureStack，该公司列举了客户如何看到警报噪音下降了 80%。

新的遗迹人工智能故事涉及人工智能的趋势，如对自然语言处理(NLP)的研究。AIOps 是关于数据以及如何使用数据来更好地优化运营，这需要 NLP。

New Relic 在市场上的同行包括大熊猫、Splunk 和 Sumo Logic 等公司。该领域还有其他几个公司，每个公司都遵循核心原则，即要求以更少噪音、更高效的方式分析大量数据。New Relic 通过用户的视角来看待 AIOps，特别是 SREs 扮演的角色和涌入的机器数据。

云计算原生计算基金会和 Red Hat 是新堆栈的赞助商。

特征图像:盖伊·菲格尔。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>