# 红帽 OpenShift 3.1 为两者打开了大门。NET 和 JBoss 中间件

> 原文：<https://thenewstack.io/openshift-3-1-opens-door-net-jboss-middleware/>

当微软和 Red Hat 上周宣布他们的历史性合作协议时，开始倒塌的墙继续倒塌。为了赶上正在三藩市举行的 [KubeCon](https://kubecon.io/) 会议，Red Hat 发布了 OpenShift 平台的 3.1 版本。这个新版本建立了以前不存在的关键桥梁，将它的技术栈的主要部分连接起来——其中一些是 Red Hat 的部分。

有了 OpenShift，基于 OpenShift 构建的分布式应用将很快可以整合最近开源的[。NET Core](https://thenewstack.io/the-opportunity-of-net-core-and-why-it-will-not-fade-away/)——我们了解到，Red Hat 现在将分发它——以及 Red Hat 的 JBoss Fuse 企业服务总线，加上 Red Hat Gluster 分布式文件存储和 Red Hat Ceph 软件定义的数据访问。

## 事态

“PaaS 的定义由来已久。Red Hat 的 OpenShift 副总裁兼总经理 Ashesh Badani 解释说:“这实际上是为了确保您可以在规模上为某些类别的应用程序提供大量的灵活性和弹性。“Heroku 是 12 因素应用程序和开发风格的最早支持者之一。但它认为应用程序显然只是无状态的，并没有真正考虑更传统地构建的应用程序，或者本质上扩展性较差的应用程序。”

Badani 对 OpenShift 3.1 的目标是让无状态和有状态应用程序共存。他向我们讲述了金融服务行业中一个非常重要的客户的故事，该客户拥有超过 700 个遗留应用程序，其中只有十几个可以使用云原生框架进行重新架构。他说，将 OpenShift 与 Gluster 和 Ceph 结合起来，将使所有在其平台上运行的容器能够持久存储。

下一点非常重要:去年 6 月在 DockerCon，包括 Weaveworks 和 ClusterHQ 在内的第三方 Docker 支持者团队首次展示了持久存储功能，这一功能是通过当时 Docker 附加组件的原型概念实现的，这些附加组件是扩展底层平台功能的模块，同时还可以相互联网。那个演示展示了当时大多数开发人员都渴望的一点功能:*持久存储*。

正如 Red Hat 的 Badani 告诉我们的那样， [OpenShift 现在支持持久存储](https://thenewstack.io/the-real-docker-ecosystem-launches-with-plugins/)，包括 Docker 容器(也可能是 Windows 容器)，而不需要这些插件。因此，他认为，一旦将传统应用程序迁移到容器化架构和 OpenShift 3.1 中，就不需要为了继续访问持久存储而对其进行修改。

随着 OpenShift 版本的推出，PaaS 平台通过[与 Kubernetes orchestrator](https://thenewstack.io/shift-red-hat-openshift-part-2-cartridges-kubernetes/) 的集成，开始了红帽全新的旅程。Badani 说，正是通过这种关系的扩展，3.1 版本使得 Gluster 卷可以作为存储抽象通过 Kubernetes 访问。

“你真的可以看到这种不可变基础设施的前景，”他继续说道，“让容器在本质上是短暂的。但是在过去，为了能够支持附加存储，您必须在平台设计之外做一些事情。所以容器是短暂的，但是当你炸毁它们时，你就失去了它们存储数据的地方。现在，我们可以说，您可以丢失容器，但我们将保存它们周围的数据。因此，您可以将它们从一个节点移动到另一个节点……您可以开始支持以比以前大得多的规模运行容器集群的概念，用于不同类型的应用程序。”

## 同一时间，同一频道

OpenShift 3.0 是 Red Hat 的 PaaS 平台的第一个版本，通过 JBoss 支持 Java EE 和基于 Apache Tomcat 的 Java。Red Hat 副总裁告诉我们，现在在 3.1 中，该平台在包括 Java 在内的容器化应用程序中增加了对 Fuse 企业服务总线的支持。这可能最终会带来某种程度的共存，使这家金融服务公司的 688 个左右的旧式应用程序能够与十几个应用程序和谐共存，从而能够迁移到目前为止，为所有这些应用程序提供一个通用的消息传递组件。

“实际上，要让 Java 开发人员加入进来，还有很多实质性的工作要做，”他说，并引用了甲骨文上个月刚刚发布的 Java SE 云服务。“我们做了大量工作将它们集成到 JBoss IDE 中，让使用基于 Eclipse 的 IDE 的人能够更容易地创建项目，然后将项目部署到 OpenShift 中。”

Badani 补充说，随着开发人员更多地转向微服务模型，他们将需要理解他们正在创建的对象之间的关系，尽管这些关系无疑会变得更加复杂。“现在，我们将下一代基于容器的部署的承诺，以及围绕 Docker 和 Kubernetes 的所有激动人心的事情，带给那些以更传统的方式开发和集成应用程序，但真正将这种基于云的新技术的力量带入他们的世界的人。”

Red Hat、Docker 和 Weaveworks 是新堆栈的赞助商。

封面艺术:[尤利娅·卡扎科娃](http://www.yulia-kazak.de/)的《推土机》，帆布丙烯画，2009 年，获得知识共享许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>