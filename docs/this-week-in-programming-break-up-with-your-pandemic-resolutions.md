# 本周节目:放弃你的疫情计划

> 原文：<https://thenewstack.io/this-week-in-programming-break-up-with-your-pandemic-resolutions/>

我知道，我知道。你被解雇了，或者被派在家工作，你立刻对自己说“有了这些额外的时间，我将完成这么多事情！”什么，没有通勤，没有人在你的办公桌旁停下来聊天来分散你的注意力，你将不会分心！你报名参加了一直磨磨蹭蹭的 Python 课程，重新开始了已经搁置多年的个人兼职项目，为你一直认为没有时间去做的日常练习准备好了瑜伽垫，并准备去追求它…

…然后什么都没发生。

就我个人而言，我有过短暂的高效和专注时期，但它们更多的时候是例外而不是规律。即使在最好的情况下，在家上网工作也会让人分心，至少现在不是最好的时候。有了 Twitter、脸书、Reddit 和任何你喜欢的新闻来源，焦点在此刻是一种珍贵的商品，我来找你没有什么建议，除此之外，我们可能不得不接受这个事实。

也就是说，如果你列出了一个自我改善的清单，并且没有划掉任何一件事情，这是可以的。在你的生活中，你已经打破了不止一个新年决心，所以在你对自己做出的疫情承诺上给自己一些宽容也没什么不寻常的。如果没有别的事情，嘿，至少 GitHub 这个星期宕机了，所以你也可以用这个作为借口。

https://Twitter . com/xCptJackSparrow/status/1245812949165342721

## 本周的节目中

