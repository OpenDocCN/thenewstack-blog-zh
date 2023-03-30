# Log4j 扫描仪盲点

> 原文：<https://thenewstack.io/log4j-scanner-blindspots/>

感谢 [Apache Java 日志库 log4j](https://logging.apache.org/log4j/) 的流行及其隐藏在代码中的能力，由于 [log4j 的](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/) [Log4Shell](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/) [安全漏洞](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/)，我们的基础设施中隐藏着地雷。一天，一小时，没有新的战功爆发。好消息是有扫描工具可以在这些易受攻击的图书馆崩溃之前找到它们。坏消息是， [Rezilion](https://www.rezilion.com/) ，一家编程安全公司，已经发现[没有一个扫描工具可以找到所有安全受损的程序](https://www.rezilion.com/blog/log4j-blindspots-what-your-scanner-is-still-missing/)。

在生产环境中检测打包软件中的 Log4Shell 的问题是，Java 代码可以嵌套到其他文件中几层。一个简单的肤浅的搜索可能会完全错过它。雪上加霜的是，log4j 可以打包成许多不同的格式，如 [Java Archive Files (JARs)](https://docs.oracle.com/javase/8/docs/technotes/guides/jar/jarGuide.html) 、Tape Archive (TAR)、Web Application Archive (WAR)、Enterprise Application Archive(EAR)Service Application Archive(SAR)等等。在这些格式中，受伤的 Java 代码可以被隐藏很多层。挖掘可疑代码真是一场噩梦。

## **使用多种工具**

因此，正如 Rezilion 漏洞研究负责人 [Yotam Perkal](https://www.linkedin.com/in/yotam-perkal/?originalSubdomain=il) 解释的那样，“为了估计行业当前的盲点有多大，Rezilion 的漏洞研究团队进行了一项调查，根据一组打包的 Java 文件评估了多种开源和商业扫描工具，其中 Log4j 以各种格式嵌套和打包。所有格式都是开发人员和 IT 团队常用的。一些扫描仪比其他的要好，但是没有一个能够检测所有的格式。

是的，你读对了最后一行。没有单一的扫描器可以找出问题代码的例子。你唯一的选择是使用多台扫描仪。

虽然 Rezilion 没有查看我在[如何找到危险的 Log4j 库](https://thenewstack.io/how-to-find-dangerous-log4j-libraries/)中提到的所有扫描器，但可以肯定的是，它们中没有一个能找到所有有问题的 lib4j 库。再一次，你需要在你的安全漏洞搜索中使用多个扫描仪。

例如，Rezilion 发现，虽然工具可以检测到具有一系列文件扩展名的多种 Java 二进制文件类型中易受攻击的 Log4j 实例，但有时这些名称正是我们要搜索的。例如，“在 [ElasticSearch](https://www.elastic.co/) 二进制检测评估中，我们检查的 JAR 名称是 elastic-search-sqlcli-7 . 4 . 2 . JAR，这个文件名不符合许多扫描器用来检测 Log4j 的基本识别模式(例如:log4j-core-。jar)，但它仍然包含 Log4j 代码中易受攻击的部分。”

此外，Perkal 继续说，源代码分析有其局限性。“虽然这种方法将有效地检测易受攻击组件的嵌套和打包实例，但它不能应用于打包的第三方软件，后者仍然构成生产中的大部分代码。此外，当涉及到暂时依赖时，它有很大的盲点和误报。”

Rezilion 指出，你还需要“运行时内存中的代码级可见性，其中代码没有打包或嵌套。”此外，Perkal 总结道，“探测能力取决于你的探测方法。扫描仪有盲点。安全领导者不能盲目假设各种开源或商业级工具将能够检测到每一种边缘情况，在 log4j 的情况下，许多地方都有大量的边缘实例。”

## **间接依赖**

除此之外， [log4j 可以被直接依赖调用](https://www.rezilion.com/wp-content/uploads/2021/12/Log4j-Rezilion-Research.pdf)的间接或传递依赖调用。事实上，Rezilion 已经发现大多数受影响的工件源于间接的、可传递的依赖。这意味着在大多数情况下，Log4j 没有被明确定义为工件的依赖项，而是作为一个可传递的依赖项被引入。此外，对于超过 80%的软件包，漏洞比一个级别更深，大多数受到五个级别以下的影响(对于某些软件包，甚至多达九个级别)。”找到这些真的是一场噩梦。

哦，是的，我们都在上周发现了这一点。问题不是“我们在哪里调用 log4j？”而是“我们哪里不用 log4j 了？”

Rezilion 建议使用多种方法来查找和修补易受攻击的代码。当然，该公司也愿意运行一个[免费评估](https://www.rezilion.com/know-if-youre-at-risk-log4j/)来快速检测您是否有未检测到的 Log4j 实例，并确定这些实例是否可被利用并需要立即采取行动。鉴于我们都需要尽可能多的帮助，我会认真考虑这个提议。

祝你好运。现在，如果你不介意，我要回去扫描了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>