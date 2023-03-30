# 2023 年 OpenJDK 导航指南

> 原文：<https://thenewstack.io/your-guide-to-navigating-openjdk-in-2023/>

当 Java 第一次被创造出来为一个遥控器编程时，有一天它可能成为许多世界范围的企业的商业基础的想法甚至没有出现在白板上。然而今天，全球 80%的企业都在使用 Java，全球有 30 亿个活跃的 JVM 和 1200 万开发人员在开发应用程序。

遗憾的是，对于开发团队和他们的操作人员来说，跟上 Java 的最新发展是一件困难的事情。如果仅仅是为了确保组织中的每个人都在使用相同版本和实现的语言，那么在构建您的 [Java 架构](https://thenewstack.io/openjdk-provider-azul-systems-weighs-in-on-java-19/)时使用一个供应商通常是明智的。当然，服务、支持、及时的安全补丁和错误修复是标准化之外的额外收获。

幸运的是，对于 Java 社区来说，Java 本身是开源的，并在通用公共许可证(GPL)下作为 OpenJDK 发布。这意味着它是由对 Java 技术进步感兴趣的开发人员和供应商社区编写和构建的。然而，像任何编程语言一样，在该平台近 30 年的历史中，积累了许多可移动的部分，这意味着很难保持所有软件保持一致并保持最新。

自 OpenJDK 成立以来，Red Hat 一直参与其中，我们很高兴看到社区的发展，其中一个项目就是围绕着平台的编译版本。虽然 [IcedTea](https://adoptopenjdk.net/icedtea-web.html) 是开源社区提供的 Java 8 Web Profile 版本，但是 Java 已经从那些早期的发行版走了很长的路。

随着时间的推移，Eclipse 基金会将这项工作发展成了 [Adoptium 工作组](https://adoptium.net/)。今天，OpenJDK 构建可以从这个工作组免费获得，名称是 [Temurin](https://projects.eclipse.org/projects/adoptium.temurin) 。Temurin 项目和 Adoptium 工作组的目标不仅是提供 OpenJDK 的二进制文件，而且是广泛测试与它们相关的代码。

Adoptium 工作组联合了 Red Hat、微软、亚马逊、谷歌和整个社区的努力，不仅产生了 Temurin，还产生了 [AQAvit 项目](https://projects.eclipse.org/projects/adoptium.aqavit)。AQAvit 提供了超过 350，000 个测试的集合，这些测试超越了已经用于证明 Java 实现符合性的 Java 测试兼容性工具包测试。

AQAvit 旨在测试真实世界的利用模式和需求，其设计非常一般化，可以作为一套安全性和持久性测试集成到传统的 Java 应用程序工作流中。

Red Hat 还通过它的许多产品和渠道提供对 OpenJDK 的直接支持。例如，如果您订阅了 Red Hat Enterprise Linux，那么您已经获得了 OpenJDK 支持。如果你付费使用你的云提供商提供的 RHEL 版本，那也包括 OpenJDK 支持。

如果你正在寻找使你的 Java 应用程序现代化的方法，并且你正在寻找减轻你的 Java 应用服务器所承受的负载，那么 [Quarkus 项目](https://quarkus.io/)已经承担了将 Java 引入容器和 Kubernetes 的任务。Quarkus 为 Java 带来了一些更具创造性的特性，这些特性对于开发人员构建高度可伸缩的云应用程序特别有用。

例如，传统的 Java 应用程序是长时间运行的整体；因此，启动时间不是优化的一个非常重要的方面。但是基于容器的应用程序会不断地启动和停止以满足扩展需求，并且在不使用时可以节省资金。因此，Quarkus 为应用程序提供了非常快的启动时间。这还有一个额外的好处，就是缩短了开发人员查看代码更改结果的反馈循环。

尽管今天许多 Java 应用程序被认为是半遗留的，但这并不意味着没有很多令人兴奋的创新正在发生。Java 整体上的一个重大改进是 Java 飞行记录器(JFR ),它允许在不需要任何修改的情况下监控和分析 Java 应用程序。

然而，缩放 JFR 有一些问题，尤其是在处理飞行中的记录方面。为了帮助缓解这些问题，红帽赞助了[低温恒温器项目](https://cryostat.io/)的创建。Cryostat 安全地管理您的集装箱化工作负载的 JFR 记录。

在 Java 生态系统的其他地方， [GraalVM](https://www.graalvm.org/) 继续发展和成熟。由于具有调试、监控和分析功能，这种高级优化编译器可以使开发过程变得更容易、更高效。而且不仅仅局限于 Java，GraalVM 还支持 R、Python 和 c，红帽有自己的 GraalVM 发行版称为 [Mandrel](https://github.com/graalvm/mandrel) 。

虽然我们多年来一直致力于在上游社区和我们自己的产品中支持和更新 Java，但我们也非常关注该语言的未来和下一代 Java 应用程序。

我们也为此贡献了时间和代码。例如，Shenandoah 垃圾收集器是我们有兴趣推进的一个上游项目。Red Hat 也为 OpenJDK 到 64 位 ARM 的[移植做出了贡献。这个低暂停](https://developers.redhat.com/blog/2021/02/01/how-red-hat-ported-openjdk-to-64-bit-arm-a-community-history#)[垃圾收集器](https://thenewstack.io/generational-shenandoah-offers-java-a-better-way-to-collect-garbage/)旨在使任务更加可预测和一致。无论是处理 200 GB 还是 2 GB 的堆，这个新项目都需要相同的暂停时间。这里的最终目标是将暂停时间与堆大小分开。

我们还在为收藏和小人国项目开发持久内存支持。后一个项目旨在将 hotspot JVM 中的 Java 对象头从 128 位减少到 64 位。这将减少 JVM 的内存占用，并提高 Java 的整体性能。

当然，现代化 Java 应用程序的最大吸引力之一是云的吸引力。将您的 Java 应用程序引入云中对于您的开发人员和 IT 团队来说都是一次变革性的体验。Quarkus 可以帮助迁移，但是 Red Hat 也提供了[迁移工具](https://developers.redhat.com/products/mta/overview)来帮助迁移过程。

无论您决定如何将您的 Java 生态系统带到云中，相同的一般步骤都有助于这种转变。首先，您需要清点所有的 Java 系统。然后你会想确定你最有价值的候选人。理想情况下，当您已经确定了一个好的 Java 应用程序候选对象时，您就可以将它作为其余应用程序的模型。

虽然 Java 有着丰富而辉煌的历史，但它也有着光明的未来。曾经争夺对平台和服务器整体控制权的同一批公司如今携手合作，增强其功能和可靠性。Java 现在比以往任何时候都更加强大，抓住这些改进是为您的应用程序指明前进道路的最佳方式。

要了解更多关于 Red Hat 对 Java 的贡献，请访问我们的“ [All Things Java](https://developers.redhat.com/java) ”页面。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>