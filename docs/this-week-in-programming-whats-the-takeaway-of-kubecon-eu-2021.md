# 本周节目:KubeCon EU 2021 有何收获？

> 原文：<https://thenewstack.io/this-week-in-programming-whats-the-takeaway-of-kubecon-eu-2021/>

大型会议总是会导致人们提出类似“关键外卖是什么？”而本周的[kube con+CloudNativeCon Europe](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)也不例外。当然，这种问题不一定只有一个答案，这当然取决于你问的是谁。你认识的那个为存储供应商工作的家伙不可避免地会开玩笑说，持久存储或类似的东西仍然是 Kubernetes 要解决的最大问题，而服务网格维护者会和你谈论代理上的伟大面板。

在活动开始前，[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)生态系统副总裁 [Cheryl Hung](https://uk.linkedin.com/in/cheryljhung) 在 Tech Beacon 上写了一篇文章，让读者看一看[会议上值得关注的四个云原生趋势](https://techbeacon.com/enterprise-it/4-cloud-native-trends-watch-kubecon-cloudnativecon-europe):物联网和边缘计算、人工智能、GitOps 和系统弹性。Hung 写道:“掌握开发和交付过程的需要成为一个紧迫的问题。”他指出，随着软件交付速度的加快，容器和 Kubernetes 的采用越来越多。

很明显，Hung 在预测她的组织举办的会议的主题方面拥有业内人士的优势，但与会者和演讲者同意吗？

New Stack 特约作者 [Bruce Gain](https://thenewstack.io/author/bruce-gain/) 就是上周出席会议的一位观察员，正如他在题为“ [KubeCon + CloudNativeCon EU 面临巨大的应用交付挑战](https://thenewstack.io/kubecon-cloudnativecon-eu-confronts-the-great-app-delivery-challenge/)的会议总结中所写的那样，他的观点确实与帮助缓解软件交付难题有关

“今天，云计算原生计算基金会的大多数沙盒项目都属于运行时和应用交付的广泛类别，这反映了 DevOps 团队在云原生环境上构建和部署应用程序时，尤其是那些基于 Kubernetes 构建的应用程序时，如何继续寻求改善开发人员和运营体验的方法，”Gain 写道，并指向 CNCF 技术监督委员会主席 [Liz Rice](https://www.cncf.io/spotlights/cncf-community-leader-spotlight-liz-rice/) 的主题演讲。“换句话说，围绕 CNCF 沙盒项目的大多数活动都与改善云原生生产管道的开发人员体验有关，”他后来继续说道。

事实上，Gain 在他的分析中继续讨论了 GitOps、服务网格和代理，但是还能期待什么呢？然而，不同的人会有不同的看法，微软 Azure Confidential Computing 开源项目经理 Aeva Black 在 Twitter 上发表了一篇帖子，得出了截然不同的结论:

他们提供的[概要](https://twitter.com/aevavoom/status/1389894868546166784)不是应用交付或 GitOps，而是该活动最重要的专题讨论小组专注于网络安全和影响隐私和安全的事情，并指出“#多样性也是#安全问题！”

说了这么多，你这次从 KubeCon 学到了什么？

## 本周的节目中

*   **AWS 介绍 CloudFront 功能:**在边缘上交付功能最近似乎很流行，本周[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)随着[介绍 CloudFront 功能](https://aws.amazon.com/blogs/aws/introducing-cloudfront-functions-run-your-code-at-the-edge-with-low-latency-at-any-scale)也来凑热闹。AWS 已经提供了 [Lambda@Edge](https://aws.amazon.com/lambda/edge/) ，这是它[在 2017 年推出的](https://aws.amazon.com/blogs/aws/coming-soon-lambda-at-the-edge/)用于无服务器边缘计算，以解决复杂的用例。现在，该公司正在推出 [CloudFront Functions](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/cloudfront-functions.html) 来解决一组不同的用例:“可以由非常短命的函数执行的简单 HTTP(s)请求/响应操作。”CloudFront Functions 让您能够以大约 1/6 Lambda @ Edge 的价格在 [218+ CloudFront edge 位置](https://aws.amazon.com/cloudfront/features/#Global_Edge_Network)运行轻量级 JavaScript 代码，以快速处理请求，例如重写 A/B 测试的 URL、操纵 HTTP 头等等。如果 CloudFront 函数不够用，也不用担心，因为 Lambda@Edge 可以根据需要在之前和之后被触发来处理额外的工作。要获得关于这两者明显不同的表格，请阅读[博客文章](https://aws.amazon.com/blogs/aws/introducing-cloudfront-functions-run-your-code-at-the-edge-with-low-latency-at-any-scale)并查看文档，了解如何[开始使用 CloudFront 函数在应用程序边缘添加定制逻辑。](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/cloudfront-functions.html)

*   **亚马逊处理金融服务数据:**并非所有数据都是生而平等的，对于金融数据来说更是如此，与其他形式的敏感数据一样，金融数据也受到监管，通常被归入组织的孤岛中。对于那些处理金融数据的人来说，你可能会兴奋地听说[亚马逊通过](https://aws.amazon.com/blogs/aws/amazon-finspace-simplifies-data-management-and-analytics-for-financial-services/)[亚马逊 FinSpace](https://aws.amazon.com/finspace) 进入这个领域，这是一个数据管理和分析解决方案，它说“将查找和准备数据的时间从几个月减少到几分钟，以便分析师可以花更多时间进行分析。”正如你可能知道的那样，数据准备工作经常落在你身上，亚马逊 FinSpace 建议通过自动化查找数据和准备数据进行分析的步骤，消除“存储、准备、管理和审计数据访问所需的无差别繁重工作”，从而提供帮助。FinSpace 为时间序列数据提供了一个内置的 100 多个函数的库，提供了集成的 Jupyter 笔记本，并提供了一个管理数据访问的框架，以审计谁在何时访问了什么数据。

*   **Kotlin 1.5.0 如期而至:**或者更确切地说，我们应该说，根据 2020 年 10 月宣布的[新发布时间表](https://blog.jetbrains.com/kotlin/2020/10/new-release-cadence-for-kotlin-and-the-intellij-kotlin-plugin/)，2021 年 Kotlin 的第一个大版本已经到来，这表明新的 kot Lin 版本每六个月发布一次，而不是在新功能准备就绪时发布。虽然这是真的，但 Kotlin 1.5.0 还附带了一系列[稳定的语言特性](https://blog.jetbrains.com/kotlin/2021/05/kotlin-1-5-0-released/#stable-language-features)，如 JVM 记录、密封接口、内联类，并包括[新的默认 JVM IR 编译器](https://blog.jetbrains.com/kotlin/2021/05/kotlin-1-5-0-released/#kotlin-jvm)，将 [Kotlin 1.4.30](https://blog.jetbrains.com/kotlin/2021/02/new-language-features-preview-in-kotlin-1-4-30/) 中预览的许多特性带到了 stable。有关更多详细信息，请查看关于 Kotlin 1.5.0 新特性的[深度探讨](https://kotlinlang.org/docs/whatsnew15.html)，或者，如果您有任何疑问，在 5 月 25 日 Kotlin 1.5 在线活动期间将会有一个现场问答。
*   **Rust 提供了一个更新:**Rust 核心团队[提供了一个更新](https://blog.rust-lang.org/inside-rust/2021/05/04/core-team-update.html)关于该语言的现状，超越了你最近听说的整个 Rust 基础。首先，核心团队在今年早些时候通过了 [2021 路线图](https://github.com/rust-lang/rfcs/pull/3037)，为核心团队设定了今年的目标。路线图聚焦于“项目健康，特别是因为它与 Rust 的治理结构相关”，其中一部分是让每个团队创建一个正式的章程，这似乎正在进行中。核心团队承担的另一个项目是对 crates.io 上的包进行审计，“确保它们是项目应该拥有的东西，确保它们有适当的权限，确保它们有人照顾它们，所有这类事情。”澄清 RFC 的这一特殊努力是“努力对这些板条箱进行分类并引入一项政策以一致地传达其存在理由和保证”的一部分。“如果你喜欢读 Rust 的书，那么本周你会读到 Rust 最不为人知的贡献者:戴夫·赫尔曼。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>