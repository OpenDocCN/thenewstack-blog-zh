# Kubernetes 上有状态应用的发展

> 原文：<https://thenewstack.io/the-evolution-of-stateful-applications-on-kubernetes/>

Kubernetes 和 containers 显然是当今 IT 界的热门话题，但如何管理运行在云原生平台之上的有状态应用程序和数据也很重要，尤其是对于运营而言。该过程包括随着组织向高度分布式容器化环境的转变，管理来自遗留有状态应用程序的数据。

在本期的 [The New Stack Makers](/podcasts/makers) 播客中，New Stack 的创始人兼发行人 [Alex Williams](/author/alex/) 在 Kubernetes 上讨论了大数据、存储和有状态应用的概念。嘉宾[大数据和存储组织研究员 Tom Phelan](https://www.linkedin.com/in/tom-phelan-61b749/) 、[惠普企业(HPE)](https://www.hpe.com/us/en/home.html) 和[HPE 杰出工程师 Joel Baxter](https://twitter.com/joel_k_baxter?lang=en) 利用他们在容器化环境中管理有状态应用和数据的丰富经验。他们还讨论了 KubeDirector，这是一个在 Kubernetes 上运行非云本地有状态应用程序的开源平台。

[Kubernetes 上有状态应用的演变](https://thenewstack.simplecast.com/episodes/the-evolution-of-stateful-applications-on-kubernetes)

Baxter 最初寻求的问题之一是如何解决多集群环境中的数据访问问题。他解释说，当时，典型的使用模式可能涉及在将数据复制到集群环境进行处理之前预先接收数据。

“这一过程有许多不利之处，因为您增加了对更多存储的需求，并且增加了整个过程的时间。但它的一个好处是，一旦你把数据放在集群中，你就可以让任何可以访问该集群的人都可以访问这些数据，”巴克斯特说。“这是一个独立的阶段，你可以让一些管理人员说，‘好吧，你现在可以访问这些数据了。这是你的副本。"

另一种方法是将数据转移到一个公共存储库中。“你让人们按需访问它，而现在，突然之间，你探索了所有这些认证和授权问题，例如谁应该有权访问哪些数据，以及如何在运行时动态管理这些数据，”巴克斯特说。“所以，这肯定是困扰我们一段时间的事情之一。”

最终找到了一个解决方案，在计算集群之间匹配 Kerberos 身份。“这是能带来顾客的价值的一部分，”巴克斯特说。

作为一种帮助将大量传统应用移植到容器化环境的方式，KubeDirector 有助于填补传统运营商在迁移到原生云时无法提供的空白。

“开源社区中有很多运营商可以让你下载和运行你的应用，但当我们谈论拥有数百个(如果不是数千个)遗留应用的企业时，他们希望在容器上运行。他们不具备每一种应用的专业知识，”费伦说。“所以他们通常不会编写一个操作符，它是一段 [Go](https://golang.org/) 代码，对应用程序有深入的了解，对 Kubernetes API 有很好的理解。”

KubeDirector 通过为相应的应用程序提供操作员功能，能够处理数百个 YAML 文件。“这意味着你可以拥有数百个这样的 YAML 文件，只需一个操作员和一个 KubeDirector 实例，就可以管理和控制所有不同类型的遗留应用程序，”Phelan 说。“这是一个非常强大的工具，可以非常容易地为 Kubernetes 添加新应用程序支持。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>