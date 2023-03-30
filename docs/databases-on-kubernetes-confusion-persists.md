# Kubernetes 上的数据库:关于采用的困惑依然存在

> 原文：<https://thenewstack.io/databases-on-kubernetes-confusion-persists/>

“开放数据”的美妙之处在于，它允许第三方测试他人研究的有效性。虽然我们相信数据收集的方式，但我们对 Percona 最近关于开源数据管理的报告中发布的一些图表有所怀疑，因为我们自己的分析产生了不同的结果(因此我们不会重新发布 Percona 的图表)。

根据 Percona 的说法，超过四分之三在生产中运行 Kubernetes 的公司说他们的公司使用容器“作为他们的数据库”这个令人惊讶的统计数据来自我们对来自[开源数据管理软件调查](http://percona.com/open-source-data-management-software-survey)的 [Percona](https://www.percona.com/) 提供的原始数据的分析。进一步挖掘，我们发现 47%部署了生产 Kubernetes 的公司在“Kubernetes”上运行生产数据库

我们刚刚出版的《[状态的状态:云原生存储的新方法](https://thenewstack.io/ebooks/storage/state-of-state-cloud-native-storage-for-developers/)》电子书解释说，企业应用程序中的托管状态过去意味着将数据存储在安装在硬件上的数据库中，并管理运行有状态应用程序，这些应用程序通常由严格的服务级别协议(SLA)管理。公司现在使用 Kubernetes 来管理计算和存储资源。有时状态通过存储服务在容器内处理，而其他时候通过不同种类的存储系统处理。

我们不知道 Kubernetes 上运行的数据库中有多少是在一个容器中运行的。Percona 的报告否定了自己的发现，称[“超过 25%的受访者正在使用容器，但不一定是为了运行数据库。”然而，他们的问题显然是关于用于数据库的容器。我们对实际数据更有信心，因为它与 Diamanti 调查中 32%的容器用户一致，即容器将用于数据库。](https://thenewstack.io/percona-postgresql-and-the-complex-database-landscape/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>