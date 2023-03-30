# 为什么彭博把数据押在 Kubernetes 上

> 原文：<https://thenewstack.io/why-bloomberg-bet-its-data-on-kubernetes/>

[为什么彭博将其数据押在 Kubernetes](https://thenewstack.simplecast.com/episodes/why-bloomberg-bet-its-data-on-kubernetes) 上

彭博在过去几十年里成功保持了金融信息和数据巨头的地位，这在很大程度上要归功于技术。1981 年，当彭博成为美国华尔街和金融交易大厅里的大型电脑终端的代名词时，这家公司成立了，现在它自称是一家信息和技术公司。它在全球拥有 19，000 名员工，提供软件、金融、媒体和数据服务，数据深深嵌入其 DNA 中。最近在其庞大的数据管理结构中增加了一个 Kubernetes 层，这是彭博大约三年前采用的。

在[kube con+CloudNativeCon North America 2018](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2018/)上录制的播客中，[彭博](https://www.bloomberg.com/)的数据和分析基础设施负责人 [Steve Bower](https://www.linkedin.com/in/stevenbower) 讨论了彭博为什么以及如何将其数据和基础设施运营过渡到 Kubernetes 和一个主要是云的原生平台，以及他从这一迁移中学到了什么。

Bower 的数据和基础设施小组支持的服务包括数据库、搜索引擎和 Hadoop 基础设施，最终形成数千个数据库实例和大量依赖于不同数据服务的分析平台，Bower 说。

彭博管理的数据的范围和数量显然是巨大的。鲍尔说，数据和数据管理是动力，例如，彭博的招聘网站和彭博终端上的债券筛选，其 [Hadoop](https://hadoop.apache.org/) 基础设施，金融数据和媒体馈送的直接新闻。

大约三年前，彭博建立了鲍尔所描述的“我们自己的黑客版本的 Kubernetes，以便管理和运行(我们的数据服务)。”问题是:为了跟上数据服务不断增长的需求，需要扩展基础设施。

“大约三年前，我们为自己构建了一个系统，并认识到它不会扩展到我们想要的位置，所以我们开始在生态系统中寻找东西。我们看了不同的东西，来到 Kubernetes 真的是因为它实际上有这种与我们建立的非常相似的模型，这是一个非常声明性的模型，你可以声明某个东西应该存在，然后某个东西去让它发生，”鲍尔说。“这就是我们所建立的，它有点符合我们的模式。”

对于微服务，鲍尔说:“这不一定是分解它的行为，而是改变人们构建、部署和管理软件的实际模式。”所以只是为了打破现状而打破现状。我觉得你听到的好像是，‘哦，我想把一切都交给微服务’，我想，“好吧，你有好的理由吗？”鲍尔说对我来说，实际上，原因是可测试性。例如，我们使用一些服务来管理如何在 [Solr](http://lucene.apache.org/solr/) 中更改配置，以及如何将数据从部署的模式和配置移动到我们的 Solr 集群中。我们建立了一个服务，除此之外什么也不做，我们已经有三年没有重新部署它了。"

例如，Bower 的团队看到了将其数据管理基础架构集中到一个一致平台的真正价值。“在我看来，对我们来说，商业价值在于[团队成员]现在可以专注于他们正在开发的实际工具。例如，我们是 Solr 生态系统的一大贡献者，在彭博有一群提交者，”鲍尔说。“我宁愿他们把所有的时间都花在这上面，而不是弄清楚如何收集指标并在一堆服务器上协调他们的软件。这就是我们的商业价值所在。”

作为一个异类，彭博数据基础设施集团在开发新的基础设施和技术时，并不一定要有明确的业务目标。“在这方面，彭博是一家有趣的公司，”鲍尔说。“实际上，很多都是自下而上的。作为工程师，我们应该考虑如何建设和管理。”

Alex Williams，The New Stack 的创始人兼主编，和 TNS 的执行主编 Joab Jackson 一起主持了这个播客。

KubeCon + CloudNativeCon 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>