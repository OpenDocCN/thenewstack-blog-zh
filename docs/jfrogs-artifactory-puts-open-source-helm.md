# JFrog 的 Artifactory 如何让开源掌舵

> 原文：<https://thenewstack.io/jfrogs-artifactory-puts-open-source-helm/>

在本期 [The New Stack Makers](/tag/the-new-stack-makers/) 播客中，我们将探讨 JFrog 如何将开源放在其 Artifactory repository manager 的最前沿。我们听到 [Artifactory](https://www.jfrog.com/artifactory/) 如何帮助开发人员在 CI/CD 管道中充分利用 Docker 容器，开发人员在使用容器时可能面临的挑战，以及 Java 软件开发如何帮助 Artifactory 的工作流管理方法奠定基础。在 OSCON 2016 期间，New Stack 创始人 Alex Williams 接受了 JFrog 开发者倡导者 [Baruch Sadogursky](https://www.linkedin.com/in/jbaruch) 的采访。

[JFrog 的 Artifactory 如何开源掌舵](https://thenewstack.simplecast.com/episodes/how-jfrogs-artifactory-puts-open-source-at-the-helm)

在 YouTube 上也能听到对话[。](https://www.youtube.com/watch?v=NKhU90-E2SI)

开源是 JFrog 的开源存储库管理工具 Artifactory 创建的基础。Sadogursky 清楚地表明，如果没有开源的发展，很可能就没有 Artifactory。

“15 年前，我们已经有了不错的依赖管理，允许人们在日常开发中使用开源。当时的情况是，这些依赖项和开源库都是从互联网上直接下载的。Sadogursky 说:“虽然它使他们变得非常非常容易接近，并增加了开源在组织内部的使用，但它也有自己的缺点，主要是在使用开源的管理和可用性方面。

Artifactory 向用户提供了一个[开源](https://sourceforge.net/projects/artifactory/)和一个[企业版](https://jfrog.com/artifactory/)，Sadogursky 指出，该平台最受欢迎的版本是其开源产品。JFrog 也身体力行，Artifactory 的依赖项 100%可供开源社区使用。“我们站在开源的基础上。这就是我们存在的原因，也是我们所提倡的，”Sadogursky 指出。

Jfrog 为那些在 Artifactory 和 JFrog 的 [Bintray](https://www.jfrog.com/bintray/) 分发平台的开发工作流中使用容器的人提供了 [Docker](http://docker.com) 集成，这在 CI/CD 管道中特别有用。Sadogursky 继续解释说，虽然有许多不同的方式与 Docker 的工作都有自己的优点。毕竟，很难制作一个在很长一段时间内保持稳定的 Docker 文件。

Sadogursky 说:“如果你在一个月后运行相同的 Docker 版本，你会得到相同的 Docker 映像的可能性非常非常低。”

JFrog 的最终目标是提供 Artifactory 来替代这项费力又困难的任务。Sadogursky 指出，建立一个形象，并以此作为所有其他形象的标准，是其吸引力的一部分。

“我们为使用 Artifactory 的开发人员提供的是不可变的、稳定的 Docker 映像的升级，您只需构建一次，然后通过 CI/CD 管道进行升级。确保您构建、测试和准备的映像与您在生产中运行容器的映像完全相同。虽然这看起来很明显，但实现起来并不容易，”他说。

第一资本公司和 T4 码头公司是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>