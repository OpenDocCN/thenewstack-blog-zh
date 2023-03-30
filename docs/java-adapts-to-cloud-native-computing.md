# Java 适应云原生计算

> 原文：<https://thenewstack.io/java-adapts-to-cloud-native-computing/>

虽然 Java 仍然是企业中使用最广泛的编程语言，但它在新兴的云原生生态系统中表现如何？很好，一组研究这种语言的甲骨文工程师评论道。事实上，他们估计目前有超过 5000 万个 Java 虚拟机在云中并发运行。

在最新一期的 New Stack Makers 播客中，我们与 [Georges Saab](https://www.linkedin.com/in/georgessaab/) 讨论了 Java 的现状，他是甲骨文软件开发副总裁，负责 Java 平台组； [Donald Smith](https://www.linkedin.com/in/donaldojdk/?originalSubdomain=ca) ，甲骨文产品管理高级总监；以及甲骨文产品管理高级总监 [Sharat Chander](https://twitter.com/Sharat_Chander) 。TNS 编辑[达里尔·塔夫脱](/author/darryl-taft/)和[约阿布·杰克逊](/author/joab/)主持了对话。

[Java 适应云原生计算](https://thenewstack.simplecast.com/episodes/java-adapts-to-the-cloud-native-computing)

对话中最感兴趣的可能是正在进行的修改 Java 的新举措，以使其更易于使用，对云原生开发者更友好。一个是 Amber 项目，这是一项培育更小的、面向生产力的 Java 语言特性的努力。

“从历史上看，Java，尤其是 Java Enterprise，素有需要大量样板文件的名声。这是我们致力于随着时间的推移以兼容的方式逐渐[减少]的东西，努力使开发人员更容易更有效率，同时确保我们最终得到的 Java 代码仍然是超级可读和可理解的，”Smith 指出。

第二个项目叫做 [Panama](https://openjdk.java.net/projects/panama/) ，旨在促进 Java 和本地语言(如 C++)之间的互操作性。它可以被认为是对 Java 本地接口(JNI)的更新，更安全、性能更好、更易于使用。为了解决可扩展性问题，该公司推出了[项目 Loom](https://cr.openjdk.java.net/~rpressler/loom/Loom-Proposal.html) ，旨在通过部署由 Java 运行时管理的轻量级线程结构，显著降低编写高效并发应用程序的难度。目标是提供一种比当今许多云原生开发人员使用的典型“反应式”模式更简单的编程方式。

因此，“你写的代码可以更好地扩展，你写的代码更简单，更容易理解和推理，更容易监控、管理和调试，”Smith 说。

在硬件方面，有一个 OpenJDK 项目 [Java Valhalla](https://wiki.openjdk.java.net/display/valhalla/Main) ，该项目旨在重新平衡 CPU 能力(在过去几十年中呈指数增长)和内存(容量增长并不明显)之间日益增长的差距。

“我们看到了 CPU 性能的巨大进步。但是我们还没有看到记忆行为的同样变化。因此，我们有这些体系结构，我们在其中做各种各样的技巧，以确保 CPU 可以访问内存，”Smith 说。Valhalla 为开发人员指定更高级的数据类型奠定了基础，这将在机器学习工作中非常有用。

除了这些项目，Oracle 团队还讨论了 Java 新的加速发布节奏、Java 在容器中的使用以及其他主题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>