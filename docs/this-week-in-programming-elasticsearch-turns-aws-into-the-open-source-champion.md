# 本周编程:Elasticsearch 让 AWS 成为开源冠军

> 原文：<https://thenewstack.io/this-week-in-programming-elasticsearch-turns-aws-into-the-open-source-champion/>

在我们讲述开源软件的故事时，我们经常用好的和坏的、开放的和封闭的、自由的和不自由的来描述事物。两年前，当[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS) [为 Elasticsearch](https://opendistro.github.io/for-elasticsearch/) 创建开放发行版时，一些人认为该公司是在[分流项目](https://thenewstack.io/what-the-fork-amazon/)以回避其限制 AWS 将 Elasticsearch 作为服务出售的企图。在 Twitter 和其他地方发表意见的人普遍认为，这是互联网巨头利用其影响力欺负较小的开源公司的又一个例子。在大卫对抗歌利亚的故事中，歌利亚 AWS 不公平地从 Elastic 的劳动中获利，本质上是窃取他们的劳动成果，利用他们的市场支配地位掩盖较小的公司，并将其产品作为服务出售。

天哪，事情怎么会变了。

本周，Elastic 宣布它[已经受够了 AWS 提供开源软件作为服务的](https://www.elastic.co/blog/why-license-change-AWS)，并且它将把 Elasticsearch 和 Kibana 的许可证从 Apache 2.0 改为双重许可证，受[服务器端公共许可证(SSPL)](https://www.mongodb.com/licensing/server-side-public-license) 和[弹性许可证](https://github.com/elastic/elasticsearch/blob/0d8aa7527e242fbda9d84867ab8bc955758eebce/licenses/ELASTIC-LICENSE.txt)的约束，让用户可以选择应用哪种许可证。这两个许可证都包含限制软件使用的条款——[开源倡议认为](https://opensource.org/node/1099)此举违反了[开源定义](https://opensource.org/osd)的第六点，即“许可证不得限制任何人在特定领域使用程序。”

“随着向 SaaS 交付模式的转变，一些云服务提供商已经通过提供服务的方式利用了开源产品，而不需要回报，”Elastic 解释道。“这一变化不会影响我们的大多数用户，但它将限制云服务提供商提供我们的软件即服务。”

作为回应，AWS 本周宣布，它将“[加快真正开源的 Elasticsearch](https://aws.amazon.com/fr/blogs/opensource/stepping-up-for-a-truly-open-source-elasticsearch/) ”，这一次真正分叉该项目，以便在 Apache 2.0 许可下保持可用。

该公司写道:“为了确保这两个包的开源版本仍然可用并得到良好的支持，包括在我们自己的产品中，我们今天宣布 AWS 将加强创建和维护 ALv2 许可的开源 Elasticsearch 和 Kibana 的分支。”

尽管 Elastic 的[反复断言](https://www.elastic.co/blog/why-license-change-AWS)AWS 一直在做的事情是“不好的”，但似乎更“不好”的是关闭一个以前的开源项目。虽然围绕整个事件的一般叙述带有“AWS 不好，其他人都好”的轻松语气，但另一个 [Twitter 帖子](https://twitter.com/adamhjk/status/1352427062057787393)提供了一个颠倒的视角，使大卫和歌利亚的框架受到质疑。

## 本周的节目中

*   **Red Hat 扩大 RHEL 免费使用:**去年年底， [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 采取了不受欢迎的步骤[放弃 Linux CentOS，转而支持流媒体版本](https://thenewstack.io/red-hat-deprecates-linux-centos-in-favor-of-a-streaming-edition/)，现在该公司已经[宣布了](https://www.redhat.com/en/blog/new-year-new-red-hat-enterprise-linux-programs-easier-ways-access-rhel)其 Red Hat Enterprise Linux (RHEL)的两个新的免费使用案例，分别针对[小型生产工作负载](https://www.redhat.com/en/blog/new-year-new-red-hat-enterprise-linux-programs-easier-ways-access-rhel#Bookmark%201)和[客户开发团队](https://www.redhat.com/en/blog/new-year-new-red-hat-enterprise-linux-programs-easier-ways-access-rhel#Bookmark%202)。“当我们宣布我们打算过渡到 CentOS Stream 时，”他们写道，“我们计划创建新的程序来解决传统上由 CentOS Linux 服务的用例。”自 2021 年 2 月 1 日起，RHEL 的“个人开发者”订阅可用于多达 16 个系统的生产。与此同时，作为 Red Hat 开发人员计划的一部分，开发团队“现在可以通过客户现有的订阅免费添加到该计划中。”请关注新的堆栈，以获得 Linux 大师杰克·沃伦的详细介绍。

*   **AWS 增加 Go SDK v2，结束 Python 2.7 支持:**亚马逊网络服务本周提供了几个关于其 AWS SDK 的更新，包括[的](https://aws.amazon.com/blogs/developer/aws-sdk-for-go-version-2-general-availability/) [AWS SDK for Go version 2 (v2)](https://github.com/aws/aws-sdk-go-v2/releases) 的，它需要 Go 1.15 或更高版本，并且“在 CPU 和内存利用率方面比版本 1 有显著的性能改进。”新特性包括模块化、将每个 AWS 服务客户端打包为独立的 Go 模块、单一配置类型中的直观配置、通过提供更简单的 API 客户端来简化 API 客户端方法、性能改进等等。至于 Python 2.7，AWS 已经[宣布截止 2021 年 7 月 15 日结束支持](https://aws.amazon.com/blogs/developer/announcing-end-of-support-for-python-2-7-in-aws-sdk-for-python-and-aws-cli-v1/)。随着官方对 Python 2.7 的支持在一年前结束，AWS 表示，它将“加入这些反对意见，以保持安全和最新的 SDK。”查看完整的帖子，了解如何让自己跟上时代。

*   **GitHub 的企业服务器 3.0 预览版:**去年在 GitHub Universe Keynote 上首次发布，GitHub 已经[发布了 GitHub 企业服务器 3.0](https://github.blog/2021-01-15-github-enterprise-server-3-0-is-here/) 的发布候选版本。候选版本为用户提供了一种在转移到他们的生产环境之前测试功能和提供反馈的方式，这可能是一个好主意，因为 GitHub 说“这是企业服务器有史以来最大的变化。”新功能包括 GitHub Actions 的引入，发布和使用包以及代码的能力，iOS 和 Android 应用的测试版，以及与 [GitHub Advanced Security](https://github.com/features/security) 相关的功能，如代码扫描和秘密扫描。
*   **DigitalOcean 应用平台连接 GitLab:** DigitalOcean 的[应用平台](https://www.digitalocean.com/products/app-platform)，去年年底宣布，现在[已经引入了 GitLab 集成](https://www.digitalocean.com/blog/introducing-gitlab-integration-for-digitalocean-app-platform)(加入已经存在的 [GitHub 集成](https://www.youtube.com/watch?v=fE0ybwkW9Pw))，这将允许用户直接从他们的 GitLab 库部署代码。该集成还具有“推送时自动部署”功能，每次推送至包含源代码的分支时，该功能会自动重新部署他们的应用程序。该公司指出，比特桶集成“指日可待”

*   **Rust 的文档获得速度提升:**Rustdoc 团队写了一篇博客，总结了最近的 [Rustdoc 性能改进](https://blog.rust-lang.org/inside-rust/2021/01/15/rustdoc-performance-improvements.html)，指出“这都是关于清理的。”这个帖子是在 Rustdoc 团队负责人 Guillaume Gomez 最近的一条推文展示了速度的提高之后发布的，社区集体发出了“你是怎么做到的？”像往常一样，Rust 博客提供了香肠是如何制作的内幕，详细介绍了团队通过“移除 rustdoc 中的实现并直接使用编译器类型”来偿还技术债务的工作展望未来，该团队仍然希望“简化和返工大量 rustdoc 源代码”，并表示还有更多工作要做，以帮助加快该语言的文档编制速度。
*   **“一种新型的开源组织”:**最后，[希波克拉底许可证](https://firstdonoharm.dev/)和[贡献者契约](https://contributor-covenant.org/)的创建者 [Coraline Ada Ehmke](https://en.wikipedia.org/wiki/Coraline_Ada_Ehmke) ，本周宣布创建[伦理资源(OES)](https://ethicalsource.dev/blog/oes-announcement/) 组织，试图挑战“开源软件可以不受限制地用于任何目的，[甚至是明显的‘邪恶’目的](https://opensource.org/faq#evil)”的观点 Ehmke 认为“自从开源定义被创建以来，世界已经发生了变化——开源已经变得无处不在，现在正被坏人用来在世界各地进行大规模监控、种族主义警察和其他侵犯人权的行为，”他说“作为技术专家，我们必须接受我们的工作对社会产生了巨大的影响，这意味着我们有巨大的责任来最小化它可能造成的伤害。伦理资源组织的成立是为了帮助技术人员接受这些责任，并学习如何在我们的工作中实现公正和公平。我们团结一致，坚信软件自由不能先于人类自由。”如果争论开源的本质是你最喜欢的消遣之一，那么这是你的一周，所以出去吧。

专题图片:美国参议员伯尼·桑德斯“顺便拜访”我们的一个煎饼早餐([伯尼·桑德斯坐在椅子上，手里拿着米滕斯米姆模板](https://www.kapwing.com/explore/bernie-sanders-sitting-in-a-chair-with-mittens-meme-template)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>