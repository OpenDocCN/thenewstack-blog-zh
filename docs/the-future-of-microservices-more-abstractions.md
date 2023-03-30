# 微服务的未来？更多的抽象

> 原文：<https://thenewstack.io/the-future-of-microservices-more-abstractions/>

这篇文章的作者是 Container Solutions 的主编。

微服务 10 年前出现，是软件中有时发生的融合发展的例子之一。虽然这一术语可以归功于全球软件咨询公司 [Thoughtworks](https://www.thoughtworks.com/) 的[詹姆斯·刘易斯](https://twitter.com/boicy)和马丁福勒，但是[阿德里安科克罗夫特](https://www.linkedin.com/in/adriancockcroft/)当时在网飞和许多其他硅谷公司也在讨论类似的想法。[亚马逊](https://aws.amazon.com/?utm_content=logo-sponsorpage&utm_source=thenewstack&utm_medium=website&utm_campaign=platform)、[谷歌](https://about.google/)和[易贝是在大约相同的时间独立达成或多或少相同架构模式的公司之一。](https://www.ebayinc.com/)

在这个术语被创造出来的十年里，我们看到了 Kubernetes、service mesh 的兴起和无服务器的开始，我们也开始看到微服务被应用到前端的影响。除了水平扩展实践，微服务允许开发人员更快速地部署代码，比起组件的可维护性，更支持组件的可替换性。

无论好坏，对于许多人来说，微服务已经成为默认的架构选择。对于拥有自治团队和松散耦合系统的组织，微服务可以很好地工作，但是它们带来了与任何分布式系统一起工作所固有的复杂性。

“我强烈主张公共云相对于私有云及数据中心的显著优势，我认为这一点非常明确。在许多情况下，是恐惧在那些情况下阻止了人们前进"[独立技术顾问 Sam Newman](https://www.linkedin.com/in/samnewman/) 告诉 New Stack，他正在看他的书的第二版"[构建微服务](https://samnewman.io/books/building_microservices_2nd_edition/)"。“但有了微服务，这个世界要复杂得多。”

考虑到这一点，微服务时代已经过去十年了，思考我们已经走到了哪里，以及我们仍然需要解决哪些问题是一件有趣的事情。

## 评估:部署和运行时

现在有各种各样成熟的、设计良好的微服务框架，涵盖了大多数语言的基础，JVM 上有过多的选项，包括 [Spring Boot](https://spring.io/projects/spring-boot) 、 [Dropwizard](https://www.dropwizard.io/en/latest/) 、 [Helidon](https://helidon.io/#/) 、 [Lagom](https://www.lagomframework.com) 、 [Micronaut](https://micronaut.io) 和 [Quarkus](https://quarkus.io/) ，以及诸如 [Go 工具包](https://github.com/go-kit/kit) for Go、[烧瓶](https://flask.palletsprojects.com/en/2.0.x/)和[等选项](https://falconframework.org)

同样，良好的监控选项比比皆是。 [OpenTelemetry](https://thenewstack.io/getting-started-with-opentelemetry-for-java/) 的出现意义尤为重大。由 OpenTracing 和 OpenCensus 合并而成，它拥有广泛的供应商和语言支持，提供了分布式遥测数据的标准化。这意味着开发人员只需对他们的代码进行一次检测，然后就可以交换和更改监控工具，比较竞争解决方案，甚至在生产中针对不同需求运行多种不同的监控解决方案。

然而，当我们考虑部署和运行时时，情况就变得有些模糊了。Kubernetes 或多或少已经成为微服务的代名词，其复杂性不断增加，促使云本地咨询公司 [Container Solutions](https://www.container-solutions.com/) 的首席科学家[Adrian Mouat](https://blog.container-solutions.com/10-predictions-for-the-future-of-computing)推测我们将看到竞争对手崛起。

“值得注意的是，复杂性并不只是隐藏在引擎盖下。它正蔓延到界面上，影响着用户，”Mouat 说。“在`kubectl run`破解并运行一个演示还是相当容易的。但是，运行生产应用并找出如何安全地公开它们需要了解大量不同的功能，这不可避免地会导致 YAML 文件比大多数微服务源代码都长。”

纽曼总结了一个基本挑战:“Kubernetes 对开发者并不友好。令我震惊的是，我们仍然没有一个好的、可靠的、类似 Heroku 的抽象，它被广泛应用于 Kubernetes 之上。”

[Spotify](https://www.spotify.com/) 的工程总监 [Pia Nilsson](https://www.linkedin.com/in/pia-nilsson-02b47b1/) 谈到了这家快速扩张的公司的新工程师合并他们的第 10 个 pull 请求平均需要 60 天。作为回应，该公司推出了一个[开发者门户](https://thenewstack.io/design-a-better-kubernetes-experience-for-developers/)，后台，现在是[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)的[沙盒项目](https://backstage.io/)。

[网飞](https://about.netflix.com/)非常重视 DevEx——该公司为开发者“铺平的道路”——用它来帮助[加速采用](https://www.infoq.com/presentations/devex-netflix-graphql/)graph QL 等新技术。同样，我们也看到了内部开发和通过像 T21 这样的供应商开发的开发平台的兴起。[大使实验室](https://www.getambassador.io/)有一个[开发者控制平面](https://www.getambassador.io/developer-control-plane/)的相关概念——其网站声称，“使开发者能够控制和配置整个云开发循环，以便更快地发布软件。”

> “Kubernetes 对开发者并不友好。令我震惊的是，我们仍然没有一个好的、可靠的、类似 Heroku 的抽象，它被广泛应用于 Kubernetes 之上。”

—《构建微服务》的作者萨姆·纽曼

大使实验室(Ambassador Labs)开发人员关系总监丹尼尔·布莱恩特(Daniel Bryant)告诉《新堆栈》，“如果你看看 Airbnb、 [Shopify](https://www.shopify.com/) 和 [Lunar](https://tech.lunar.app) 等公司正在做的事情，就会发现它们之间有明显的共性。他们正在为他们的开发人员创建一个类似 Heroku 的 CLI，以便像“创建新的微服务”这样的命令可以搭建一些脚手架，插入 CI，插入管道，插入可观察性。问题是，您向开发人员公开的抽象是什么，以便他们获得所需的可见性，并使他们所需的需求也变得清晰？”

更进一步，Bryant 继续说道，“开发者需要指定某些操作特性:这是一个内存密集型服务；此服务需要低延迟；这个服务需要非常接近那个服务。现在，你可以通过编造库本内特和写大量的 YAML 来做到这一点。这里的抽象并不完全正确，特别是当你引入其他部署机制时，比如[无服务器](https://thenewstack.io/category/serverless/)和[低代码/无代码](https://thenewstack.io/how-low-code-can-help-enterprise-software-development/)。

“我想知道，谁通过平台公开了正确的抽象，然后让工程师们如何打包他们的代码，谁就会胜出——但他们打包代码的方式是一样的，平台公开了一些传统上属于操作属性的属性。”

## 开放式应用模型

关于 Kubernetes 的一些其他倡议值得关注。由[微软和阿里云](https://thenewstack.io/open-application-model-build-the-next-generation-of-cloud-native-applications/)联合创建的[开放应用模型](https://oam.dev) (OAM)是一种描述应用的规范，将应用定义与集群的运营细节分离开来。因此，它使应用程序开发人员能够专注于应用程序的关键元素，而不是部署位置的操作细节。

[交叉平面](https://crossplane.io)是 [OAM](https://thenewstack.io/oam-the-kubernetes-application-model-bridging-development-and-deployment/) 的特定于 Kubernetes 的实现。组织可以使用它来构建和运营跨各种基础架构和云供应商的内部平台即服务(PaaS ),这使得它在多云环境中特别有用，例如那些在大型企业中通过并购越来越常见的环境。

虽然 OAM 试图将部署细节的责任从编写服务代码中分离出来，但服务网格旨在通过专用的基础设施层将服务间通信的责任从单个开发人员身上转移出去，该基础设施层专注于使用代理管理服务间的通信。不幸的是，它们也受到复杂性的困扰，并且还会引入相当大的性能开销。

因此，到目前为止，服务网格在生产中的许多成功实现都是在非常精通技术的初创公司中实现的。在 2020 年 InfoQ 的 Wes Reisz 的[播客中，纽曼建议在选择一个之前等待六个月，他告诉新的堆栈，他仍然给出同样的建议。](https://www.infoq.com/podcasts/monolith-microservices/?)

纽曼说:“就堆栈的重量、管理、影响以及这些东西对性能的影响而言，它们的现实是可怕的。”“有些组织说，如果没有它们，他们就不会有现在的成就， [Monzo 就是一个很好的例子](https://monzo.com/blog/2019/04/03/deploying-envoy-proxy)，在一个拥有异构技术堆栈的组织中，你需要大规模地做类似于共同[传输层安全性]的事情，我可以看到它的价值。但在我看来，这仍然像是“伟大的理念，糟糕的执行”我们可能会说同样的话，但我认为。"

## 隐藏服务网格

有一件事可能会发生，至少对于性能问题不那么严重的企业客户来说，那就是服务网格被推向平台的更深处，并且在很大程度上对开发人员是隐藏的。[红帽 OpenShift](https://www.openshift.com/try?utm_content=inline-mention) ，比如[在幕后整合 Istio】，还有多个类似的举措将服务网格与公共云平台更紧密地整合，比如](https://www.openshift.com/blog/istio-on-openshift-in-2020) [AWS App Mesh](https://aws.amazon.com/app-mesh/?aws-app-mesh-blogs.sort-by=item.additionalFields.createdDate&aws-app-mesh-blogs.sort-order=desc&whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc) 和 [Google 云平台流量总监](https://cloud.google.com/traffic-director)。

也正在进行工作来减少由服务网格引入的网络开销。一些最有前景的是由 [Cilium](https://cilium.io) 团队完成的工作，该团队利用 Linux 内核中的 [eBPF](https://ebpf.io) 功能来实现其所谓的“非常高效的联网、策略执行和负载平衡功能”

> 我认为现在我们需要为我们其余的人进行领域驱动设计。因为即使是普通开发人员，而不是架构师，也需要对如何确定实体和边界的范围有所了解，这很大程度上取决于良好的 API 设计

—Daniel Bryant，大使实验室开发人员关系总监

然而，另一种可能性是，我们可能会完全转移到不同的运行时。[前沿论坛](https://leadingedgeforum.com/)，[的顾问西蒙·沃德利](https://acloudguru.com/blog/engineering/simon-wardley-is-a-big-fan-of-containers-despite-what-you-might-think)认为功能即服务(Faas)/无服务器将最终取代 Kubernetes 成为分布式应用程序事实上的标准运行时，我们正在看到一些现实世界中的生产实例，例如 [BBC](https://www.bbc.com/) ，它已经从以前的 LAMP 堆栈直接转到了[Amazon Web Services](https://aws.amazon.com/?utm_content=inline-mention)上的 Lambda

“我认为 FaaS 是管理部署的一个伟大的抽象，”纽曼说。“作为一个开发人员友好的部署软件的抽象，这是我们自 Heroku 以来最好的东西。我确实认为当前的实现很差，但是他们会改进的。但是他们只是在一个地方处理一件事情的执行。这并没有解决更大网络系统的抽象问题。”

作为一个例子，纽曼引用了微软 Azure 的持久功能，它通过反应式扩展提供了类似于 continuations 的东西，允许开发者在一个无服务器的环境中构建有状态的工作流和功能。但是，尽管部署抽象可能会改进，但想象您可以完全抽象出编写分布式系统的复杂性是幼稚的。

“你不能假设你要与之交谈的东西就在那里，”纽曼说。“你不能假设数据会神奇地瞬间从一个时间点传送到另一个时间点。因为它不是。再多的抽象也无法解决这个根本问题。”

## 自治团队的架构

另一个仍然具有挑战性的领域与整个系统架构有关，以及与团队组织和结构相关的问题。正如 [IBM](https://www.ibm.com/cloud?utm_content=logo-sponsorpage&utm_source=thenewstack&utm_medium=website&utm_campaign=platform) 、[的全球开发者领袖](https://blog.container-solutions.com/cloud-native-is-about-culture-not-containers) [Holly Cummins](https://www.linkedin.com/in/holly-k-cummins) 指出的，“即使有适当的自治团队，系统级的考虑也不会消失。”

Bryant 说，Eric Evans 的[域驱动设计](https://www.amazon.com/gp/product/0321125215/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=0321125215&linkCode=as2&tag=martinfowlerc-20)是微服务运动的基石，任何软件架构师都应该阅读。但是他更进了一步:

“我认为现在我们需要 DDD 为我们其余的人，”他告诉新堆栈。“因为即使是普通的开发人员而不是架构师，也需要对如何确定实体和边界的范围有所了解，这在很大程度上取决于良好的 API 设计。一旦你理解了耦合和内聚的重要性，关注点和边界的分离，你就会自然地投入到你正在处理的任何抽象(模块、类、服务、应用)中。”

即将出版的 Newman 的书《构建微服务》的第二版介绍了许多关于下一代服务的概念。

在更新这本书时，纽曼告诉《新书库》，“我想多谈谈耦合。我想多谈谈凝聚力。我想谈更多关于信息隐藏的内容，这对我来说是一件大事。

“我认为，即使人们理解了分布式系统这一方面，他们也没有理解这样一个事实，即从根本上说，微服务只是模块化架构的一种形式。然而，许多创建微服务的人并不知道什么是模块化架构，也不知道如何实现模块化。”

纽曼的新书还带来了自 2014 年第一版出版以来出现的组织思维的一些变化。他特别引用了马修·斯凯尔顿(Matthew Skelton)和曼努埃尔·派斯(Manuel Pais)关于如何组织业务和技术团队以实现快速流动的极具影响力的作品[团队拓扑](https://teamtopologies.com/book)，以及妮可·福斯格伦(Nicole Forsgren)、杰斯·亨布尔(Jez Humble)和吉恩·金(Gene Kim)的[加速](https://itrevolution.com/accelerate-book/)书，该书探索了精益管理和 DevOps 原则背后的科学。

修订过程不仅揭示了有多少关于微服务的新知识需要分享，还揭示了这些知识是如何不断积累的。

“我想让我的书成为你阅读的书，让你对什么是微服务以及它对软件开发的影响有更广泛的理解，”纽曼说。“我发现我在向人们推荐，哦，你应该看看那本书的第四章。现在我会说这个，而不是那个。我不想在推荐我自己的书时一直模棱两可。这就是我写第二版的原因:因为我希望它又好又准确。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>