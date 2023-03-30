# 本周编程:GitHub 加入开源筹款游戏

> 原文：<https://thenewstack.io/this-week-in-programming-github-gets-in-the-open-source-fundraising-game/>

随着春季会议季节的继续，本周在巴塞罗纳举行了以 Kubernetes 为中心的 [Kubecon + CloudNativeCon](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2019/) 会议，GitHub 在柏林举办了自己为期一天的以自我为中心的会议， [GitHub Satellite](https://githubsatellite.com/) ，在那里，微软拥有的基于 Git 的存储库继续向新的和熟悉的方向扩展其功能。

来自柏林的消息可能是[引起最大反响的](https://github.blog/2019-05-23-announcing-github-sponsors-a-new-way-to-contribute-to-open-source/)是 [GitHub 赞助商](https://github.com/sponsors)，它将 GitHub 带入了开源筹款领域——这个领域最近出现了一些新成员，如 Linux 基金会最近宣布的[community bridge](https://thenewstack.io/linux-foundation-unveils-communitybridge-an-open-source-funding-platform/)。除了[测试版赞助商功能](https://github.com/sponsors/)，GitHub 还宣布了 [GitHub 赞助商匹配基金](https://help.github.com/articles/about-github-sponsors)，其中 GitHub 表示它“将匹配开发者在 GitHub 赞助商第一年的所有贡献，最高可达 5000 美元”，并且第一年不收取支付处理费，也不收取平台费。(总的来说，这一切听起来与 CommunityBridge 的公告极其相似。)

你不太可能听到来自开源资助领域竞争对手的太多抱怨，因为 GitHub 确保邀请了[开放集体](https://opencollective.com/)、[社区桥](https://funding.communitybridge.org/)、 [Tidelift](https://tidelift.com/) 、Ko-fi 和 [Patreon](https://patreon.com/) ，所有这些从一开始就被整合在一起。虽然努力使 GitHub 成为一站式商店，并让人们直接在他们消费产品的地方捐款似乎是显而易见的，但 Techcrunch 的 Frederic Lardinois 指出，这一举措可能会引起一些争议。

“这可能会在一些开源开发者中引起争议，他们不希望经济利益影响人们的工作。这可能有一定的道理，因为这可能会促使开源开发者专注于更有可能吸引财务贡献的项目，而不是更深奥的项目，这些项目有趣且具有挑战性，但不太可能在 GitHub 上找到财务支持者，”Lardinois 写道，GitHub 回应说，该产品“正在测试中，以超越这种担忧。”

虽然这是一个担忧，但 Twitter 上表达的另一个担忧更接近问题的核心:我们真的应该依赖个人来资助开源项目吗？

当然，比担心更常见的是那些开源开发者(更不用说文档和其他贡献者了)，他们希望这次发布意味着他们最终会看到他们的工作有了回报。

至于 GitHub 扩展的其他方向，该公司专注于[增强的安全性](https://github.blog/2019-05-23-introducing-new-ways-to-keep-your-code-secure/)和[为企业客户提供简化的体验](https://github.blog/2019-05-23-build-like-an-open-source-community-with-github-enterprise/)。在安全性方面，GitHub 越来越关注用于管理依赖关系安全性的工具，他们在这个方向上扩展的一种方式是收购和集成 Dependabot，它将“监控您的依赖关系中已知的安全漏洞，并自动打开 pull 请求，以将其更新到所需的最低版本”。该公司还[与 WhiteSource](https://help.github.com/en/articles/about-security-alerts-for-vulnerable-dependencies) 等公司合作，以扩大他们的漏洞数据范围，将[令牌扫描](https://help.github.com/en/articles/about-token-scanning)正式推出，并推出了[维护者安全咨询](https://help.github.com/articles/about-maintainer-security-advisories)的测试版，“一个私人工作区，用于讨论、修复和发布安全咨询给那些依赖 GitHub 项目的人——而不会向潜在的黑客通风报信。”

当然，其他人仍然认为这一事件的最大新闻隐藏在简化企业体验的细节中。

https://twitter.com/jessfraz/status/1131617156674850817

但是不要相信我的话——看看主题演讲，了解所有细节。

[https://www.youtube.com/embed/xAbJkn4uRL4?feature=oembed](https://www.youtube.com/embed/xAbJkn4uRL4?feature=oembed)

视频

## 本周的节目中

*   **GitLab 的多个受让人合并请求&容器支持:**正如我们之前提到的，每当 GitHub 发出一些声音，GitLab 就在那里响应。这一次，它不是一个直接的响应，而是 GitLab 自己的 GitLab 11.11 的[版本，它包括对合并请求](https://about.gitlab.com/2019/05/22/gitlab-11-11-released/)的[多个被分配者的支持，可用于 GitLab Starter，以及对容器支持的增强。长话短说，新的合并请求特性将“允许多个被指派者，这样所有负责变更的人都可以被指派到合并请求中。”新 GitLab 的其他功能包括针对 Slack 和 Mattermost](https://about.gitlab.com/2019/05/22/gitlab-11-11-released/#multiple-assignees-for-merge-requests) 的[自动部署事件通知、针对 GitLab Runners](https://about.gitlab.com/2019/05/22/gitlab-11-11-released/#deployment-notifications-for-slack-and-mattermost) 的 [Windows 容器执行器支持，允许在 Windows 上使用 Docker 容器、针对 GitLab Premium 上的 Docker 图像](https://about.gitlab.com/2019/05/22/gitlab-11-11-released/#windows-container-executor-for-gitlab-runner)的[缓存依赖代理，以及自我管理的 GitLab 实例的用户提供](https://about.gitlab.com/2019/05/22/gitlab-11-11-released/#caching-dependency-proxy-for-container-registry)[实例级 Kubernetes 集群](https://about.gitlab.com/2019/05/22/gitlab-11-11-released/#instance-level-kubernetes-cluster-configuration)的能力。GitLab 用户，请查看帖子了解全部细节。
*   **Twitter 继续其 API 努力:**我们已经讨论 Twitter 的 API 问题近十年了，ProgrammableWeb 继续跟踪这个故事，[本周写了关于 Twitter 开发者实验室的文章](https://www.programmableweb.com/news/twitter-unveils-twitter-developer-labs-first-step-toward-next-gen-api/brief/2019/05/17)。很长一段时间以来，该公司一直试图修复其早期方式的错误，随着[的发布](https://blog.twitter.com/developer/en_us/topics/tools/2019/building-the-next-generation-of-the-twitter-api.html)，该公司已经制定了“构建其所谓的‘下一代 Twitter API’的计划”显然，下一代的第一步将是“一个名为 Twitter 开发者实验室的新项目，它将允许开发者测试新的 API 特性并提供反馈。“当然，这听起来比该公司过去快速行动、打破第三方开发者创造的一切的方法要好。正如 ProgrammableWeb 在总结中写道，“开发者是否会发现 Twitter 的最新努力令人信服，这还有待观察。具体来说，目前还不清楚 Twitter 开发者实验室能否成功重新吸引那些因公司过去的决定而将注意力转移到其他平台或完全离开生态系统的开发者。”
*   **脸书开源深度学习框架皮媞亚:**脸书[开源](https://code.fb.com/ai-research/pythia/)一个新的深度学习框架，建立在 [PyTorch](https://pytorch.org/) 框架上，称为[皮媞亚](https://github.com/facebookresearch/pythia)，该公司表示，由于其“模块化、即插即用的设计”，它允许研究人员“快速构建、复制和基准测试人工智能模型”这个新框架是专门为视觉和语言任务设计的，“例如回答与视觉数据相关的问题，自动生成图像字幕”，以及“简化进入不断增长的视觉和语言子领域的过程，让研究人员能够专注于更快的原型制作和实验。”脸书写道，皮媞亚的功能将包括“参考实现，以显示以前的最先进模型如何实现相关的基准测试结果，并快速评估新模型的性能”，以及多任务处理和支持“分布式训练和各种数据集，以及自定义损失、度量、调度和优化器。”

*   **Windows 10 让 Python 安装变得超级简单:**看起来微软已经疯了，[把 Linux 加入桌面](https://www.theregister.co.uk/2019/05/06/windows_subsystem_for_linux_terminal/)，现在… [Python](https://devblogs.microsoft.com/python/python-in-the-windows-10-may-2019-update/) ？显然如此。Windows 的 Python 团队(微软会让你知道它目前雇佣了“语言和主要运行时的四个关键贡献者”)已经正式[宣布](https://blogs.windows.com/windowsexperience/2019/05/21/how-to-get-the-windows-10-may-2019-update/)它已经“通过帮助社区发布到微软商店，并与 Windows 合作，添加一个默认的‘Python . exe’命令来帮助找到它，从而使在 Windows 上安装[Python]变得更加容易。”他们承认，多年来，由于规模和安全性的原因，Windows 已经落后于“唯一一个没有现成 Python 解释器的主流操作系统”，但现在这种情况已经得到了弥补。将 Python 添加到微软商店的[将使在 Windows 10 上安装 Python 变得容易，并“自动提供 Python、pip 和 idle 等常用命令(以及版本号为 python3 和 python3.7 的等效命令，就像在 Linux 上一样)。”更简单的是，微软指出，随着 2019 年 5 月最新的 Windows 更新，Windows 的每次安装都将包括 python 和 python3 命令，这些命令将直接带你进入](https://docs.python.org/3.7/using/windows.html#windows-store) [Python 商店页面](https://www.microsoft.com/p/python-37/9nj46sx7x90p?Cid=AnnounceBlog)。
*   谁拥有围棋？不是社区:至少，这是[的观点](https://utcc.utoronto.ca/~cks/space/blog/programming/GoIsGooglesLanguage)Chris Siebenmann，一位“ [Unix 牧人](https://utcc.utoronto.ca/~cks/unix-herder.html)”写道“Go 有社区贡献，但它不是一个社区项目”，称这一论断“无可争议”。所有这些都是为了回应[一条推特](https://twitter.com/kapoorsunny/status/1130150301468700674)的提问“难道我们不能有类似 OpenGo 的东西，让社区可以实现泛型，而不是等待官方#go 泛型的出现？”Siebenmann 写道，“为什么这种情况不会发生，有很多答案，但通常不会大声说出来的一个答案是，Go 是谷歌的语言，而不是社区的语言。”Siebenmann 指出，去年的 Go 模块的实现，违背了社区的大部分呼声，这是一个很好的例子，“社区的声音对 Go 的发展并不重要，我们这些在谷歌之外与 Go 合作的人不得不接受这一点。”

GitLab 和 Tidelift 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>