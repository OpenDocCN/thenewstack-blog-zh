# 用军械库的 Minnaker 踢三角帆上的轮胎

> 原文：<https://thenewstack.io/kick-the-tires-on-spinnaker-with-armorys-minnaker/>

Armory 是开源交付工具 [Spinnaker](https://spinnaker.io/) 的企业版提供商，在本周的[kube con+CloudNativeCon Europe](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)之前推出了 [Minnaker](https://github.com/armory/minnaker) ，为开发人员和组织提供了一种更快、更简单的方法来测试 Spinnaker，而无需进行全面的生产安装，也不会有任何困难。

该公司在一份新闻声明中写道，Minnaker 使用轻量级 [K3S](https://k3s.io/) Kubernetes 发行版和 [Armory Operator](https://docs.armory.io/docs/installation/armory-operator/) 构建，部署在虚拟机中，允许公司“仅在 10 分钟内而不是 10 天内实现软件部署”。

[军械库](https://www.linkedin.com/in/chadtripod)[的现场首席技术官 Chad Tripod](https://www.armory.io/) 解释说，安装 Spinnaker 的正常过程可能涉及许多步骤和多个团队，从供应 Kubernetes 集群和持久存储，到与云运营团队合作处理入口。有了 Minnaker，所有的复杂性都消除了。

“你必须做很多事情，采取很多步骤，才能真正意识到实际的管道和 Armory 本身的价值，因此 Minnaker 所做的就是在前端解决用户体验问题。我们所有在 Armory 与这些大公司一起工作并交付软件的人，我们采用了所有这些最佳实践，像任何优秀的工程公司一样，我们尽可能地自动化了许多步骤。我们试图抽象出平台的力量，从试图获得提升以进入门内，实际上从中获得一些价值，”Tripod 说。“我们将它放在一个可消耗的包中，在开始时，最初的提升不到 10 分钟，我们可以让你从零开始部署一条管道到 Kubernetes。”

更简单地说，Armory CEO [Daniel R. Odio](https://www.linkedin.com/in/drodio) 说“对于工程师来说，Minnaker 是一种非常非常优雅的方式，他们可以在午休时尝试它，或者可以在笔记本电脑上运行 Spinnaker。”

在创造 Minnaker 的过程中，军械库团队解决了三个具体的部署障碍。首先，他们取消了对 [halyard](https://spinnaker.io/reference/halyard/) 的需求，这是一个位于集群之外的容器，用于编程、安装和配置 Spinnaker，而是转移到 CRD 和操作器。“现在我们有了一个非常 Kubernetes 本地的声明式设置模型，”Tripod 说。

接下来，使用 YAML 和 Kubernetes 的本地配置管理工具 [Kustomize](https://kustomize.io/) 完成安装和设置，Tripod 说这使得很容易集成到 GitOps 模型中。从那里，Tripod 说他们为大规模运营的公司提供了最佳实践，他说所有这些都添加到一个工具中，不仅可以作为 Spinnaker 的介绍，还可以过渡到全面的 Spinnaker 安装。

Tripod 说:“我们基本上是以一种很容易推送到 Git repo 的方式来制作 Minnaker 的，一旦你完成了初始测试和验证，然后从 GitOps 模型中，你可以将它部署到你可能拥有的任何生产级 Kubernetes 集群中。”“所以它有一个非常好的工作流程来达到一个非常大的规模。”

Odio 解释说，许多公司面临的问题不仅仅是最初实施 Spinnaker 的时间，而是心理转变。他说，许多企业已经使用 bash 脚本构建了“spit，polish，and tape”的定制交付管道，并且通常甚至害怕接触它们，因为最初的创建者早已不在了。Minnaker 让开发人员可以很容易地测试 Spinnaker——他们所需要的只是一个运行虚拟机的地方，比如云中的 Ubuntu 实例——然后从那里开始向他们团队的其他人展示什么是可能的。

“公司传统上已经建立了他们自己的软件交付工具，并且它经常是不一致的。也许有些团队构建了金丝雀部署，而其他团队没有。它非常脆弱，”Odio 说，并解释说 Spinnaker 依赖于不同于许多连续交付系统的分类，将应用程序置于中心。“这在很大程度上实际上是关于内部教育和讲故事，以及能够展示而不是讲述。Minnaker 在这个非 prod 用例中的真正价值是允许团队理解这种新方式的可能性，然后他们可以在内部证明摆脱他们投入如此多的所有工具所需的更重的负担和投资。这些公司存在沉没成本谬误，他们在非云原生的传统工具上投入了大量资金。这真的很好。”

除了入门之外，奥迪奥解释说，Minnaker 和 Armory 的真正价值在于包含这些最佳实践，这些实践带来了多年的经验，现在有了简化的安装体验。

“我要说的是，除非您深入了解 Spinnaker，否则今天还不能很好地理解从盒子中获取最佳实践的能力。但是，举例来说，为了能够让一只金丝雀下降，你只需将它添加到你的管道中，曼-惠特尼算法是基于谷歌和网飞十多年来在云规模上部署的所有知识，所有这些数据，你只需免费从盒子里拿出来，”奥迪奥说。“简直不可思议。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>