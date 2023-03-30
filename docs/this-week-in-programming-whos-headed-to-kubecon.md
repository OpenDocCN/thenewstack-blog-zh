# 本周节目:谁要去 KubeCon？

> 原文：<https://thenewstack.io/this-week-in-programming-whos-headed-to-kubecon/>

一个多月前，随着 Delta 变体在美国迅速蔓延并填满 ICU，我们想知道被取消的 AWS re:enforce 会议[是否只是许多多米诺骨牌倒下的第一张](https://thenewstack.io/this-week-in-programming-is-aws-reinforce-just-the-first-domino-to-fall/)。虽然未来似乎不确定，(这不是过去两年的总括声明吗？)我们在 2020 年初看到的大规模取消再也不会重演。

作为新的堆栈，我们当然对即将于 10 月中旬在洛杉矶举行的 [KubeCon + CloudNativeCon 北美](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)特别感兴趣。好吧，现在我们只剩下几个星期了，看起来所有的系统都运转正常…但是你会在那里吗？

虽然展览仍将继续，但看起来今年的 [KubeCon+CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 在亲自出席方面会有点，我们应该说，清淡。会议要求所有与会者出示疫苗接种证明，但这似乎并没有抑制与会者，而是对在室内聚集大量人群感到厌倦，再加上持续的旅行禁令。

最近的一条 Twitter 帖子显示，许多你原本会在 Kubernetes 年度活动中期待的名字，包括 Kubernetes 创始人之一的 Joe Beda ，将不会出席，原因正是这些。为了证实这一事实，[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)的执行董事[普里扬卡·夏尔马](https://www.linkedin.com/in/pritianka)最近告诉新堆栈，今年的会议实际出席人数将少于往常，可能会达到 4000 人左右，而不是 2019 年的近 12000 人。

对于那些参加展览的人来说，将会有你们通常的各种聚会、同地活动和会谈，尽管其中一些甚至会是虚拟的，甚至会有一次会后去迪斯尼乐园的旅行。

## 本周的节目中

*   **Google 向 Google Cloud Docs 添加运行代码:**曾几何时，Web 是一种相当静态的体验，但那种日子已经一去不复返了，因为 ide 等越来越频繁地进入浏览器。这方面的另一个例子是谷歌的新能力，即[直接从谷歌云的文档](https://developers.googleblog.com/2021/09/run-code-directly-from-google-cloud-documentation.html)中运行代码，增加了一个[云外壳](https://cloud.google.com/shell?shell_enabled=true)集成“在每个文档页面中”，这“让你在学习谷歌云服务的同时，在预配置的虚拟机实例中测试代码”要使用该功能，你必须使用你的谷歌云账户激活账单验证，但你将能够测试“免费的[免费层](https://cloud.google.com/free?shell_enabled=true)服务，如 Pub/Sub 和 Cloud Vision。”
*   **GitHub 的安全特性只是 Rust & npm 的第一步:** GitHub 本周发布了两个公告——在 GitHub 咨询数据库中增加了对 Rust 的[支持，以及一个](https://github.blog/2021-09-23-github-advisory-database-now-supports-rust/)[新的 npm 访问令牌格式](https://github.blog/2021-09-23-announcing-npms-new-access-token-format/)——GitHub 项目经理 [Grey Baker](https://www.linkedin.com/in/greysteil) [在 Twitter 上说](https://twitter.com/greybaker/status/1441122135561412609)这两个都是“即将到来的迹象”。现在，Rust 的加入意味着 Rust 开发人员可以更容易地检查 GitHub 上的安全问题，新的 npm 访问令牌格式使他们更容易发现，并意味着 GitHub secret scanning 可以使用新格式找到并自动撤销任何泄露的 npm 令牌。然而，展望未来，Baker 说 Rust 的加入“是我们供应链功能中全面支持 Rust 的第一步——依赖图和[依赖机器人](https://github.com/dependabot)支持即将到来。”与此同时，新的 npm 访问令牌格式将“让我们做的不仅仅是补救泄漏，明年年初，我们将开始允许高级安全用户通过拒绝包含可识别凭据的推送来防止泄漏(通过简单的覆盖体验)”，此外“让我们在不久的将来让 npm 凭据泄漏成为过去。”

*   **微软展望“Visual Studio 可扩展性的未来”:**随着上周发布预览版 4，Visual Studio 2022 的发布仍在继续，微软本周写道[Visual Studio 可扩展性的未来就在这里](https://devblogs.microsoft.com/visualstudio/the-future-of-visual-studio-extensibility-is-here/)。这篇博客文章着眼于“几个激动人心的可扩展性更新，这些更新要么现在可用，要么即将出现”，包括一个公共的 [VSExtensibility repo](https://github.com/microsoft/VSExtensibility) ，它将托管与扩展相关的公告、代码示例和关于预览功能的文档。你可能已经知道，Visual Studio 2022 将是 64 位的，需要使用 [VS 2022 扩展迁移指南](https://docs.microsoft.com/en-us/visualstudio/extensibility/migration/update-visual-studio-extension?view=vs-2022)来迁移扩展。帖子中强调的其他新功能包括扩展语言服务器协议(LSP)和 Visual Studio 社区工具包的添加，这是一组项目模板、API 包装器和生产力工具，“为在 Visual Studio 中编写扩展提供了更简单、更流畅的体验。”最后，Visual Studio 2022 还引入了新的进程外可扩展性模型，这意味着 Visual Studio 将能够在进程外加载扩展，从而允许“更可靠的扩展，不会导致 Visual Studio 挂起或崩溃。”
*   **IBM 推出 API 开发者游乐场:**今年早些时候， [IBM](https://www.ibm.com/cloud?utm_content=inline-mention) 推出了 [IBM API Hub](https://developer.ibm.com/apis/) ，让开发者可以访问该公司的 numbers APIs，现在该公司推出了[新的 API 开发者游乐场](https://developer.ibm.com/blogs/accelerate-tech-exploration-developer-playground-ibm-api-hub/)，开发者可以“在一个免费的游乐场环境中使用 API”开发者乐园目前处于测试阶段，它为开发者提供了“一个 web IDE 环境，在这里你可以在几分钟内获得源代码并配置、构建和运行应用程序。”对于感兴趣的人，IBM 表示在[混合云 2021 数字开发者大会](https://developer.ibm.com/conferences/digital-developer-conference-hybrid-cloud/#agenda)上提供了[实践研讨会](https://developer.ibm.com/conferences/digital-developer-conference-hybrid-cloud/track-5-labs/s6-data-quality-ai-api/)。
*   **谷歌引入了一个“基于维基百科的图像-文本数据集”:**最后，对于你的机器学习爱好者来说，谷歌已经[引入了](https://ai.googleblog.com/2021/09/announcing-wit-wikipedia-based-image.html)基于[维基百科的图像文本(WIT)数据集](https://github.com/google-research-datasets/wit)，一个大型多模态数据集，“通过从维基百科文章和维基媒体图像链接中提取与图像相关的多个不同文本选择来创建。”根据这篇博客文章，像这样的数据集通常是通过手动为图像添加标题或通过网络爬行和提取替代文本来创建的，但每一种都有自己的困难。相比之下，维基百科被证明提供了 108 种语言的各种主题的准确信息。他们写道，WIT“是公开可用的最大的图像-文本多模态数据集”，并且“拥有比任何其他数据集多 10 倍或更多的语言。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>