# Quarkus 为 Spring Boot 用户提供了一条无服务器的实时编码之路

> 原文：<https://thenewstack.io/quarkus-gives-spring-boot-users-a-path-to-serverless-and-live-coding/>

[](https://www.linkedin.com/in/alhandy/)

 [亚历克斯·汉迪

亚历克斯是红帽公司的技术营销经理。在他之前的生活中，他报道了第一台 iMac 的发布，然后开始了 20 多年的科技记者生涯。他的作品出现在《连线》、《亚特兰大宪法日报》和《奥斯汀美国政治家》上。](https://www.linkedin.com/in/alhandy/) [](https://www.linkedin.com/in/alhandy/)

当你想到无服务器计算、微服务和开放混合云时，有一种语言你可能没有听过云专家们谈论:Java。这是一个真正的耻辱。尽管 Java 目前缺乏吸引力，但它过去是，现在仍然是商业中的主力语言。事实上，根据 Tiobe 指数，英语仍然是世界上第三受欢迎的语言。对于需要一次保持单个应用程序连续运行数年的公司来说，这是首选语言，在这种情况下，即使是一分钟的中断也会造成数百万美元的损失。

然后，世界决定不仅没有必要构建如此复杂的防弹应用程序和运行时，而且实际上偶尔让您的集群让服务器脱机是可取的——只是为了保持混乱的一致性。开放式混合云中的应用不是拥有巨大 CPU 和大量 RAM 的庞大昂贵的服务器，而是可以在任何地方一致地运行:服务器、桌面、边缘系统、虚拟机、公共云以及介于两者之间的任何东西。

事实上，快速启动、小内存占用、无状态和无服务器应用程序的世界似乎已经将传统的(利润丰厚的)单片 Java 应用程序世界抛在了身后。因此，Java 的复杂世界及其各种各样的辅助工具和开源项目在很大程度上被排除在云革命之外。这需要很多聪明的人和工具来改变或重新培训。

这就是为什么 Red Hat 的一个开发团队创建了 Quarkus 项目。2017 年，在研究现代化 Java EE 应用程序的方法时，该团队认为，调整和欺骗 Java 虚拟机(JVM)的无休止的竞赛已经走到了死胡同。随着像 [Azul Systems](https://www.azul.com/) 这样的公司提供 100 核 CPU 和专门设计的 JVM 来处理需要数十亿字节内存的庞大、不间断的 Java 应用程序，围绕垃圾收集和即时编译项目的进一步优化 JVM 的竞赛似乎已经展开并取得了胜利。

相反，羽翼未丰的 Quarkus 团队的排名上升了。他们认为，Quarkus 将彻底改变 Java 的使用方式；它将作为一个框架，而不是 Tomcat 或 WebSphere 的替代品。相反，它将完全重新定义用 Java 开发的意义。此外，当与 Red Hat OpenShift 结合使用时，它可以利用 Kubernetes 作为基础设施提供的众多好处。

## 缓慢起步的新贵

在微服务和无服务器云领域中，Java 面临的最大问题之一是启动 JVM 和应用程序所需的时间。运行 Java 应用程序的大部分工作都是在应用程序启动之前完成的。当您的应用程序应该启动一次并永远运行时，这没什么大不了的，但是当您在这个云原生时代像对待牛而不是宠物一样对待您的应用程序时，启动时间就成了一个真正的问题。当仅仅让应用程序运行就需要 10 秒钟时，您无法按需启动替换服务器。

启动时间是一个很大的问题，目前，只有 [6%的 AWS Lambda 应用程序是用 Java](https://newrelic.com/resources/ebooks/serverless-benchmark-report-aws-lambda-2020) 编写的。当然，你也可以把这归因于 Java 应用程序占用的内存大小。例如，对于一个简单的“Hello World”应用程序，使用 [Spring Boot](https://spring.io/projects/spring-boot) 的 Java 占用超过 100 兆字节。Node.js 应用程序需要大约 40MBs。带有 Quarkus 的 Java 只需要 17MBs 内存。

Quarkus 还提供了使用[Mandrel](https://github.com/graalvm/mandrel)(GraalVM 社区的一部分)本地编译和运行 Java 应用程序的能力，允许所有那些昂贵的前期计算成本在编译时一次性支付。这意味着 Quarkus 应用程序可以像 Go 或 Node 应用程序一样快速跳跃和运行，这在以前对 Java 来说是不可行的。

Red Hat 的技术倡导者 James Falkner 表示，Quarkus 能够在传统 JVM 中运行的同时完成所有这些工作，因为它是一个框架。“你可以在 Hotspot 这样的传统 JVM 上运行它。它仍然是字节码，并且被解释。对于原生编译，我们使用底层 VM；这是一个高度优化的简单 VM，在 VM 中运行你的字节码。没有 JIT，有更简单的垃圾收集。夸尔库斯做出取舍；它不是以牺牲占地面积为代价来最大限度地提高吞吐量。”

Falkner 说，“这是一种非常不同的构建和运行 Java 应用程序的方式。夸库斯已经做了所有的前期工作。本机编译功能可以消除死代码，它会查看所有路径，并消除任何永远不会被采用的路径。它解决了传统上在运行时完成的依赖性、注释扫描和 JAR 文件加载，并在构建时一次性完成。”

对于现有的 Spring Boot 用户，[Red Hat 的首席技术营销经理 Daniel Oh](https://twitter.com/danieloh30) 表示，有一条途径可以迁移到 Quarkus。Quarkus 团队为 Quarkus 提供了 Spring 兼容的 API，允许应用程序快速移植。“如果你在 Quarkus 上使用这个功能，Spring 开发者不需要修改任何代码，只需要导入并运行 Quarkus，”Oh 说。

对于使用 Spring Boot 应用程序的开发人员来说，使用新的迁移工具时，迁移过程变得更加容易。[Migration Toolkit for Applications](https://developers.redhat.com/products/mta/overview)(MTA)是一个工具集，支持跨越[广泛的转换和用例](https://developers.redhat.com/products/mta/use-cases)的大规模 Java 应用程序现代化和迁移项目。它加速应用程序代码分析，支持工作量估算，加速代码迁移，并帮助您将应用程序迁移到云和容器。

当然，仅仅使用 Spring 兼容层并不能让开发者获得 Kubernetes 和 Quarkus 的一些以云为中心的特性，比如单点登录和对捆绑 Kubernetes 特性和触发器的支持。

但是开发人员在使用 Quarkus 进行开发时，仍然可以利用 JVM 中的 Hotspot 特性。Oh 说 Quarkus 给开发者提供了一个现场编码的体验。他们可以在云中运行他们的代码，编辑它，然后快速地将它换到一个正在运行的 Hotspot JVM 上，并立即看到结果，而不是等待漫长的重新部署。

“内循环开发速度快如闪电，”福克纳说。他补充说，Quarkus 还需要“更少的代码来构建相同的应用程序。”最后，当移植到 Quarkus 时，Java 应用程序需要的类总体上更少，节省了 RAM 和开发时间，同时也降低了技术债务。

Red Hat 的应用程序迁移工具包产品经理 Miguel Perez Colino 说,“当你编译成本机时，管理基础设施的人会爱上它。一位用户告诉我，他们来这里是为了速度，他们留下来是为了效率。他们检查夸尔库斯速度的数字，它快如闪电。”

事实上，Quarkus 的好处很多，但不幸的是，它们并不适用于每一个 Java 应用程序。事实上，Quarkus 的一个伟大之处在于，它使现有的企业 Java 开发人员能够回到 Java，开始构建开放的混合云应用程序——就像他们在 go 和 JavaScript 中更酷的表亲一样。

此外，Quarkus 并不是真的打算用来移植现有的必须全天候运行的单一 Java 应用程序。Falkner 说，高度可伸缩的无状态应用程序仍然是使用 Quarkus 构建容器的方法；而传统的单一 Java 应用程序并非如此。

然而，由于许多企业都希望将这些单片应用程序长期迁移到微服务，Falkner 说 Quarkus 是这些迁移的一个很好的目标。虽然应用程序本身可能需要重新设计，需要的不仅仅是重构，但 Quarkus 的速度和性能有助于以更敏捷的速度进行这一旅程，这要归功于它实现的更快的开发人员反馈循环。

正是因为这个原因，[汉莎技术公司在采用该项目时发现了这一点。最终，它能够使用 Quarkus 将 Java EE 工件迁移到云中。Falkner 预计，有一整个宇宙的应用程序，将更好地服务于移动到 Quarkus，而不是重写在一些其他较新的语言。毕竟，有了 Quarkus，Java 终于可以在无服务器的云中翱翔了。](https://quarkus.io/blog/aviatar-experiences-significant-savings/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>