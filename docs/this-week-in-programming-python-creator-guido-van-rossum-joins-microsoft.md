# 本周编程:Python 创造者 Guido Van Rossum 加入微软

> 原文：<https://thenewstack.io/this-week-in-programming-python-creator-guido-van-rossum-joins-microsoft/>

周四， [Guido Van Rossum](https://en.wikipedia.org/wiki/Guido_van_Rossum) ，Python 编程语言的创造者，结束了他在 T2 的短暂退休，加入了微软的开发者部门。

这个消息带来了一连串的祝贺和功能请求，尽管一些建议的功能确实已经存在，[已经存在。其他人仍然遇到了](https://twitter.com/gvanrossum/status/1327005853501726720)[信息丰富的回复](https://twitter.com/zooba/status/1327008431723716608)，这使得产生的帖子值得一读，特别是如果你正在 Twitter 上寻找编程语言世界的快速“谁是谁”。微软的米格尔·德·伊卡萨指出，这一新成员加入了该公司正在增长的语言设计者和贡献者的名单。

那么，我们能从这一切中期待什么呢？这是一个[公司对开源](https://twitter.com/BrideOfLinux/status/1327298934868414464)的收购吗，就像长长的回复列表中更后面的一些人似乎总是暗示的那样？还是微软在策划所有语言的弗兰肯斯坦，一点这个，一点那个？

十有八九，你们这些使用微软产品的 Python 开发者在不久的将来可能会有一些好的特性值得期待，仅此而已，但是总会有挥之不去的恐惧…尤其是当涉及到微软的时候。正如范罗森建议的，敬请关注。

## 本周的节目中

*   **Visual Studio Code 为非 Python 用户引入了一个 Jupyter 扩展:**虽然 Visual Studio Code 已经在去年通过 [Python 扩展](https://code.visualstudio.com/docs/python/jupyter-support)提供了 Jupyter 笔记本支持，但其他想要使用 Jupyter 笔记本的非 Python 开发人员现在可以通过 Visual Studio Code 的新 [Jupyter 扩展](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)来实现，它[本周与 VS Code 的【2020 年 11 月发布](https://devblogs.microsoft.com/python/introducing-the-jupyter-extension-for-vs-code/)一起引入了。他们写道，新的扩展将为 R、Julia 和 Scala 等语言的用户提供“同样丰富的 Jupyter 笔记本体验”，并将使“为 Python 以外的语言构建新的 Jupyter 体验更加容易。”新的扩展为当今 Jupyter 笔记本支持的任何语言内核提供了基本的笔记本支持，并在 GitHub 上的 MIT 许可下可用[。首先，安装](https://github.com/microsoft/vscode-jupyter) [VS Code Insiders build](https://code.visualstudio.com/insiders) 、 [Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) 和您选择的语言的 Jupyter 内核。
*   **。NET 5.0 带来 C# 9，F# 5 &更多:**带[。NET Conf 2020](https://devblogs.microsoft.com/dotnet/net-5-0-launches-at-net-conf-november-10-12/) 这上周，微软也[宣布。NET 5.0](https://devblogs.microsoft.com/dotnet/announcing-net-5-0/) ，其中包括 [C# 9](https://devblogs.microsoft.com/dotnet/c-9-0-on-the-record/) 、 [F# 5](https://devblogs.microsoft.com/dotnet/announcing-f-5/) 、[ASP.NET 内核](https://devblogs.microsoft.com/aspnet/announcing-asp-net-core-in-net-5/)和 [EF 内核](https://devblogs.microsoft.com/dotnet/announcing-the-release-of-ef-core-5-0/)。目前[可供下载](https://dotnet.microsoft.com/download/dotnet/5.0)。NET 5.0 是微软的第一个版本。NET 统一之旅”,该公司正在“统一。NET 集成到一个产品体验中，同时使您能够只选择。你想用的. NET 平台。”虽然他们说他们曾打算用。NET 5.0，疫情给这个计划带来了一点麻烦，所以现在它将被推广。NET 5.0 和。NET 6.0。这里有很多内容可以阅读，包括每种语言版本的一系列新功能，所以请确保点击查看更多内容。但是在你进入下一部分之前，还要注意 AWS 已经提供了自己的关于[的博客文章。AWS 上的. NET 5 以及支持该版本的各种服务和工具。](https://aws.amazon.com/blogs/developer/net-5-on-aws/)

*   **GitHub 将要求基于令牌的认证:**微软新闻的另一点，该公司已经[表示](https://devblogs.microsoft.com/visualstudio/a-more-secure-github-experience/)在 11 月 13 日，GitHub 和 Visual Studio 都将“在使用 REST API 认证时不再接受帐户密码，而是要求使用基于令牌的认证(例如，个人访问或 OAuth)，用于 GitHub.com 的所有认证操作。”
*   **Visual Studio 2019 获得“Git 体验”:**在我们离开微软之前，还有一个重大发布要提到，那就是 [Visual Studio 2019 v16.8](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-v16-8/) ，它带来了围绕 IntelliCode 的改进。NET、XAML 和 Web 工具，以及[“Git 体验”](https://devblogs.microsoft.com/visualstudio/announcing-the-release-of-the-git-experience-in-visual-studio/)的发布和 C++20 的一致性。在这个版本中，默认情况下 Git 是打开的，您可以从 Git 菜单中克隆、创建或打开存储库，还可以使用集成的 Git 工具窗口来提交和推送对代码的更改，管理分支，更新您的远程存储库，以及解决合并冲突。如需详细信息，请查看[发行说明](https://docs.microsoft.com/en-us/visualstudio/releases/2019/release-notes)和[文档](https://aka.ms/vsgitdocs)。同时，改进的 C++20 支持在编译器、标准库和 IDE 中增加了主要的 C++20 特性。

[https://www.youtube.com/embed/UHrAg3iKoe0?feature=oembed](https://www.youtube.com/embed/UHrAg3iKoe0?feature=oembed)

视频

*   **GoLang 庆祝十一年:**又到了[用 Go 语言的十一岁生日来回顾去年的时候了](https://blog.golang.org/11years)。虽然这个数字没有去年那么圆，而且正如该团队在其帖子中指出的那样，“这是艰难的一年”，但仍然有很多值得强调的，包括 [Go 1.14 版本](https://blog.golang.org/go1.14)、 [Go 1.15 版本](https://blog.golang.org/go1.15)，以及 [go.dev 和 pkg.go.dev](https://blog.golang.org/go.dev) 的推出。最近，Go 团队发布了其[年度 Go 用户调查](https://blog.golang.org/survey2020)，结果即将出炉，他们让我们一窥即将到来的事情，例如 2 月份的 Go 1.16 和明年 8 月的 1.17。Go 1.16 将包括新的[文件系统接口](https://tip.golang.org/pkg/io/fs/)和[构建时文件嵌入](https://tip.golang.org/pkg/embed/)，以及对新的 Apple Silicon Macs 的支持，而 Go 1.17 将可能包括“新的基于寄存器的 x86-64 调用约定(不破坏现有汇编！)”和[支持 go 测试命令](https://golang.org/design/draft-fuzzing)中的模糊化。他们写道，Go 1.16 还可以期待“迄今为止最流畅的 Go 模块体验”，而且，由于没有任何关于 Go 的讨论可以放弃提及这一点，所以[泛型的最新设计草案](https://blog.golang.org/generics-next-step)正在制定中，目标是“在今年年底之前让人们尝试一些东西，也许是 Go 1.18 测试版的一部分。”
*   **DigitalOcean 提供部署按钮:**你的开源维护者现在可以为你的用户提供一个[“部署到 DigitalOcean”按钮](https://www.digitalocean.com/docs/app-platform/how-to/add-deploy-do-button/)，该公司表示，这将允许他们[轻松地将开源应用](https://www.digitalocean.com/blog/easily-deploy-open-source-apps-with-the-new-deploy-to-digitalocean-button-and-other-app-platform-enhancements)部署到其[最近](https://thenewstack.io/digitalocean-app-platform-eases-kubernetes-deployments-for-developers/)宣布[数字海洋应用平台](https://www.digitalocean.com/products/app-platform/)。你只需将按钮嵌入 README.md 文件中，DigitalOcean 就会在那里“处理应用程序的部署过程”，而不用担心“编写任务和更新说明的繁琐费时”这个按钮对你来说是免费的，但是用户需要支付相应的费用，起价为每月 5 美元。
*   **谷歌解决开源隐语:**正如我们之前在这里讨论的那样，考虑到年份，有些计算机术语有点令人生厌，需要改变。好吧，谷歌已经在它的[谷歌开源项目办公室](https://opensource.google/)启动了一个[在开源项目中更加包容语言的倡议](https://opensource.googleblog.com/2020/11/googles-initiative-for-more-inclusive.html)来解决这样的语言。从上个月开始，谷歌运营的新项目删除了“从属”、“白名单”和“黑名单”等术语，代之以更具包容性的替代词，如“副本”、“允许列表”和“阻止列表”，而更复杂的既定项目将在 2021 年开始这一过程。你可能会问，为什么？查看[谷歌开发者文档风格指南](https://developers.google.com/style/inclusive-documentation)寻找答案。“无论使用何种措辞，有必要理解某些术语会强化偏见，替换它们是积极的一步，既能为每个人创造更友好的氛围，也能在技术上更加准确。简而言之，文字很重要，”他们写道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>