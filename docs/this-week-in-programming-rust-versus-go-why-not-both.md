# 本周编程:Rust vs . Go？为什么不能两者兼得！

> 原文：<https://thenewstack.io/this-week-in-programming-rust-versus-go-why-not-both/>

在过去的一周里，许多开发人员花时间做了一件似乎十分之九的开发人员都喜欢的事情:辩论为什么一种语言比另一种语言更好。(下面是 10 个选项中最不受欢迎的一个。)

在本周的“一种语言或另一种语言”中，我们有一个来自 RedisLabs 的开发者倡导者[洛里斯·克罗](https://twitter.com/croloris)的条目，他提出了一个场景，你在 Go 中写了一些东西，然后有人问了一个不可避免的，“令人不寒而栗”的问题——“[为什么 Go 不生锈？](https://kristoff.it/blog/why-go-and-not-rust/)”

以免你认为这是一个围棋爱好者的独特攻击，Cro 立即指出了这两种语言之间的相似之处，并提供了 Rust 胜出的几点:

*Rust 和 Go 的[消息传递](https://courses.lumenlearning.com/ivytech-mktg101-master/chapter/reading-defining-the-message/)重叠。*

*走的快，锈的更快。*

*Go 有高效的垃圾收集器，Rust 有静态内存管理。*

*Go 有很好的并发支持，但是 Rust 有可证明正确的并发。*

*Go 有接口，Rust 却有特质等零成本的抽象。*

尽管如此，Cro 写道，Go 是一种非常适合编写服务的语言，非常简单，非常适合企业软件。Cro 关于为什么人们可能会选择 Go 而不是 Rust 的论点的关键点主要与 Go 的“简单性”(不要与[“易于使用”](https://kristoff.it/blog/simple-not-just-easy/)混淆)有关，以及该语言完全是[关于大规模抑制复杂性的事实](https://kristoff.it/blog/why-go-and-not-rust/#go-is-about-suppressing-complexity-at-scale)。

Cro 写道，“对于企业软件开发来说，Rust 不如 Go 引人注目”，原因有几个，包括与 Java 或 C#相比，Go 编译器的速度和学习曲线。当然，我们跳过了许多详细的原因，以便让你有理由跳过来看看这篇博文，但我们发现结论为语言爱好者提供了一条平衡的建议:“让我们避免将我们的身份与单一语言捆绑在一起，首先最重要的是拥抱实用性。应该避免使用像 Rustacean 或 Gopher 这样的部落名称，因为它们本质上是诱导更强品牌的营销工具。

这让我们回到了最初的推文，不是吗？这通常不是一个与另一个的对比，而是何时使用一个，何时使用另一个。正如一位黑客新闻评论者所指出的，有时候，[答案是两者兼而有之，同时](https://news.ycombinator.com/item?id=20987528)。

## 本周的节目中

*   **GitLab 承诺 CI/CD & Ops:** GitLab 本周举行了其“[首次用户大会](https://about.gitlab.com/2019/09/17/live-from-commit-news/)”，同时有消息称该公司已[获得更多资金](https://about.gitlab.com/2019/09/17/gitlab-series-e-funding/)。新的堆栈已经出现，并提供了从现在开始对公司的期望的详细描述，但可以说，CI/CD 和其他形式的 Ops 是使用的词汇之一。GitLab 正计划增加与亚马逊弹性 Kubernetes(EKS)服务的高级集成，以及与 HashiCorp 的合作关系。GitLab 将“使运营团队能够轻松管理 GitLab 中的基础设施配置，然后可以由 [TerraForm Cloud](/context-new-versions-of-hashicorps-terraform-cloud-for-teams-and-for-governance/) 执行，”HashiCorp 的 [Vault secrets 管理工具](https://www.vaultproject.io/)“为开发人员提供一种编程方式来确保他们的分布式应用程序的安全性。” [GitLab 和 VMware](https://www.globenewswire.com/news-release/2019/09/17/1916738/0/en/GitLab-to-Enable-Cloud-Native-Transformation-on-VMware-Cloud-Marketplace.html) 还合作将 GitLab 引入 VMware 云市场。
*   **GitHub 的西班牙语帮助文档:**在一份声明中，我的大脑立刻想到，“等等，那还不存在吗？”GitHub 说[你好！为了帮助用西班牙语编写文档](https://github.blog/2019-09-16-product-documentation-now-available-in-spanish/)，写下“随着拉丁美洲成为我们不断增长的市场之一，我们希望缓解不会说英语的一些挑战，并为拉丁美洲和西班牙的更多开发人员提供机会。”这些文档已经有了简单的中文和日文版本，现在也有了西班牙文版本，不过 GitHub 指出，如果一篇翻译过的文章中有一些句子还是英文的，那么它很可能是新的，正在等待翻译。

*   **GitHub 在软件安全方面采取了一些措施:**在 GitHub 的进一步消息中，该公司围绕其对[保护软件所采取的措施发布了几项公告，一起](https://github.blog/2019-09-18-securing-software-together/)。他们在博客中写道:“就像拉请求创建了管理贡献的标准流程一样，生态系统需要更好地定义管理开源代码漏洞的流程。”“这就是我们在 GitHub 着手打造的东西。”为此，GitHub 宣布完成对 Semmle 的[收购。Semmle 是一个语义代码分析引擎，它“允许开发人员编写在大型代码库中识别代码模式的查询，并搜索漏洞及其变体”，已被许多大牌公司使用，并负责迄今为止开源项目中的 100 多个 CVE。说到 CVEs，GitHub 也已经成为开源项目的 CVE 编码权威，这意味着它现在可以为在 GitHub 上打开的安全建议发布](https://github.blog/2019-09-18-github-welcomes-semmle/)[CVEs](https://en.m.wikipedia.org/wiki/Common_Vulnerabilities_and_Exposures)——所有这些都是简化安全流程的一部分。最后，GitHub 还宣布[依赖图支持现在可用于具有 Composer 依赖关系](https://github.blog/2019-09-18-dependency-graph-supports-php-repos-with-composer-dependencies/)的 PHP 存储库。随着 PHP 和它的依赖管理器 [Composer](https://getcomposer.org/) 的流行，GitHub 决定带来它的依赖机器人功能，这些功能也可用于其他编程语言的[包管理器](https://help.github.com/en/articles/listing-the-packages-that-a-repository-depends-on#supported-languages)，包括 Maven、NPM、Yarn、Nuget 和其他一些语言。

*   **微软开源 C++标准库:** DevClass 报道[微软已经转向 GitHub 开源 C++ STL](https://devclass.com/2019/09/18/microsoft-turns-to-github-to-open-source-c-stl/) ，现在可以在 [Apache 2.0 许可下使用，LLVM 例外](https://github.com/microsoft/STL/blob/master/LICENSE.txt)。根据微软关于 MSVC STL 开源的博客，这一举措将“允许我们的客户随时关注我们的发展，尝试我们最新的变化，并通过审查帮助改进我们的拉取请求。”目前，微软表示，它没有计划在 MSVC 工具集中开源任何其他东西，但有一个条件——他们“将花一些时间彻底检查我们的构建系统，测试基础设施和问题跟踪，这将推迟 C++20 库功能的一些工作。”
*   **Quarkus 增加了一个 web 界面:**根据 JaxEnter 的说法，随着 Quarkus 0.22.0 的发布，开源的“Kubernetes Native Java stack tailored for GraalVM&open JDK HotSpot，由同类最佳的 Java 库和标准精心制作”Quarkus 已经推出了一个新的用户友好的 Web 界面。新特性包括改进的 Spring API 支持，对 [Spring Web API](https://quarkus.io/guides/spring-web-guide) 和 [Spring Data JPA API](https://quarkus.io/guides/spring-data-jpa-guide) 的扩展，一个新添加的[模板](https://github.com/quarkusio/quarkus/issues/new?assignees=&labels=extension-proposal&template=extension_proposal.md&title=)使得对 Quarkus 提出更改变得更加容易，以及前面提到的 [code.quarkus.io](https://code.quarkus.io/) 的推出，它“将帮助您创建一个无痛苦的应用程序”，具有一个基于 Web 的用户界面，该界面“旨在实现更简单的用户体验，并帮助用户引导他们的应用程序并发现其扩展，所有这些都在
*   **苹果要求为一些应用提供“用苹果登录”选项:** iOS 开发者注意了——programmable web 报道[苹果已经更新了其开发者指南](https://www.programmableweb.com/news/apple-updates-developer-guidelines-sign-apple-and-kids-category/brief/2019/09/16)，要求应用在使用其他第三方登录时也提供“用苹果登录”选项。这些可能包括登录，如脸书登录、谷歌登录、Twitter 登录、LinkedIn 登录、亚马逊登录或微信登录。苹果表示，如果你的应用只使用你自己的登录，那就继续吧。为了确保你符合规定，请查看[指南](https://developer.apple.com/app-store/review/guidelines/#sign-in-with-apple)中的例外情况。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>