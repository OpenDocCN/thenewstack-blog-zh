# 本周编程:忘记微服务，单片是前进的方向

> 原文：<https://thenewstack.io/this-week-in-programming-forget-microservices-monoliths-are-the-way-forward/>

几周前，我们看了看开源服务 mesh Istio 的奇怪案例及其表面上矛盾的[决定放弃微服务](https://blog.christianposta.com/microservices/istio-as-an-example-of-when-not-to-do-microservices/)并返回到 monolith。本周，我们发现了一个标题，不是别人，正是谷歌云的忠实信徒和布道者[凯尔西·海塔尔](https://github.com/kelseyhightower)，他写道——作为他的“不受欢迎的观点”系列的一部分——巨石柱是未来的。

是的，你没看错。

Hightower 在博客文章的第一句话就清楚地阐述了这个问题:“单片是未来，因为人们试图用微服务解决的问题并不符合现实。”

那么人们试图用微服务代替单片来解决的这个问题到底是什么呢？Hightower 提出了一个假设(并不那么假设),一家缺乏纪律的公司最终导致了代码库的灾难，作为回应，决定采用微服务作为解决方案——作为一种将不同代码的不同部分相互分离的方法。

Hightower 说，事实是“现在你已经从编写糟糕的代码变成了构建糟糕的基础设施，并在其上部署糟糕的代码。”

更糟糕的是，一位 HackerNews 评论者写道,,公司经常最终将他们的整体分割成“微服务”,结果却是一个分布式的整体，而不是微服务。所以现在，他们在基础设施方面享受着增加的复杂性，而代码库却没有提供微服务的任何实际优势。

“大多数人认为微服务架构是灵丹妙药，因为‘看看 X 有多简单’，但其实没那么简单。他们写道，现在它是一个分布式系统，很有可能，它是一个最糟糕的分布式整体，”他们概述了一些基本要点，以帮助确定这是否是你的新非微服务架构的落脚点——其中最明显的可能是“没有 Y 或 Z，服务 X 就无法工作，并且/或者你没有如何处理其中一个宕机的策略。”

我想知道这将我们置于炒作周期的哪一部分？

## 本周的节目中

*   **用你的 AI 做一个 AI 的侧面怎么样？**当你处理训练对象检测模型所需的大型图像数据集时，手动标记可能是一项“令人生畏的任务”，但 IBM 发布了一款[云注释工具，以简化人工智能数据标记的过程](https://developer.ibm.com/blogs/ibm-cloud-annotations-tool-eases-the-process-of-ai-data-labeling/)，它使用人工智能来帮助标记图像……以训练你的人工智能。使用开源的[云注释](https://github.com/cloud-annotations)项目可以访问这个新工具，它将自动标记你使用人工智能上传的图像，并允许你“存储你需要的数据，从任何地方访问数据，并在多个合作者之间实时共享。”看看这个。

*   **Python pandas 达到 1.0:**Python[pandas](https://pandas.pydata.org/)数据分析和操作库在十多年后终于[实现了 1.0 版本](https://github.com/pandas-dev/pandas/releases/tag/v1.0.0)，JaxEnter 采访了 Pandas 开发团队的成员 [Tom Augspurger](https://tomaugspurger.github.io/) ，他表示"[1.0 版本并不意味着 Pandas 开发的结束，甚至不意味着 Pandas 开发的放缓](https://jaxenter.com/python-pandas-1-0-0-tom-augspurger-167593.html)。“这篇文章从 Augspurger 的角度来看这个版本，而 DevClass 也写了关于最新的 pandas 版本的文章，提供了这个库的最新特性的更简单的细节。
*   **GitHub 推出测试版 Actions API:**自从 GitHub 第一次[推出 Actions](https://thenewstack.io/this-week-in-programming-github-dives-into-devops-with-actions/) 以来，已经过去了将近一年半的时间，它的工作流工具后来[扩展为 CI/CD 用例](/github-expands-into-continuous-integration-and-deployment/)，每个人都在它的最初版本中看到了。现在，该公司终于发布了一个[动作 API](https://developer.github.com/changes/2020-01-28-actions-api/) 的测试版，它使客户能够使用 REST API 管理 GitHub 动作，包括秘密和自托管运行程序的管理。现在，在你开始构建这个新的 API 之前，请注意 GitHub 的警告，他们“可能会根据开发者的反馈改变这些 API 的某些方面[……]，但我们不会提前通知。”

*   **在 GitHub 上了解开源:**本周 GitHub 又提供了一点信息，因为该公司创建了一个新功能，通过帮助您找到好的初始问题，将其分解为几个方法，使[开始为开源做出贡献](https://github.blog/2020-01-22-browse-good-first-issues-to-start-contributing-to-open-source/)变得更加容易。首先，你可以按主题浏览，去*github.com/topics/<主题>*——比如[github.com/topics/machine-learning](https://github.com/topics/machine-learning)或者访问[github.com/topics](https://github.com/topics/machine-learning)浏览主题列表。接下来，如果你心中有一个项目，你可以通过访问*github.com/<所有者> / <资源库> /contribute* 找到适合初学者的项目问题。最后，如果你已经为一些事情做出了贡献，但不知道下一步该去哪里，你可以去 github.com/explore 看看你的策划名单，根据你过去的贡献，明星等等。如果你想知道 GitHub 是如何制作这个功能的，该公司还向[提供了一篇关于“使这个功能成为现实的机器学习算法”的博客文章](https://github.blog/2020-01-22-how-we-built-good-first-issues/)
*   **Go 1.15 稳扎稳打:**随着 Go 1.14 的发布临近，Go 团队发布了一篇博文，概述了[对 Go 1.15](https://blog.golang.org/go1.15-proposals) 的提议，写道:“按照 [Go 2 中概述的过程，我们来了！](https://blog.golang.org/go2-here-we-come)博文，在我们的开发和发布周期中，又到了考虑我们是否希望在定于今年 8 月发布的下一个版本 Go 1.15 中包含语言或库的变化的时候了。”该团队注意到，错误处理在今年早些时候遇到了一些反对，提出了 [try 提案](https://golang.org/issue/32437)，并且此后没有提出任何好的(更好且无争议的)替代方案，所以……他们打算暂时搁置这个提案。与此同时，模块和泛型正在积极开发中，而“一些常年的最爱，如枚举和不可变类型的请求”缺乏足够的发展和紧迫性。因此，该团队写道，他们已经“得出结论，这次最好推迟重大变化”，而是“集中精力进行几项新的审查和对语言的小调整。”因此，Go 1.15 暂时附带了三个小提议，Go 团队表示，他们希望“在 Go 1.15 发布周期的开始(在 Go 1.14 发布时或发布后不久)实现，以便有足够的时间来收集经验和提供反馈。”另一个完全独立但相关的消息是，围棋团队成员 [Brad Fitz](https://en.wikipedia.org/wiki/Brad_Fitzpatrick) 本周宣布他将[离开谷歌](https://bradfitz.com/2020/01/27/leaving-google)，并写道他将“继续留在围棋社区，但会更少，而且会有所不同。”

*   **设置好就忘了:**就像 Ronco Rotisserie 一样，似乎你的 JavaScript 程序员喜欢安装一次库，然后就再也不想它们了——这是根据 Cloudflare 的一篇博客文章，该文章发现 JavaScript 库一旦安装就几乎不会更新。Cloudflare 从其 JavaScript 存储库和 CDN [CDNJS](https://cdnjs.com/) 收集数据，查看不同版本的 jQuery 和 TweenMax 的使用统计数据，发现尽管新版本在发布时可能会显示更多的采用，但没有迹象表明很多人真的会更新他们的旧版本以使用新版本。根据 Cloudflare 的说法，这个故事的寓意是“无论你发布什么库，它都将永远存在于网站上”，“如果要继续支持整个 web，底层 web 平台因此必须无限期地支持过时的约定。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>