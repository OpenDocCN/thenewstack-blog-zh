# 本周编程:信任应该在开源安全中有一个家吗？

> 原文：<https://thenewstack.io/this-week-in-programming-should-trust-have-a-home-in-open-source-security/>

明尼苏达大学的研究人员[和 Linux 内核开发人员](https://thenewstack.io/university-of-minnesota-researchers-tried-to-poison-the-linux-kernel-for-a-research-project/)之间的余波还在继续，此前研究人员在一篇题为“[关于通过伪君子提交](https://github.com/QiushiWu/QiushiWu.github.io/blob/main/papers/OpenSourceInsecurity.pdf)在开源软件中秘密引入漏洞的可行性”的论文中描述了他们如何故意向 Linux 内核提交一些会引入漏洞的提交，详细描述了他们如何故意向 Linux 内核提交一些会引入漏洞的提交。

当 Linux 维护者发现这一点时，他们很快[禁止整个大学进行 Linux 开发](https://www.zdnet.com/article/greg-kroah-hartman-bans-university-of-minnesota-from-linux-development-for-deliberately-buggy-patches/)，然后 [Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention) [向大学发送了一份要求清单](https://www.zdnet.com/article/the-linux-foundations-demands-to-the-university-of-minnesota-for-its-bad-linux-patches/)，大学似乎很快同意了，从 IEEE 会议上撤回了它被接受的论文，并同意提供“所有必要的信息，以确定任何 MN 大学实验中已知易受攻击代码的所有建议。”

现在，你可能会发现自己和我一样，不知道安全研究的伦理要求，也不完全知道这些事情是如何工作的，但它仍然阐明了一些事情。许多帖子中的各种评论者指出，提交这种类型的错误的能力已经是一种已知的威胁，并且证明它可以做到几乎没有实现。

在对本月事件的回顾中，Linux 周刊的新闻创建者 Jonathan Corbett 提供了一些经验教训，其中包括“内核维护者(以及许多其他自由软件项目的维护者)工作过度，没有时间仔细检查他们手中的每一个补丁。结果，他们被迫依赖于向他们提交补丁的开发者的可信度。可以说，当信任到位时，内核开发过程几乎不可持续；如果传入的补丁通常不可信，它将无法保持完整。”

虽然所有的错误都应该被正确地定位，但建议在运行全球关键系统的操作系统中确保安全的当前方法可能需要一些加强，这也是指责受害者吗？这个实验没有遵守伦理实验的规则，这个论点可能是有根据的，但是伦理与现实世界的安全没有什么关系。似乎目前正在玩的游戏是一个我们依靠每个人公平游戏的游戏，这似乎是一种奇怪的安全方法。

正如 Corbett 进一步写道，“内核进程的速度是它最好的属性之一，我们都依赖它来尽快获得特性。但是，这种速度可能与严肃的补丁审查和低数量的总体错误不相容。有一段时间，我们可能会看到事情变得慢了一点，因为维护人员觉得需要更仔细地审查变更，尤其是那些来自新开发人员的变更。但是，如果我们不能将一个更仔细的过程制度化，我们将继续看到许多错误，不管它们是有意还是无意被插入的，都没有关系。”

## 本周的节目中

*   **脸书也变得生疏了:**上周，我们看了看[微软是如何变得生疏的](https://thenewstack.io/this-week-in-programming-microsoft-gets-rusty/)，本周，[在脸书讲述 Rust 的历史](https://engineering.fb.com/2021/04/29/developer-tools/rust/)也在宣扬它的生疏，因为该公司宣布正式[加入非盈利组织 Rust Foundation](https://developers.facebook.com/blog/post/2021/04/29/facebook-joins-rust-foundation/) 。在帖子中，该公司讲述了 Rust 如何在道路上制造，从 2016 年开始，有一个名为[猫怪](https://github.com/facebookexperimental/eden/tree/master/eden/mononoke)的重写项目。“一开始用 C++开发猫怪是显而易见的选择，”他们写道。“当时，脸书的后端代码库是非常 C++的，这意味着猫怪在默认情况下是用 C++实现的。但是源代码管理团队需要考虑源代码管理后端的可靠性需求。当损坏或停机可能导致服务停止时，可靠性是重中之重。这就是团队选择 Rust 而不是 C++的原因。”猫怪的成功给其他团队和项目带来了 Rust，现在该公司表示，那里的 Rust 开发人员数量急剧增长，导致其编程语言组织成立了 Rust 团队，该团队将专注于从语言和工具链的角度支持内部用户，为 Rust 本身做出贡献，在脸书提供 Rust 与 C++的互操作性，并与 Rust 基金会合作。

*   **微软提升了对 Python 的支持:**当然，虽然我们都在怀疑这个怀疑那个，但微软也不希望我们忘记 Python，它仍然是最受欢迎的语言之一，因为该公司通过将对 Python 软件基金会的赞助提升到新的最高愿景水平，进一步加强了对 Python 社区的[支持。以免你认为互联网只是由闪亮的新玩具组成，微软展示了它近年来对 Python 的支持，包括它用该语言开发的许多项目，以及它认为是核心 CPython 开发者和 Python 生态系统中关键开源项目的贡献者和维护者的众多员工，包括 pandas、Dask、Jupyter、nteract、scikit-learn 和 Apache Arrow。](https://devblogs.microsoft.com/python/supporting-the-python-community/)
*   **Azure 为带有 WebSockets 的实时应用引入 Web PubSub:**微软已经[预展了](https://azure.microsoft.com/blog/easily-build-realtime-apps-with-websockets-and-azure-web-pubsub-now-in-preview/)其 [Azure Web PubSub](https://azure.microsoft.com/en-us/services/web-pubsub/) ，这让开发者能够[使用 WebSockets](https://aka.ms/webpubsub) 构建实时 Web 应用。该服务将得到全面管理，全球可用，并提供本机 WebSocket 支持，这意味着它将通过 WebSocket APIs 支持多种语言。它还将提供与 Azure 函数的原生集成，允许开发人员使用 WebSockets 用 C#、JavaScript、Python 和 Java 构建无服务器应用程序。David Fowler，现在是微软的员工，也是实时 ASP.NET[SignalR](https://dotnet.microsoft.com/apps/aspnet/signalr)库的创始人之一，T10 提供了一个关于这两个产品之间差异的快速 Twitter 线程 T11，指出 Web PubSub 允许你带自己的 WebSocket 库，这“降低了使用该服务的门槛，你只需要一个 HTTP 客户端和一个 WebSocket 客户端就可以开始了。”该功能目前处于预览阶段，但你可以通过访问 [Azure Web PubSub 服务页面](https://aka.ms/webpubsub)，查看[预览文档](https://docs.microsoft.com/azure/azure-web-pubsub)，仔细阅读[代码示例](https://aka.ms/awps/samples)，或者点击[快速入门指南](https://aka.ms/awps/getting-started/quick-start)来开始。

*   **dependent bot 转为 GitHub-Native:** GitHub 本周表示，将[关闭 Goodbye Dependabot 预览版](https://github.blog/2021-04-29-goodbye-dependabot-preview-hello-dependabot/)以支持 GitHub-Native 版本的依赖性更新工具，终止日期为 2021 年 8 月 3 日。目前，[dependent bot 预览版](https://dependabot.com/)和 Dependabot 本身将不再接受新客户，随着这一举措，一些功能也将离开，包括 PHP 环境变量注册表、自动合并和实时更新，尽管该公司表示希望在不久的将来恢复更新。对于你的 dependent bot 预览版用户，你需要做的就是在 8 月 3 日之前将“升级到 GitHub-native dependent bot”的请求合并到你的库中。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>