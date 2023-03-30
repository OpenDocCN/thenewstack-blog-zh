# LinkedIn 将 Gradle 构建自动化引入 Python

> 原文：<https://thenewstack.io/linkedins-python-contribution-gives-gradle-added-boost/>

LinkedIn 为 Gradle 新开放的源代码 Python 插件 [{py}gradle](https://github.com/linkedin/pygradle) ，进一步扩展了构建自动化技术的生态系统。

[LinkedIn 在每周执行 30 万次构建的过程中，使用 Gradle](https://www.youtube.com/watch?v=At5X0bamEFI) 来整合 42 种不同编程语言的依赖关系。

它称{py}gradle 是对 [Setuptools](https://pypi.python.org/pypi/setuptools) 的增强，而不是替代，Setuptools 是一个 Python 核心库，用于管理依赖性、编码构建步骤、指定输出分布等。

高级员工软件工程师 Stephen Holsapple 在一篇博客文章中写道，虽然 Setuptools 对于具有少量外部依赖的自包含 Python 应用程序很好，但它并不能完全满足 LinkedIn 的需求。

Gradle 的依赖管理使得它们可以被外部系统和团队探索；允许公司重用元数据中的逻辑进行代码审查、集成测试和部署；并构建涉及多种编程语言的项目。

## 重量级输入

Gradle 的首席营销官 Miko Matsumura 解释说，在过去，构建过程是一项“不起眼”的任务，只需在一台“微型计算机”上编译和链接。

然而，今天的开发人员可能正在使用十几个不同的开源库。

“它的起源是‘我只是想编译这个并让它运行。’但是[那]已经变成一个复杂的上游和下游现象，”松村说。

“跑”到底是什么意思？我希望它在这个容器环境中运行，在这个客户机环境中运行。我希望它能在 iOS 和 Android 中运行，在大屏幕和小屏幕上运行。所以这种“跑”的想法不再是以前的样子了。

“现在，仅仅让它运行就变成了这个集成、自动化和测试的复杂图表——有大量的事情要做，特别是如果你试图实现连续交付，”他说。

总部位于德国的咨询公司 Gradleware 搬到了旧金山，因为它正在获得 LinkedIn 等互联网巨头的青睐，这些巨头正在投入数百万美元开发开源 Gradle 项目的技术。除了 LinkedIn，它还与谷歌、网飞、游戏开发平台 Unity 和其他公司合作。

谷歌在 2013 年让 Gradle 成为 Android 应用的首选构建系统。

如今，Gradle 拥有超过 800 个插件——[LinkedIn 也开源了其 Hadoop 插件](http://siliconangle.com/blog/2015/08/19/linkedin-open-sources-its-groovy-gradle-plugin-for-hadoop/)——并支持包括 Eclipse、Android Studio 和 IntelliJ 在内的 ide 和包括 Jenkins、Chef、Puppet、Docker 和 Ansible 在内的 DevOps 工具。

它处理跨多个存储库类型的可传递依赖，包括 Maven、 [Ivy](http://ant.apache.org/ivy/) 和平面文件。

## Maven 对 Ant 对 Gradle

Gradle 的创始人 [Hans Dockter](https://www.linkedin.com/in/hansdockter?authType=NAME_SEARCH&authToken=G8v9&locale=en_US&srchid=164693751471436944338&srchindex=1&srchtotal=1&trk=vsrp_people_res_name&trkInfo=VSRPsearchId%3A164693751471436944338%2CVSRPtargetId%3A6191941%2CVSRPcmpt%3Aprimary%2CVSRPnm%3Atrue%2CauthType%3ANAME_SEARCH) 在德国创建了基于 [Groovy](http://www.groovy-lang.org/) 的语言，在尝试使用 [Maven](http://maven.apache.org/) 自动构建 XML 任务失败后。他与澳大利亚人亚当·默多克合作创建了这家公司，尽管两人从未谋面。自 2008 年发布 1.0 版本以来，Gradle 一直是开源的。

该公司去年 12 月宣布了来自 Data Collective 和 True Ventures 的 420 万美元的种子资金。

根据对 Java 工具的 ZeroTurnaround 调查，Gradle 还在继续增长，但是到目前为止还没有对 Maven 构成重大挑战。

在其 2014 年的民意调查中，58%的开发人员认为 Gradle 是他们最想了解的技术。然而，在其 2016 年的[报告](https://zeroturnaround.com/rebellabs/java-tools-and-technologies-landscape-2016/)、中，68%的开发者将 Maven 列为他们最常用的构建工具，而 16%的人引用了 Gradle，11%的人说 [Ant](http://ant.apache.org/) ，这是谷歌之前为 Android 选择的工具。

在 2014 年 Maven、Ant 和 Gradle 的零周转比较中，Gradle 在短学习曲线、简单性、社区和文档以及其他因素上胜出。然而，它在构建速度和开发工具集成数量上选择了 Maven，这两个问题 Gradle 一直在解决。

根据 Matsumura 的说法，Ant 和 Gradle 有相似的 DNA。

“Ant 是无限脚本化的。它具有难以置信的灵活性。Maven 不够灵活，但具有超强的声明性表达能力。你可以用 Maven 说一些简单的东西，因为行业惯例，它会解释你的意思，”他说。“Ant 不会对您要做的事情做任何假设。这意味着你必须明确而痛苦地告诉 Ant 你想要发生什么。

“Hans 的领域特定语言结合了 Ant 的灵活性和 Maven 的领域表达能力。当你在 Gradle 中说一些东西时，它非常接近人类可读。你可以用几行代码说一些事情，而在 Ant 中，这需要几千行代码，”他说。

6 月发布的 Gradle 3.0 包括对 Java 9 和 T4 kot Lin 编程语言的支持。

然而，该公司正在超越其 Java 根源。

“我们变得越来越通晓多种语言，”松村说。“我们意识到，只有 Java 或 XYZ 之类的开发商店已经很少了。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>