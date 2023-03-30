# 本周编程:何时不做微服务

> 原文：<https://thenewstack.io/this-week-in-programming-when-not-to-do-microservices/>

微服务，微服务，微服务，微服务。到现在为止，你可能已经听过这个词太多了，你会情不自禁地回到十年前史蒂夫·鲍尔默在舞台上唱的“开发者”这首歌。

也许你的公司已经做出了改变，离开了它的遗留系统，进入了分布式体系结构的乐土，或者也许它只是在考虑这一步。毕竟做微服务什么都比较好吧？

也许不是。

本周，我们听到了一个这样的软件项目的故事，它已经走上了微服务的道路，只是决定 monolith 确实是要走的路，它来自于一个你可能认为除了 100%专注于分布式架构之外什么都不会做的项目——开源服务网格 [Istio](https://istio.io/) 。

这个故事来自于[的 Christian Posta](https://www.linkedin.com/in/ceposta/) ，他是一位拥有 [Solo.io](https://www.solo.io/) 的现场厨师技术官，他提供了 Istio 作为[一个何时不做微服务](https://blog.christianposta.com/microservices/istio-as-an-example-of-when-not-to-do-microservices/)的例子，他写道“当应用程序架构的顶点已经成为进行更改和“走得更快”的瓶颈(由于各种人员/流程/技术因素)时，微服务方法可能是合适的[，但它不是唯一的方法](https://blog.christianposta.com/microservices/when-not-to-do-microservices/)。

在 Istio 的情况下，你可能会认为一个旨在“帮助解决微服务/云架构带来的困难的应用联网挑战”的工具，Posta 写道，最好由[微服务架构](/category/microservices/)本身来提供。相反，Istio 计划在下个月推出的 Istio 1.5 中恢复到一种更单一的方法，原因很简单，Posta 引用了一些设计文件:“微服务方法的复杂性被证明没有提供它想要的价值或目标。相反，它与这些目标背道而驰。”

Posta 提供了一个图表，展示了当前实现的复杂性，它有点像一碗意大利面条。跳过 Istio 本身的本质细节，他的帖子中间的一点确实抓住了眼前的问题:

*采用微服务架构的首要权衡是复杂性。当你从一个东西(整体)变成一堆相互通信的小东西(为了优化某个特定的关注点)时，你会显著增加架构的复杂性以及运行这些东西所必需的基础设施的复杂性。*

*在你意识到利益的范围内，这可能是一个必要的权衡。如果没有，你最好评估一下你的假设，然后修正方向。这就是 Istio 现在的情况。*

结果图看起来就像是仍在盒子里的意大利面条——整洁、有序、简单。现在，当然，这可能是微服务的一般故事，但关键是，所有的复杂性最终只有在交付预期结果时才是值得的。无论是出于伸缩性的考虑，出于不同目的使用不同语言的愿望，领域分组，还是安全性的考虑，微服务都有合理的理由，但简单地避免令人恐惧的术语“monolith”并不在其中。

Posta 写道，对于 Istio 来说，回到 monolith 现在为其用户提供了一些他们在忍受微服务架构乌托邦时没有享受到的好处，包括通过单个可部署服务进行简单安装，降低配置复杂性，更容易调试，以及提高效率。

[https://www.youtube.com/embed/KMU0tzLwhbE?feature=oembed](https://www.youtube.com/embed/KMU0tzLwhbE?feature=oembed)

视频

## 本周的节目中

*   **Visual Studio Code 2020 Python 发布:**让我们从本周的新闻结尾开始，所有 Visual Studio Code Python 开发人员都要安装一个新的[Visual Studio Code 2020 1 月发布](https://devblogs.microsoft.com/python/python-in-visual-studio-code-january-2020-release/)。最新的 [Python 扩展](https://marketplace.visualstudio.com/items?itemName=ms-python.python)提供了 Jupyter 笔记本编辑器中的性能改进、Jupyter 笔记本中的内核选择、加载时终端中的环境自动激活，以及保存和启动时重建 ctags 的修复。现在，我们知道你们有多喜欢 Python，我们也不想告诉你们，但是…
*   **…C 语言现在是最受欢迎的:**或者至少， [TIOBE 指数](https://www.tiobe.com/tiobe-index/)是这样说的，它是根据“全球熟练工程师的数量、课程和第三方供应商”以及，嗯，在谷歌、必应等网站上的搜索，对顶级编程语言进行排名。虽然 Python 已经占据了 2018 年的头把交椅，正如他们在博客中写道的那样，“每个人都认为 Python 将连续第二次成为 TIOBE 的年度编程语言”，但 C 打败了它。为什么？它将 C 语言的流行归功于物联网，在物联网中，C 语言既普及又快速。TIOBE 还指出 Swift 和 Ruby 的收益非常突出，而 Rust、Kotlin、Julia 和 TypeScript 的表现不如预期。但是，嘿，这只是一场赛马，所以代码在什么工作，对不对？

*   **Ruby 发布 2.7，改进了垃圾收集:**说到 Ruby，这个有着 25 年历史的语言刚刚发布了 Ruby 2.7，InfoWorld 为我们带来了最新产品发布的细节，它说明显的是[改进了垃圾收集和模式匹配](https://www.infoworld.com/article/3404481/ruby-27-improves-garbage-collection-pattern-matching.html)。根据 Ruby 2.7 的[发布说明，note 的特性包括模式匹配、read-eval-print-loop (REPL)的改进、压缩垃圾收集的引入以及位置和关键字参数的分离。详细的解释可以看一看。](https://www.ruby-lang.org/en/news/2019/12/25/ruby-2-7-0-released/)
*   **Go 用 Go 1.14 继续前进:**与此同时，Go 用 Go 1.14 继续前进，InfoWorld 再次详细介绍了 Go 1.14，并指出这个最新版本[专注于运行时和编译器改进](https://www.infoworld.com/article/3512622/go-114-focuses-on-runtime-compiler.html)，以及对 Windows 和 WebAssembly 的支持。该版本尚未发布，但预计将于 2 月中旬发布，并且[发布说明](https://tip.golang.org/doc/go1.14)指出该版本是“在 macOS 上支持 32 位二进制文件的最后一个版本。”

*   **回顾和决心继续:**你认为我们已经度过了 2019 年？你已经下定决心了吗？不完全是。随着新年的到来，我们中的一些人仍然停留在 2019 年，而另一些人仍然认为还有时间对 2020 年进行最后一次预测。事不宜迟，这里有一些穿过我们的饲料，你可能会发现有价值的。首先，JavaScript 包管理器 npm 提供了一份 2019 年的[安全审查，其中包含一些基本数据，如 737 个错误发布的](https://blog.npmjs.org/post/190109399410/npm-security-2019-in-review) [npm 令牌被撤销](https://blog.npmjs.org/post/182015409750/automated-token-revocation-for-when-you)，以及通过[捕获 Komodo Agama 钱包后门](https://blog.npmjs.org/post/185397814280/plot-to-steal-cryptocurrency-foiled-by-the-npm)而避免被盗的 1300 万美元加密货币。AWS 提供了一份[十大 AWS 开源博客帖子](https://aws.amazon.com/blogs/opensource/top-ten-aws-open-source-blog-posts-in-2019/)的列表，GitLab 提供了一份 2019 年的[回顾，探讨了](https://about.gitlab.com/blog/2020/01/09/2019-year-in-review/)[产品](https://about.gitlab.com/blog/2020/01/09/2019-year-in-review/#product)、[社区](https://about.gitlab.com/blog/2020/01/09/2019-year-in-review/#community)和[公司](https://about.gitlab.com/blog/2020/01/09/2019-year-in-review/#company)方面的所有亮点。对于那些还在为 2020 年的新你制定策略的人，黑客新闻有一个关于 2020 年应该学习什么技术的帖子。顶级答案？"学习如何真正使用关系数据库、关系数据建模和 SQL . "

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>