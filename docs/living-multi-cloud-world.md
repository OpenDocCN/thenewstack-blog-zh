# 生活在一个多云的世界:Bosh，Kubo 和开放服务代理 API

> 原文：<https://thenewstack.io/living-multi-cloud-world/>

[](https://www.cloudfoundry.org/)

[Childers](https://www.cloudfoundry.org/)

[Childers 在大规模计算和开源软件方面已经花费了超过 18 年的时间。2015 年，他成为云铸造基金会的联合创始人，担任技术参谋长。他是 Apache CloudStack 的第一任副总裁，在 SunGard 领导企业云服务时，他帮助推动了该平台的发展，后来又在 Cumulogic 担任产品战略副总裁。在 SunGard 之前，他领导了包括 IRS.gov、USMint.gov、美林和 SEI Investments 在内的组织的任务关键型应用程序的重建工作。Chip 是 OSCON、LinuxCon North America、LC Japan、LC EU、ApacheCon、O ' Reilly Software Architecture Conference 等活动的资深演讲者。在空闲时间，奇普喜欢带着他的黑色实验室徒步旅行，驾驶双体船和太阳鱼，并试图跟上他年轻的女儿。](https://www.cloudfoundry.org/)

[](https://www.cloudfoundry.org/)[](https://www.cloudfoundry.org/)

随着云原生计算在企业中的兴起，支持各种风格的云原生计算的平台正在不断完善。到目前为止，每一个已经出现的平台——包括 [Kubernetes](/category/kubernetes/) 、Mesos 和像 [Cloud Foundry](https://www.cloudfoundry.org/platform/) 这样的云原生应用平台——都是在考虑特定用例的情况下构建的。

一些平台是通用的，但是是从特定的架构角度设计的。其他的则更具体于它们被设计来处理的用例。例如，Kubernetes 是一个通用的容器管理平台，它是从一个非常特定于容器的角度设计的。同样，Apache Mesos 是一个通用的计算资源管理平台，但它的根源是管理大数据系统的方法，主要是在 Hadoop 和 Spark 生态系统中，这一点很清楚。[Cloud Foundry Elastic Runtime](https://www.cloudfoundry.org/platform/)的用例更具体一些。它专注于尽可能快地从代码到运行和可操作的应用程序。

作为一个实用主义者，我从来不相信“一个平台统治所有人”的思维模式。现实是企业使用多个平台。他们一直是，也将永远是。在当今的云原生世界中，我们需要一种方法来让这些多个平台协同工作。

在过去的几个月里，几个项目同时启动，共同使这种企业涅槃成为可能，包括 [Kubo](https://pivotal.io/kubo) 和[Open Service Broker API](https://www.openservicebrokerapi.org/)(OS papi)。也许令人惊讶的是，这些新的努力使用了在云铸造生态系统中已经存在多年的工具: [BOSH](http://bosh.io/) 。

## 为什么 BOSH 对多平台世界有意义

为了正确看待 Kubo 和 OSBAPI，让我们从 BOSH 开始，它是 Cloud Foundry 生态系统中的一个分布式系统工程工具，可以简化发布工程、部署和生命周期管理。BOSH 回答了您希望在哪个平台上安装软件的问题。BOSH 提供了 Cloud Foundry 的多云功能。它有一个抽象层，让您可以与几乎任何基础架构类型进行对话，无论是像 Amazon 或 Azure 这样的公共云、私有云还是虚拟化基础架构 OpenStack 部署、vSphere 集群或裸机。最重要的是，BOSH 旨在支持部署的“第二天”需求。

许多不同的软件都是为 BOSH 打包的，它非常适合云原生应用程序部署和生命周期管理。Cloud Foundry Elastic Runtime 使用 BOSH 作为其部署工具。

## Kubo:为 Kubernetes 带来多重云

一些采用 BOSH 和 Cloud Foundry 的大型企业也在使用 Kubernetes。然而，Kubernetes 集群的生命周期管理正在成为一个棘手的问题。去年秋天，谷歌和 Pivotal 合作创建了 Kubo T1，这是一个开源项目，使用 BOSH 来管理 Kubernetes 集群。BOSH 为多个平台提供了一致且强大的运营和生命周期管理能力。Kubo 是一个很好的例子，它展示了开源项目如何协同工作，为拥有复杂环境的用户提供更好的服务。

除了 Kubo 作为一种简化多平台管理的方式，Kubernetes 也在不断发展。在上个月的 KubeCon 大会上，有很多关于另一项努力的讨论，即[开放服务代理 API](https://www.openservicebrokerapi.org/) ，因为 Kubernetes 社区正在用 OSBAPI 构建其新的 Kubernetes 服务目录。

Open Service Broker API 是一组抽象，是一种使平台和后端服务协同工作的方式。例如，它可以在数据库即服务和平台之间创建一个契约，使平台能够请求一个新的数据库实例，然后将其与应用程序相关联。

OSBAPI 可以快速地将多种服务集成到一个平台中。它还解放了开发人员，使他们可以专注于自己的应用程序代码，而不是供应和绑定服务。使用 Kubo 可以最大限度地降低成本，并且可以为他们提供单击式部署。你可以在这里了解奥斯巴皮[的历史和背景。](https://thenewstack.io/cloud-foundrys-service-broker-api-role-in-kubernetes-and-open-source-platforms/)

与其将 API 视为云控制器团队决定的东西，不如将其视为您在云控制器中实现的东西。通过这种方式，可以将各种能力带入到多云环境中。

就其本身而言，Kubernetes 服务目录可以进一步简化异构系统的管理。服务可以存在于任何平台上，但您将有一种统一的方式来管理基于容器的工作负载、适合作为容器推出的内容或您希望作为代码推出的内容。

## 欢迎来到现实世界

不是挑一个单一的平台。我们接受了企业是复杂环境的现实，我们专注于让竞争系统也能很好地协同工作。我们没有强迫用户做出选择；我们给了他们选择。

所有这些努力加在一起，为正在努力处理多个复杂系统的大型 IT 企业创造了更好的体验。通过让他们一起工作，每个人都赢了。

Cloud Foundry Foundation 基金会是新堆栈的赞助商。

由[吉安保罗·拉·帕格利亚](https://unsplash.com/@gianpaololapaglia)通过 [Unsplash](https://unsplash.com/photos/bWI4Vd4vI3w) 拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>