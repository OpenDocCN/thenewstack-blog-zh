# Pivotal 为其云原生平台增加了一项无服务器服务

> 原文：<https://thenewstack.io/pivotal-introduces-serverless-platform/>

无服务器计算的快速升温如果不是流动的，就什么都不是。虽然亚马逊网络服务的[λ](https://aws.amazon.com/lambda/)确实在市场上突出了这个领域，但是[谷歌](https://cloud.google.com/kubernetes-engine)、 [IBM](https://www.ibm.com/cloud/functions) 、[微软](https://cloud.google.com/functions/)和[甲骨文](http://fnproject.io/)都有自己的产品。 [Pivotal](https://pivotal.io/) 现在也是提供这种服务的公司之一，在本周于旧金山举行的 [SpringOne 平台](https://springoneplatform.io/)会议上展示了一个新平台。

新的无服务器产品是 Pivotal Cloud Foundry 2.0(PCF)的一部分。此次发布的亮点不仅包括无服务器功能，还包括一个面向平台用户的新“应用商店”市场，以及将 [Kubernetes](/category/kubernetes/) 容器编排引擎和 [VMware 的 NSX](https://www.vmware.com/products/nsx.html) 集成到平台中的[和](/category/kubernetes/)[于 2018 年初全面上市，两者均用于管理容器和防火墙。](https://www.vmware.com/products/nsx.html)

Pivotal 战略高级副总裁 James Watters 表示，Pivotal 没有构建新的无服务器框架，而是利用其现有的平台基础设施为更传统的应用程序提供无服务器风格的生命周期。该产品是现有功能的顶峰，支持遗留 Java 和企业应用程序基础设施。

Watters 说，这一点很重要，因为像 Amazon 这样的供应商目前提供的许多无服务器产品都因专有基础设施而存在隐性的锁定。其他产品，如 IBM 的 OpenWhisk 和 Oracle 的 fn，试图通过提供一种在任何地方运行的方法来解决基于函数的计算中隐含的运行时问题。

然而，Pivotal 避开了已经在企业中运行了近 20 年的新基础设施。随着该公司 2009 年收购 SpringSource(当时称为 VMware)，Pivotal 成为基于云的企业 Java 应用程序的标准载体。

但是 Watters 说，Pivotal 将 Cloud Foundry 集成到其核心平台中，实现的不仅仅是 Java 运行时。“许多人围绕较低级别的基础架构发布了许多公告。Pivotal 是运行 Java 最快、最灵活的方式。NET 和 Node.js。我们将它们作为语言服务来运行。我们将为它构建容器，将它与服务网集成，你可以将它作为一种语言服务来消费，”Watters 说。

Pivotal 的功能即服务，加上新的 Kubernetes 和 NSX 管理功能，使 Pivotal 的平台能够处理从第 2 层到第 7 层的整个端到端云环境。Watters 说，这个名为 Pivotal Function Service (PCF)的功能接口“为企业提供了一站式服务，让他们可以在一个多云平台上消费应用、功能和服务代理”。

Watters 说，对于企业来说，PCF 的很多好处是简化了开发工作流程和环境。

“人们已经开始抓住核心产品中的一件大事，”沃特斯说，“我们有这个嵌入式操作系统，它是 [Cloud Foundry](https://www.cloudfoundry.org/) 独有的。我们有一个[嵌入式操作系统](https://pivotal.io/platform/pcf-components/stemcells)，我们用 [Bosh](https://bosh.io/) 运行和更新它。企业能够以恒定的速度进行安全修补和虚拟机重建。在一个主要漏洞出现的几天内，你可以让你的整个产业完全修补。消除开发人员独自修补整个堆栈的所有痛苦是有帮助的。”

## K8s

至于决定作为一等公民与 Kubernetes 集成的动力，当 Pivotal 的最大股东 VMware 明确对虚拟机作为数据中心测量单位感兴趣时，Watters 说客户已经要求容器支持。“我们有一个客户只用两名操作人员就能操作 20，000 个集装箱。现在，他们希望在其上为打包的应用程序运行容器服务。也许他们想运行这些预建的 ISV 容器，或者在平台上运行 [Elasticsearch](http://www.elastic.co/) 。这就是 Pivotal Container Service 的用武之地，”Watters 说。

Pivotal 能够从一个操作控制台运行容器、虚拟机、长时间运行的服务器、短时间运行的功能，甚至管理防火墙，它希望其产品能够吸引希望加快开发速度的企业。Watters 说，其价值的很大一部分也是像任何其他应用程序一样可靠地处理函数的能力，警告是当完成时它的规模为零。

“这是 [Pivotal 容器服务](https://pivotal.io/pks)的一个特性，它将允许您对事件做出响应，然后在默认情况下扩展到零。这是一段面向事件的代码，当事件流被接收和完成时，它的规模将变为零，”Watters 在谈到 Pivotal 构建其功能的方式时说。

Watters 说:“总的来说，对于企业的应用程序来说，我们已经使自动扩展变得更加可用。“我们的所有这些客户端都可以自动扩展，他们过去一直使用机架和堆栈式服务器，并针对峰值进行调度。在某种意义上，函数比自动缩放器更容易，因为它们默认缩放到零。现在，它是一个跨平台的大型共享计划应用程序集。”

“我们的金融服务客户说，‘当市场在一天结束时关闭，我必须运行一些事件，清理东西，然后关闭，’Watters 说。这种能力甚至延伸到了语言框架本身。

“我认为我们所做的是首先推出[春季云功能](https://github.com/spring-cloud/spring-cloud-function)，”沃特斯说，他指的是 7 月份的发布。那个版本“使得开始编写这些功能成为可能，并且我们创建了一个自定义代码的共享库，所以你可以共享它们。现在我们只是对它们进行优化，并将其集成到事件源中。我们认为这是正在运行的其他应用程序的扩展。都是一模一样的 Spring 代码。”

“如果你看一下 [Spring Cloud Function](https://spring.io/blog/2017/07/05/introducing-spring-cloud-function) ，这是语言方面的一个示例实现，你可以使用 [RabbitMQ](https://www.rabbitmq.com/) 或 [Kafka](https://kafka.apache.org/) 和其他事件源。我们认为对于各种各样的应用程序，事件在一天中很少发生。我们可以更有效地安排这些简单的任务。这并不意味着每个应用程序都应该被重构为一个函数。世界上的亚马逊人正试图说服每个人重构整个产业来做到这一点。我们是企业最重要的新功能的实用集成者。我们坚持我们的编织，我们做好了 Java 云的准备。我们也试图在容器和函数方面更加务实。我们正在寻找使用这些东西的有效方法，”沃特斯说。

由[佩德罗·拉斯特拉](https://unsplash.com/photos/jEAcDBsrRNw?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)通过 [Unsplash 拍摄。](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>