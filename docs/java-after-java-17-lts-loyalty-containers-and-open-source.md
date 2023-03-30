# Java 17 之后的 Java:LTS 忠诚、容器和开源

> 原文：<https://thenewstack.io/java-after-java-17-lts-loyalty-containers-and-open-source/>

[](https://www.linkedin.com/in/jemiahsius/)

 [杰迈亚·西乌斯

杰迈亚·西乌斯是 New Relic 的开发人员关系总监，他致力于建立一个与 New Relic 合作的成功开发人员社区。他还是一名全栈工程师，拥有 JavaScript、ES6、Node、React、PHP 等领域知识。工作之外，Jemiah 还是微笑信托管理委员会的成员，在过去的七年里，他帮助这个非营利组织向超过 250，000 人提供健康膳食、衣物和资源。](https://www.linkedin.com/in/jemiahsius/) [](https://www.linkedin.com/in/jemiahsius/)

在当今庞大的软件行业中，任何一个开发人员都不可能完全掌握每一种可用的编程语言。但是，尽管许多开发人员被期望在一个角色中使用多种编码语言，一些核心支柱提供了跨行业和应用程序的广泛实用性。值得注意的是，在 Sun Microsystems 公开发布 Java 年后，它仍然非常受软件开发人员的欢迎。根据[编程语言流行指数](https://pypl.github.io/PYPL.html)，该指数分析了语言教程在谷歌上被搜索的频率，Java 以 18.03%的比例成为世界上第二大流行的编程语言，仅次于 Python。

Java 因其巨大的多功能性而受到开发人员的喜爱，并且易于部署和移植。这种语言是独立于平台的，可以从一个计算机系统平滑地移植到另一个系统。Java 提供了数以千计的库，允许开发人员快速构建新的应用程序并磨练他们的技能，并且它由几十年的文档和聚合的行业知识支持。

为了更好地了解 Java 及其在更大的软件开发生态系统中的作用，New Relic 根据从数百万个提供性能数据的应用程序中收集的匿名信息，发布了 [2022 年 Java 在生态系统中的状态](https://newrelic.com/resources/report/2022-state-of-java-ecosystem) ，。去年 9 月发布了 Java 17，这是该语言自 2018 年 Java 11 以来的第一个长期支持(LTS)版本。自从发布以来，软件开发行业有没有看到任何重大的转变？

## 新宠和不断变化的忠诚度

在过去的两年里，软件开发商已经将很大一部分应用程序转移到 Java 11 上，这证明了 LTS Java 版本的吸引力。虽然截至 2020 年 3 月，绝大多数应用程序运行在 Java 8 上(84.48%)，但现在近一半(48%)的应用程序在生产中使用 Java 11，相比之下，Java 8 中的应用程序为 46.5%。相比较而言，Java 17 还没有确立显著的地位。然而，Java 17 在最初发布后的几个月里已经超越了非 LTS 版本，如 Java 6、Java 10 和 Java 16。

一般来说，与 LTS 版本相比，非 LTS 版本的 Java 采用率极低。虽然一些供应商提供了 Java 非 LTS 版本的补丁，但大多数都没有，这可能导致软件开发人员不愿意发布临时版本。根据 New Relic 的数据，Java 14 是在用的非 LTS Java 版本中最受欢迎的，而 Java 10 和 Java 16 并列垫底。

## Java 的开源进化

15 年前，Sun 宣布 Java 将成为开源软件，这是开源运动中最重要的一步。这个过程从核心 Java 平台开始，但一年后扩展到包括开放 Java 开发工具包(OpenJDK)。随着时间的推移，随着开发人员从 Sun(现在的 Oracle)迁移到其他 JDK 发行版，这种开源运动带来了有趣的发展。

2020 年，甲骨文主导了 Java 市场，大约 75%的用户依赖该公司的 JDK。然而，在过去的两年里，出现了显著的民主化。虽然甲骨文仍然以 34.5%的市场份额领先，但亚马逊的市场份额已经增长到 22%。此外，其他四家厂商占据了至少 5%的市场份额:Eclipse Adoptium (11.5%)、Azul Systems (8.2%)、Red Hat (6%)和 IcedTea (5.4%)。

Java 最初的开放源码使该语言走上了更加用户友好、适应性更强的未来之路。更重要的是，Sun Microsystem 的决定为其他公司提供了一个重要的例子，即开源他们最重要的解决方案，从而产生了重要的开放工具，如 Kubernetes 和 OpenTelemetry。

## 集装箱占据中心舞台

除了 Java，[容器化应用](https://thenewstack.io/ci-cd-devops-and-containers-a-winning-trio/)对云计算的重要性已经显著增长。根据云计算本地计算基金会最近的[年度调查](https://www.cncf.io/reports/cncf-annual-survey-2021/)，93%的受访者目前正在生产中使用或计划使用容器。New Relic 对应用程序数据的分析表明，这种趋势也适用于 Java，因为超过 70%的向 New Relic 报告的 Java 应用程序都是从容器中进行的。

当然，[容器](https://thenewstack.io/containers-microservices-two-peas-devops-pod/)改变了开发者使用计算和内存资源的方式。使用容器的工程师更有可能运行少于四个内核的应用程序，他们也更有可能追求更小的内存设置。开发人员必须意识到这些决定会如何影响其他重要的应用程序，如垃圾收集，因为运行小程序的本能会限制为大环境设计的工具的好处。

Java 是当今软件开发的一个基本元素，这种语言的每一次新的发展都会导致整个行业趋势的更广泛的转变。以 Java 为例，我们可以更好地理解我们最重要的工具和解决方案是如何构建、部署和改进的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>