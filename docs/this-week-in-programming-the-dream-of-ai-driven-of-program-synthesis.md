# 本周编程:人工智能驱动的程序合成之梦

> 原文：<https://thenewstack.io/this-week-in-programming-the-dream-of-ai-driven-of-program-synthesis/>

对于每一个程序员来说，编写能够让[完全自动化](https://www.theatlantic.com/technology/archive/2018/10/agents-of-automation/568795/)他们所做的事情的代码可能有点梦想,这样他们就可以什么都不做而获得报酬……对吗？然而，从某种意义上说，当程序员被完全取代并自动离职时，这个梦想就变成了一场噩梦。

不要担心，我们还远未实现这一目标，但[麻省理工学院本周在自动化代码创建的道路上又迈出了一步，它编写了一个名为](http://news.mit.edu/2019/toward-artificial-intelligence-that-learns-to-write-code-0614) [SketchAdapt](https://arxiv.org/pdf/1902.06349.pdf) 的新程序编写人工智能，它“学习如何编写简短的高级程序，同时让第二套算法找到合适的子程序来填充细节。”

“与自动化程序编写的类似方法不同，SketchAdapt 知道何时从统计模式匹配切换到效率较低但更通用的符号推理模式，以填补空白，”他们写道。“SketchAdapt 不是依靠专家来定义程序结构，而是使用深度学习来计算程序结构。研究人员还增加了一个转折:当神经网络不确定将什么代码放在哪里时，SketchAdapt 会被编程为留下空白，供搜索算法填充。

SketchAdapt 程序是由麻省理工学院[计算机科学和人工智能实验室](https://www.csail.mit.edu/) (CSAIL)的教授阿曼多·索拉-莱萨马创建的。这个名字听起来可能很熟悉，因为这不是他第一次涉足这个领域——他首先创建了 [Sketch](https://people.csail.mit.edu/asolar/papers/Solar-Lezama09.pdf) ，这是“基于这样一种想法，即如果提供一个高级结构，可以机械地找到程序的低级细节”，并看到了“自动给编程作业评分并将手绘图表转换为代码的副产品”

对于那些对幕后更感兴趣的人来说，这个视频展示了太阳能莱萨马公司的一堂课，讲的正是这些想法，但是……十年前:

## 本周的节目中

*   **Visual Studio Code for Java:** 虽然第一个 Visual Studio Code 的 Java 语言服务器是在几年前的一次黑客马拉松中开发的，但微软现在已经通过[发布了 Visual Studio Code installer for Java](https://devblogs.microsoft.com/visualstudio/announcing-visual-studio-code-java-installer/)使它成为官方的。在博文中，微软吹嘘了其最近对 Java 的承诺，指出微软 Azure 在 2018 年成为了 [AdoptOpenJDK](https://adoptopenjdk.net/) 项目的[白金赞助商](https://adoptopenjdk.net/sponsors.html)，并称之为“我们的一个转折点，我们还增加了一个功能，以检测和帮助开发者在他们的环境中安装 JDK 二进制文件，并将 AdoptOpenJDK 作为推荐的发行版。”因此，面向 Java 开发人员的 Visual Studio 代码的[安装程序](https://aka.ms/vscode-java-installer-win)，它“自动检测您的本地开发环境中是否有基本组件，包括 JDK、Visual Studio 代码和必要的 Java 扩展。”安装程序将检测并安装所有需要的工具，但是如果你想了解更多关于如何开始的信息，请查看他们的教程[。目前，该安装程序可用于 Windows 的](https://code.visualstudio.com/docs/java/java-tutorial)[下载](https://aka.ms/vscode-java-installer-win)，macOS 版本也即将推出。
*   **Java(以及更多)也加入了 App Engine:**当我们在这里谈论 Java 的时候，谷歌也在测试版中为 App Engine 添加了 [Java 11 运行时。现在，开发者可以使用 Java 编程语言的最新](https://cloud.google.com/blog/products/application-development/turn-it-up-to-eleven-java-11-runtime-comes-to-app-engine)[长期支持版本](https://www.oracle.com/technetwork/java/java-se-support-roadmap.html)在 Google App Engine 上开发和部署你的应用。谷歌指出，Java 11 运行时不再提供基于 Servlet 的运行时，这意味着你需要将服务器与你的应用捆绑在一起，让你自由选择你想要的任何库或框架，如 [Spring Boot](https://spring.io/projects/spring-boot) 、 [Vert.x](https://vertx.io/) 、 [SparkJava](http://sparkjava.com/) 、 [Ktor](https://ktor.io/) 、 [Helidon](https://helidon.io/#/) 或 [Micronaut](https://micronaut.io/) 。除了 Java，App Engine 还将内存增加了一倍，并将 Go 1.12 和 PHP 7.3 添加到其第二代运行时列表中，“这让你可以使用任何语言库，直接访问网络，并连接到谷歌云 VPC 网络，给你一个更习惯的开发者体验，支持原生模块和更快的执行速度。”去年发布的第二代运行时包括 Node.js 10、PHP 7.2、Python 3.7 和 Ruby 2.5(alpha)——现在是 Java 11、Go 1.12 和 PHP 7.3。

*   GitHub 包注册取消删除，增加测试版测试人员:GitHub 的[新发布的包注册](https://github.blog/2019-05-10-introducing-github-package-registry/)在一个月的测试后做了一些[更新](https://github.blog/2019-06-19-updates-to-github-package-registry/)，首先是删除其他项目可能依赖的包的功能。“当一个项目依赖于一个包时，”他们写道，“只要项目需要，包就应该是可用的。为了避免破坏可能依赖于某个包的项目，GitHub 包注册表不再支持通过 GitHub UI 或 API 删除包或版本。在特殊情况下，用户可以通过 GitHub 支持创建删除软件包的请求，我们将与作者合作解决他们的问题。”除了禁止删除，该公司还在测试程序中增加了 2000 个额外的账户，更多账户正在增加。

*   **GitHub 通过收购 Pull Panda 提供代码评审:** GitHub 表示，在收购 [Pull Panda](https://pullpanda.com/github) 后，它现在为[提供了一种更好的代码评审协作方式](https://github.blog/2019-06-17-github-acquires-pull-panda/)，这有助于团队“在 GitHub 上创建更高效和有效的代码评审工作流”该工具提供了三个特性:拉式提醒、协作者需要评审时的松弛提醒、拉式分析和拉式分配器，后者自动在团队中分发代码。这三个功能现在作为一个 GitHub Marketplace 应用程序——Pull Panda——免费提供，GitHub 正在努力将它们完全集成。DevClass [在谈到收购](https://devclass.com/2019/06/18/github-acquires-pull-panda-pushes-toolset-for-free/)时写道，Pull Panda 并不是第一家，GitHub 在 2014 年收购了 WYSIWYG 网页设计工具 Easel，在 2011 年收购了 Ordered List，在去年成为微软的一部分后又收购了 Spectrum 和 Dependabot。

[https://www.youtube.com/embed/RtZdbZiPeK8?feature=oembed](https://www.youtube.com/embed/RtZdbZiPeK8?feature=oembed)

视频

*   **GitLab 用限定范围的问题标签帮助工作流程:**git lab 很快看到了另一面，推出了[限定范围的问题标签](https://about.gitlab.com/2019/06/20/issue-labels-can-now-be-scoped/)，它承认这可能看起来“太小了，不足以引起轰动”，但表示值得关注，因为它“可能有助于减少周期时间”基本上，使用范围标签，“团队可以将互斥标签(共享相同范围)应用于问题、合并请求或 epic，解决定制字段和定制工作流状态用例。范围标签使团队可以定义一个基本的自定义字段，以避免混淆并清理问题列表(即减少重复标签)。”与其写更多的东西，这里有一个快速的视频来解释。

[https://www.youtube.com/embed/4BCBby6du3c?feature=oembed](https://www.youtube.com/embed/4BCBby6du3c?feature=oembed)

视频

*   随着 iOS 和 Android 客户端网络库 [Envoy Mobile](https://envoy-mobile.github.io/) 的发布， Envoy Proxy 已经[移动化](https://eng.lyft.com/announcing-envoy-mobile-5c2067d9ade0)。Envoy 背后的公司 Lyft 解释说，Envoy 最初是本着“网络应该对应用程序透明”和“当网络和应用程序出现问题时，应该很容易确定问题的根源”的想法发布的，但“现实是，如果移动应用程序的用户只能在一小部分时间内完成所需的产品流，服务器端边缘的三个 9 是没有意义的。”因此，Lyft 正在推动 Envoy 超越边缘，进入移动设备，其中 Envoy Mobile 与数据中心中的 Envoy 一起，将扩展到“整个分布式系统网络，而不仅仅是服务器端部分。”Envoy Mobile 旨在直接编译到 iOS 和 Android 的客户端移动应用程序中。
*   npm 将令牌安全和卫生扩展到 GitHub:JavaScript 包管理器 npm 的管理员表示，现在[将与](https://blog.npmjs.org/post/185680936500/protecting-package-publishers-npm-token-security) [GitHub 的令牌扫描合作计划](https://developer.github.com/partnerships/token-scanning/)合作，将令牌安全和卫生扩展到 GitHub 。现在，他们写道，“每当你在公共存储库中提交或推送对 GitHub 的更改，并且在更改中发现 npm 令牌，它就被发送到 npm 进行验证。如果它有效，我们将撤销它，并通过电子邮件通知维护者这一行动。”

图片由 Pixabay 的 Tumisu 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>