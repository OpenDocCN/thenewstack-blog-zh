# Lightning 演示:开放服务网格、交叉平面、云状态、开放策略代理和 Grafana

> 原文：<https://thenewstack.io/lightning-demos-open-service-mesh-crossplane-cloudstate-open-policy-agent-and-grafana/>

[KubeCon+CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/) 赞助了这个播客。

在这一集的 [The New Stack Makers](/podcasts/makers) 播客中，五位嘉宾分别提供了他们各自开源云原生项目的实践“闪电演示”，作为下周云原生计算基金会 [KubeCon + CloudNativeCon 北美](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/?utm_source=thenewstack&utm_medium=website&utm_campaign=KCCNC-NA-2020-Registration)的预告片。

闪电演示嘉宾在[开放服务网格](https://openservicemesh.io/) (OSM)服务网格上展示[微软](https://www.linkedin.com/in/michelle-noorali/)[高级软件工程师 Michelle Noorali](https://www.microsoft.com/en-us/)； [Phil Prasek](https://www.linkedin.com/in/philprasek2/) ，在[交叉平面](https://crossplane.io/)控制平面上[向上](https://upbound.io/)的主要产品经理； [James Roper](https://www.linkedin.com/in/jamesproper) ，云架构师 [Lightbend](https://www.lightbend.com/) ，关于 [Cloudstate](https://cloudstate.io/) 分布式状态管理框架； [Torin Sandall](https://www.linkedin.com/in/torin-sandall-1967387/) ， [Styra](https://www.styra.com/) 开源副总裁、[开放策略代理](https://www.openpolicyagent.org/) (OPA)策略引擎的共同创建者；以及[Grafana Labs 的应用副总裁 Ryan McKinley](https://www.linkedin.com/in/ryan-mckinley/) 对 [Grafana](https://grafana.com/) 监控软件。

[https://www.youtube.com/embed/twPnWY3tWwE?feature=oembed](https://www.youtube.com/embed/twPnWY3tWwE?feature=oembed)

视频

## 开放式服务网格

“服务网格帮助你从你的核心业务逻辑或核心应用中提取所有与应用网络相关的逻辑，”Noorali 说，展示了总部位于 OSM 的控制平面如何与 Kubernetes 一起工作。“这个控制平面读取您想要应用的、与您的应用程序的网络相关的任何配置。”

Noorali 描述了 OSM 是如何针对服务网格接口(SMI)构建的。集成多个服务网格的规范。"它定义了大多数人希望从服务网格中得到的服务网格基本特性."

OSM 的设计非常简单，易于理解，易于安装，“但却是一个强大的服务网格工具，”她说。

“我们试图尽可能坚持己见，给那些想要服务网格功能的人提供不需要太多旋钮和新调谐旋钮的服务，”Noorali 说。

## 交叉平面

加速开发的竞赛取决于许多因素，其中之一是基础设施的复杂性。在他的演示交叉平面控制平面中，Prasek 展示了如何为开发人员创建云 API 来轻松部署云服务。他在亚马逊网络服务(AWS)的[上行](https://upbound.io/)云环境中使用 Crossplane 来提供一个[PostgreSQL](https://www.postgresql.org/)实例。

Prasek 说:“我们发现，人们想要一种更加集成的云原生声明式管理方法，但适用于所有基础设施和所有云服务。

## 云状态

Cloudstate 是一个开源的无服务器框架，用于将状态附加到无服务器工作负载，以支持需要在内存中为扩展会话保存数据的应用程序。“我们所做的是彻底改变了国家管理模式，”罗珀说。

在他的演示中，Roper 展示了 Cloudstate 如何通过框架为应用程序提供状态，“而不是应用程序必须从其他地方获取自己的状态。”

“你所做的是部署这些实体，它们保存状态，因为框架了解它们是什么类型的实体，你的一致性问题是什么，你的可扩展性问题是什么。它可以为您管理这些状态，部署和扩展它们，并确保它们在必要时具有弹性，”Roper 说。

## 打开策略代理。

OPA 是一个开放源代码的通用策略引擎，可在各种软件中实施策略。OPA 提供了一个可重用的构建模块来编写和执行重要的规则，这些规则决定了谁可以在系统中做什么。

“我们喜欢说，你可以在任何系统、任何服务、堆栈的任何层使用它，无论你是在谈论 CI/CD 期间执行规则，还是在 Kubernetes 集群上的护栏中[放置]安全措施，或者[保护]对敏感微服务 API 的访问，”Sandall 说。

在他的演示中，Sandall 展示了 OPA 如何为微服务 API 授权工作。这个演示应用程序由一个为一家公司提供员工档案的服务组成。

通过演示设置，他展示了如何设置不同的服务图策略来控制哪些服务可以相互通信。他展示了如何设置应用程序级别的策略，显示哪些经理可以查看哪些绩效评估，同时不给员工访问权限。

Sandall 建议想要开始使用 OPA Playground 的用户查看一下 [OPA Playground](https://play.openpolicyagent.org/) ，“这是一个在线环境，在这里你可以基本上评估政策并测试它们，看看它们做了什么。”

## 格拉夫纳

Grafana 在单一界面中可视化数据，例如来自时间序列数据库的数据。麦金利说，例如，Prometheus 监控 Kubernetes 的副本可能会在 [Loki](https://grafana.com/blog/2018/12/12/loki-prometheus-inspired-open-source-logging-for-cloud-natives/) 中存储日志或来自 [ServiceNow](https://www.servicenow.ind.in/) 的其他数据。麦金利演示了 Grafana 7 的新功能，并展示了他的团队如何使用 Grafana 构建新平台。

麦金利说:“Grafana 的主要目标是让你的数据存在于任何地方。

亚马逊网络服务 (AWS)和 [Lightbend](http://lightbend.com) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>