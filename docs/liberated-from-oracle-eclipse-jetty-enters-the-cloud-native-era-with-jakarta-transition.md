# 随着 Jakarta 的转变，Eclipse Jetty 从 Oracle 中解放出来，进入了云原生时代

> 原文：<https://thenewstack.io/liberated-from-oracle-eclipse-jetty-enters-the-cloud-native-era-with-jakarta-transition/>

web 服务器和 servlet 容器项目 Eclipse Jetty 发布了 [Jetty 11](https://www.eclipse.org/jetty/documentation/jetty-11/programming_guide.php) ，它不仅被认证为与 Jakarta EE 9 Servlet 规范完全兼容，还被移入了`jakarta.*`名称空间，这被 [Eclipse Foundation](https://www.eclipse.org/org/foundation/) 执行总监 [Mike Milinkovich](https://twitter.com/mmilinkov) 视为整个生态系统的一个好迹象。

Milinkovich 在一次采访中说:“Jetty 是 Java 应用程序最优秀、最常用的运行时之一，他们现在采用 Jakarta 名称空间的事实确实有助于加强这样一个信息，即生态系统正在与我们一起移动，我们正在从`Javax.*`名称空间移动到`Jakarta.*`。“这最终是一个关键的支持事实，即生态系统正在跟随我们与 Jakarta 的合作，转向 Jakarta 命名空间，并帮助我们推动大量新的创新，特别是云原生创新。”

随着 2019 年 9 月 Jakarta EE 8 规范的发布，Eclipse Foundation [完成了 Java 企业版(EE)规范从 Oracle 到 Jakarta 的过渡](https://thenewstack.io/java-ee-move-to-eclipse-foundation-makes-way-for-cloud-native-java/)。此后不久，Jakarta EE 9 [引入了“大爆炸”方法](https://eclipse-foundation.blog/2020/12/08/jakarta-ee-9-delivers-the-big-bang/)，其中所有规范 API 都将名称空间改为`jakarta.*`而不是`javax.*`，以便完全脱离 Oracle。米林科维奇解释说，这一举措远远超出了命名的范围，实际上是允许创新，而以前创新是被甲骨文制定的规则扼杀的。

“将 Java EE 引入 Eclipse Foundation 并迁移到 Jakarta E 的主要原因不仅仅是为了保持稳定性，还在于加快创新的步伐。我们在与 Oracle 谈判这一转让时遇到的一个棘手问题是使用`Javax.*`名称空间。最后，我们决定必须想出一个新的名称空间。我们必须把所有这些规范从 Java.x 名称空间移到 Jakarta 名称空间，”Milinkovich 说。“一旦我们做到了这一点，我们现在就可以灵活地开始真正改变这些 API，真正开始创新。只要我们在操作`Javax.*`名称空间，我们就有一组由 Java 社区进程强加给我们的约束，这基本上是一组无法解决的约束。”

尽管 Jetty 在使用上取得了如此突出的地位，但 Milinkovich 指出，它从未能够通过 Java EE servlet 规范的认证，因为“JCP 的规则被认为过于繁琐”，而且“他们必须与 Oracle 签订许可协议，这将有一定的限制。”然而，在 Jakarta EE 下，检查合规性的[技术兼容性工具包](https://en.wikipedia.org/wiki/Technology_Compatibility_Kit)已经开源，加上 Milinkovich 所说的基本上是“零成本许可计划”，该基金会正在重新参与。

“这是 Java 最初成功的一部分，对吗？供应商之间的“一次编写，随处运行”的强大兼容性，这些都是原始 Java 价值主张的一部分。我们看到，围绕 TCKs 的新许可模式和我们作为 Jakarta 的一部分实施的兼容性计划为这一点注入了新的活力。我们已经大大降低了进入门槛，我们真的很高兴看到 Eclipse Jetty 项目有史以来第一次获得全面认证。

除了 Jetty 自己的认证之外，项目负责人还参与了 Jakarta servlet 规范过程本身，Milinkovich 说他看到他们专注于增强规范向前发展。

“这可以追溯到我刚才谈到的‘云本土创新’，”米林科维奇说。“我们真正希望看到的是 servlet 规范本身的新功能，使其在云原生时代变得更加强大和更加相关。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>