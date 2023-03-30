# 谷歌的 Android N 将转移到 OpenJDK

> 原文：<https://thenewstack.io/android-n-will-use-openjdk-implementation-java-apis/>

谷歌移动操作系统的下一个版本——Android N——将很快出现在我们面前，当它到来时，不管它将以什么样的美味命名，它都不会使用谷歌对甲骨文专有 Java APIs 的实现。

当 Ycombinator 黑客新闻论坛[的用户在 Android 代码库上发现“神秘的”git 提交](https://news.ycombinator.com/item?id=10803775)时，经过许多猜测，谷歌已经确认下一版本的 Android 不会将甲骨文的专有 API 实现到 *[VentureBeat](http://venturebeat.com/2015/12/29/google-confirms-next-android-version-wont-use-oracles-proprietary-java-apis/)* 。Android 的下一个版本将使用 Java 标准版的开源实现；OpenJDK。

OpenJDK 是由 Oracle 批准的 Java 平台标准版的免费开源实现。不像现在已经退役的 Apache Harmony 实现——目前大多数 Android 的 Java APIs 都是从它派生出来的——open JDK 是在更严格的 GNU 通用公共许可证下许可的，这意味着任何代码更改或修复都必须反馈给整个社区。自从 Apache Harmony 在未能从 Sun Microsystems 获得技术兼容性工具包许可证后消亡以来，OpenJDK 已经成为许多软件开发领域中事实上的 Java SE 实现。

谷歌想要做出这样的改变有很多原因。谷歌的一位发言人告诉 VentureBeat，他们计划为开发者创建一个公共代码库来开发应用和服务。Google 与 OpenJDK 社区合作并为其做出了贡献；这位发言人说:“作为一个开源平台，Android 是建立在开源社区的协作之上的。”

随着去年 Java 8 的发布，为开发者带来了许多特性，比如 Lambda 表达式。Android 开发人员也将欣赏与 Java 库更好的兼容性，因为许多库开始需要 Java 8。OpenJDK 自 2011 年以来一直是 Java 的官方参考实现，这将使开发人员更容易移植最初为非移动平台编写的代码。正如 VentureBeat 推测的那样，谷歌想要改变甲骨文专有的 Java SE 实现还有另一个原因，即它与甲骨文的法律战。

## 谷歌诉甲骨文

虽然 Android 目前主导着移动设备市场份额，超过 82%的智能手机运行该操作系统，但它也参与了一些重要且代价高昂的战斗。

谷歌面临的一场重要法律战是它对甲骨文 Java APIs 的实施。在 2007 年发布的 Android SDK 中，Android 包含了 Java SE 子集的 Apache Harmony 实现。Apache Harmony 已经退役，Google 已经替换了它一段时间了。

2010 年，甲骨文收购了 Java 语言及其标准库的原始开发者 Sun Microsystems，同年，甲骨文起诉谷歌侵犯版权和专利。法律战仍在继续；预计其最终决定不仅会对甲骨文和谷歌产生巨大影响，还会影响大型科技公司在决定如何开发新软件方面的权力，以及公平使用法和开源许可证在多大程度上保护 API 的使用和实施。

与此同时，随着联邦巡回上诉法院的法院裁决，推翻了早些时候的地区法院裁决，并确认 API 的“结构、序列和组织”是有利于甲骨文的版权保护，谷歌取消其 Java APIs 实现并使用甲骨文认可的 OpenJDK 可能有很大的意义。

不管 Google 使用 OpenJDK Java APIs 实现的原因是什么，使用统一的开源 Java SE 应该对开发人员有好处。Android 操作系统的最终用户几乎肯定不会注意到这一变化，Android N 及其继任者主宰 Android 版本市场份额还需要很长时间，但 Android 和 OpenJDK 的未来值得期待。

特征图片:Unsplash 的“咖啡豆”获得了 [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) 的许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>