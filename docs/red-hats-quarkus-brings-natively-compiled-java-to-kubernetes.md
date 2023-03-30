# Red Hat 的 Quarkus 为 Kubernetes 带来了本地编译的 Java

> 原文：<https://thenewstack.io/red-hats-quarkus-brings-natively-compiled-java-to-kubernetes/>

当每个人都在谈论最新的语言时，很容易忘记 Java 仍然是企业应用程序领域的王者。Java 多年来一直占据大多数语言排行榜的前几名，而且还没有显示出任何移动的迹象，因此，当然，将 Java 引入现代微服务软件架构的努力对许多人来说是令人兴奋的下一步。这正是 Red Hat 去年在 Quarkus 上所做的工作，quar kus 是今年早些时候发布的“Kubernetes 原生 Java 框架”，它将 Java 编译成原生可执行文件，以减少运行时内存需求和启动时间。

在一篇介绍新框架的[博客文章](https://developer.jboss.org/blogs/mark.little/2019/03/07/quarkus-is-here)中， [Red Hat](https://www.redhat.com/en) 工程副总裁 [JBoss Middleware](https://developers.redhat.com/middleware/) 首席技术官 [Mark Little](https://www.linkedin.com/in/mark-little-3545a3/) 强调了 Java 在企业中的主导地位和对 it 的投资是提供更好的 Java 容器化方法的主要原因。

“重要的是要记住，Java 仍然是在后端工作的企业开发人员的头号编程语言，许多组织已经在基于 Java 的开发人员组织和软件上投入了大量的时间和金钱，因为它已经统治了软件领域这么多年，”Little 写道。“因此，随着这些东西向云的过渡，能够继续利用它们对于这个庞大的社区来说非常重要。但是对 Java(性能、运行时内存占用、引导时间等)的关注。)导致一些人重新评估他们对 Java 的投资，并考虑一些新的语言，尽管事实上许多这些语言还没有工具、实用程序等丰富的生态系统。这是 Java 社区多年来建立起来的。”

[https://www.youtube.com/embed/sz1puApRyoE?feature=oembed](https://www.youtube.com/embed/sz1puApRyoE?feature=oembed)

视频

在接受 New Stack 采访时，Little 同意将 Quarkus 称为“框架”可能有点用词不当，但他继续解释了该工具如何将 Java 引入 Kubernetes。

“它不仅仅是一个框架。这个术语用错了。这不仅仅是一个垫片或其他东西上的一薄层，”利特尔说。“有一种叫做 [Graal 和 Substrate](https://medium.com/palantir/first-steps-with-graal-and-substrate-vm-193f8a8bf60e) 的新成果，它允许你将 Java 编译成本地可执行文件，就像你从 C、C++或 Go 中得到的一样。Java 只需构建一次，使用 JVM 就可以在任何地方运行。如果你编译成 native，你就把它扔出窗外了。通常 Kubernetes 管理的容器是基于 Linux 的。编译到 Linux 上并不是一个很大的缺点。它几乎对所有的库伯内特人都有效。你得到的图像要小得多，这对启动时间有很大的影响。对于像无服务器这样的环境，您可能需要进行实时反应，能够根据事件在几毫秒内启动 Java 程序改变了目标。过去，你必须考虑在几秒钟内完成这项工作。”

Quarkus 不仅减少了大小和启动时间，这意味着您可以将更多的 Java 应用程序塞进一个容器中，而且还充当了“万物之间的粘合剂”,例如 Kubernetes 提供的所有服务。虽然 Little 说他想强调原生编译不是必需的，但他也指出 Quarkus 使这比以前容易得多，允许开发人员享受这些其他好处。

“如果你想继续这种一成不变的方式，你必须做出一些改变。我们对 Quarkus 做的事情之一是尝试开发一个工具或核心组件，使开发人员能够拥抱不变性，而不必担心 Graal 和 Substrate 强加给你的底层细节，”Little 说。"如果你尝试不使用夸库，你可以做到，但是很难做对."

[马里奥·富斯科](https://www.linkedin.com/in/mario-fusco-3467213/)，Red Hat 的 [Drools](https://www.drools.org/) 核心开发者，提供了一篇关于他们如何[将一个 13 岁的 Java 项目变成一流的无服务器组件](https://developers.redhat.com/blog/2019/03/14/quarking-drools-how-we-turned-a-13-year-old-java-project-into-a-first-class-serverless-component/)的博文。他在文章中写道，他们的主要目标是“让规则引擎的核心变得更轻、更独立、更易于跨不同平台移植，并且非常适合在容器中运行”，为此他们求助于 GraalVM，最终在 Quarkus 上完成了这项任务。

这个用例举例说明了 Little 提供的场景，这是最初构建 Quarkus 的主要原因。

Little 说:“一些客户已经联系我们，他们正面临着从 Java 转向 Golang 或 Javascript 的压力，因为与 Java 相关的发布可能会很快。“这让他们退后一步，认为启动时间和内存占用可能不是 Java 的问题。他们可以利用他们已经拥有的 15 年 Java 经验，而不是转向一种新的语言。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>