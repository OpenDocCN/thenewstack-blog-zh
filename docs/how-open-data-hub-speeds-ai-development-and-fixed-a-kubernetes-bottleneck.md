# 开放式数据中心如何加速人工智能开发并修复 Kubernetes 瓶颈

> 原文：<https://thenewstack.io/how-open-data-hub-speeds-ai-development-and-fixed-a-kubernetes-bottleneck/>

[](https://www.linkedin.com/in/alhandy/)

 [亚历克斯·汉迪

亚历克斯是红帽公司的技术营销经理。在他之前的生活中，他报道了第一台 iMac 的发布，然后开始了 20 多年的科技记者生涯。他的作品出现在《连线》、《亚特兰大宪法日报》和《奥斯汀美国政治家》上。](https://www.linkedin.com/in/alhandy/) [](https://www.linkedin.com/in/alhandy/)

许多公司想知道如何正确地将 AI/ML 工具应用到他们的工作和业务应用中。找到这种应用程序用途的一个好方法是看一看商业世界的其他部分正在用机器学习做什么，并尝试在您的组织内找到可以应用它的位置。

作为一个例子，网飞推荐引擎已经被广泛使用，它是一个公开的 100 万美元算法挑战的产物。由此产生的功能可以帮助数百万网飞用户浏览一个巨大的节目和电影库。这增加了用户对平台的兴趣，并有助于服务变得更有用。

如何将这种推荐引擎模式应用到您的业务中？在 Red Hat，它是如何应用到我们自己的业务中的？我们有一些顶尖人才在研究这些机器学习应用，在这个过程中，我们发现了一些关于开源项目的有趣事情，这些项目推动了 [Red Hat OpenShift 平台](https://www.openshift.com/try?utm_content=inline-mention)。

## 瓶颈上游开源项目

如果在为您的公司构建机器学习模型时，您遇到了您正在使用的基础架构内部的限制，该怎么办？[红帽首席数据科学家兼团队负责人 Don Chesworth](https://www.linkedin.com/in/chesworth/) 在研究机器学习模型时就遇到了这样的情况。

Chesworth 已经建立了三个机器学习模型。他的重点是使用这些模型来帮助 Red Hat 支持其客户。他正在使用 Pytorch、GPU、Kubernetes 和[开放数据中心](http://opendatahub.io/)(一个 100%基于开源的机器学习平台)来构建、部署和运行这些模型。

在这三个模型中，两个侧重于分析传入支持请求的文本，第三个(目前正在开发中)向客户提供类似网飞的建议:例如，“询问此主题的客户也发现这五篇知识库文章很有用。”

不幸的是，对 Chesworth 来说，微调最后一个模型以提高其准确性是极其缓慢的。这可能需要大约 100 次测试，他计算出每次测试需要大约 73 个小时才能完成。这对于计划中的用例来说是行不通的，因为要花将近一年的时间才能确定这个模型是否足够准确，能够提供给 Red Hat 的客户。

一段时间以来，Red Hat 一直在为未来的 AI/ML 工作负载进行规划。我们从这些内部 AI/ML 计划中获得了许多知识，并将它们贡献给了一个名为[开放数据中心](http://opendatahub.io/) (ODH)的开源社区项目。Open Data Hub 是基于 Apache Spark、Pytorch、Tensorflow、JupyterHub、KubeFlow、Apache AirFlow、Seldon 等开源社区项目的参考架构。开放数据中心的各种组件的部署通过开放数据中心 Kubernetes 运营商完全自动化。ODH 还包括补充红帽产品，如红帽 Ceph 存储和红帽决策者。

[人工智能库](http://opendatahub.io/docs/ai-library/installation.html)是我们的另一个开源项目，这次是由红帽人工智能卓越中心团队发起的。这是在 Red Hat OpenShift 上提供 ML 模型作为服务的一种努力。这些模型作为服务的开发是一个社区驱动的开源项目，以使 AI/ML 模型更容易访问。

Chesworth 知道容器中的共享内存非常有限，PyTorch 需要大量的共享内存来在多个 GPU 之间分发数据。当他请求开放数据中心团队增加共享内存时，出现了一个问题。Kubernetes 容器中的共享内存是不可配置的。

虽然 Chesworth 在 Red Hat 工作，但他不是内核开发人员，也不是 Kubernetes 的贡献者。幸运的是，许多这样的人存在于 Red Hat。尽管开放数据中心团队最终找到了一个解决方案，但这不仅仅是修补他的系统并完成它的问题。Chesworth 知道，这也需要上游贡献出完善的代码，为任何地方的任何人解决问题。

“默认情况下，”Chesworth 说，“在容器中你有 64MB 的共享内存。Pytorch，当你在多个 GPU 之间分配它时，使用共享内存在系统之间交换数据。在 Kubernetes 和 CRI-O 没有简单的方法来改变这种默认。”

作为背景，CRI-O 是 Kubernetes 的一个轻量级容器运行时。

在 OpenShift 3.11 中已经解决了这个问题的一个变通方法，但是这个解决方案让开发者更加困难。另外，它不是一个基于 Kubernetes 的通用解决方案。因此，Red Hat 团队在上游的 Kubernetes 社区解决了这个问题，这样整个世界都可以从修复中受益——不仅仅是 Chesworth。

开放数据中心团队[的成员向 CRI-O 上游提交了](https://github.com/cri-o/cri-o/pull/4402) [一个补丁](https://github.com/cri-o/cri-o/pull/4174)，该补丁随后被包含在 Kubernetes 1.20 版本中。由于这个补丁，Chesworth 的训练工作现在只需要 49 分钟，而以前估计需要 73 个小时。

这意味着 Chesworth 将不必等待近一年来确定他的模型的准确性，而是可以在一个月内做到这一点。此外，他可以全年训练多个模型，为他服务的团队提供数据驱动的预测。

这使得 Red Hat 的客户支持团队每晚都能轻松运行推荐引擎，将新内容添加到支持文档数据库和通过客户支持推荐引擎提供新内容之间的时间只有 42 分钟。当你的产品在全球范围内全天候被消费时，这一点非常重要。如果突然有 100 个来自世界各地的支持请求，而新发现的问题解决方案没有及时呈现给这些用户，那么将会有大量的支持请求，这将会增加员工和资源的负担。

如果您可以在问题升级之前提供解决方案，从而减少每个支持联系人所需的时间，那么各方都会受益:客户很高兴他们不必再去挖掘支持数据库或搜索论坛。支持人员很高兴他们能够关注有独特问题的客户。Chesworth 很高兴，因为他的机器学习算法正在做他们本来要做的事情:节省每个人的时间。

正如大多数企业软件开发工作一样，每天结束时真正的资源是时间——时间永远不够。开发人员反馈的编译、测试和部署之间的时间。时间训练算法。更新数据库的时间。跟踪 Kubernetes 或 Linux 内核中的一个 bug 所花费的时间。如果你能减少或消除这些时间，你可以为你的团队节省大量的时间。

*赞助商说明:Red Hat OpenShift 的最新版本[刚刚公布](https://www.openshift.com/blog/red-hat-openshift-4.7-is-now-available)。*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>