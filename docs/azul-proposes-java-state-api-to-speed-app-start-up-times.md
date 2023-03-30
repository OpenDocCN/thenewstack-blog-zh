# Azul 提出 Java State API 来加快应用启动时间

> 原文：<https://thenewstack.io/azul-proposes-java-state-api-to-speed-app-start-up-times/>

Java 平台提供商 Azul 提出了一种新的 API，通过保存运行时的状态来帮助开发人员避开 Java 应用程序漫长的启动和预热时间。

[Anton Kozlov](https://github.com/AntonKozlov) ，[Azul 的软件工程师](https://mail.openjdk.java.net/pipermail/discuss/2021-July/005862.html)向 [OpenJDK](https://thenewstack.io/microsoft-openjdk-goes-ga-at-build/) 社区提出了一个名为[检查点协调恢复(CRaC)](https://github.com/crac) 的新 API。根据甲骨文 Java 平台集团的说法，Azul 最初在 2019 年提出了 CRaC，并在本周重新提出了提案。

“Java 应用程序可以通过保存 Java 运行时的状态(快照、检查点)来避免长时间的启动和预热，”Kozlov 写道。然后，保存的状态用于快速启动实例(恢复)。但是在保存状态之后，执行环境可能会改变。此外，如果多个实例同时从保存的状态启动，它们应该获得一些唯一性，并且它们的执行应该在某个点分开。”

Kozlov 补充说，解决这些问题的一个实用方法是让 Java 应用程序知道状态何时被保存和恢复。然后应用程序将能够处理环境变化，他说。

“OpenJDK 是 Java 平台标准版创新的地方，”甲骨文 Java 平台集团在一份声明中说。“这个提议在 [2019 JVM 语言峰会](https://openjdk.java.net/projects/mlvm/summit2019/)上进行了讨论和提交，我们欢迎看到更多的进展，它可能是 OpenJDK 的一个项目。”

Azul 的首席技术官 Gil Tene 表示，该公司还没有针对这种 API 和功能的特定 Java 版本。Azul 希望在 JDK 增强提案(JEP)流程和一个项目中开发 CRaC，并提议将其包含在一些未来的 OpenJDK 和 Java SE 版本中。

> CRaC 是“Java 需要增加其在云原生世界中的相关性的特性类型。”——Eclipse 基金会的迈克·米林科维奇

“这显然不会在 17 年，希望能在接下来的某个版本中出现，”Tene 说。考虑到这种东西成熟通常需要的时间，Azul 预计不会早于 19 或 20，“可能会更长，”他说。

T2 Eclipse 基金会 T3 的执行董事 Mike Milinkovich 说他对具体的技术提议没有任何评论，该基金会是基于 Java 的 T4 Eclipse IDE T5 以及其他开发者工具的管理者。“然而，这是 Java 需要增加其在云原生世界中的相关性的特性类型。我希望 OpenJDK 社区将此视为推动 Java 平台创新的机会，”他说。

CRaC 项目的目标是提供一个 Java API，用于应用程序和运行时之间的协调，以保存和恢复状态，”Kozlov 写道。

“运行时应该支持多种方式保存状态:虚拟机快照、容器快照、 [CRIU 项目](https://criu.org/Main_Page)Linux 等。，”他说。“我们希望推出一个对任何底层机制都足够通用的 API。我们还计划探索 API 和运行时中的安全检查，如果状态可能无法恢复或在恢复后无法正常工作，这些检查会阻止保存状态。”

Constellation Research 的分析师 Holger Mueller 说:[事实上，让开发者生活更好的工具总是受欢迎的。](https://www.linkedin.com/in/holgermueller/)

“看到让开发者生活更好的创新总是好的，最近这个领域发生了很多事情，这很好，”他说。“由于开发速度是构建更好更快的下一代应用的关键，开发工具启动时间和重新寻找工作一直是生产力的消耗。因此，很高兴看到有人提议帮助 Java 开发人员获得一个关于改变开发人员工作未来的有状态 IDE。”

与此同时，科兹洛夫提议他成为 CRaC 项目的项目负责人，他说，“JDK 的分叉将是这个项目的起点”。

然而，分叉并不是一个不好的“分叉”，它只是意味着它将拥有自己独立于主线的构建，就像甲骨文的 [Valhalla](https://openjdk.java.net/projects/valhalla/) 和 [Panama](https://openjdk.java.net/projects/panama/) Java 项目一样，例如，甲骨文 Java 平台集团说。

在去年给 OpenJDK 维护者的一篇帖子中， [Tene 写道](https://mail.openjdk.java.net/pipermail/discuss/2020-September/005594.html):“在 Java 领域，我们的目标是创建一个通用的 CRaC API，它将允许应用程序和/或应用程序框架与任意的检查点/恢复机制相协调，而不依赖于特定的实现或实现检查点和恢复的操作方法。这样的 API 将允许应用程序框架(例如， [Tomcat](https://tomcat.apache.org/) ， [Quarkus](https://thenewstack.io/quarkus-gives-spring-boot-users-a-path-to-serverless-and-live-coding/) ， [Micronaut](https://micronaut.io/) 等)。)以可移植的方式执行所需的协调，这将不需要特定于检查点/恢复机制的编码。”

在同一篇帖子中，Tene 说 Azul 希望启动一个项目，专注于指定 CRaC API，并提供至少一个支持 CRaC 的检查点/恢复 OpenJDK 实现，希望最终通过相关的 jep 在未来的 OpenJDK 版本中上游包含。

“我们可能希望在未来的 Java SE 规范中也包含这个 API，”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>