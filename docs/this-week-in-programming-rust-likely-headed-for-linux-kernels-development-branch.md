# 在本周的编程中:Rust(可能)走向了 Linux 内核的开发分支

> 原文：<https://thenewstack.io/this-week-in-programming-rust-likely-headed-for-linux-kernels-development-branch/>

Rustaceans 的梦想 [Rust 包含在 Linux 内核](https://lwn.net/Articles/829858/)中是一个微小的，非常微小的一步，随着本周的“[有意的裸机](https://git.kernel.org/pub/scm/linux/kernel/git/next/linux-next.git/commit/rust?id=c77c8025525c36c9d2b9d82e4539403701276a1d)”包含在 Linux 内核的开发分支 [Linux-next](https://www.kernel.org/doc/man-pages/linux-next.html) 中。当[我们最后一次看到](https://thenewstack.io/this-week-in-programming-linux-kernel-keepers-mull-in-tree-support-for-rust/)时，Rust 在那些希望在 Linux 内核开发中使用该语言的人眼中还只是一个小亮点，Linux 的创造者 Linus Torvalds [表示了他的认可](https://lkml.org/lkml/2020/7/10/1261)，现在这个亮点又亮了一点。

但是，抑制你的热情，因为在 Rust 完全登陆 Linux 内核之前，这仍然是许多必要步骤中的第一步。

一篇关于 LWN.net 的简短帖子简洁地总结了我们的现状:

关注 linux-next 集成树的人可能已经注意到了一个重要的增加:对用 Rust 语言编写设备驱动程序的初始支持。[文档/rust](https://git.kernel.org/pub/scm/linux/kernel/git/next/linux-next.git/tree/Documentation/rust) 中有一些文档，而代码本身在 [rust](https://git.kernel.org/pub/scm/linux/kernel/git/next/linux-next.git/tree/rust) 顶层目录中。在 linux-next 中出现通常意味着为即将到来的合并窗口做好了准备，但不清楚这里是否是这样；这段代码还没有得到广泛的审查。无论如何，这是朝着用更安全的语言编写驱动程序的能力迈出的重要一步。”

事实上， [Miguel Ojeda](https://ojeda.dev/) ，一个软件开发者和 Linux 项目[的维护者](https://lore.kernel.org/rust-for-linux/CANiq72nbNxpps+p4wYp03ncrbGH9FFoTfHQZwg_vGdPO41eGmQ@mail.gmail.com/t/#u)[写道](https://github.com/Rust-for-Linux/linux)被提议的包含“当然并不意味着我们将使它成为主线，但是它是使事情尽可能顺利的一个很好的步骤”，在关于 Rust 的包含的任何决定被做出之前，一些改变被期望。

对于那些不太熟悉 Rust 的人来说，这里的部分吸引力来自于 [Rust 的内存安全特性](https://doc.rust-lang.org/nomicon/meet-safe-and-unsafe.html#:~:text=Safe%20Rust%20is%20the%20true,other%20kind%20of%20Undefined%20Behavior.)，尤其是与 C 语言相比，Linux 内核目前是用 C 语言编写的。然而，部分问题是 Rust 是基于 LLVM 而不是 GCC 编译的，因此支持的架构较少。这是我们最近在[看到的一个问题](https://lwn.net/Articles/845535/)，因为 Python [密码术](https://cryptography.io/en/latest/)库用 Rust 替换了一些旧的 C 代码，导致某些架构将不受支持。目前，将 Rust 包含在 Linux 内核中的提议限制了这个问题，它说 Rust 将被用于编写驱动程序，至少最初是这样，正如另一篇关于主题的[LWN.net 文章中所提到的，“无论如何永远不会在更模糊的架构上使用。”](https://lwn.net/Articles/829858/)

与此同时，如果你正在寻找 Rust 在 Linux 开发中的效用的进一步证据，只需看看亚马逊 Web 服务在 Bottlerocket 上的努力，这是一个主要用 Rust 编写的 Linux 容器发行版。

## 本周的节目中

*   **用内嵌 Lambdas 转换 S3 数据:**亚马逊正在将其广受欢迎的[亚马逊简单存储服务(S3)](https://aws.amazon.com/s3/) 数据存储与其无服务器功能服务 [AWS Lambda](https://aws.amazon.com/lambda/) 配对，以创建[亚马逊 S3 对象 Lambda](https://feedproxy.google.com/~r/AmazonWebServicesBlog/~3/VUHvNcl-l04/) ，这一新功能将允许用户在从 S3 检索数据时对其进行处理。如果您没有看到这一新功能的直接和明显的效用，它们提供了许多潜在的用例，从模糊个人身份信息(PII)到转换数据格式，例如从 XML 到 JSON，甚至是使用来自其他服务的信息来扩充数据。以前，像这样的功能需要为每个用例定制一个数据集，或者需要一个代理层在移动时执行数据转换。不仅如此，本例中的 Lambda 函数是与 S3 GET 请求一起内联执行的，这意味着您的应用程序代码可以保持不变。

[https://www.youtube.com/embed/uTBgpK07E38?feature=oembed](https://www.youtube.com/embed/uTBgpK07E38?feature=oembed)

视频

*   **AWS 模拟故障注入:**当我们谈论 AWS 时，该公司还[推出了](https://aws.amazon.com/blogs/aws/aws-fault-injection-simulator-use-controlled-experiments-to-boost-resilience/)一款[故障注入模拟器(FIS)](http://aws.amazon.com/fis) ，以进一步帮助用户提高可靠性，称这款新工具是对它为此已经提供的许多工具的补充，如[亚马逊云观察](https://aws.amazon.com/cloudwatch/)、[自动伸缩](https://aws.amazon.com/autoscaling)、[负载平衡](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html#concepts-availability-zones)等等。他们写道，故障注入属于“相对较新的[混沌工程](https://en.wikipedia.org/wiki/Chaos_engineering)领域”，它“专注于通过创建破坏性事件、观察系统如何响应以及实施改进来增加应用程序的压力。”有了 FIS，用户将能够通过注入故障，在他们的 AWS 工作负载上执行受控实验，然后等着看会发生什么。这个想法是，你学习你的系统如何对各种类型的故障做出反应，以便更好地理解故障模式。这些“实验”可以在您的开发环境中运行，但如果您愿意，甚至可以在生产环境中运行，每个实验都针对一组特定的 AWS 资源，并对它们执行一组操作。目前，这些服务包括 [EC2](https://aws.amazon.com/ec2/) 、 [ECS](https://aws.amazon.com/ecs/) 、 [EKS](https://aws.amazon.com/eks/) 和 [RDS](https://aws.amazon.com/rds/) ，更多服务正在进行中。
*   **GitHub 的 dependent bot 现已向私人回购开放:** GitHub 大约两年前收购了 dependent bot，并一直在稳步努力将该技术带给其用户。现在，该公司已将[dependent bot 提供给私有依赖](https://github.blog/2021-03-15-dependabot-private-dependencies/)，该工具将致力于保持依赖无漏洞和最新。这个版本将允许用户通过存储注册表的访问令牌或者通过[授予 dependent bot 对所需私有库的访问权限](https://docs.github.com/en/github/setting-up-and-managing-organizations-and-teams/managing-security-and-analysis-settings-for-your-organization#allowing-dependabot-to-access-private-repositories)，来授予 dependent bot 对私有包注册表(包括 GitHub 包、Artifactory、Azure 工件等)和私有 GitHub 库的访问权限。出于好奇，GitHub 指出“在 Dependabot 中发生了很多事情，从[生态系统更新](https://github.com/github/roadmap/issues/150)到[噪音更小的通知](https://github.com/github/roadmap/issues/133)，提供了[公共路线图](https://github.com/github/roadmap/projects/1?card_filter_query=label%3A%22security+%26+compliance%22)以进一步洞察下一步的发展。这种使其工具对私有存储库开放的举动似乎是一种趋势，该公司也于上周向私有存储库开放了其 GitHub 讨论功能。

*   **谷歌结束 2020 年文档季，开放 2021 年应用:**谷歌的[文档季](https://developers.google.com/season-of-docs)，该计划将技术作家与开源项目配对，以帮助创建文档，[结束了其 2020 年的长期运行项目](https://opensource.googleblog.com/2021/03/season-of-docs-announces-successful-2020-projects.html)。该公司写道，“15 名技术作家成功完成了他们长期运行的技术写作项目”，并指出这项工作持续了几个月。谷歌还表示，它目前正在接受 2021 年项目的[组织申请](https://docs.google.com/forms/d/e/1FAIpQLSd3oGOB6vdfUIb8tjrByYBfESlK6VYK9slwNejJABuSWMK42g/viewform)，看起来持续交付基金会(CDF)和它的一些项目[可能会在明年加入](https://lists.cd.foundation/g/cdf-toc/message/635)。
*   **帮助 Rust 展望未来:**在寻求成为“构建分布式系统的最受欢迎的选择之一”的过程中，Rust 的[异步基金会工作组](https://rust-lang.github.io/wg-async-foundations/)正致力于[为异步 Rust](https://blog.rust-lang.org/2021/03/18/async-vision-doc.html) 建立一个共同的愿景，他们正在寻求您的帮助，为异步 Rust 创建一个共同的[愿景文档](https://rust-lang.github.io/wg-async-foundations/vision.html#-the-vision)。他们写道，他们的目标是“让整个社区参与到想象的集体行动中:我们如何才能让使用异步 I/O 的端到端体验不仅是一个实用的选择，而且是一个快乐的选择？”该文档将讲述一个[角色](https://rust-lang.github.io/wg-async-foundations/vision/characters.html)的故事，每个角色都绑定到一个特定的 Rust 值。[例如，Grace](https://rust-lang.github.io/wg-async-foundations/vision/characters/grace.html) 是一名 C++程序员，他喜欢 Rust 的内存安全这一想法，该文档提出了一些问题，如 Grace 最想要什么功能，鉴于她的故事，她期望什么？如果这听起来像是你正在做的事情，请查看现状故事的[模板](https://rust-lang.github.io/wg-async-foundations/vision/status_quo/template.html)，其中有你需要打开拉动请求的所有信息，或者前往[如何愿景](https://rust-lang.github.io/wg-async-foundations/vision/how_to_vision.html)页面，该页面详细介绍了整个愿景文档流程。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>