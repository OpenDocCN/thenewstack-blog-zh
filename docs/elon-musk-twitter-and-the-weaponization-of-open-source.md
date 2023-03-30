# 埃隆·马斯克、推特和开源的武器化

> 原文：<https://thenewstack.io/elon-musk-twitter-and-the-weaponization-of-open-source/>

当我本周第一次坐下来写这个话题时，我的第一反应是在整个介绍中说一些类似于“啊，我们能不能不要这样？”然后直接跳到每周新闻摘要。但是后来我听到了开源 Twitter 的部分，我的兴趣被激起了。

如果你还不知道这个消息的话，世界首富埃隆·马斯克已经提出[完全收购 Twitter】，之前他已经成为最大股东，差点加入董事会，但后来决定不加入。](https://twitter.com/elonmusk/status/1514564966564651008)

这是戏剧性的一周。

不管怎样，在本周的一次 ted 演讲中，当被问及为什么想收购 Twitter 时，马斯克回答说他想开源 Twitter。

现在，并不是没有开源的 Twitter 替代品。他们已经在那里呆了十年左右了。

当我们谈论“开源”时，这是很重要的一部分，对吗？我们希望能够自己经营它。我们希望能够在我们自己的服务器上获取代码，并根据我们的需求进行调整。我们希望共同帮助解决问题，修复错误并为代码库做出贡献。

但这不是重点。

我们不是在谈论开源 Twitter，以便我们可以将其转移到一个基金会，确保其适当的治理，并确保没有单一实体对其方向有太多的权力。与其说马斯克突然成为将一切都转向开源的领导者，不如说马斯克希望开源 Twitter，以揭开帷幕，揭露他眼中 Twitter 算法中邪恶的反言论自由倾向。

对于开源 Twitter 的想法，我的第一反应是响亮的“太好了！”如果开源对运行我们互联网的基础设施足够好，那么它对 Twitter 也足够好，对吗？不管背后的意图是什么，我们仍然会得到上述所有的好处，对不对？

我不知道。

首先，Musk 特别提到了开源 Twitter 的“算法”,而不是全部功能，所以从拥有开源项目到运行自己的实例，这可能是一大步……但我们可以做到这一点。第二，[正如许多人问](https://twitter.com/smartereveryday/status/1507137526397640709)的那样，随着像 Twitter 这样的算法完全开源，潜在的垃圾邮件和游戏会泛滥吗？如果你告诉每个人所有的排名是如何工作的，这难道不是一个如何创建完美垃圾邮件的教程吗？

对我来说，最有趣的部分是，在这种情况下，开源的想法，因为感知和声明的意图，并不被视为一件好事。相反，开源专有软件的想法被视为一种武器，许多人担心这只会助长仇恨言论，而不会让我们摆脱企业贪婪的束缚。

## 本周的节目中

*   **Visual Studio“增强”Git:** Visual Studio 已经看到[增加了](https://devblogs.microsoft.com/visualstudio/supercharge-your-git-experience-in-vs/)一个“相对较新的 Git 特性”，该团队称[将在 VS](https://devblogs.microsoft.com/visualstudio/supercharge-your-git-experience-in-vs/) 中增强你的 Git 体验。[提交图](https://devblogs.microsoft.com/devops/supercharging-the-git-commit-graph/)通过以提交图文件的形式提供一种缓存来帮助解析和排序提交，从而改善了由于大小而导致的 Git 性能问题。(如果你真的想知道它是如何工作的，可以看看[这篇博文](https://devblogs.microsoft.com/devops/updates-to-the-git-commit-graph-feature/#what-is-the-commit-graph-and-what-is-it-good-for)。)该功能在 Visual Studio 的最新预览版本(17.2 Preview 3 或更高版本)中可用，并将自动显示一个通知，您可以在其中选择启用提交图，或者您可以在设置中手动启用它。就性能改进而言，微软表示，它已经看到“对于一个有 332k 次提交的存储库，在 Git 存储库窗口中加载分支历史记录的性能平均提高了 25%”。
*   **GitHub Discussions 获得民意调查，聊天集成&更多:** GitHub Discussions 本周获得[一系列新功能](https://github.blog/2022-04-12-whats-new-in-github-discussions-organization-discussions-polls-and-more/)，包括组织讨论、民意调查、Slack 和微软团队的[集成](https://github.blog/changelog/2022-02-10-discussions-support-in-the-github-app-for-microsoft-teams-and-slack/)，以及更快获得所需答案的方式。组织讨论将讨论的范围从存储库层面扩展到了组织层面，您可以在家酿社区中看到[在起作用。民意调查，一个“被高度要求的功能”，就像它听起来的那样；与 Slack 和 Teams 的集成也是如此，它在每次创建或回答讨论时都提供一个通知。最后，Q & A 答案会变得更容易找到，方法是给出“在帖子顶部标记为答案的原始张贴者的回答预览，并提供一个链接，该链接会带你到完整的答案以了解更多细节。”](https://github.com/orgs/Homebrew/discussions)

*   **Visual Studio 2022 放弃 Mac Preview 9:** 当我们谈论 Visual Studio 时，[Visual Studio 2022 for Mac Preview 9](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-for-mac-preview-9/)刚刚在本周发布，重点是“解决以前预览版本中报告的主要问题”，例如[无法移动文件](https://developercommunity.visualstudio.com/t/Cant-move-files-in-VS-2022-for-Mac/1695923)、[无响应的水平和垂直拆分器](https://developercommunity.visualstudio.com/t/IDE-horizontal-and-vertical-splitters-be/10004981)、无法调试单元测试、[拒绝保存的 XAML 文件](https://developercommunity.visualstudio.com/t/XAML-files-refuse-to-save/1498383)如果这些问题都不在你的愿望清单上，好消息是，你可以[在 Visual Studio“帮助”菜单中对影响你的首要问题](https://docs.microsoft.com/en-us/visualstudio/mac/report-a-problem)进行投票，或者通过[搜索现有问题](https://developercommunity.visualstudio.com/search?space=41&ftype=problem&stateGroup=active&sort=newest)并对影响你的问题进行投票。
*   **GitLab 的下一个容器注册表:**git lab 容器注册表的[“下一代”将在未来几周内在 GitLab.com 推出，详细信息现已公布。该功能最初于 2016 年](https://about.gitlab.com/blog/2022/04/12/next-generation-container-registry/)在[推出，此后发生了许多变化，包括引入新的 PostgreSQL 后端来存储元数据，以及自动在线垃圾收集器来删除未标记的图像并回收存储空间。这些功能在今年 1 月被迁移，GitLab 说“将近 20%的容器注册流量已经被路由到新版本。”现在，该公司准备开始迁移](https://about.gitlab.com/releases/2016/05/22/gitlab-8-8-released/)的第二阶段[，该阶段将“将 2022 年 1 月 22 日之前创建的图像库迁移到新的容器注册表”，并“解除对您一直要求的许多功能的封锁”。GitLab 提供了一个详细的时间表，根据你支付(或不支付)GitLab.com 的等级，来预测什么和什么时候会发生。该公司还指出，迁移将只针对带标记的图像(未标记和未引用的清单将被留下)，“一旦迁移到新的注册表，存储库将受到连续的在线垃圾收集，删除任何未标记和未引用的清单以及保留超过 24 小时的层。”想要了解更多的细节，要么去看看博客，要么去看看](https://gitlab.com/gitlab-org/container-registry/-/issues/374#phase-2-migrate-existing-repositories)[史诗](https://gitlab.com/groups/gitlab-org/-/epics/5523)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>