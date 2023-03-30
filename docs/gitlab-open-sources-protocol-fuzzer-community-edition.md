# GitLab 开源协议 Fuzzer 社区版

> 原文：<https://thenewstack.io/gitlab-open-sources-protocol-fuzzer-community-edition/>

模糊测试看起来像是一种相对较新的发现错误的技术，但实际上它可以追溯到 50 年代，当时他们从垃圾箱中取出穿孔卡片进行输入，以发现大型机软件的问题。这些天我们在技术上有了一点进步。例如，GitLab 刚刚[开源了其新收购的 Protocol Fuzzer 社区版](https://about.gitlab.com/blog/2021/03/23/gitlab-open-sources-protocol-fuzz-test-engine/)。

这很重要，因为这个协议和应用程序编程接口(API)的大部分 Fuzzer 特性只有商业许可才可用。确实需要更广泛地提供调试功能。一项 [2020 GitLab DevSecOps](https://about.gitlab.com/developer-survey/) 调查发现，虽然 81%的开发人员认为模糊测试很重要，但只有 36%的人实际上在使用 fuzzing？为什么？因为设置 fuzzing 并将其与他们自己的持续集成(CI)系统集成太麻烦了。

这并不是 Protocol Fuzzer 开源的第一个版本。在其之前的管理下，Peach Tech 的早期版本 [Peach Fuzzer 社区版已经被开源](https://www.peach.tech/wp-content/uploads/Evolution-of-Peach_From-Project-to-Product-29July2015.pdf)。然而，这个版本更受限制，它的[代码只在 SourceForge](https://sourceforge.net/projects/peachfuzz/) 上可用。今天，[协议 Fuzzer 代码，在 MIT 许可下，可以在 GitLab](https://gitlab.com/gitlab-org/security-products/protocol-fuzzer-ce) 上获得。

虽然这个程序比早期版本包括更多的功能，但它的代码仍然在很大程度上基于 Peach Tech 的[Peach Fuzzer Professional v4](https://www.peach.tech/wp-content/uploads/Peach-Fuzzer-Release-Notes-4.0f.pdf)，GitLab [于 2020 年](https://thenewstack.io/gitlab-adds-security-fuzzing-with-double-acquisition/)收购了该软件。例如，该计划仍然包含引用桃科技。此外，一些功能已被删除，并将在未来作为 GitLab 的一部分提供。

核心特性是，它包括运行和编排模糊测试的引擎，以及定义自己的协议所需的部分。以前，你只能通过购买 Peach Fuzzer 的商业版本或者使用一个更老的、无人维护的 Peach Fuzzer 社区来使用它的工具。后者缺少商业版本中的许多功能和缺陷修复。

据 GitLab 的 Secure: Fuzz [首席产品经理](https://about.gitlab.com/job-families/product/product-manager/)、 [Sam Kerr](https://www.linkedin.com/in/samkerr/) 称:“通过开源许多以前只能通过付费许可证获得的东西，我们很高兴能够让更多的安全研究人员、学生和开发人员试验和使用协议模糊测试来发现其他工具无法发现的漏洞和错误。这也使得每个人都可以贡献自己的力量，进一步推动艺术的发展。”

自从收购 Peach Tech 以来，该公司一直专注于集成 API 模糊测试的 T4，并发布了几个迭代。“现在，我们正在关注如何提供协议模糊测试，”克尔在电子邮件中写道。

您可以在开源版本中看到很多这样的内容。“我们的[管理承诺](https://about.gitlab.com/company/stewardship/)的一部分是，我们希望向社区提供我们所有 DevSecOps 阶段的开源部分，其中包括模糊测试。到目前为止，主要的替代方案是 Peach Tech community edition 的旧版本，该版本上次更新是在五年前，或者选择不进行任何模糊测试。

克尔总结道，“每个人都可以从模糊测试中受益，以找到其他工具遗漏的错误和漏洞。我们很高兴在协议模糊测试器上做更多的事情，我们希望尽快开源这些部分，以确保[每个人都可以贡献](https://about.gitlab.com/company/strategy/#everyone-can-contribute)。[社区参与](https://about.gitlab.com/blog/2021/03/23/how-you-contribute-to-gitlabs-open-devops-platform/)将帮助我们更快地添加新功能，并允许用户为他们自己的特定用例贡献新功能，同时我们制定自己的路线图。”GitLab 已经在其[模糊测试方向页面](https://about.gitlab.com/direction/secure/fuzz-testing/fuzz-testing/)上给出了更多关于其未来计划的细节。

然而，此时要使用 Protocol Fuzzer，您可能需要已经有了使用该程序早期版本的经验。目前，除了关于如何在 Linux、macOS 和 Windows 上构建程序的说明之外，几乎没有最新的文档。不过，这一天终将到来，而且正如该项目长达十年的历史所显示的那样，对于那些愿意花时间掌握它的人来说，该项目有望取得良好的效果。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>