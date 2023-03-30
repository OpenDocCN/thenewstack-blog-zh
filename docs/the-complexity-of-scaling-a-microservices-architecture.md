# 扩展微服务架构的复杂性

> 原文：<https://thenewstack.io/the-complexity-of-scaling-a-microservices-architecture/>

[](https://www.broadcom.com/info/aiops/docker-monitoring)

 [Nicolas Bohorquez，软件开发人员

Nicolas Bohorquez(@ Nickmancol)是一名来自哥伦比亚的软件开发人员，目前正在意大利都灵的 Collegio Carlo Alberto 攻读复杂经济系统数据科学硕士学位。此前，Nicolas 是一些初创公司开发团队的成员，并在美洲创办了三家公司。他热衷于复杂性建模和使用数据科学来改善世界。](https://www.broadcom.com/info/aiops/docker-monitoring) [](https://www.broadcom.com/info/aiops/docker-monitoring)

微服务架构提供了[许多明显的优势](http://www.boringgeek.com/thoughts-on-migrating-to-a-microservices-architecture)，但它们也带来了挑战。

其中最大的挑战是扩展。有效地扩展微服务应用程序需要一种与整体扩展完全不同的方法，在整体扩展中，您通常只依赖负载平衡器和应用程序的副本(或者 Chris Richardson [称为](http://microservices.io/articles/scalecube.html)“X 轴可伸缩性”))

这是一个重要的主题，因为尽管微服务的可伸缩性看起来很容易理解，但实际上很难掌握。抽象意义上的扩展微服务的基本规则和原则在现实环境中并不总是适用，因为在现实环境中，您每小时要处理数百万个请求。

本文从抽象的角度讨论了您的团队在扩展微服务架构时应该考虑的一些初始挑战。它还确定了可能有助于应对这些挑战的各种工具。

## 挑战 1:处理微服务复杂性

复杂性很难定义，但总的概念是与许多组件和部件相关联的，这些组件和部件在一定的时间范围内相互作用，形成一个系统。复杂系统是许多著名机构的研究课题，微服务架构是复杂系统的完美案例。这不仅意味着技术的转变，还意味着组件连接方式、通信方式以及人们如何协作以保持一切正常运行。

处理复杂环境(如面向微服务的解决方案)的一个有用技术是将其视为一个网络。网络分析为您提供了了解架构中的结构属性和关键节点(微服务、组件和代理)的工具、指标和方法，以及如何保护它们免受意外故障的影响，以实现弹性或稳定性。许多研究论文[1]、[2]和[书籍](http://barabasi.com/networksciencebook/)提供了对网络分析的基本理解。此外，诸如 [Kubernetes](http://kubernetes.io/) 、 [Swarm](https://docs.docker.com/swarm/) 和 [Mesos](http://mesos.apache.org/) 等工具将帮助您整合基础设施，以开发和部署完整的解决方案。

## 挑战 Waldo 在您的微服务架构中处于什么位置？

作为通过应用程序接口(API)协同工作的已定义任务的小型独立单元，微服务可以在您的架构中大量涌现，从几十个到数百个，甚至更高数量级。添加更多微服务意味着增加您的解决方案的复杂性，您必须确保新的微服务可以与您现有的微服务一起扩展。一个流氓(依赖)微服务就能让你整个解决方案瘫痪！

微服务发现和注册工具，如网飞的 [Eureka](https://github.com/Netflix/eureka) ，允许对可用服务进行分散管理(如域名服务器)。Eureka 是一个用于“弹性中间层负载平衡和故障转移”的服务注册中心，允许服务自动注册和发现其他服务。它还提供了在这些服务的实例之间分配负载的机制。

## 挑战 3:跟踪微服务问题

日志记录是每个软件解决方案的重要组成部分，但是在微服务架构中，跟踪环境中所有组件的问题很快就会变成一场噩梦。应对微服务监控挑战需要一些功能，例如将请求映射到微服务拓扑，或者对从其他服务收集信息的集中式端点进行检测。同样重要的是，能够在动态环境中建立正常活动的基线，了解监控环境中服务之间的依赖关系，并将基础架构的一层(如主机服务器)中的事件与其他层(如应用程序服务)相关联。)

## 挑战 4:微服务通信

在微服务领域，通信是一个巨大的挑战。创建清晰的操作契约和定义职责是架构师和开发人员的两项常见任务。两个已完成的项目都必须使用一种语言来说明每个服务的功能，在许多情况下，还必须说明上下文元素或对其他微服务的依赖性。

当您的解决方案扩展到数百个微服务时，清楚了解每个微服务的特性和要求对于生存至关重要。Swagger 和 [API Blueprint](https://apiblueprint.org/) 是有助于阐明微服务工作方式的两个工具示例。

## 挑战 5:构建微服务专业知识

从危机中学习的团队积累的知识可以用于未来。为此，自动化和可重复性是管理微服务的成熟流程的两个主要特征。为了从过去的事件中学习，像[动物园管理员](https://zookeeper.apache.org/)这样的工具可以方便地存储你的操作中所涉及的工具的配置。

## 结论

伟大的架构意味着巨大的挑战。当你选择一个模型来解决一个问题时，要意识到其中的折衷。无论是哪种模式，问题的范围从复杂性到清晰的沟通和[监控](https://www.ca.com/us/info/docker-container-monitoring-essentials.html)。如果你和你的团队准备好用合适的工具来解决问题，微服务是有用的和高度可扩展的。做好准备——从其他角度(运营、开发和测试等)可以看到更多的挑战。

***了解更多监控微服务，获取免费电子书:*** [容器监控&管理](https://www.ca.com/us/info/docker-container-monitoring-essentials.html#download) ***。***

**参考资料和进一步阅读**

1.  watts d .和 h . Strogatz s .(1998 年)。小世界网络的集体动力学。*自然*。第 393 卷。440-2.10.1038/30918.
2.  Laurent，g .，Saramä ki，j .，和 Márton，K. (2015 年)。从呼叫到社区:时变社会网络模型。*欧洲物理杂志 B* 。88.10.1140/epjb/e2015-60481-x。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>