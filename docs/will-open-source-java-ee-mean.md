# 开源 Java EE 意味着什么？

> 原文：<https://thenewstack.io/will-open-source-java-ee-mean/>

当[甲骨文的](http://www.oracle.com)软件布道者，[大卫·德拉巴塞](https://twitter.com/delabassee)通过博客文章宣布甲骨文正在考虑将 Java EE 传递给一个开源基金会时，这个消息引发了一大堆其他方面的坚忍和沉默的声音，他们都在谈论这个早已被遗忘的旧平台的未来。

不到十年前， [Java 企业版](http://www.oracle.com/technetwork/java/javaee/overview/index.html)仍然是大型企业编写和运行 Java 应用程序的主要方式。今天在某种程度上仍然如此。甚至就在四年前，Oracle 设法在 Java EE 7 中发布了该平台的重大更新。现在，Java EE 8 即将在甲骨文全球大会上发布，带来了期待已久的特性，如 JSON 绑定 API、JCache 和对服务器发送事件的支持。

自从 1998 年最初作为 Java 专业版发布以来，Java EE 版本的节奏一直在缓慢下滑。直到版本 1.4，每年都有发布，耗时两年。然后，Java EE 5 (1.5)花了三年才问世，这种模式一直持续到 Java EE 7 的出现。2010 年，甲骨文收购了该技术的原始开发者 Sun Microsystems。现在，在甲骨文的监管下，四年一次的发布似乎成了常态。

前提是甲骨文继续全面监督该项目。然而，Delabassee 的博客帖子似乎表明，这种延长周期可能会被打破。如果甲骨文真的坚持向开源基金会捐赠 Java EE、其参考实现和[测试兼容性工具包](https://jcp.org/en/resources/tdk) (TCK)的想法，它只能改善平台的整体状态，在今天的多云世界中，它在很大程度上被归为遗留平台。

> 外部世界已经远远超越了 Java EE，Java EE 现在有点像一个法律雷区，被认为对于大多数微服务应用程序来说过于庞大。

Java EE 发展缓慢的主要原因可以归咎于 [Java 社区进程](https://www.jcp.org/en/introduction/overview) (JCP)，也可以归咎于 Oracle 本身。多年来，Java 社区进程一直是一个缓慢移动的机构，存在少量的内部结构冲突。当甲骨文接管 JCP 时，其主席 Patrick Curran 承担了一项艰巨的任务，即通过使用现有的结构来批准这些变更，从而修改组织的政策和程序。

发生了一些变化，但作为一个例子，说明这些问题是多么复杂和长期，JCP 仍然没有解决其 TCK 许可问题。这些出现在 10 多年前，当时 Android 刚刚成形。TCK 用于确认 Java 实现的兼容性，谷歌最初的 Android Dalvik 引擎是使用未经 TCK 测试的软件构建的，其中一些来自于 [Apache Harmony](http://harmony.apache.org/) 项目，这是一个由[盖尔·马格努松](https://twitter.com/geirmagnusson)领导的 Java 开源实现。

Harmony 激怒了 Sun Microsystems，在 Oracle 收购 Sun 之前，它也在抱怨 TCK 的限制性许可。该许可证规定，从本质上讲，任何经过测试的实现都只能在服务器或台式计算机上使用。值得注意的是，移动设备、电器和嵌入式系统被排除在外，这确保了为 Java ME(移动版)之外的那些系统实现的 Java 不能说是与主流 Java 官方兼容的。

这些是[甲骨文与谷歌](https://www.eff.org/cases/oracle-v-google)诉讼的根源，该诉讼扩展到了 Java 技术许可的许多其他领域。应该注意的是，虽然 Oracle 在拥有 Sun Microsystems 之前就赞成修改 TCK 许可证，但它现在有很多年的时间来改变措辞，但没有这样做。它还继续就 Java 提起诉讼，并在诉讼过程中赢得了一些裁决，这些裁决可能会给 API 重新实现带来复杂的许可要求，从而威胁到所有的软件。

这就是 JCP 及其进程带来的包袱。Curran 和 JCP 的执行委员会一直致力于开放该流程并引入更多参与者，但外部世界已经远远超出了 Java EE，Java EE 现在有点像一个法律雷区，被认为对大多数微服务应用程序来说过于庞大。

这并不是说不需要更好的 Java EE 和对平台的更多改进。事实上，成千上万的企业应用程序仍然使用 Java EE 作为后端。让这些应用程序更好地与 JSON、JavaScript 和微服务协同工作肯定会有所帮助。

这就是为什么 Red Hat、IBM、Tomitribe 和其他公司合作创建了 [Microprofiles.io](https://microprofile.io/) 。这组 Eclipse 项目旨在使 Java EE 更适合在微服务环境中使用:因为如果一个遗留应用程序可以在它自己的自然环境中转换成微服务，那么对每个相关人员来说事情都会变得更容易。

[红帽](http://www.redhat.com)的高级首席产品经理 John Clingan 说，开源的 Java EE 可以加快这个老化平台的创新步伐。“Java EE 以相对稳定、有分寸的步伐在 JCP 发展。Oracle 已经定义了一个意向声明，并且我们正在执行这个意向声明，以转向开源基金会。它有可能使 Java EE 更加敏捷，按照行业希望的速度响应行业的发展。

当被问及为什么他认为甲骨文现在会做出这一举动时，克林顿说，“我认为这回到了行业变化的本质。如果你看看 Node.js 发生了什么，它就成了一个基金会。从微概要的角度来看，我们决定通过一个基础来做这件事，我认为这似乎是语言运行时或平台的一个自然的决定。现在的趋势是开放它，让他们更加协作。老实说，管理 Java EE 是一个组织的一项相当大的投资，所以我认为他们希望给更广泛的社区参与的机会，”Clingan 说。

“这一切都要回到速度上来,”Clingan 说,“这就是为什么要创建微型文件。”。“我们想做的是更快地将功能交付到开发人员手中，而不是花时间构建一个规范，花数年时间构建，然后在最后交付。我们希望采用一种更加开源的方法。让我们反复定义规范，让开发人员尽早掌握它们，”Clingan 说。

这也说明了 Java EE 生态系统中的一个更大的问题:开发人员的日常速度问题。如果没有持续更新的 Java EE，企业应用程序可能会被最新的革命拒之门外:从容器到微服务。事实上，这就是创建微文件的原因:帮助 Java EE 应用程序适应微服务世界。传统上，Java EE 开发一直很麻烦，需要大量的 XML 和配置，这与 Node.js 等快速移动、轻量级和模块化的系统相反。

在这个问题之后，[项目 Jigsaw](http://openjdk.java.net/projects/jigsaw/) 的 OpenJDK 已经很久了，这是一项模块化 Java 的努力，在 JCP 内一直是争论的焦点，得到了像 Red Hat 和 IBM 这样的主要供应商的反对。争论的焦点是 Java 的核心部分纠缠不清，以及 Jigsaw 的大部分工作一直由甲骨文自己的[马克·莱因霍尔德](https://twitter.com/mreinhold)负责，这一事实可能会给甲骨文的竞争对手留下不好的印象。撇开 Java SE 的问题不谈，Java EE 也可以使用一些模块化和精简功能。

Clingan 说，“Java SE 9 的模块化是一个完全正交的问题。我们必须解决这个问题。Java EE 8 几乎已经发布了，它并没有试图解决模块化的问题。最有可能发生的是，当 Java EE 被移入开源基金会时，我认为更广泛的 Java EE 社区，几十年来参与其中的所有人，无论是[Java EE 守护者](https://javaee-guardians.io/)，Microprofile 人员，还是 EE 开发人员，总的来说，都必须将其定义为开源项目的一部分。”

红帽是新堆栈的赞助商。

由 [Cole Mader](https://unsplash.com/photos/2RKl5pcopIw?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash 上拍摄的特征图像。](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>