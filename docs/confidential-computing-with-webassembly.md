# 使用 WebAssembly 解决机密计算难题

> 原文：<https://thenewstack.io/confidential-computing-with-webassembly/>

德克萨斯州奥斯汀。—回到他们在 [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 、 [Mike Bursell](https://www.linkedin.com/in/mikebursell) 和 [Nathaniel McCallum](https://www.linkedin.com/in/npmccallum/) 工作的时候，他们努力应对机密计算的挑战——在处理组织最敏感的数据时，将它们隔离在一个安全的飞地中。

[机密计算](https://thenewstack.io/confidential-computing-is-transforming-data-encryption-in-healthcare-finance/)对处理敏感、高价值数据的组织特别有用，例如金融机构，但也包括各种各样的组织。

“我们觉得保密计算将会是一个非常大的东西，应该易于使用，”时任红帽公司首席技术官办公室首席安全架构师的伯塞尔说。“与其重写所有的应用程序并学习如何使用机密计算，不如让它变得简单。”

但这并不简单。其中最大的难题是:证明，主机通过这种机制以加密方式测量工作负载，并将测量结果传达给第三方。

“我们面临的一个重大挑战是，所有的认证过程都是不同的，”McCallum 说，他作为虚拟化安全架构师领导了 Red Hat 的机密计算战略。

“机密计算中的所有技术都是不同的。因此，它们都将产生不同的加密缓存，即使它们运行的是相同的底层代码。”

随着越来越多的组织将其工作负载部署到多云和混合环境，这些差异带来了工作负载等效的技术问题。如果一个工作负载被部署到三个不同的架构，使用三种不同的技术运行他们的机密计算，McCallum 问道，“我怎么知道这些都是相同的？”

在 Red Hat，McCallum 和 Bursell 致力于解决这个问题，并启动了一个名为 [Enarx](https://enarx.dev/) 的项目，这是一个在可信执行环境(TEEs)中运行应用程序的开源框架。红帽向 Linux 基金会的机密计算联盟捐赠了 Enarx。

2021 年，总部位于英国剑桥附近的伯塞尔和住在北卡罗来纳州罗利附近的麦卡勒姆共同创立了一家围绕 Enarx 建立的公司 Profian。通过这样做，他们在迅速增长的网络组装领域插上了一面旗帜。

在 6 月份 Linux 基金会的北美开源峰会上，Profian 的两位联合创始人向 New Stack 讲述了他们的项目计划，首席执行官 Bursell 表示，其中包括在本季度发布一个[最小可行产品(MVP)](https://thenewstack.io/building-an-minimum-viable-product-a-founders-guide-to-success/) 。

## Enarx 基于 Wasm 的方法

麦卡勒姆说，证明挑战的解决方案是使用某种字节码，比如 [WebAssembly (Wasm)](https://thenewstack.io/what-is-webassembly-and-why-do-you-need-it/) 。(Profian 的首席技术官 McCallum 在 Red Hat 时是字节码联盟的创始成员；Bursell 是其董事会的董事。)

Wasm 是一种基于堆栈的虚拟机的二进制指令格式，可作为编程语言的可移植编译目标，支持客户端和服务器应用程序在 web 上的部署。

> “WebAssembly 允许您说，我已经创建了一个应用程序，并且我可以证明这正是在所有这些实例上运行的应用程序。密码证明。这是最大的胜利。”

— Mike Bursell，Profian 联合创始人兼首席执行官

WebAssembly 引以为豪的优势——构建一次，随处运行——避免了构建系统来管理在各种部署环境中由各种证明技术生成的所有加密缓存。

Enarx 提供了基于 WebAssembly 的单一运行时 TEE 和证明，允许开发人员使用他们喜欢的语言部署应用程序，如 [Rust](https://thenewstack.io/rust-whats-next-for-the-fast-growing-programming-language/) ，C/C++，C#， [Go](https://thenewstack.io/what-made-golang-so-popular-the-languages-creators-look-back/) ， [Java](https://thenewstack.io/java-adapts-to-cloud-native-computing/) ， [Python](https://thenewstack.io/an-introduction-to-python-for-non-programmers/) ，Haskell 等等。甚至 [COBOL](https://thenewstack.io/u-s-unemployment-surge-highlights-dire-need-for-cobol-skills/) 。

该框架是硬件和云服务提供商中立的；为了保持 Wasm 的承诺“构建一次，在任何地方运行”，开发人员可以跨多个目标透明地部署相同的代码。

“WebAssembly 允许您说，我已经创建了一个应用程序，并且我可以证明这正是在所有这些实例上运行的应用程序。密码证明，”伯塞尔说。

“这是一个巨大的胜利，除了 WebAssembly 允许我们使用完全相同的二进制字节码在英特尔机器、ARM 机器和 AMD 机器上运行，这对我们来说太棒了。”

## 不缺少用例

Enarx 旨在解决的问题非常普遍。

“很难找到没有问题的人，”Bursell 说。“如果您有敏感数据或敏感应用程序，并且受到高度监管、严格审计或只是规避风险，您就不能将某些工作负载放在云中。银行不能，医疗保健、制药、能源、电信、政府、国防、安全——更不用说标准企业了。”

因此，他补充说，这些组织不得不将数据保留在内部，放弃了云的优势。“这意味着不仅仅是维持所有这些的成本。这是因为无法随着业务的发展而快速涌入云并扩大规模。

![Photo of Mike Bursell, CEO of Profian. ](img/4ee96949e5344f694e6c46bc2cb36806.png)

Mike Bursell，Profian 的首席执行官兼联合创始人。

“如果你有了一个新的应用程序，突然每个人都在使用它，你能等五个星期再买一个新的服务器吗？不，你不能；你希望能够把它直接放在云中。”

[机密计算](https://www.profian.com/white-paper-intro-confidential-computing)提供了绝对隐私的承诺，Bursell 指出:“即使是云服务提供商也不能查看或改变你的应用程序或数据。”对于一个不仅要处理敏感客户数据，还要处理专有信息(如金融服务公司的投资算法)的组织来说。

“投行皇冠上的宝石实际上在应用程序中，而不是数据，”他说。

此外，麦卡勒姆说，由于网络越来越分散的性质，通过[边缘和物联网(物联网)](https://thenewstack.io/category/edge-iot/)，新的用例即将出现。

“外围已经没有了，”Profian 的 CTO 说。“如果说过去 15、20 年告诉了我们什么的话，那就是攻击既有外部的，也有内部的。因此，如果您要保护这些东西，即使是在内部，即使是在本地，您仍然需要所有相同的保证。”

## 与芯片制造商关系密切

随着它继续开发 Enarx 并向 MVP 迈进，Profian 与许多科技公司建立了合作伙伴关系，包括 Enarx 项目赞助商 [Equinix](https://metal.equinix.com/?utm_content=inline-mention) 和 PhoenixNAP。它还与芯片制造商 IBM、英特尔、AMD 和 ARM 密切合作。

McCallum 说，Profian 的解决方案要求服务器芯片至少达到 Ice Lake Xeon Scalable 或 AMD Milan Epyc 的水平，主要的云提供商现在正在部署这些芯片。该公司还计划支持 ARM 的第 9 版 CCA 领域和英特尔即将推出的 TDX。

“我们要做的事情之一是允许人们在硬件所在的任何地方部署，”Bursell 说。“选择特定的 CSP 或特定的地理位置可能有特定的原因。但是，无论您是部署在都柏林、旧金山还是上海，您都会得到同样的保证，因为您使用的是同样的芯片，具有同样的加密证明。”

![Photo of Nathaniel McCallum, CTO of Profian](img/85ba9c9a8e8f5cf2b89aa3b15a9e7648.png)

Profian 的联合创始人兼首席技术官纳撒尼尔·麦卡勒姆(Nathaniel McCallum)。

他补充说，因为 Enarx 是基于 WebAssembly 构建的，所以工作负载部署在哪里并不重要。

麦卡勒姆呼应了这一观点。“有些人极度痛苦，他们昨天就需要这种东西，”他说。“他们正在现有的基础设施上进行部署。所以他们专门针对硬件技术进行编码。但是，如果这变得脆弱，你有什么选择来切换到另一种硬件技术呢？

“WebAssembly 给我们的一个关键优势是，如果一个平台上存在硬件漏洞，您不会被淹没。您可以在另一个平台上部署，同时我们与硬件供应商一起创建缓解方案。”

他补充说，随着新平台的出现，如 ARM，“你根本不需要修改你的工作负载，你的工作负载保持不变。突然间，您可以获得新的平台支持。一旦硬件可用，您就可以继续部署，就像您过去一直部署的方式一样。”

## 可以玩的新演示

作为如何向开发人员社区介绍新项目的模型，Bursell 将目光投向 Docker，即平台即服务项目，它允许开发人员快速构建、测试和部署应用程序。

“这些 Docker 中的一个在早期是正确的，只是让人们尝试东西变得非常容易，”他说。“这绝对是我们认为正确的方法。”

因此，Profian 已经[推出了 Enarx](https://try.enarx.dev/) 的演示。“任何人都可以使用它，任何人都可以玩它，”Bursell 说。“因为我们想让它更容易玩。”

> “突然之间，WebAssembly 将非常迅速地成为一个成熟稳定的平台，拥有非常广泛的语言支持。”

Profian 联合创始人兼首席技术官 Nathaniel McCallum

McCallum 说，该演示将允许用户在短时间内部署一个工作负载，而不必设置任何东西:“硬件或内核，所有的云资源，一切都为你设置好了。它给了你一个机会，让你真正地在零摩擦的平台上进行实验。”

Bursell 说，机密计算中调试的简易性将作为演示的一部分展示。他说，Profian 将提供的调试环境将使用相同的环境和 Wasm 运行时。

“你可以在你的 Linux 机器上、Mac 电脑上、Windows 机器上，甚至在 Raspberry Pi 上测试它。因此，您可以对其进行测试，了解您正在运行的内容，然后使用 Profian 将它部署到可信的执行环境中，它仍然可以工作。”

McCallum 说，当它离开浏览器时，WebAssembly 才刚刚开始兑现它的承诺。

“对很多人来说，感觉像是过了很久才来到这里，却从来没有来过，”他说。“但是有很多工作要做。而它发生的方式恰恰不会引起从事这项工作的人的太多注意。因此，突然间，WebAssembly 将迅速成为一个成熟稳定的平台，拥有非常广泛的语言支持。”

*要了解 Wasm 的更多新内容，请查看新堆栈的 Makers 播客的最近一集，这是在 6 月份的北美开源峰会上录制的:*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>