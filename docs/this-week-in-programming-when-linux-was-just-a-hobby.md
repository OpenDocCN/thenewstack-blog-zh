# 本周编程:当 Linux“只是一种爱好”时

> 原文：<https://thenewstack.io/this-week-in-programming-when-linux-was-just-a-hobby/>

当我回想起 1991 年，试着回忆当时我在哪里，可能是在某个地方，有一张 [x286](https://en.wikipedia.org/wiki/Intel_80286) 和一堆 5.5 英寸的软盘，背景是 1200 波特调制解调器的[尖叫声，同时登录](https://youtu.be/ckc6XSSh52w?t=17) [Prodigy](https://en.wikipedia.org/wiki/Prodigy_(online_service)) 并抱着一丝希望我的父母不会拿起电话线。与此同时，在地球的另一端，无论是从字面上还是从表面上看，Linus Torvalds 都在忙于构建操作系统，这个系统将会运行我们今天所知道的大部分互联网。

没错，本周，开源 Linux 操作系统迎来了 30 岁生日，至少按照一个公认的标准来看是这样的。

正在庆祝的周年纪念日是 Linus [第一次在](http://www.cs.cmu.edu/~awb/linux.history.html)[新闻组](https://en.wikipedia.org/wiki/Usenet)的消息中公开提到新操作系统的周年纪念日，当时他称之为“一个(免费的)操作系统(只是一个爱好，不会像 gnu 一样庞大和专业，在 clones 是 386(486)。”

在本周的一篇文章中，Linux 爱好者兼作家 Steven J. Vaughan-Nichols(经常为新的堆栈做出贡献的人)从他与 Torvalds 的对话中摘录了操作系统的起源，列举了 Linux 现在在 IT 领域的主导地位:

“三十年后，Linux 统治了它。几乎所有的主要网站——包括谷歌、脸书和维基百科——都运行在 Linux 上。云也是一样。即使在微软自己的 Azure 上，最流行的操作系统也是 Linux。至于超级计算机，全球最快的 500 台超级计算机中的 500 台都运行 Linux 。得益于 Android，Linux 也是最受欢迎的终端用户操作系统。对于一个爱好操作系统来说还不错！”

他注意到托瓦尔兹说你可以争辩说 Linux 有四个生日，第一个可以追溯到同年的 7 月 3 日，但是我的理论是它仅仅是那个信息的文本(*仅仅是一个爱好！这使得它脱颖而出，成为值得庆祝的节日。我知道，至少，那个时候我和一个朋友正忙着编写的“只是一个爱好”的操作系统，在所有事情的基础上，肯定没有遵循类似的命运。*

## 本周的节目中

*   **GitHub 使其 CLI 可扩展:**你已经听过(也经历过)太多次持续上下文切换的失败，所以毫不奇怪 GitHub 宣布 [GitHub 的命令行界面(CLI) 2.0 包括扩展](https://github.blog/2021-08-24-github-cli-2-0-includes-extensions/)。有了扩展，任何人都可以在 GitHub CLI 的核心功能上定制命令，并以你认为合适的方式扩展它。现在，您不必从终端切换到 web 浏览器来执行 GitHub 中的某些操作，而是可以创建一个扩展来完成。更好的是，如果其他人已经创建了您需要的扩展，您可以安装它。创建一个扩展就像构建一个以 gh-为前缀的存储库一样简单，在 CLI 中，您可以简单地运行“gh extension create”来构建一个预填充了预先编写的 Bash 的存储库。GitHub CLI 2.0 附带了一些示例扩展，如 [gh 用户状态](https://github.com/vilmibm/gh-user-status)、 [gh 分支](https://github.com/mislav/gh-branch)、 [gh 贡献](https://github.com/vilmibm/gh-contribute)、 [gh 屏保](https://github.com/vilmibm/gh-screensaver)和 [gh 分类](https://github.com/samcoe/gh-triage)，在[文档](https://docs.github.com/en/github-cli/github-cli/creating-github-cli-extensions)中有更多关于如何开始的信息。
*   **Kotlin 1.5.30 增加了对 Apple Silicon 的支持等等:**随着 Kotlin 1.5.30 的[发布，最新版本的 Java-alternative Kotlin 于本周发布，作为“Kotlin 1.6.0 之前的最后一个增量版本，它包括许多实验语言和标准库特性”，这些都是为 Kotlin 1.6.0 设计的。这意味着在它们被锁定之前，是时候尝试它们并分享反馈了。实验性的特性包括“密封 when 语句、对选择加入需求的更改、注释类的实例化、对 Duration 和 Regex stdlib APIs 的改进等等。”然而，除了实验之外，Kotlin 1.5.30 还增加了对苹果芯片的](https://blog.jetbrains.com/kotlin/2021/08/kotlin-1-5-30-released/)[原生支持](https://blog.jetbrains.com/kotlin/2021/08/kotlin-1-5-30-released/#kotlin-native)，Kotlin/JS IR 后端升级到 Beta 版的[，在多平台应用程序的共享原生代码中使用自定义 cinterop 库的能力，](https://blog.jetbrains.com/kotlin/2021/08/kotlin-1-5-30-released/#kotlin-js)[对 Kotlin Gradle 插件](https://blog.jetbrains.com/kotlin/2021/08/kotlin-1-5-30-released/#gradle)提供的 Java 工具链的支持，等等。

[https://www.youtube.com/embed/rNbb3A9IdOo?feature=oembed](https://www.youtube.com/embed/rNbb3A9IdOo?feature=oembed)

视频

*   **GitLab 为 macOS 添加测试版构建云:**很快，运行 macOS 的开发人员在使用 [GitLab](https://about.gitlab.com/?utm_content=inline-mention) 时，将不再需要托管自己的运行程序来执行 CI/CD 工作流。本周，该公司[推出了 git lab Build Cloud for MAC OS Beta](https://about.gitlab.com/blog/2021/08/23/build-cloud-for-macos-beta/)，它将为构建苹果产品提供一个按需平台，并与 GitLab SaaS CI/CD 集成。这些功能目前处于本月早些时候开始的有限测试版中，目标是在 2021 年 11 月 GitLab 14.5 中全面推出。用于 macOS 的 Build Cloud 将在 macOS VM 上托管 GitLab runner，在测试期间只有一种类型可用，提供 4 个 vCPUs、10 GB RAM 和 14 GB 存储空间用于构建。要加入免费的测试版，并且在测试期间不计入使用配额，请打开一个问题并请求访问。
*   **GitLab 14.2 增加 Markdown 预览，扩展 Gitpod 集成:**当我们谈论 GitLab 时，该公司还[发布了 GitLab 14.2](https://about.gitlab.com/releases/2021/08/22/gitlab-14-2-released/) ，它不仅增加了 macOS Build Cloud Beta，还为[提供了在编辑](https://about.gitlab.com/releases/2021/08/22/gitlab-14-2-released/#preview-markdown-live-while-editing)、[新 DevOps 采用指标](https://about.gitlab.com/releases/2021/08/22/gitlab-14-2-released/#track-use-of-dependency-scanning-and-fuzz-testing)和[扩展 Gitpod 集成](https://about.gitlab.com/releases/2021/08/22/gitlab-14-2-released/#launch-a-preconfigured-gitpod-workspace-from-a-merge-request)的同时预览 Markdown 的能力。关于这最后一点，GitPod 集成(之前在 GitLab 13.5 中介绍过)使得审查现有的合并请求比以往任何时候都更容易。现在，不需要在切换到目标分支并再次构建之前针对主分支构建一个环境，您可以直接从 merge request 页面启动 Gitpod。要开始，只需[启用 Gitpod 集成](https://docs.gitlab.com/ee/integration/gitpod.html#enable-gitpod-in-your-user-settings)。

*   **GitHub 变得透明:**又到了一年中的这个时候，GitHub 会公开所有 DMCA 的下架请求、用户信息披露、传票、法院命令、搜查令和其他类似信息，自 2014 年以来，它每年都会这样做。事实上，这是一年中这个时间的两倍，因为该公司现在说它每年做两次，以进一步增加其透明度。所以，如果你对这类事情的所有数据都感兴趣，那就去看看 GitHub 的 [2021 年透明度报告](https://github.blog/2021-08-25-2021-transparency-report-january-to-june/)，其中包括 1 月至 6 月的统计数据。在六个月的时间里，共有 172 项披露用户信息的请求，“102 张传票(96 张刑事传票和 6 张民事传票)，47 份法院命令，13 份搜查令，以及三项基于紧急情况的请求(与绑架、儿童剥削和炸弹威胁有关)。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>