# 不要暂停你的 Kubernetes 采用――PaaS 它代替！

> 原文：<https://thenewstack.io/dont-pause-your-kubernetes-adoption-paas-it-instead/>

如果你正在使用基于云的软件，现在就不可能忽略 Kubernetes 这个因素。大多数团队希望利用容器化和编排的全部好处，当然是使用 Kubernetes。然而，他们在两个重要领域遇到了麻烦:

1.在生产中部署和操作 Kubernetes 所需的广泛技能

2.业务成果的深度以及如何证明 Kubernetes 的支出是合理的

在本文中，让我们探讨一下影响 Kubernetes 采用的各种技术和非技术领域。这里提供的见解来自作者的个人经历，以及与世界各地以不同方式与 Kubernetes 合作的各种技术专家无数小时的互动。

## 定义起点

对于软件开发团队来说，迁移到 Kubernetes 可能会很复杂，这取决于他们在云原生演进中的当前状态。

可能已经有团队在使用 Docker 或 containers，在这种情况下，迁移到 Kubernetes 是一个有机的过程。团队还可能会在虚拟机上投入大量资金，从虚拟机开始，他们将不得不一次性跳过容器化和流程编排。

由于 PaaS 工具，可能有一些团队的工作流由云抽象主导，在这种情况下，通往 Kubernetes 的道路将需要一些定制的工程工作来适应这些变化。所有对 Kubernetes 感兴趣的团队都应该使用现代工具和足够的自动化。所以，每一条通往库伯内特斯的道路都有一个水坑(或者两个)！

![](img/391802f50de7cd7fa9ebd5b6a1ed7e59.png)

## 以前发生过这种情况吗？

Kubernetes 有几个“第一次”这是第一个展现出惊人增长的开源社区！贡献者的数量增长得相当大，相当快。云本地计算基金会的一项 [2021 年调查显示，全球有 390 万名 Kubernetes 开发者，比上一年增长了 69%。自开源项目开始以来，超过 4000 个组织做出了超过 280 万的贡献，形成了 Kubernetes 的轨迹。这些数字使它成为有史以来最受欢迎的开源项目之一，并且它的受欢迎程度还在继续增长。](https://www.containiq.com/post/kubernetes-statistics)

然而，这并不是技术的采用第一次产生曲棍球棒曲线。在过去，一些趋势已经显示出巨大的潜力，尤其是在技术趋势方面。特别是，2011-2015 年间 Docker 的采用以及在此之前 VM 炒作的轨迹浮现在脑海中。

## PaaS 基底

平台即服务或 PaaS 被定义为运行应用程序和托管堆栈的基础架构的抽象。通常，它们作为一个环境提供给软件开发团队，应用程序可以部署到这个环境中。根据 PaaS 基础架构的设计，开发人员会看到一个界面，允许他们调整基础架构所需的参数，同时指定他们正在部署的应用程序的大小和形状。通常，PaaS 工具还允许使用扩展来消费服务。

通常，不同的语言和框架倾向于使用不同的生产路径。当使用 PaaS 时，该界面提供了一种同质和统一的方法来部署应用程序，而不考虑用于编写应用程序的语言。除此之外，PaaS 工具利用控制平面，控制平面在其操作方式中起着核心作用。

控制平面——名副其实——通过资源调配、访问和配置，支持应用程序管理的各个方面。服务是 PaaS 工具链的重要组成部分。它们独立于核心的 PaaS 功能，通常以连接器的形式提供。这些连接器被赋予不同的名称(市场、基金会、服务、经纪人等)。)旨在使使用 PaaS 特性部署的应用程序更加完整。

## PaaS 承诺

1.  PaaS 可以支持定制的工作流，使团队能够高效地工作。
2.  PaaS 支持引入新的方式来轻松构建、运行和部署应用。
3.  PaaS 允许在不影响团队的情况下替换底层技术。

## 工具示例

有许多工具可以帮助团队缩小 Kubernetes 差距。这里有几个例子:

RedHat stable 的 OpenShift 是一个成功的容器化和 Kubernetes 平台的流行例子。 [Cloud Foundry Korifi](https://www.cloudfoundry.org/technology/korifi/) 是 Cloud Foundry 社区帮助将工作负载轻松部署到 Kubernetes 的一次尝试。它保留了久经考验的 cf 推送体验，并且是一个[开源](https://github.com/cloudfoundry/korifi)工具，可以部署到所选的 Kubernetes 集群，使其成为一个引人注目的选择。最近公布的还有 [Epinio](https://epinio.io/) 、 [Acorn Labs](https://acorn.io/) 、 [Porter](https://porter.run/) 和 [KubeVela](https://kubevela.io/) 。

## 权衡(咄！)

![](img/d6918ec19d13680da36ad9ab56a5dc1b.png)

当谈论 PaaS 平台时，关于选择一个固执己见的工作流的警告往往主导了讨论。大约十年前，Gartner 发表了一篇有趣的论文，题为:PaaS 中的生产力与控制权衡。其中强调的一些问题至今仍有争议。工程领导层不应在开发团队的绩效效率和 SRE 员工的卓越运营之间做出选择。

由于向容器化的大规模转变，PaaS 工具声称提供的升级、打包、安全和其他工程方面的问题正在慢慢得到解决。由于诸如 [GitOps](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/) 、 [Buildpacks](https://thenewstack.io/container-images-the-easy-way-with-cloud-native-buildpacks/) 以及一些提供自动化的声明式语法等趋势，构建中的同质性正逐渐成为一种规范。

许多服务声称它们避免了锁定，因为它们是基于标准的，因此你可以将你的代码移动到任何地方。这可能在一方面是正确的，但另一方面是你被服务提供的东西所束缚。

## 摘要

PaaS 工具通常有助于促进技术转变。他们已经展示了在不断变化的工具的模糊水域中航行的成功历史。当使用 PaaS 工具来帮助他们采用和适应新工具时，软件工程团队有很多收获——特别是 Kubernetes。

对于小型和精简的软件工程团队来说，PaaS 工具可以让开发人员专注于应用程序开发，而不是集成交付和 Kubernetes 就绪，从而提高他们的生产率。对于关注运营需求的规模稍大的团队，PaaS 工具可以帮助对每个部署进行精细调整，并在整个组织中统一应用部署最佳实践。对于企业规模的团队，PaaS 除了提供底层部署、打包和其他基本功能外，还涵盖了安全性和合规性的关键领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>