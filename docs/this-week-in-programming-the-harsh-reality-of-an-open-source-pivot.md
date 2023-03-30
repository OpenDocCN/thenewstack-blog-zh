# 本周编程:开源支点的残酷现实

> 原文：<https://thenewstack.io/this-week-in-programming-the-harsh-reality-of-an-open-source-pivot/>

本周， [Sourcetrail](https://www.sourcetrail.com/) ，一个更容易探索和理解新代码库的工具，[的团队决定放弃商业上可行的 ghost](https://www.sourcetrail.com/blog/open_source/) 和[向大众免费提供开源项目](https://github.com/CoatiSoftware/Sourcetrail)。这一决定来自一些他们无法再否认的简单事实，其中最大的事实是“对于一个小公司来说，销售一种产品，其假定价值并不立即为每个用户所清楚，这是一个相当大的劣势。”事实证明，虽然他们认为他们有一个所有开发人员都想要的有用工具，但它的效用并没有立即显现给所有他们原本希望成为客户的人。此外，他们写道，开发人员已经习惯了免费工具。

“许多开发工具都是免费的。这是一件伟大的事情:这意味着构建软件不会受到付费墙的限制。让我们诚实地面对这一点，这也意味着我们作为软件开发人员更愿意评估和使用免费的替代方案，而不是商业工具。”

他们陈述的其他挑战——无法扩展、缺乏语言支持、缺乏对通用工具的支持以及跨平台兼容性——是任何以前关闭过技术项目的人可能都太熟悉的要点。他们没有像其他人所说的那样对许可证进行调整或收取更多费用，而是决定放弃商业许可证，全力以赴使用病毒性 GNU 通用公共许可证，并希望至少通过消除开发者不使用 Sourcetrail 的金钱和管理原因，他们可能会获得一些有意义的采用。对于那些想知道开源软件的一些好处的人来说，该团队的开源决定读起来像一个案例研究:

“如果我们取消商业许可，任何开发者都可以开始使用 Sourcetrail，而无需接受条款、花钱或说服管理层。此外，满意的用户可能更少保留向其他开发者推荐 Sourcetrail。它将允许每个有问题阻止他或她在期望的代码库上使用 Sourcetrail 的人来解决这个问题。从过去使用开源代码编辑器插件的经验来看，我们知道人们随机插话、提出改进建议、讨论问题甚至解决问题是多么的棒。通常，他们的背景与我们不同，因此他们拥有我们无法提供的专业知识。”

如果 [Codefresh 的 1 亿美元开源基金](https://codefresh.io/codefresh-news/lets-get-100m-serious-about-open-source/)真的包括开源项目的资金([而不是“软件信用”](https://www.theregister.co.uk/2019/11/21/codefresh/))，Sourcetrail 可能会很好，但相反，该团队写道，他们希望通过 [Patreon 支持者](https://www.patreon.com/sourcetrail)自筹资金继续该项目的工作。他们写道:“唯一困扰我们的是，如果没有人有时间积极维护开源项目，它们通常会衰退。”

在撰写本文时，他们希望每月收到的最低 1500 美元中，有 99 美元已经到了。

## 本周的节目中

*   **脸书与微软合作开发 Visual Studio 代码:**我们知道你有多喜欢 Visual Studio 代码，所以你可能会对[脸书和微软合作远程开发](https://developers.facebook.com/blog/post/2019/11/19/facebook-microsoft-partnering-remote-development/)的消息感到兴奋(或畏缩)，脸书说它将切换到 [Visual Studio 代码](https://code.visualstudio.com/)作为脸书的默认开发环境。随着这一变化，该公司表示，它还将与微软合作，帮助增强他们的[远程开发扩展](https://code.visualstudio.com/docs/remote/remote-overview)，以帮助提供“大规模远程开发”显然，这种转变很久以前就已经开始了，Visual Studio 代码在“测试版”中被广泛使用，现在脸书说“Visual Studio 代码现在是脸书未来发展的一个既定部分。”希望这对您最喜欢的 IDE 来说是个好消息。
*   **Rust 开始关注 GitHub 动作:**虽然 Rust 可能刚刚迁移到 Azure Pipelines，但该团队现在写道，它正在[评估 GitHub 动作](https://blog.rust-lang.org/inside-rust/2019/11/14/evaluating-github-actions.html)，并附言承认“我们对 Pipelines 作为一个产品感到满意，但微软和 GitHub 都要求我们尝试 GitHub 动作，因为它更紧密地集成到我们已经使用的 GitHub 工作流中。”毕竟，当微软拥有这一切时，并不存在真正的竞争。Rust 正在寻找 GitHub Actions 来取代 Azure Pipelines 作为 [rust-lang/rust](https://github.com/rust-lang/rust) 库的 CI 提供者，并且自从 GitHub Actions 首次宣布以来，它一直是其 beta 版的一部分。为什么？基本上，它与 GitHub 连接得非常好，在那里它存储了所有的代码。到目前为止，该团队写道，他们“在初步测试中实现了 60%的构建速度，这要归功于专用构建器池中内核数量的增加，而且还有很大的空间来并行化和更快地完成构建。”

*   去听吧，地鼠们！现在是时候通过填写 [2019 Go 开发者调查](https://blog.golang.org/survey2019)来表达你的观点了(不是说你还没有),该调查是最新的，准备好了，直到 12 月 15 日。因此，如果你对你最喜欢的后端语言有想法(我们知道，你有)，请确保继续并[填写 2019 年 Go 开发者调查](https://google.qualtrics.com/jfe/form/SV_b1xqnBCMpZAhJZ3)。Go 团队写道，以前的调查(其中有三个)已经“在推动我们的语言、生态系统和社区的变化方面发挥了巨大的作用，包括[gopls 语言服务器](https://about.sourcegraph.com/go/gophercon-2019-go-pls-stop-breaking-my-editor)，新的[错误处理机制](https://blog.golang.org/go1.13-errors)，模块镜像[等等”，所以不要落后。如果你感兴趣，这里有前三年调查的](https://blog.golang.org/module-mirror-launch)[结果](https://blog.golang.org/survey2018-results)。
*   **微软为 AKS 带来保密计算:**对于那些在微软的 [Azure Kubernetes 服务](https://azure.microsoft.com/en-us/services/kubernetes-service/)上开发的人来说，你现在可以利用该公司新提供的在 Kubernetes 上的[保密计算，它甚至在代码运行时保护数据，而不仅仅是在数据静止时。要使用该功能，您只需](https://azure.microsoft.com/blog/bringing-confidential-computing-to-kubernetes/)[在支持 SGX 的硬件上创建一个 Kubernetes 集群](https://github.com/Azure/aks-engine/blob/master/docs/topics/sgx.md)，例如运行 Ubuntu 16.04 或 Ubuntu 18.04 的 [DC 系列虚拟机](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/sizes-general#dc-series)，并将机密计算设备插件安装到这些虚拟机中。这一消息是在 Linux 基金会下的[机密计算联盟](https://thenewstack.io/linux-foundation-forms-the-confidential-computing-consortium-to-protect-data-in-use/)[最近推出](https://confidentialcomputing.io/)之后发布的，现在该联盟通过 [Kubernetes with Azure](https://aka.ms/aks-engine-open-enclave) 使该功能易于应用。
*   Kotlin 是目前 Android 开发的一流语言，本周 Kotlin 的世界有一些更新，包括 Kotlin 1.3.60 的[发布](https://blog.jetbrains.com/kotlin/2019/11/kotlin-1-3-60-released/)，Kotlin 1.4 的一些细节，以及由谷歌和 Udacity 共同推出的用于学习高级应用开发技能的新课程[。JaxEnter 对 Kotlin 1.3.60](http://android-developers.googleblog.com/2019/11/new-learn-advanced-skills-for.html) 的新特性进行了总结，部分集中在 Kotlin 是 Android 应用程序开发中比 Java 更受欢迎且越来越多地被采用的语言这一事实上。因此，他们写道“新的默认转换器使得转换到 Kotlin 更加容易。1.3.60 修复了一些以前的转换问题，包括角壳问题。”关于其他新特性的细节，请查看这篇文章，但要知道这是一个小版本，所以没什么大不了的。至于 Kotlin 1.4，NPE 断言，允许“when”中的“break”和“continue”，以及尾部递归函数的修复和更改是值得期待的。与此同时，PacktPub 指出，Kotlin 1.3.60 提供了 [Kotlin 工作表和对新 Kotlin/Native 目标和其他更新的支持](https://hub.packtpub.com/kotlin-1-3-60-released-kotlin-worksheets-support-kotlin-native-targets/)，以及 IntelliJ IDEA 和 Kotlin Eclipse IDE 插件更新。

来自 Pixabay 的 enriquelopezgarre 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>