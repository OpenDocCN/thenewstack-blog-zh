# 本周编程:C++很烂吗？

> 原文：<https://thenewstack.io/this-week-in-programming-does-c-suck/>

上周晚些时候，Slashdot 向其 Twitter 粉丝提出了一个简单的问题——c++是一种糟糕的语言吗？——我从一位连续创业者那里得到了答案，他是商业太空公司 SpaceX 的首席执行官，也是电动汽车公司特斯拉的首席执行官。他关于 C++的回答？是的，这是一种可怕的语言。

现在，你的第一个问题可能是，马斯克真的是那么好的程序员吗？好吧，谢天谢地，已经有人问过这个问题了，而且还做了一些全面的网络调查。引用马斯克早期的互联网项目，他在 12 岁时创作并出售的游戏，以及更多，Quora 上最受欢迎的答案似乎是马斯克有能力提供有效的意见。虽然 UML 创造者格雷迪·布奇[提出了 C++创造者比雅尼·斯特劳斯特鲁普可能不敢苟同的](https://twitter.com/Grady_Booch/status/1015789218499448832)，唉，Stroustrup】还没有加入浪费时间在 Twitter 上争论半无意义的事情的世界。

现在，这整个争论的核心是由独立游戏程序员[乔纳森·布洛](https://en.wikipedia.org/wiki/Jonathan_Blow)开发的一个尚未发布的 C++ [的替代](https://www.gamesindustry.biz/articles/2018-07-02-jonathan-blow-c-is-a-weird-mess)。根据这篇文章，Blow 称 C++是一种“非常糟糕、非常糟糕的语言……他们说:‘我们将成为添加了一堆东西的 C’，这是一个好主意。但他们在开始时做出了许多非常糟糕的决定，后来他们不得不修正这些决定，这有点混乱。”

Blow 应该比 Musk 更清楚——他已经做了几十年的游戏编程，包括 [Braid](https://store.steampowered.com/app/26800/Braid/) 和 [The Witness](https://store.steampowered.com/app/210970/The_Witness/) 。因此，Blow 正在创造 Jai 成为“比 C++更好的游戏编程语言”,致力于“提高程序员的生活质量……简化系统；并通过允许程序员用少量代码构建大量功能来增强表达能力。”

很有可能，就像 Musk-spectrum 一样，你可能会喜欢或讨厌 C++。毕竟，即使是 Blow 也评论说“C++在某些方面是一种强大的语言，因为它是我们制作游戏的语言，所以很明显它在做一些正确的事情。但这让事情变得比想象中困难得多。”但是如果你真的倾向于“C++很烂”的那一面，请留意 Jai——它将在今年年底推出封闭的测试版，因此可能会有替代品。

感谢你没有在 C 语言中抛出代码，([除非你是](https://www.geeksforgeeks.org/undefined-behavior-c-cpp/)):

有一件事是肯定的，谷歌似乎不是 C++的粉丝，因为他们已经发布了一个名为 Google Carbon 的实验性[编程语言，他们不介意看到它取代 C++。](https://thenewstack.io/google-launches-carbon-an-experimental-replacement-for-c/)

## 本周的节目中

*   **BDFL(不是真的)死了，BDFL 万岁:**首先，本周来自 ZDNet 的一个故事解释了所有你可能不理解的围绕 Python 创造者吉多·范·罗苏姆下台的小缩写。“仁慈的终身独裁者”，或 BDFL，已经声明，在研究语言近 30 年后，他不想“为了一个 PEP (Python 增强提案)[【PEP 572 赋值表达式】](https://mail.python.org/pipermail/python-dev/2018-July/154601.html)而不得不如此努力，并发现这么多人鄙视[他的]决定。”因此，他给自己“一个永久的假期，不再做 BDFL”，他在他的[公告](https://mail.python.org/pipermail/python-committers/2018-July/005664.html)中写道，问道“那么你们都打算做什么？创造民主？无政府状态？独裁统治？一个联邦？”最后，van Rossum 指出 [Python CoC(社区行为准则)](https://www.python.org/psf/codeofconduct/)是下一步可能发生的事情的指南，并指出“如果你不喜欢那份文件，你唯一的选择可能就是自愿离开这个小组。也许有些问题需要决定，比如什么时候某人应该被踢出去(这可能是禁止人们使用 python-dev 或 python-ideas，因为这些也包括在 CoC 中)。”

*   对于 JavaScript 包管理器 [npm](https://www.npmjs.com/) 来说，这是忙碌的一周。本周早些时候，该项目[宣布了 npm.community](https://blog.npmjs.org/post/175587538995/announcing-npmcommunity) ，它说这将“允许我们给社区一个单一的地方来报告影响 npm 的错误，无论它们是在网站上，命令行工具中还是在注册表本身中。”虽然过渡将于 7 月 12 日或 13 日上线，当时还有另一篇博客文章，但截至本文撰写之时，还没有任何文章发布。或许这是因为 2018 年 7 月 12 日的[操作事件](https://blog.npmjs.org/post/175824896885/incident-report-npm-inc-operations-incident-of)，该事件涉及大约 4500 个帐户的访问令牌，这些令牌“可能是在我们采取行动关闭该漏洞之前获得的。”虽然没有发现“在此窗口期间实际获得或使用任何令牌来访问任何 npmjs.com 帐户”的证据，但 npm 采取了预防措施，“撤销了在世界协调时下午 2:30 之前创建的每个访问令牌”，要求每个注册的 npm 用户重新进行身份验证并生成新的访问令牌。

*   **GitHub 现在检查 Python 的安全问题:** GitHub 已经[宣布](https://blog.github.com/2018-07-12-security-vulnerability-alerts-for-python/)Python 包现在将获得[与 JavaScript 和 Ruby](https://blog.github.com/2017-11-16-introducing-security-alerts-on-github/) 相同的安全待遇，这是去年首次宣布的。“Python 用户现在可以访问依赖图，并在他们的存储库依赖于具有已知安全漏洞的包时收到安全警报，”该公告称。"在接下来的几周里，我们将会把更多的 Python 历史漏洞添加到我们的数据库中."阅读完整公告，了解如何为您的项目启用 Python 安全警报的详细信息。
*   微软宣布推出 Azure Dev Spaces 和 ML.NET 0.3:这也是微软忙碌的一周，它在本周发布了两个与开发者相关的公告。首先，[Azure Dev Spaces](https://blogs.msdn.microsoft.com/visualstudio/2018/07/09/announcing-the-public-preview-of-azure-dev-spaces/)的公开预览，“Azure Kubernetes 服务(AKS)的云原生开发体验，在这里您可以在处理应用程序的同时，始终与云和您的团队保持联系。”基本上，Azure Dev Spaces 使利用容器开发变得很容易,“所有这些都不需要您在本地机器上安装 Docker 或 Kubernetes 工具，也不需要您学习 Docker 或 Kubernetes 的概念，如 Dockerfiles 或 Helm charts ”,使用您选择的代码编辑器。接下来，微软还[宣布了 ML.NET 0.3](https://blogs.msdn.microsoft.com/dotnet/2018/07/09/announcing-ml-net-0-3/)，这是其跨平台、开源机器学习框架的最新版本。NET 开发人员。这个版本“支持将模型导出到 ONNX 格式，支持使用因子分解机器、LightGBM、Ensembles 和 LightLDA 创建新类型的模型”，并解决了“从社区收到的各种问题和反馈”

*   **回到基础知识:**最后，本周，一些帖子引起了我们对开发基础知识的关注。首先，[这篇关于“web 架构 101”](https://engineering.videoblocks.com/web-architecture-101-a3224e126947)的内容丰富的博客文章着眼于“我希望在开始做 Web 开发人员时就知道的基本架构概念。”由 StoryBlocks 的工程副总裁 Jonathan Fulton 撰写，这篇文章深入探讨了当你访问一个网站时会发生什么。
*   **结束所有备忘单的备忘单:**接下来，对于那些已经不了解 DNS 是什么或负载平衡器做什么的人来说，[这是“你需要的唯一备忘单”](https://cheat.sh/)根据[GitHub 知识库](https://github.com/chubin/cheat.sh)自述文件，这份终极备忘单提供了“对世界上最好的社区驱动的备忘单知识库的统一访问”，并且“涵盖了 55 种编程语言、几种 DBMSes 和 1000 多种最重要的 UNIX/Linux 命令。”

谷歌和微软是新堆栈的赞助商。

马修·盖瑞特拍摄的特写照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>