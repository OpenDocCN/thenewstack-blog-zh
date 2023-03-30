# 如何正确监控 Elasticsearch

> 原文：<https://thenewstack.io/properly-monitor-elasticsearch/>

[](http://www.opsview.com)

[Eric berns en](http://www.opsview.com)

[Eric berns en 是 Opsview 的内容营销主管，ops view 是一家领先的本地基础设施、应用和云服务监控软件提供商。](http://www.opsview.com)

[](http://www.opsview.com)[](http://www.opsview.com)

作为一个分布式 RESTful 搜索和分析引擎， [Elasticsearch](https://www.elastic.co/) 是一个常用的工具，用于支持各种面向数据的应用的快速搜索。实时分析、可扩展搜索解决方案和多租户支持等功能都在 Elasticsearch 的日益流行中发挥了重要作用。然而，并非所有用户都知道如何正确监控 Elasticsearch，从而将数据转化为可操作的见解。通过了解监控 Elasticsearch 的最重要方面，更容易获得对软件的全面了解，并确保您的工具部署尽可能顺利。

## 弹性搜索监控工具

利用 Elasticsearch 功能的唯一方法是使用监控工具来帮助监督您的 Elasticsearch 环境。有很多工具是为维护目的而设计的，但是关注面向数据的资源更有效率。诸如 [Elastic Monitoring](https://www.elastic.co/products/x-pack/monitoring) (以前的漫威)和 [ElasticHQ](http://www.elastichq.org/) 之类的工具是方便地实时查看性能指标和处理集群任务的合适选项，以便您可以识别基础架构中出现的趋势。 [Elastic 策展人](https://github.com/elastic/curator)是另一个直观的产品，可用于管理弹性搜索索引和快照。

### 弹性搜索监控插件

安装正确的监控工具后，正确监控 Elasticsearch 的下一步是组织适合您的 Elasticsearch 环境细节的插件。插件增强了基本的 Elasticsearch 功能，虽然许多使用 Elasticsearch 的用户为生产案例提供了开箱即用的选项，但最好的插件弥补了缺失的功能。不幸的是，Elasticsearch 5.0 不支持站点插件(由于安全风险)，但仍然有一些有用的插件可以用来监控 Elasticsearch 集群。请务必调查最相关的插件，如[脑波强化器](https://github.com/lmenezes/cerebro)和[头部](https://github.com/mobz/elasticsearch-head)，然后根据您的具体需求利用它们。

### 重要的弹性搜索指标

一旦您设置好监控工具和插件，您就可以开始组织 Elasticsearch 指标，它将查明您的基础架构中发生的任何问题。[elastic search API](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs.html)随时高效地捕捉性能指标，集群健康和搜索/节点/索引性能等数据点都是其运行状态的重要指标。通过密切关注这些指标，您将自动更好地了解 Elasticsearch。

### 性能试验

进行持续的性能测试将有助于最大化您的弹性搜索监控工作。为了确保您的配置方法高效运行，您应该始终如一地测量集群增长等领域，并利用 Elasticsearch 的基准测试工具( [Rally](https://github.com/elastic/rally) )作为测量系统变化影响的手段，并最终防止性能不佳。

利用 doc 值和避免交换将有助于为您的环境保持理想的速度，并且通过这些策略保持 Elasticsearch 的最新状态，您的监控计划将确保 Elasticsearch 得到充分优化，并且为您的用户保持闪电般的搜索速度。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>