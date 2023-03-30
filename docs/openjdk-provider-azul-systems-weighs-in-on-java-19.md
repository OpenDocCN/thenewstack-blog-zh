# OpenJDK 提供商 Azul Systems 参与 Java 19

> 原文：<https://thenewstack.io/openjdk-provider-azul-systems-weighs-in-on-java-19/>

在[甲骨文](https://developer.oracle.com/?utm_content=inline-mention)最近发布了 [Java 19](https://jdk.java.net/19/) 之后， [Azul Systems](https://www.azul.com/) 的副首席技术官[西蒙·里特](https://www.linkedin.com/in/siritter/?originalSubdomain=uk)会见了新的堆栈，分享了关于该版本(也称为 Java 开发工具包(JDK) 19)的一些技术见解，以及它与旧版本的不同之处。Azul 是 [OpenJDK](https://thenewstack.io/pivotal-throws-its-weight-behind-openjdk-with-spring-runtime/) 项目的主要贡献者，也是 [Zulu OpenJDK](https://www.azul.com/downloads/?package=jdk) 发行版的提供者。

![](img/ba5c16b05f1e24ea20b87d465f9faba3.png)

西蒙·里特

**是什么让 Java 19 区别于它的前辈？**

JDK 19 延续了 Java 平台开发的稳定步伐，这是自切换到基于时间的六个月发布周期以来的第十个版本。与大多数版本一样，这个版本被归类为功能版本，而不是[长期支持(LTS)版本](https://thenewstack.io/java-after-java-17-lts-loyalty-containers-and-open-source/)，这意味着用户不太可能在生产中部署它，除非他们使用系统化的 [CI/CD](https://thenewstack.io/ci-cd-devops-and-containers-a-winning-trio/) 策略，并且可以毫无问题地更改 JDK。

有哪些关键的新功能？

JDK 19(不包括 JEP 422 Linux/RISC-V 端口)包含的所有 JDK 增强提案(JEP)都是预览功能或孵化器模块。这表明它们在成为最终版本之前仍会发生变化。

JDK 19 中的两大 jep 是更大的[项目 Loom](https://blogs.oracle.com/javamagazine/post/going-inside-javas-project-loom-and-virtual-threads) 的一部分，旨在在 Java 中实现更好、更可伸缩的并发。第一部分是 JEP 425，虚拟线程。多个 JVM 线程可以共享一个操作系统线程，而不是将每个 JVM [ [Java 虚拟机](https://thenewstack.io/this-week-in-programming-microsoft-jumps-back-into-java-with-openjdk-build-preview/) ]线程映射到一个操作系统(OS)线程。JVM 负责调度和上下文切换 Java 线程。这在基于 web 的应用程序中非常有用，这些应用程序处理大量长时间空闲的连接(例如，当用户正在做决定时)。许多连接可以共享一个操作系统线程，并且只在需要时使用它，而不是持有一个操作系统线程(数量更有限)。

第二部分是 JEP 428，结构化并发。这旨在通过将在不同线程中运行的多个任务(从相同的父线程中分支出来)视为单个工作单元来简化 Java 并发程序。JEP 428 提供了一种机制，将一个任务分成并发的子任务，这些子任务都返回到同一个地方:任务的代码块。与此相关的一个明显问题是，这与现有的 ForkJoinPool 功能有何不同？ForkJoinPool 旨在处理计算密集型任务，而结构化并发 API 则用于 I/O 密集型任务。

**关于 Java 19，还有什么吸引你的地方？**

在 Java 语言级别，Switch 的模式匹配有了更新。最显著的变化是使用 when，而不是用于保护模式。此外，JEP 405 这次为记录引入了更多的模式匹配。通过匹配记录类型声明，编译器可以处理解构，并且可以直接访问记录的元素。

外来函数和内存(FFAM) API 已从孵化器模块移至预览功能。这是 Project Panama 的一部分，它取代了 Java 原生接口(还为 sun.misc.Unsafe 中的一些功能提供了一个公共 API)。Vector API(不要与 Vector collections 类混淆)已经更新，并提供了与 FFAM API 的更紧密集成。该 API 旨在支持程序员在 CPU 级别控制 SIMD 向量运算的使用。

总之，JDK 19 是另一个对开发者有很大吸引力的版本，并使 Java 平台不断向前发展。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>