# Linux 内核中的 Rust:“足够好”

> 原文：<https://thenewstack.io/rust-in-the-linux-kernel-good-enough/>

为 Linux 内核带来 Rust 的努力本周继续进行，来自 Linux Rust 的项目维护者 Miguel oje da 本周发布的[更新](https://lkml.org/lkml/2021/12/6/461)引起了新的兴奋。虽然更新警告说 Rust 支持“仍被认为是实验性的”，但它指出，该项目已经从使用 beta Rust 编译器转向使用稳定版本，从上周四刚刚发布的 Rust 1.57.0 开始。

此外，该项目已经迁移到 Rust 的 2021 版，并计划在每次发布新的稳定编译器时迁移到新的稳定编译器。

“通过升级编译器，我们已经能够去掉我们正在使用的一些不稳定的功能，”Ojeda 写道，并进一步指出“我们将继续升级，直到我们不再依赖任何不稳定的功能；在这一点上，我们可能希望开始声明支持最低 Rust 版本，如 GCC 和 Clang。”

对于此次更新，Ojeda 还表示，尽管仍处于试验阶段，“支持已经足够好，内核开发人员可以开始为子系统编写 Rust 抽象，并编写驱动程序和其他模块”，这通常是一直以来的计划。

当我们第一次看到 Linux 内核中 Rust 的想法时，我们注意到其目的不是用 Rust 重写内核的 2500 万行代码，而是用比 Linux 开发中通常使用的标准 C 更安全的内存语言来增加新的开发。

使用 Rust 的部分问题是 Rust 是基于 LLVM 编译的，而不是 GCC，因此支持的架构较少。当 Python [cryptography](https://cryptography.io/en/latest/) 库用 Rust 替换了一些旧的 C 代码，导致某些架构不被支持时，我们看到[出现了这个问题。因此，对驱动程序使用 Rust 将限制这种特殊限制的影响。](https://lwn.net/Articles/845535/)

Ojeda 进一步指出，Rust for Linux 项目在过去的一年中被邀请参加了许多会议和活动，甚至获得了来自 Red Hat 的一些支持，该公司与 Arm、谷歌和微软一起支持这项工作。根据 Ojeda 的说法，Red Hat 说“Red Hat 正在考虑对内核工作使用 Rust 的兴趣。”

关于 Rust 用 LLVM 而不是 GCC 编译的说明，Ojeda 还说 Rust 编译器的 GCC 后端被合并到上游 Rust 中，并且“如果后端继续发展，我们希望很快能够开始尝试用 GCC 编译内核的 Rust 端！”

## 本周的节目中

*   *   *   **GitHub 更新其代码搜索:** GitHub 推出了其[改进代码搜索](https://github.blog/2021-12-08-improving-github-code-search/)的预览版，据称将提供“在 GitHub 上搜索代码的实质性改进”在发布时，新功能将覆盖超过 500 万个最受欢迎的公共存储库，以及您自己的私有存储库中的代码，并支持多种方式来搜索代码——精确字符串、正则表达式、布尔运算符，以及根据项目、存储库、组织等确定范围。该功能尚未完全可用，但你现在可以[注册加入预览版的等候名单](https://cs.github.com/about)。虽然你可以阅读关于搜索如何工作的所有内容，但这是那些当你看到它时效果会更好的事情之一，所以快速浏览一下介绍视频，看看你附近的 GitHub 会有什么。

        [https://www.youtube.com/embed/UOIPBfPXkus](https://www.youtube.com/embed/UOIPBfPXkus)

        视频

        *   **…和 Python 代码导航:**伴随着 GitHub 改进代码搜索的消息，该公司还发布了针对 Python 的[精确代码导航，以及 pull 请求中的代码导航](https://github.blog/2021-12-09-precise-code-navigation-python-code-navigation-pull-requests/)，这两个都是普遍可用的。pull requests change 中的代码导航将代码导航直接带到 pull requests 的“files changed”选项卡中，而不仅仅是在 GitHub 的代码浏览器中，而 Python 的精确代码导航提供了精确的定义，而不是以前提供的“模糊”定义。Python 特性是使用本周推出的[栈图](https://github.com/github/stack-graphs/)框架[提供支持的](https://github.blog/2021-12-09-introducing-stack-graphs/)，虽然目前只支持 Python，但在未来几个月内将会添加其他[支持的语言](https://docs.github.com/en/repositories/working-with-files/using-files/navigating-code-on-github#about-navigating-code-on-github)。
        *   **GitHub Actions 获得容器签名:**GitHub 本周的最后一次更新——该公司在 GitHub Actions 中引入了[保护容器的新容器签名功能，这部分是通过](https://github.blog/2021-12-06-safeguard-container-signing-capability-actions/)[开放软件安全基金会(OpenSSF)](https://openssf.org/) 实现的，它是该基金会的创始成员之一。具体来说，OpenSSF 托管了 [Sigstore](https://www.sigstore.dev/) 项目，该项目允许开发人员安全地构建、分发和验证签名的软件工件，GitHub 已经宣布它已经“将 Sigstore 对容器图像签名的支持集成到了 [GitHub Actions starter 工作流](https://github.com/actions/starter-workflows/blob/main/ci/docker-publish.yml)中，这样开发人员就可以在默认情况下对他们的容器图像进行签名。”这个新特性将有助于确保您从容器注册中心获取的代码实际上是您认为的那样，而不是可能引入漏洞的东西。首先，查看一下 [starter 工作流模板](https://github.com/actions/starter-workflows/blob/main/ci/docker-publish.yml)，它让您在从公共存储库运行时利用无密钥签名。
        *   你想从铁锈中得到什么？随着 [2021 年铁锈状况调查启动](https://blog.rust-lang.org/2021/12/08/survey-launch.html)，是时候让所有的铁锈人听到你们的声音了。该报告调查了 Rust 社区的成员，项目本身的表现如何，还有哪些可以改进的地方——所有这些都是由你[填写调查问卷](https://surveyhero.com/c/jzesmzph)收集的。这份匿名问卷需要 10 到 30 分钟，一直持续到 12 月 22 日，所以赶快行动吧。今年的调查结果将发布到 Rust 博客上，你也可以查看去年的调查结果。
        *   **科特林特色调查结果出炉:**当我们谈论调查时，[结果来自 2021 年科特林特色调查](https://blog.jetbrains.com/kotlin/2021/12/kotlin-features-survey-2021-results/)。该调查询问 Kotlin 开发人员 Kotlin 中最期待的特性是什么，虽然他们指出该调查“并不详尽”,并且不能保证“这些特性中的任何一个将很快成为语言，即使他们已经收到了很多投票”,但他们确实说“你们的投票有助于我们在长期内优先考虑我们的工作”好吧，尽管这相当不令人鼓舞，研究人员说他们收到了[1540 个完整的回复](https://docs.google.com/spreadsheets/d/17cgK6kO--5HmZ3M23sGNdbdWn7MeYe8dKVUNfuvrXbA/edit#gid=351766805)，最受欢迎的前三个特性包括多批处理和联合类型(45%)、集合文字(32%)和扩展函数和属性的多接收器(30%)。关于结果的更多信息，他们在实现这些功能的过程中，以及其他非常受欢迎的功能，请前往[博客帖子](https://blog.jetbrains.com/kotlin/2021/12/kotlin-features-survey-2021-results/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>