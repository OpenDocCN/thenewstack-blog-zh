# 本周节目:特拉维斯·CI 希望澄清困惑...又

> 原文：<https://thenewstack.io/this-week-in-programming-travis-ci-hopes-to-clear-up-confusion-again/>

持续集成(CI)平台 [Travis CI](https://travis-ci.org/) 去年宣布，[将引入一种新的定价模式](https://blog.travis-ci.com/2020-11-02-travis-ci-new-billing)，此前[将期待已久的](https://docs.travis-ci.com/user/migrate/open-source-on-travis-ci-com/)从 travis-ci.org 迁至新的 travis-ci.com 地区，从那以后，似乎每个人都不知道该如何继续。去年宣布后不久，该公司向[提供了一篇博客文章进行澄清](https://blog.travis-ci.com/oss-announcement)，写道它“最近从 Travis CI 社区和其他地方收到了许多关于 Travis CI 开源未来的反馈和问题。”本周，该公司提供了另一个关于其开源条款的“更新和澄清”,首先是关于反馈、问题和困惑的几乎相同的介绍。

虽然在 Travis CI 看到的问题肯定不是孤立的——就在上周，我们写了关于 [crypto-miners 如何超越 Docker Hub 的 autobuilds](https://thenewstack.io/this-week-in-programming-crypto-miners-overrun-docker-hubs-autobuild/)——但该公司似乎遇到了一个完全不同的问题:与客户清楚地沟通问题及其解决方案。

不要夸大其词，尽管有些人似乎认为用户正在离开 Travis CI[成群结队](https://twitter.com/_james_fuller/status/1404366396285407233)，但是 [curl](https://curl.se/) 的创建者和首席开发人员 [Daniel Stenberg](https://daniel.haxx.se/) 本周写了一篇博客，概述了他为什么要与 Travis CI 说再见，并将开源项目的构建转移到 [Zuul CI](https://zuul-ci.org/) 和 [Circle CI](https://circleci.com/) 的原因。对于 Stenberg 来说，似乎一切都归结于糟糕的沟通，以及他所看到的 Travis CI 违背了为开源项目提供免费构建的承诺。

“我们很快了解到，新的领域也意味着新的规则和新的层级。现在我们必须申请被认可为开源项目(在使用他们的服务作为开源项目 7.5 年之后)。但是，为了利用他们的免费层，开源项目已经不够了，”Stenberg 写道，引用了该公司最近一封电子邮件中的措辞，该邮件称，项目“不得由商业公司或组织赞助(金钱或员工支付项目工作费用)”才能被视为开源。

至于[失信](https://twitter.com/bagder/status/1399246627957886979)，Stenberg 引用了之前发布在 Travis CI 网站上的措辞“测试你的开源项目总是 100%免费的！说真的。一直都是。我们喜欢把它看作是我们回报社会的一种方式，这个社会也给了我们很多。”

作为 curl 的付费维护者，Stenberg 说他们不再有资格在 Travis CI 上免费构建，他们从 6 月 14 日起停止迁移他们的构建。他说，Stenberg 面临的另一个问题是，当 curl 的制作资金用完时，他们联系了 Travis CI，但从未得到回应。他似乎不是唯一一个。

就在斯腾伯格的博客文章发表两天后，Travis CI [提供了最新的澄清](https://blog.travis-ci.com/2021-06-16-ibm-aws)，准确地指出了一些与斯腾伯格相同的抱怨。

Travis CI 团队写道:“我们最近通过电子邮件直接向开源客户提供了修订后的服务条款，这造成了一些混乱。”。“我们的目的是确保我们为开源项目指定的基础设施专门用于符合开源社区目标的项目，而不是用于明确的商业目的的项目。我们知道，其他组织通过捐赠开发者时间等方式为开源社区做出了贡献，这些贡献绝不会限制开源项目免费构建 Travis CI。”

展望未来，Travis CI 表示，它将提供“零信用合作伙伴队列解决方案，在赞助基础设施上构建开源仓库的开发人员可以免费获得对 Travis CI 构建的无缝访问”，而不是要求他们通过电子邮件联系公司。“开发者只需要修改他们开源项目的 YAML 文件，就可以使用合适的环境，而不必担心信用消耗，”他们解释道。

至少对于 Stenberg 和 curl 项目来说，这个举动似乎是[太少，太迟](https://twitter.com/bagder/status/1405537041689968650)。

## 本周的节目中

*   **Visual Studio 2022 预览版发布:**你已经听说了所有关于 [Visual Studio 2022 和它的 64 位更新](https://devblogs.microsoft.com/visualstudio/visual-studio-2022/)，现在你可以得到 [Visual Studio 2022 预览版 1](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-preview-1-now-available/) ，第一个包含新 64 位平台的版本。微软表示，此次发布的目标是“测试和调整这一新的 64 位平台的可扩展性”，它希望这一平台能够消除一些你在过去使用 32 位版本时可能遇到的令人讨厌的错误。预览版可以与其他版本一起安装，微软正在敦促扩展作者更新他们的 64 位扩展，并警告用户许多扩展不会立即在 Visual Studio 2022 中可用。虽然这个预览版主要与 64 位相关(以及对 IntelliCode 的[更新)，但 Preview 2 正在进行中，他们说这将是“一系列令人兴奋的新功能和性能改进。”](https://devblogs.microsoft.com/visualstudio/type-less-code-more-with-intellicode-completions)

*   **GitHub Desktop 改进拖放功能，获得原生 M1 支持:**[GitHub Desktop 的最新版本已经发布](https://github.blog/2021-06-16-github-desktop-2-9-squashing-reordering-amending/)，像最近的许多其他工具一样，增加了对苹果时尚的新 M1 芯片的原生支持，据说这将提高性能，减少崩溃。除此之外，GitHub Desktop 2.9 在最近版本中引入了一些功能，通过“扩展拖放功能，允许您压缩和重新排序历史中的提交，修改以前的提交，从以前的提交开始新的分支，等等。”要想看到这些功能，要么[下载最新的 GitHub 桌面](https://desktop.github.com/)要么去博客上看一些动态的 gif 图片。
*   **Go 1.17 测试版发布以解决奇想乐队:**虽然 Go 1.17 要到 2021 年 8 月才发布，但 Golang 团队[已经发布了 Go 1.17 的测试版](https://groups.google.com/g/golang-announce/c/i4EliPDV9Ok/m/MxA-nj53AAAJ?pli=1)以开始测试该语言的最新版本。Go 1.17 将不会像最初建议的那样，在其新功能中包括 fuzzing，[的发布说明](https://tip.golang.org/doc/go1.17)称只包括“该语言的三个小增强”Infoworld 上的一篇文章深入探讨了这个最新版本，指出语言特性旨在“简化编写符合 unsafe 的代码”。指针的安全规则。”此外，Go 编译器还“实现了一种使用寄存器而不是堆栈传递函数参数和结果的新方法”，这有望提高性能并减少二进制文件的大小。

*   **Red Hat 提供自托管 GitHub 操作:**在去年年底发布的功能基础上，Red Hat 本周推出了在 Red Hat OpenShift 上部署自托管 GitHub 操作运行程序的能力[，这使得在您自己的集群而不是 GitHub 的集群上运行工作流成为可能。当](https://developers.redhat.com/blog/2021/05/12/self-hosting-github-actions-runners-on-openshift) [GitHub 已经提供了基础设施](https://docs.github.com/en/actions/using-github-hosted-runners/about-github-hosted-runners)的时候，你为什么要这么做呢？红帽很高兴你问了。他们说，自托管运行器提供了一些独特的好处:它们与 GitHub Enterprise Server 一起工作，它们没有使用限制，并且它们有持久磁盘。使在 OpenShift 上运行自托管 GitHub 操作变得容易的新工具包括[open shift Actions runners](https://github.com/redhat-actions/openshift-actions-runner)，一个从这些图像部署 pod 的 Helm 图表，以及一个自动化 Helm 安装的操作，将 runner 管理构建到您的工作流中。
*   **Shipwright 为 Kubernetes 带来了容器构建:**Red Hat 又推出了一个，它与 IBM 合作创建了 [Shipwright](https://developers.redhat.com/articles/2021/06/17/shipwright-framework-building-container-images-kubernetes) ，这是一个在 Kubernetes 上构建容器映像的框架。Shipwright 引用了对供应链安全的日益关注，将容器构建过程直接引入到 Kubernetes 基础设施中，从而减少了一个需要保护的地方。Shipwright 使用“熟悉的 Kubernetes 风格的 API”，并使用 [Tekton](https://tekton.dev/) 运行工作负载，并提供“一系列现代容器构建工具，如[云原生构建包](http://buildpacks.io/)、 [Kaniko](https://github.com/googlecontainertools/kaniko) 、 [Buildah](https://buildah.io/) 、[源到图像(S2I)](https://github.com/openshift/source-to-image) 、[构建工具包](https://docs.docker.com/develop/develop-images/build_enhancements/)和 [ko](https://github.com/google/ko) ”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>