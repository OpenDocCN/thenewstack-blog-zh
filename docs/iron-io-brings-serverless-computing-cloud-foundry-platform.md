# Iron.io 为 Cloud Foundry 平台带来了无服务器计算

> 原文：<https://thenewstack.io/iron-io-brings-serverless-computing-cloud-foundry-platform/>

[无服务器](/category/serverless/)计算的承诺是，对于开发者来说，it [可以抽象出](https://t.co/aUaUvBAPUN)大量的基础设施:只需编写你的函数，服务会处理剩下的事情。随着 AWS Lambda 和其他基于云的产品越来越受欢迎，这种架构越来越受欢迎， [Iron.io](https://www.iron.io/) 为企业运营团队提供了在他们自己的基础设施中建立无服务器服务的能力。

Iron.io 的旗舰软件 [IronWorker](https://www.iron.io/platform/ironworker/) 的一个优势是，它可以轻松嵌入各种云原生和私有云平台，大大减少了系统管理员为用户提供无服务器服务所需的培训和维护量。

[Cloud Foundry](https://www.cloudfoundry.org/) 是最新一个获得原生 Iron.io 集成的平台，这是在最近的 Cloud Foundry 欧洲峰会上宣布的。

在本期 [The New Stack Makers](/tag/the-new-stack-makers/) 播客中，我们在峰会上询问了 Iron.io 首席执行官 [Chad Arimura](https://twitter.com/chadarimura) 关于 Iron.io 软件如何在 Cloud Foundry 上运行的问题。我们还讨论了 Docker 稳定性、将 Iron.io 与 [BOSH](https://thenewstack.io/bosh-hooks-cloud-foundry-google-cloud-platform-offers-large-scale-vm-lifecycle-management/) 部署工具集成的可能性、异步无服务器作业的新兴用例，以及最近围绕无服务器架构的兴趣爆发[。](https://thenewstack.io/serverless-computing-use-cases-image-processing-social-cognition/)

[用 Iron.io](https://thenewstack.simplecast.com/episodes/running-serverless-technology-on-cloud-foundry-with-iron-io) 在云代工厂上运行无服务器技术

采访也可以在 YouTube 上[观看。](https://youtu.be/8zmOgQyiWrE)

那么，这种与 Cloud Foundry 的集成实际上是如何工作的呢？

基本上，该公司已经将 Iron.io 平台几乎完全安装在可由云代工厂的新 Diego 运行时引擎运行的 [Diego](https://docs.cloudfoundry.org/concepts/diego/diego-architecture.html) 容器中。

“在我们整合之前，我们的平台将在虚拟机和容器上运行，本质上是与 Cloud Foundry 并行运行，”Arimura 说。“现在，Iron.io 实际上在 Diego 运行时中运行其工作负载。这是一个非常自然的工作流程。”

通过在 Cloud Foundry 中作为内部作业运行，这个 Iron.io 部署可以在内部调用其他 Cloud Foundry 资源，从而节省集成工作。Cloud Foundry 最终用户可以像任何其他 Cloud Foundry 服务一样，利用 Iron.io 执行无服务器任务。管理员无需学习和维护单独的 Iron.io 堆栈。

“它看起来像一个本地的 Irion.io 作业，但实际上是在 Diego 内部运行的。Arimura 说:“这是进入 Cloud Foundry 的一个干净的界面。

对于 Iron.io 来说，Cloud Foundry 只是该公司打算与之合作的一系列平台中的最新一个。

Arimura 说:“我们真的喜欢完全不知道底层平台是什么。除了 Cloud Foundry，IronWorker 还可以轻松地与 OpenStack、OpenShift、 [Kubernetes](/category/kubernetes/) 、Mesos 以及主要的公共云提供商合作。所有这些平台的 API 都是一样的。

Arimura 说:“我们的目标是让它们看起来像一个本地服务，所以它不是单独部署或维护的。”

无服务器最适合运行处理某种周期性或传入任务的功能，如视频编码或解码，或图像处理。功能代码不是在服务器上运行，而是在需要时快速启动，然后在工作完成后立即返回休眠状态。

Iron.io 的平台已经在一些相当大的公司找到了家，包括特纳广播公司、Twitter 和谷歌。

专注于精酿啤酒的社交网站[使用 Iron.io 处理用户的签到，用户向该服务报告他们喝的每一种品牌的啤酒。Untappd 是 Iron 的首批客户之一，已经将运营规模从每周末几千人的入住扩大到超过 50 万人的入住。](https://untappd.com/)

“他们在一个完全无服务器的基础设施上做到了这一点，”Arimura 说。

[Docker](https://www.mirantis.com/software/docker/kubernetes/) ， [Iron.io](https://www.iron.io/) ， [Mesosphere](https://d2iq.com/) ， [OpenShift](https://www.openshift.com/) 和 [Cloud Foundry Foundation](https://www.cloudfoundry.org/) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>