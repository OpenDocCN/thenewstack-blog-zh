# 本周节目:《我的世界》走向开源

> 原文：<https://thenewstack.io/this-week-in-programming-minecrafts-move-to-open-source/>

上周，我们稍微绕了一点弯子，进入了关于可视化编程语言的辩论，最后以一个流传的视频结束。与其描述视频，不如再分享一遍。值得，如果你没看过的话:

[https://www.youtube.com/embed/H-U96W89Z90?feature=oembed](https://www.youtube.com/embed/H-U96W89Z90?feature=oembed)

视频

没错，这是 Gameboy 游戏[口袋妖怪红](https://en.wikipedia.org/wiki/Pok%C3%A9mon_Red_and_Blue)的全部，完全用《我的世界》代码块编写。你敬畏吗？我知道我肯定是。而这还只是[的冰山一角](https://www.youtube.com/user/sethbling)，真的。还有一个用《我的世界》代码块编程的雅达利 2600 模拟器。有一台[摄像机](https://youtu.be/xgA1wrkMe4U)。除此之外，我们还会做更多的链接，但是可以说《我的世界》是编程世界中一股有趣而强大的力量。

(点击上面的推文可以看到，是的，《我的世界》是编程顿悟的终极。)

现在，我明白如果你不是迫不及待地想在《我的世界》境内编写你的下一个项目(毕竟，再造口袋妖怪红只花了 21 个月。)但是也许你想使用一些用来构建《我的世界》的代码，这就是我们本周在这里讨论的[:](https://www.altchar.com/games-news/578587/minecraft-making-two-of-its-libraries-open-source)[《我的世界》团队已经开始开源其代码库](https://minecraft.net/en-us/article/programmers-play-minecrafts-inner-workings)。

根据这篇博文，他们正在开始向你认为合适的任何用途开放不同的独立图书馆，只要你给他们信任。根据麻省理工学院的许可，第一批被开源的两个库是 [DataFixerUpper](https://github.com/Mojang/DataFixerUpper) ，它“确实像它听起来的那样，并且是《我的世界》游戏引擎最重要的部分之一”和[准将](https://github.com/Mojang/brigadier)，游戏的命令引擎。第三个库 Blaze3D 正在考虑成为开源库。

因此，如果你准备好了获得启迪，按照上面嵌入的迷因，你的开源能力就在路上了。(现在，我们将跳过关于这些语言排序是否正确的辩论。)与此同时，这里是我们上周在编程领域看到的其他内容。

## 本周的节目中

*   ML.NET 增加 API&更多:继续向最终的 1.0 版本进军，微软[宣布了 ML.NET 0.6](https://blogs.msdn.microsoft.com/dotnet/2018/10/08/announcing-ml-net-0-6-machine-learning-net/)，这是其跨平台、开源机器学习框架的最新版本。NET 开发人员。他们将该版本分为三个主要功能:用于构建和使用机器学习模型的新 API，对预训练 ONNX 模型进行评分的能力，模型预测的显著性能改进。NET 类型系统一致性等等。这篇文章对每一个都进行了更详细的介绍，但简短的版本是，这些 API 支持新的任务和代码工作流，这是以前的 LearningPipeline API 所无法实现的。至于 ONNX 模型，它们现在加入了 0.5 版本中添加的 TensorFlow 模型，[性能改进](https://blogs.msdn.microsoft.com/dotnet/2018/10/08/announcing-ml-net-0-6-machine-learning-net/#performance-improvements)包括一些大幅加速。
*   **Visual Studio Code 九月发布:**微软保持了每月对 Visual Studio Code 的稳定宣传，在[本月发布的](https://code.visualstudio.com/updates/v1_28)中提供了许多小更新，包括 windows 上新的自定义标题和菜单栏。根据这篇博文，亮点包括一些有用的小功能，比如能够[回到你上次编辑的网站](https://code.visualstudio.com/updates/v1_28#_navigate-to-last-edit-location)，[将你的代码片段定制到一个工作区](https://code.visualstudio.com/updates/v1_28#_project-level-snippets)，[更好的降价折叠](https://code.visualstudio.com/updates/v1_28#_better-markdown-folding)，以及一些 [Git 改进](https://code.visualstudio.com/updates/v1_28#_git-integration)。此外，微软还宣布了针对 Visual Studio 代码的 [Python 扩展的 9 月发布，它说这将关闭总共 45 个现有问题。已解决的问题包括在分割终端中对 Python 环境的支持、在终端中自动激活环境，以及对内置断点()的调试器支持。该公告还表示，新版本已经致力于减少 Python 语言服务器的 CPU 和内存消耗。](https://blogs.msdn.microsoft.com/pythonengineering/2018/10/09/python-in-visual-studio-code-september-2018-release/)
*   **GitHub 安全警报背后:**为下周的 [GitHub 宇宙](https://githubuniverse.com/)做准备，该公司正在拉开帷幕，一窥内部运作。根据一篇关于如何将机器智能应用于 GitHub 安全警报的博客文章，该公司“创建了一个机器学习模型，它扫描与公共提交(提交消息和链接的问题或拉请求)相关的文本，以过滤出那些与可能的安全升级相关的内容。”然后，该模型“在特定的时间范围内聚合，以获得一个安全版本可能影响的所有依赖关系的整体视图”，并“输出一个它认为需要警报并且当前没有被我们系统中任何已知的 CVE 覆盖的软件包和版本范围的列表。”我们当然希望这将比亚马逊厌恶女性的机器学习模型更有效。

*   **Travis CI 对 Windows 支持感到兴奋:**似乎 Travis CI 的用户对 [Windows 支持的早期发布感到兴奋](http://blog.travis-ci.com/2018-10-11-windows-early-release)，这意味着他们现在可以在 Linux、Mac 和 Windows 上运行测试——所有这些都在同一个版本中。根据公告，Windows 可以在 travis-ci.org 的[或 travis-ci.com 的](https://travis-ci.org/)[或](https://travis-ci.com/)上用于开源和私有项目，企业支持也在路上。他们说 [npm](https://www.npmjs.com/) 同样对 Windows 感到兴奋，因为“超过 40%的 npm 用户在 Windows 机器上安装它，但是直到今天只有极小一部分软件包在 CI 中积极运行 Windows 测试。将 Windows 支持添加到 Travis CI 将为 JavaScript 社区的一大部分提供更稳定的开发体验 npm 注册表中 32%的项目使用 Travis CI。”目前，Windows 构建环境支持 Node.js、Rust 和 Bash 语言，预计 2019 年 Q2 将发布稳定版本，届时他们也将发布 Windows 构建环境企业版。
*   **谷歌为用户提供粒度控制:**随着该公司宣布(最终)将[终止其有缺陷的社交实验](https://www.blog.google/technology/safety-security/project-strobe/)(在发现一些固有的安全缺陷后)，谷歌宣布[通过谷歌 OAuth 和 API](https://developers.googleblog.com/2018/10/more-granular-google-account.html)获得更粒度的谷歌账户权限。所有权限将不再列在一个单独的权限对话框中，而是“将在自己的对话框中一次显示一个应用程序请求的每个权限”，并且“用户将能够单独授予或拒绝权限。”因此，开发人员应该审查他们的应用程序，以确保它们符合[谷歌 API 服务:用户数据政策](https://developers.google.com/terms/api-services-user-data-policy)中的指导原则，并考虑几个设计建议，例如仅在需要时请求权限，而不是在安装应用程序时一起请求。
*   **最新消息:** Mozilla 希望我们都知道，JavaScript 和 WebAssembly 之间的[调用终于快了](https://hacks.mozilla.org/2018/10/calls-between-javascript-and-webassembly-are-finally-fast-%f0%9f%8e%89/)。根据 Mozilla Hacks 上的一篇博客文章，使 JavaScript 和 WebAssembly 容易结合一直是 Mozilla 的一大优先事项，但两种语言之间的函数调用阻止了这一点。长话短说，他们现在很快，他们有大约 3000 多个单词和非常有趣的图形，关于为什么和如何在背后，所以点击查看所有血淋淋的细节。
*   **关注 Spinnaker:** 最后，本周，TechCrunch 建议我们所有人 [Spinnaker 是下一个值得关注的大型开源项目](https://techcrunch.com/2018/10/09/spinnaker-is-the-next-big-open-source-project-to-watch/)。 [Spinnaker](https://www.spinnaker.io/) ，如果你不熟悉的话，是网飞和谷歌去年 7 月推出的开源持续交付(CD)平台。然而，现在该项目宣布了一个“正式的治理系统”，TechCrunch 建议该系统可以成为事实上的标准，就像 Kubernetes 一样。

微软是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>