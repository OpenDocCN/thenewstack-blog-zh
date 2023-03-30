# AWS Re:Invent 和 KubeCon:隐形基础设施竞赛

> 原文：<https://thenewstack.io/kubecon-aws-reinvent-race-invisible-infrastructure/>

[](http://iguaz.io/blog/)

 [亚龙·哈维夫

亚龙·哈维夫，iguazio 的 CTO 兼联合创始人，是一位涉足大数据、云、存储和网络的连续创业者。在加入 iguazio 之前，Yaron 是 Mellanox 的数据中心解决方案副总裁，负责技术创新、软件开发和解决方案集成。亚龙发推文为@亚龙特拉维夫。](http://iguaz.io/blog/) [](http://iguaz.io/blog/)

经过两周的全面云融合，我终于回家了，从拉斯维加斯的 AWS re:Invent 开始，到奥斯汀的 KubeCon 结束。

KubeCon 的共同主题是关于 Kubernetes 和容器变得无聊。这类似于 re:Invent 强调的，关于开发自动化和使基础设施不可见。会议以备受期待的 [Google](https://cloud.google.com/kubernetes-engine) 开发者倡导者 [Kelsey Hightower](https://twitter.com/kelseyhightower) 的演讲开始，他在演讲中演示了一个典型的开发流程:每次代码提交到 GitHub，Google Cloud 都会自动构建并运行一个容器(pod)，然后为其提供一个 HTTP 端点进行测试。

最终合并时，代码出现在生产 HTTP URL 下。在整个演示过程中，Hightower 不需要使用或考虑底层的 Kubernetes 基础设施。为了说明这一点，他安装了 Kubernetes，使用了“好的，Google，创建一个 Kubernetes 集群！”语音指令。

虽然令人印象深刻，但我忍不住挠头。Hightower 刚刚向我们展示了我一周前在 re:Invent 看到的东西，这是在亚马逊工作的“无服务器”…

在另一场会议上，Kubernetes 的联合创始人 [Brendan Burns](https://www.linkedin.com/in/brendan-burns-487aa590/) 展示了他的[超粒子](https://metaparticle.io/)项目，他现在是[微软](https://azure.microsoft.com/en-us/?v=17.14)杰出的 Azure 工程师。作为 Kubernetes 之上的一层，它具有简化的分布式计算 API 语义，用于工作负载平衡、分布式锁、主选举、分片等。

> AWS re:Invent 是关于消费的，而 KubeCon 是关于我们的创作者群体的。

Metaparticle 仍处于起步阶段，但它将允许我们通过从代码中自动构建所需的基础架构，来构建可扩展的应用程序，而无需考虑底层基础架构。我认为我们将会看到更多帮助主流开发者采用云原生模式的尝试，有可能将这种模式集成为无服务器平台不可或缺的一部分。

GitHub [现在在生产中使用 Kubernetes](https://thenewstack.io/github-goes-kubernetes-tells/)，并分享说它几年前曾试图设计自己的解决方案，这导致了一个结论，即这是一个太大的挑战。工程师们基本上一直在等待，直到现在，生态系统有了一个管理容器的合适解决方案。GitHub 在 Kubernetes 上建立了一个自动化的软件交付管道，其中每个代码更新都要经过几个自动化测试和集成步骤。最后，在整个生产现场使用之前，使用[金丝雀部署](https://martinfowler.com/bliki/CanaryRelease.html)进行小规模部署。

我不禁想到这两个节目的区别在于消费和创造。AWS re:Invent 是关于“这是我们构建的，你如何使用它来运行得更快”(即消费)，而 KubeCon 的主题是“这是我们如何构建它，这里是你可以下载源代码的地方”(作为一个创作者社区)。从两个展会的人数来看，高科技消费者似乎比美国创造者多 10:1。

[无服务器](/category/serverless/)趋势并没有跳过 KubeCon，一系列的演示和公告支持让基础设施对开发者不可见的核心信息。像 [nuclio](https://nuclio.io/) 、 [Kubeless](https://github.com/kubeless/kubeless) 和[裂变](http://fission.io/)这样的开源平台与 Kubernetes 进行了原生集成，使功能成为另一种托管集群资源。[我的公司](https://github.com/bivas) [iguazio](https://www.iguazio.com/) 的大数据高级架构师 Eliran Bivas 在他的演讲中解释了如何在 Kubernetes 上从头开始构建端到端的实时分析管道，而无需 Hadoop 和 YARN 复杂性。

一个单一的掌舵命令被用来自动部署大数据工具，如 [Spark](https://spark.apache.org/) 和 [Zeppelin](https://zeppelin.apache.org/) ，以及用于实时事件处理、人工智能和仪表盘的 [nuclio](https://nuclio.io/) 无服务器功能。从此，数据科学家可以通过交互式 Zeppelin 笔记本电脑查询数据，开发人员可以通过 nuclio 的交互式 IDE 或 GitHub push 添加或更新代码。基础设施是无形的。

在 KubeCon 大会上,[云本地计算基础](https://www.cncf.io/)达到了重要的里程碑。在一次面对面的[无服务器工作组](https://github.com/cncf/wg-serverless)讨论中，我也是参与者之一，我们最终确定了白皮书，并设法将各种通用事件 API 的提案整合为一个。这是使无服务器功能可跨平台移植以消除当前锁定的第一步。

我们在存储工作组中取得的进展较少，因为我们仍然在争论“[云原生存储](https://thenewstack.io/state-cloud-native-storage/)”实际上是什么(在此阅读我的观点)。我猜这是展会上唯一一个看不见基础设施的地方。

云本地计算基金会、谷歌和微软都是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>