*   **GitLab 将 18 个付费功能移至开源:**本周，GitLab 宣布 [18 个功能移至开源](https://about.gitlab.com/blog/2020/03/30/new-features-to-core/)，涵盖了整个软件开发和交付生命周期的大部分内容。在一封电子邮件中，产品管理 GitLab EVP，Scott Williamson 告诉我们，这些功能“涵盖了软件开发生命周期的许多方面，包括项目规划、开发、设计管理、服务台管理、包管理、Kubernetes 管理和发布管理。”虽然这一举措已经获得批准，但 GitLab 并不打算独自完成，它正在寻求社区的帮助。该公司写道，“如果在核心/免费版中拥有这一功能对您很重要，我们邀请您贡献自己来加速这一过程。我们不只是允许您帮助我们移动这些代码，我们是在请求您帮助我们移动这些代码。”
*   **TypeScript 3.9 Beta 带来更快的编译时间:**微软发布了 [TypeScript 3.9 Beta](https://devblogs.microsoft.com/typescript/announcing-typescript-3-9-beta/) ，称该版本专注于“性能、完善和稳定性”据 InfoWorld 报道，最引人注目的特点是它将[大幅削减编译时间](https://www.infoworld.com/article/3535211/typescript-39-slashes-compile-times-for-packages.html)，解决“与一些软件包相关的极差的编辑和编译速度”InfoWorld 写道，这一努力已经导致了“编译时间的显著减少——例如，在 material-ui 的情况下，大约减少了 40%”,并指出 TypeScript 3.9 的产品发布预计在 5 月 12 日。JAXEnter 还写了新版本，指出了[编辑器的改进](https://jaxenter.com/typescript-3-9-beta-170481.html)以及编译时间，还强调了微软写道“虽然最初计划在 3.9 版本中推出'[等待类型](https://github.com/microsoft/TypeScript/pull/35998)，但它将不得不等待更长时间，”因为“许多代码受到等待的影响，我们已经决定我们需要取消该功能，以确保我们可以在以后更顺利地推出它……”

*   **StackOverflow 变暗:**变暗，也就是说，以你们 troglodyte 开发人员一直要求的方式——它在过去的一周开启了它的黑暗模式，并写了一篇博客文章，探讨[在 StackOverflow 上构建黑暗模式的困难](https://stackoverflow.blog/2020/03/31/building-dark-mode-on-stack-overflow/)，顺便说一下，它说这是“Stack Overflow 的元社区(共 41，785 个问题)上投票最多的第 12 个问题,也是所有功能请求中投票最多的第 1 个问题所以，高兴吧，因为你终于如愿以偿了。要打开它，只需前往您的[用户首选项](https://stackoverflow.com/users/preferences/current)。
*   **Kubernetes IDE:**对于那些不幸的、神话般的“全栈”开发人员来说，他们不仅要编码，还要管理 Kubernetes，本周有一个解决方案正在流传: [Lens](https://k8slens.dev/) 称自己为“Kubernetes IDE”，它是一个适用于 MacOS、Windows 和 Linux 的独立应用程序，提供可见性、实时统计、日志流和实际故障排除功能，以及全面管理您的 Kubernetes 集群的能力。在麻省理工学院许可下发布的[，Lens 提供内置的普罗米修斯统计，管理多个集群和多个工作区的能力，以及内置的“上下文感知终端”。但是不要相信我们的话，听听这个奇怪的机器人女士告诉你它是如何工作的。](https://github.com/lensapp/lens)

[https://www.youtube.com/embed/04v2ODsmtIs?feature=oembed](https://www.youtube.com/embed/04v2ODsmtIs?feature=oembed)

视频

*   **“Visual Studio 代码的真正开源替代方案”:**说到 ide，[我们在本周早些时候写了](https://thenewstack.io/eclipse-theia-offers-a-true-open-source-alternative-to-visual-studio-code/)关于 [Eclipse 忒伊亚](https://theia-ide.org/)代码编辑器的第一个生产就绪版本，Eclipse 基金会称该版本为寻求构建自己的 ide 的公司提供了“Visual Studio 代码的真正开源替代方案”。很可能你已经在不知不觉中遇到了忒伊亚，因为它已经成为 Red Hat 的 [CodeReady Workspaces](https://developers.redhat.com/products/codeready-workspaces/overview) ，Eclipse Foundation 自己的 [Eclipse Che](https://www.eclipse.org/che/) 和 [Google Cloud Shell](https://cloud.google.com/shell) 的基础。忒伊亚的一个吸引人的特性是，它与所有的 Visual Studio 代码扩展完全兼容，从一开始就提供了大量的语言支持。虽然忒伊亚可以通过一些工作编译成一个独立的 IDE，但现在它主要专注于成为众多垂直领域的新 IDE 的基础。
*   **谷歌开放代码搜索:**谷歌决定为谷歌开源项目开放[代码搜索，称其为他们“最受欢迎的内部工具”之一代码搜索让你可以使用正则表达式搜索代码，通过语言和交叉引用等过滤，并提供你在使用谷歌时所体会到的“键入即建议”的体验。查看](http://opensource.googleblog.com/2020/04/code-search-for-google-open-source.html)[快速参考](https://developers.google.com/code-search/reference)，了解你可以搜索的所有方法。现在，代码搜索开始支持 Angular，Bazel，Dart，Flutter，Go，Tensorflow 和其他几个，随着时间的推移，其他人预计会增加。
*   **科技对抗新冠肺炎:**上周最后一次，上周推出了更多资源来帮助你们科技人员对抗新冠肺炎，我们希望在回到你们之前安排的网飞狂欢会议之前快速提供这些资源。首先，谷歌[启动了一个新冠肺炎公共数据集项目](https://www.programmableweb.com/news/google-launches-covid-19-public-datasets-program/brief/2020/03/31)，让研究人员和教育工作者免费访问公共数据集的托管库，包括[约翰霍普金斯系统科学与工程中心](https://console.cloud.google.com/marketplace/details/johnshopkins/covid19_jhu_global_cases?filter=solution-type:dataset&q=covid&id=430e16bb-bd19-42dd-bb7a-d38386a9edf5)、世界银行的全球健康数据和 [OpenStreetMap](https://www.programmableweb.com/company/openstreetmap) 数据。对于那些充斥着数据却没有处理能力的人来说，总会有量子计算，对吧？Techcrunch 写道 [D-Wave 让任何致力于回应新冠肺炎的人都可以免费使用其量子计算机](https://techcrunch.com/2020/03/31/d-wave-gives-anyone-working-on-responses-to-the-covid-19-free-access-to-its-quantum-computer/)。“这一提议不仅仅对那些专注于新药的人有效，”他们写道，“而且对致力于解决当前危机的任何方面的任何研究或团队开放，无论是后勤、病毒传播建模还是研究新的诊断方法。”最后，IBM 提供了“公民沃森助手”来回答新冠肺炎的问题，据说已经被许多政府机构使用。

GitLab 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>