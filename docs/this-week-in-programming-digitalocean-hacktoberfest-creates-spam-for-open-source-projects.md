# 本周节目:数字海洋黑客节为开源项目制造垃圾邮件

> 原文：<https://thenewstack.io/this-week-in-programming-digitalocean-hacktoberfest-creates-spam-for-open-source-projects/>

开源软件的一大好处是，任何人，只要受过一点教育，有一定的愿望，都可以成为贡献者。所以很明显，正确的做法是给那些潜在的贡献者一点点推动，也许是某种形式的奖励，让他们越过最初的门槛，对吗？

这是 DigitalOcean 的 hack toberfest(T1)背后的基本理念，开发者被要求在 10 月份对任何开源项目提出四次请求以获得奖励。虽然这个活动已经进行了七年，但今年的活动已经引起了不小的轰动(而且它开始才一天)，开源项目维护者抱怨说， [DigitalOcean 的 Hacktoberfest 非但没有帮助，反而伤害了开源](https://blog.domenic.me/hacktoberfest/)。

这篇由 whatwg/html 库[的开发者和开源维护者撰写的博客文章，继续指责 Hacktober fest 是“对开源维护者社区的企业资助的分布式拒绝服务攻击”，因为他在活动的第一个小时引用了近十几个垃圾邮件拉请求。](https://twitter.com/domenic)

“我最热切的希望是 DigitalOcean 能看到他们对开源社区造成的伤害，并结束 Hacktoberfest。我希望他们能尽快做到这一点，在 10 月份成为 2020 年地狱年的另一个低点之前，”德尼科拉写道。“2021 年，他们可以考虑将其作为一个选择加入项目重新推出，维护者同意在每个存储库的基础上处理这种 t 恤激励的贡献者。”

与此同时，博客作者 Joel Thoms 进一步[指出，YouTuber](https://joel.net/how-one-guy-ruined-hacktoberfest2020-drama) 是今年垃圾邮件数量大幅上升的原因，他指出，“这种低质量的公关垃圾邮件似乎来自拥有 67.2 万观众的 YouTuber，他在那里演示了对回购提出拉请求是多么容易，”视频演示的将项目称为“惊人的项目”的拉请求现在出现在 21，177 期上。

DigitalOcean 对围绕 Hacktoberfest 的争议做出了回应，承认“Hacktoberfest 参与者的至少 4%的 pull 请求被标记为‘无效’或‘垃圾邮件’。”“作为回应，该公司发布了今年活动的一些变化，允许项目选择退出该活动，并承诺如果发现用户向项目发送欺诈性的拉式请求，将禁止他们参加该活动和其他数字海洋活动，并承诺对未来的活动进行改变。对于受影响的维护者，该公司写道:“很抱歉，黑客节的这些意外后果给你们中的许多人带来了更多的工作。我们知道还有更多的工作要做，这就是为什么我们邀请您[加入我们的社区圆桌讨论](https://docs.google.com/forms/u/1/d/e/1FAIpQLSdb2uld_Ln43cWn0Xvfe64S59us38SHl510tHWafTRpctzXOA/viewform?usp=send_form)，我们承诺倾听您的想法并根据您的想法采取行动。”

至于你现在可以做的事情，GitHub 也加入了寻找解决方案的行列，使项目能够在一段时间内限制交互。

## 本周的节目中

*   **GitHub 获得集成代码扫描:**去年，GitHub 收购了 Semmle，这是一个语义代码分析引擎，旨在识别大型代码库中的代码模式，并搜索漏洞及其变体。现在，[公司完成了将这些功能作为原生工具引入 GitHub 的工作](https://github.blog/2020-09-30-code-scanning-is-now-available/)，并表示用户可以[在他们的公共存储库上启用这些功能](https://docs.github.com/en/github/finding-security-vulnerabilities-and-errors-in-your-code/enabling-code-scanning-for-a-repository)。该工具于今年早些时候首次发布测试版，但现在已经正式发布。该工具与 GitHub 操作或您现有的 CI/CD 管道一起工作，并在代码创建时使用 GitHub 的代码分析引擎 [CodeQL](https://securitylab.github.com/tools/codeql) 扫描代码。开发人员可以使用 2000 多种现有 CodeQL 查询中的任何一种来扫描他们的代码或编写自己的代码，并且代码扫描功能可以使用 [open SARIF 标准](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=sarif)进行扩展。到目前为止，GitHub 表示已经扫描了超过 12，000 个存储库，发现了超过 20，000 个安全问题。至于 CodeQL 查询，已经有 132 个社区做出了贡献，GitHub 表示，它已经“与十几家开源和商业安全供应商合作，允许开发人员在 GitHub 的本机代码扫描体验中，并行运行 CodeQL 和行业领先的 SAST、容器扫描和基础设施解决方案作为代码验证。”代码扫描功能对公共存储库是免费的，你可以在文档中了解更多。如果您感兴趣，CodeQL 查询列表的[贡献](https://github.com/github/codeql)将被接受。
*   **红帽更新了 Quarkus，提供了 OpenJDK 的构建:**红帽已经[提供了对](https://www.redhat.com/en/blog/red-hat-runtimes-update-delivers-new-features-open-hybrid-cloud)[红帽运行时](https://www.redhat.com/en/products/runtimes)中一些新特性的更新，这一次主要关注 Java。对于 Quarkus，Red Hat 的 Kubernetes-native Java 框架，该公司表示，它增加了一个 Quarkus 原生编译功能，“允许所有用户以原生模式运行 Quarkus，而不是在传统的 Java 虚拟机(JVM)中运行。”除此之外，它还增加了对 [Mandrel](https://github.com/graalvm/mandrel) 项目的全面支持，这是 GraalVM 的下游发行版，提供了原生编译支持，并为 Quarkus 提供了一个在 GraalVM 中引入新功能的地方。“通过 Mandrel，”他们写道，“我们能够将 GraalVM 捆绑在 OpenJDK 11 之上，”这“对 Quarkus 用户来说很重要，因为开发人员可以使用 GraalVM 将他们的 Quarkus 应用程序编译成本机二进制文件，以进一步优化云和 Kubernetes。”该公司还向 [Red Hat Data Grid](https://www.redhat.com/en/technologies/jboss-middleware/data-grid) 引入了许多新功能，突出强调了对在 [Red Hat OpenShift](https://www.openshift.com/) 中运行的数据网格集群的跨站点复制支持。最后，OpenJDK 8 的 Red Hat 版本增加了对 Java Flight Recorder 的支持，它“使开发人员和运营团队能够观察生产中的 Java 应用程序并为其生成报告，有效地完成 Java 应用程序环境中许多其他小型实用程序的工作，如 jhat、jmap 或 jps。”

*   **OpenJDK 迁移到 GitHub:** 说到 Java 和 OpenJDK，OpenJDK 已经[完成了向 GitHub](https://github.blog/2020-09-30-github-welcomes-the-openjdk-project/) 的迁移，作为其迁移工作的一部分，代号为项目[【Skara】](https://openjdk.java.net/projects/skara)，将 [JDK 16 主线开发](https://github.com/openjdk/jdk)带入 GitHub。此前，该项目一直在 Mercurial 服务器上自托管，迁移到 GitHub 是由 Oracle 的 Java 平台组实现的。现在，GitHub 提供了一个迁移如何完成的高峰，写道“这比仅仅进行 hg-fast-export 和 git push 要复杂得多”，团队建立了“自定义 CLI 工具，与 OpenJDK 邮件列表的双向桥接，以及与 OpenJDK bug 跟踪系统的集成”，并致力于为他们的 CI 构建采用 GitHub 操作——所有这些都是[开源的](https://github.com/openjdk/skara),可在 [OpenJDK GitHub 组织](https://github.com/openjdk)中获得。
*   **使用面向 Python 的剧作家进行端到端测试预览:**微软[宣布了](https://devblogs.microsoft.com/python/announcing-playwright-for-python-reliable-end-to-end-testing-for-the-web/)[面向 Python 的剧作家](https://github.com/microsoft/playwright-python)的预览，这是一款用 Python 编写端到端测试的工具，可以自动进行 UI 交互，并可以在所有现代 web 浏览器上验证您的应用程序的功能。面向 Python API 的剧作家紧随今年早些时候发布的面向 JavaScript 的剧作家之后。除了对已部署的应用程序运行这些测试，您还可以使用[剧作家 GitHub Action](https://github.com/marketplace/actions/run-playwright-tests) 或[其他 CI/CD 提供商的工具](https://playwright.dev/#path=docs%2Fci.md&q=)在您的 CI/CD 管道中运行它们。你可以在 GitHub 上找到 Python 的剧作家[，并在 GitHub 问题](https://github.com/microsoft/playwright-python)上或在剧作家 Slack 社区上分享反馈或功能需求。

红帽是新堆栈的赞助商。

通过获得的特征图像[太棒了。](https://www.teefantastic.com/stay-at-127-0-0-1)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>