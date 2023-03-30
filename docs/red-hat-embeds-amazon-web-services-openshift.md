# 红帽将亚马逊网络服务嵌入到 OpenShift 中

> 原文：<https://thenewstack.io/red-hat-embeds-amazon-web-services-openshift/>

周二，Red Hat 在 OpenShift [中引入了内部亚马逊网络服务功能](https://thenewstack.io/red-hat-summit-serves-openstack-io-saas-containerized-java-microservices/),这让该公司看起来好像已经找到了一个与[微软的 Azure Stack](https://azure.microsoft.com/en-us/overview/azure-stack/) 有竞争力的替代品，它有效地复制了微软内部安装的云服务。但在周三早上向红帽峰会与会者进行的演示中，亚马逊和红帽建筑师揭示了幕后的某种魔力，依赖于运行 OpenShift containers 的服务器和亚马逊之间链中某处的可见性。

AWS 合作伙伴解决方案首席架构师 [Matt Yanchyshyn](https://twitter.com/mattgy) 解释道:“无论 OpenShift 在哪里运行，无论您是在笔记本电脑上运行，在自己的数据中心运行，使用我们的服务，还是在公共云中运行，如果您能够*查看 OpenShift 的*亚马逊网络服务，我们希望您能够通过 OpenShift 使用亚马逊网络服务。”

可能需要一轮克林顿式的分析来确定 Yanchyshyn 在这个上下文中的“看”是什么意思。可以说，由于互联网，每个 Azure 堆栈部署都可以在公共云中“看到”Azure。[微软的文档说得很清楚](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-deploy)Azure Stack 的使用确实需要与 Azure 的连接。因此，人们可以得出结论，OpenShift 的连接性要求实际上没有什么不同。

然而很明显，Red Hat 和 Amazon 在这里对语言的选择是有意的。演示后几分钟，Red Hat 公司发表了一篇博客文章，重复了这句话:“正如我们在主题演示中提到的，如果你能看到亚马逊网络服务，那么我们希望你能在 OpenShift 中使用亚马逊网络服务。”

[https://www.youtube.com/embed/EKo3khfmhi8?feature=oembed](https://www.youtube.com/embed/EKo3khfmhi8?feature=oembed)

视频

但是这件事绝不是小事，特别是对于任何业务是技术性的开发团队来说。验证主机的订阅状态可能是一件非常简单的事情，但是 AWS 和大量微服务之间的持续连接可能会带来潜在的延迟，任何分布式服务架构师都需要考虑这一点。

周三正式发布的 OpenShift 上提供了更完整的 AWS 服务列表，其中包括网络连接和大数据服务，被要求减少对基础设施关注的开发人员肯定会关心这些服务需要多长时间才能看到。

在一个预先录制的视频中，AWS 首席执行官[安迪·杰西](https://twitter.com/ajassy)透露了一个更加完整的亚马逊服务列表，这些服务将与 OpenShift 平台原生打包，并可在 open shift 平台上运行，无论它们在哪里运行。周二提到的 [AWS Lambda](https://aws.amazon.com/lambda/) 无服务器服务引起了一些红帽官员的质疑，是 Jassy 列表的第一项。无服务器的架构师应该感到兴奋。

同样上榜的还有:[关系数据服务](https://aws.amazon.com/rds/aurora/)、 [Aurora MySQL 和 PostgreSQL 兼容数据库](https://aws.amazon.com/rds/aurora/)、[红移数据仓库服务](https://aws.amazon.com/redshift/)、 [EMR (Elastic MapReduce)](https://aws.amazon.com/emr/) 、 [Athena 交互查询服务](https://aws.amazon.com/athena/)、 [CloudFront 内容交付网络](https://aws.amazon.com/cloudfront/)、 [Route 53 DNS 服务](https://aws.amazon.com/route53/)和[弹性负载均衡](https://aws.amazon.com/elasticloadbalancing/)这位首席执行官随后为“其他人”加入名单敞开了大门。

“它还将允许使用 OpenShift 的应用程序开发人员更快地移动，”Jassy 继续说道，“因此他们将在内部和云之间拥有更加一致的环境。此外，我们还将为 Red Hat 和 AWS 提供单一支持途径，以便您可以放心地在生产环境中部署您的应用。”

这一支持渠道在周二的 Red Hat 新闻发布会上进行了讨论，它将使 Red Hat 支持人员能够为 OpenShift 平台上运行的组件提供 AWS 认可的支持。这一安排似乎类似于红帽在 2015 年与微软达成的交易，使两家公司能够成为支持在 Azure 上部署和管理红帽组件(如 RHEL)的联系点。

Jassy 还表示，容器对这些服务的访问将使用 AWS 的本地服务代理进行仲裁，尽管 Red Hat 周三的博客帖子指定与这些代理的通信将使用[现在的标准开放服务代理 API](https://www.openservicebrokerapi.org/) 进行。

可以想象，OpenShift 可能需要“查看”AWS，以便它可以使系统中的每个组件保持最新。但是[正如红帽工程师在周二](https://thenewstack.io/red-hat-summit-serves-openstack-io-saas-containerized-java-microservices/)展示的那样， [OpenShift.io](https://openshift.io/) 托管服务——大概还有主 [OpenShift 3.5 平台](https://blog.openshift.com/announcing-the-openshift-container-platform-3-5-ga/)——将提供部署模板，让团队快速利用 CI/CD 管道和敏捷开发实践。在演示中，他们展示了当容器化应用程序的组件未能通过生产就绪测试时，这些管道中最不复杂的管道如何仍能发出适当的标志。除非 AWS 服务的多个版本同时可用，以便在服务升级之前测试新版本，否则很容易想象 OpenShift 开发人员的视野中突然出现一片危险信号。

也就是说，除非 OpenShift 平台和 AWS 的原生平台之间存在更稳固的关系，除了动词“查看”所暗示的内容红帽发言人周三晚些时候告诉新堆栈，“看到”实际上意味着连接到 OpenShift 的能力。至于软件组件之间可能需要什么类型的绑定，我们被告知，“这取决于 OpenShift 应用/服务的性质和所使用的 AWS 服务。”换句话说，我们可能要等一等……嗯，看看。

Red Hat 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>