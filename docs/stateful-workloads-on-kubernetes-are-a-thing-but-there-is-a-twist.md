# Kubernetes 上的有状态工作负载是一件事，但是有一个问题

> 原文：<https://thenewstack.io/stateful-workloads-on-kubernetes-are-a-thing-but-there-is-a-twist/>

[](https://www.sylvainkalache.com/)

 [西尔万·卡拉什

西尔万·卡拉什是一名企业家和软件工程师，目前在他联合创办的霍尔伯顿学校工作。](https://www.sylvainkalache.com/) [](https://www.sylvainkalache.com/)

Kubernetes 正在成为行业标准；蟑螂实验室[红帽](https://www.openshift.com/try?utm_content=inline-mention)曾 [发现](https://www.prnewswire.com/news-releases/new-study-reveals-biggest-trends-and-priorities-in-architecting-workloads-on-kubernetes-301360913.html)94%的受访组织在 Kubernetes 上部署服务和应用。标准化意味着在任何工作负载的任何环境下运行任何堆栈，包括有状态的工作负载。

虽然在 Kubernetes 上运行有状态工作负载曾经是不可行的，但 Kubernetes 2021 年报告 中的 [数据发现，90%的受访公司认为 Kubernetes 已经为有状态工作负载做好了准备。更令人惊讶的是，他们中的绝大多数(70%)正在生产中运行它们。因此，虽然在 Kubernetes 上运行数据是完全可能的，但有一个问题:运营商。](https://dok.community/dokc-2021-report/)

2016 年推出的 Kubernetes 运算符是可编程扩展，可执行 Kubernetes 本身无法处理的操作。运营商通过扩展 Kubernetes API 的功能来提供智能、动态的管理能力。当有些人，比如 Docker 的创始人，把他们看作 [可编程微平台](https://twitter.com/solomonstre/status/1450903129218682880?s=20&t=eWdMLOnWuB8oC7bPMFMSyg) 时，他们最有影响的地方就是对 [运行有状态的工作负载](https://thenewstack.io/kubernetes-when-to-use-and-when-to-avoid-the-operator-pattern/) 。

## 第 2 天操作

为什么会这样？虽然 [Kubernetes](https://thenewstack.io/category/kubernetes/) 现在正在为运行面向数据的工作负载提供 [坚如磐石的基础](https://thenewstack.io/kubernetes-1-24-drops-dockershim-makes-space-for-stateful-workloads/) ，但一些特定于应用的任务——更具体地说是第二天的操作——无法在本地处理。以数据库为例，第 2 天的操作包括执行备份、拍摄快照、执行故障转移、应用补丁或索引列。因为每个数据库做的事情都略有不同，所以 Kubernetes 很难在本地处理这种特定于应用程序的操作方法。

这就是为什么在 Kubernetes 上运行一个有状态的应用程序是完全可能的，但运行的好坏很大程度上取决于操作人员的水平。Kubernetes 社区 [上的数据发现，42%](https://dok.community/blog/first-data-on-kubernetes-report-published/) 的运营商用户对其质量有不同程度的抱怨。理解一个应用程序的来龙去脉可能是一项具有挑战性的任务，更不用说封装它们以便在 Kubernetes 这种高度分布式和动态的环境中运行了。

虽然[运营商框架](https://operatorframework.io/)提供了一套坚实的开发工具和 Kubernetes 组件，但对于复杂的用例，如多集群，仍有改进的空间，正如 KubeCon EU 的[datastass](https://www.datastax.com/?utm_content=inline-mention)产品经理 Christopher Bradford 在此[视频采访](https://www.youtube.com/watch?v=9LeO77sLvzQ) 中强调的。

对于最终用户来说，在超过 250 个运营商中挑选合适的运营商可能是一项艰巨的任务。质量的不同程度可以解释为它们是由各种各样的组织构建的，如服务公司、供应商、OSS 社区和个人。虽然有[](https://operatorframework.io/best-practices/)的最佳实践可以遵循，但对于如何构建它们却没有强有力的指导，也没有明显的疏忽。最后，由于可能有不同的有效方法来执行相同的操作，运营商可能会采取不同的技术方法，这些方法必须由用户来权衡。

操作员框架 提供了一个“能力水平”图表，可以帮助最终用户了解操作员的成熟度水平。它分为五个级别:

*   **第 1 级**–基本安装:自动化应用供应和配置管理
*   **2 级**——无缝升级:支持补丁和小版本升级。
*   **三级**–全生命周期:应用生命周期、存储生命周期(备份、故障恢复)。
*   **第 4 级**–深度洞察:指标、警报、日志处理和工作负载分析。
*   **Level 5**–自动驾驶仪:水平/垂直缩放、自动配置、调谐、异常检测、调度调谐

解决运营商质量问题的另一个有希望的方法是回到 Kubernetes 成功使用的方法:一种社区主导的管理方法，更具体地说，是[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)。PostgreSQL 专家 EDB 最近 [决定开源他们的 PostgreSQL 操作符](https://www.enterprisedb.com/blog/introducing-cloudnativepg-new-open-source-kubernetes-operator-postgres)——[CloudNativePG](https://cloudnative-pg.io/)——并提交给 CNCF，目标是将其作为毕业项目。

CNCF 项目的三个阶段是沙盒、孵化和毕业。为了更上一层楼，每个项目都需要证明它是可信的、可持续的、被广泛采用的、具有健康的变化率，并且是由来自多个组织的贡献者开发的。这一过程需要数年时间，但它将确保通过这一过程的运营商是生产就绪。我预测会有更多的人走这条路。

我们在 [DoK 社区](https://dok.community/)最近宣布了一个 [景观](https://dok.community/landscape/) 索引并记录了现有的产品、解决方案和顾问，这些产品、解决方案和顾问支持 Kubernetes 上的数据。它目前列出了:数据库、存储、数据管理器和操作员。最终用户找到他们的方式的另一种方式。

我们已经正式跨越了鸿沟”是 Kelsey Hightower [在宣布 Oracle 数据库的一个操作符时所说的话，指的是在 Kubernetes 上运行有状态的工作负载。既然这种实践不再仅仅针对早期采用者，我们也开始在大规模采用浪潮中冲浪，是时候让行业采用更多的标准和健壮性了。](https://twitter.com/kelseyhightower/status/1409297909774831618)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>