# 如何对待你的 Kubernetes 集群像牛，而不是宠物

> 原文：<https://thenewstack.io/how-to-treat-your-kubernetes-clusters-like-cattle-not-pets/>

戴尔科技公司的创始人、董事长兼首席执行官迈克尔·戴尔将云定义为“一种方式”，而不是一个地方

随着 IT 越来越成为每个公司的核心业务，理解云原生最佳实践不仅对开发人员来说是关键，对企业的每个部分来说也是关键。本文解释了宠物与牛的类比，以及它如何帮助企业提供更好的服务，更快地恢复，从而减少收入损失。

## **历史:宠物大战牛**

 [比尔·穆里根

比尔·穆里根是 Loodse 的 Kubernetes 倡导者。在他之前的创业公司工作的第一天，Mulligan 被告知要建立一个 Kubernetes 集群，但他不知道如何找到命令行，甚至不知道如何发音 K8s。在许多博客文章、Youtube 视频和错误之后，Mulligan 已经能够成功地向甚至他的祖母解释 Kubernetes。他目前在 Loodse 工作，帮助任何人、任何地方只需点击一下鼠标就能拥有 Kubernetes 集群。](https://www.loodse.com/) 

*宠物与牛*的类比已经成为 DevOps 服务模型的核心概念之一。这个想法最初是由微软杰出的工程师 Bill Baker 在他的演讲“ [Scaling SQL Server 2012](http://www.pass.org/eventdownload.aspx?suid=1902) 中提出的，后来由 Gavin McCance 在 CERN 谈论 [OpenStack cloud 而得到推广。牛和宠物的区别在于每个个体对你来说有多重要。](https://www.slideshare.net/gmccance/cern-data-centre-evolution)

直接引用 Randy Bias 在上发表的关于这一类比的历史:

> 在旧的做事方式中，我们像对待宠物一样对待我们的服务器，例如，邮件服务器 Bob。如果鲍勃倒下了，那就全靠他了。首席执行官收不到电子邮件，这是世界末日。在新的方式中，服务器被编号，就像牛群中的牛一样。比如 www001 到 www100。当一台服务器出现故障时，它会在生产线上被拆除、拍摄和更换。

宠物都非常重要，但是牛是可以互换的。将生产软件基础设施从宠物转移到牲畜上是创建高可用性(HA)系统的关键，该系统具有减少的故障、更小的爆炸半径和更快的灾难恢复。总之，转向黄牛服务模式有助于企业提供更好的服务，减少停机时间。

## **云本地最佳实践:宠物与牛**

可靠地运行和管理可扩展的 IT 基础设施需要使用牛和 Kubernetes 集群，这不会有什么不同。 [Joaquin Menchaca 的博客](https://medium.com/@Joachim8675309/devops-concepts-pets-vs-cattle-2380b5aab313)很好地追溯了从宠物到牲畜管理模型的演变，从裸机服务器到云原生容器和容器编排器。在每个阶段，栈的更高层变得可替换，创建[不可变生产](https://www.digitalocean.com/community/tutorials/what-is-immutable-infrastructure)，其中仅部署精确副本，并且它们可以在任何时候被替换。如果有任何需要更改的地方，就会进行新的部署，旧的部署就会被淘汰。不可变生产消除了差异，从而减少了部署失败、跨环境的一致性、轻松的横向扩展以及简单的回滚和恢复过程。

为了利用这些优势并将不可变容器投入生产，Kubernetes 已经成为事实上的标准，因为它简化了部署和编排容器的过程。然而，安装、管理和更新 Kubernetes 本身并不简单。为了避免这些挑战，集群已经成为新的宠物，公司运行几个大型的重要集群，而不是多个较小的可替换集群。这与 Kubernetes 建立的云本地原则直接矛盾。为了从云原生方法中获得全部价值，企业也必须像对待牛一样对待他们的 Kubernetes 集群。按需上下旋转它们，把它们当作一次性的、可替换的资产，而不是珍贵的宠物。

除了简化管理和节省运营时间和资金之外，将 Kubernetes 集群像牛一样运行也可以对底线产生真正的影响。例如，一家年收入 50 亿欧元的电子商务公司完全依赖于其店铺在线。每一分钟的停产都是 10，000 欧元的销售损失。在与 CNCF 的案例研究中，当 VSCO 通过 Kubernetes 标准化了他们的供应和中断恢复时，他们**将其中断时间减少了 88%**。云本地计算基金会已经看到企业像牛群一样转向使用 Kubernetes 集群。[在过去的六个月里](https://www.cncf.io/blog/2018/11/13/cncf-survey-china-november-2018/)，运行一到五个生产集群的组织减少了 37%，而运行 11-50 个集群的组织增加了 154%。将基础设施视为养牛，可以让公司简单地更换他们的基础设施，并更快地重新上线，从而节省销售。

在 Loodse，我们坚信应该把 Kubernetes 集群当作牛来对待。我们使用多种工具使我们的开发人员和运营商尽可能容易地创建和使用 Kubernetes 集群，包括[种类](https://github.com/kubernetes-sigs/kind)、 [KubeOne](https://github.com/kubermatic/kubeone) 和 [Kubermatic](https://www.loodse.com/product/) 。我们使用 kind 快速生成 Kubernetes 集群，在 CI/CD 管道中运行集成和 E2E 测试。我们最近开源了 KubeOne，因为它使开发人员能够在任何云提供商、内部或裸机集群上快速安装、管理和升级高度可用的 Kubernetes 集群。此外，我们正在积极地为上游 Kubernetes 中的 [cluster-api](https://github.com/kubernetes-sigs/cluster-api) 做出贡献，以简化集群的创建、配置和管理过程。最后，当我们为大规模安装设计 Kubermatic 时，我们也遵循了将集群变成牛群的最佳实践。这要求任何人只需点击一下鼠标，就可以创建、更新和删除 Kubernetes 集群。Kubermatic 通过将用户集群 Kubernetes 控制组件旋转为种子 Kubernetes 集群中的容器来实现这一点(这里是架构细节)。如果 worker 集群的某个控制组件发生任何问题，它将会自动重启**并被 seed Kubernetes 集群替换**，从而将控制组件和集群本身变成牛。

## **结论**

不管在堆栈的哪一层，运行牛而不是宠物都是计算基础设施的最佳实践。它为客户提供了更好的服务，减少了恢复时间，并消除了生产中断带来的收入损失。Kubernetes 成为容器编排的标准，因为它允许您像对待牛一样对待容器。Kubernetes 集群本身也应该像牛一样对待。

要了解更多关于集装箱化基础设施和云原生技术的信息，请考虑 2019 年 5 月 20 日至 23 日在巴塞罗那举行的[kube con+CloudNativeCon Barcelona](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2019/)。

![](img/084167cd0664dba0abbab8ea9e64c17a.png)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>