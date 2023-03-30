# 本周节目:GitHub 对抗开源 DMCA 争端

> 原文：<https://thenewstack.io/this-week-in-programming-github-fights-open-source-dmca-disputes/>

本周，GitHub [宣布](https://github.blog/2021-07-27-github-developer-rights-fellowship-stanford-law-school/)它将与斯坦福大学法学院合作，帮助开源开发者对抗数字千年版权法案(DMCA)的索赔。这一举动是去年围绕一个名为[的小图书馆发生的一些戏剧性事件的后续，该图书馆在 DMCA 发布下架通知后已从 GitHub 中移除。](https://github.com/ytdl-org/youtube-dl)

虽然你可能更熟悉标准的 DMCA 下架，这通常适用于未经许可使用受版权保护的材料，但根据一项不太常见的规则，youtube-dl 可能会被移除。正如 GitHub 去年在 [youtube-dl 的恢复](https://github.blog/2020-11-16-standing-up-for-developers-youtube-dl-is-back/)上所写的，该规则适用于“反盗版——指控该代码旨在规避控制访问或复制受版权保护材料的技术措施，违反了 DMCA 第【1201 条。”作为对这一事件回应的一部分，GitHub 当时承诺，它不仅会努力改变法律本身，还会改善自己对删除通知的反应，并建立一个开发者保护基金，“以帮助保护 GitHub 上的开源开发者免受 DMCA 第 1201 条删除索赔。”

作为 GitHub 专门的 [1201 审查流程](https://docs.github.com/en/github/site-policy/dmca-takedown-policy#c-what-about-circumvention-claims)的一部分，当我们通知开发者一个有效的拆除索赔时，我们还会让他们选择通过诊所寻求独立的法律支持，而不需要他们支付任何费用，”该公司在本周的公告中写道。这确保了开发商能够获得完全独立的法律支持，将他们的利益和他们社区的利益放在第一位。"

除了提供免费的法律支持，GitHub 表示，该奖学金还将“研究、教育和宣传 DMCA 和其他对软件创新重要的法律问题”，以及培训其他人如何“与开发人员合作，并代表开源社区进行宣传”

现在，也许这就是现代社会中跨国公司的本质，但是即使当你试图帮助大众时，你也会受到批评。例如，有一篇文章警告那些反对无拘无束的乐观主义的人，指出了几个警告，包括没有提到如果开发商真的被提出索赔的人起诉，会有一个法律辩护基金。

"[根据 GitHub 的透明报告](https://github.com/github/dmca/)，在过去的一个月里(截至本文撰写之时)，他们已经处理了大约 138 份 DMCA 通知，只有一份反通知。不清楚这些通知中有多少是针对 1201 条款的争议，而不是更传统的复制代码和其他内容的问题，”文章称。“因此，尽管从公共关系的角度来看，DMCA 被查封是一个大问题，但从实际角度来看，这个问题要小得多。”

更不用说，每当你谈论 GitHub 时，最容易挂掉的水果就是指出该公司与美国移民和海关执法局(ICE)的业务往来与其声称占据道德制高点的行为形成鲜明对比。

然后就是使用大量公开可用的源代码，不考虑许可，来训练一个巨大的人工智能，不考虑[是否完全合法](https://thenewstack.io/this-week-in-programming-github-copilot-copyright-infringement-and-open-source-licensing/) …

## 本周的节目中

*   **GitLab 增加了一个 Helm 包注册表** : [GitLab](https://about.gitlab.com/?utm_content=inline-mention) 本周随着[GitLab Helm 包注册表](https://about.gitlab.com/blog/2021/07/26/gitlab-helm-package-registry/)的引入，git lab 版本 14.1 中出现的一个新增功能，继续努力提供“整个 DevOps 生命周期的单一应用程序”。Helm 是一个 Kubernetes 包管理器，Helm 图表作为在 Kubernetes 集群中运行应用程序的资源定义，所有这些都可以版本化和共享。GitLab 指出，虽然您可以简单地将舵图存储在 Git 存储库中，但“随着代码的扩展，这种方法开始变得难以控制”，并且在不提供对完整代码存储库的访问的情况下，会给共享图表带来挑战。相反，GitLab 的 Helm Package Registry 将为用户提供“一个集中的存储库来存储和共享图表，以便大型组织能够以可控的方式管理许多复杂的应用程序。”除了能够更容易地存储和共享舵图，GitLab 表示，其解决方案还将使它们能够[系统地扫描漏洞](https://docs.gitlab.com/ee/user/application_security/sast/#supported-languages-and-frameworks)，在整个组织内分发，并使用 SSO/SAML 和带有部署令牌、作业令牌或个人访问令牌的授权来保护它们。目前，GitLab 表示，该产品处于“可行”的成熟期，还不建议投入生产。

*   **GitLab 的 Package Hunter 检测依赖关系中的恶意代码**:虽然 GitLab 已经提供了[依赖关系扫描](https://about.gitlab.com/blog/2021/01/14/try-dependency-scanning/)，但该公司本周[推出了 Package Hunter](https://about.gitlab.com/blog/2021/07/23/announcing-package-hunter/) ，这是一款用于检测依赖关系中恶意代码的工具。他们写道，传统依赖扫描的部分问题是，它们“通常不会检测依赖是否执行恶意代码，因为这些工具仅限于识别具有已知漏洞的依赖。”然而，Package Hunter 通过在沙盒环境中安装依赖项并监控安装期间执行的系统调用来分析依赖项“恶意代码和其他意外行为”，其中 [Falco](https://falco.org/) 为系统调用监控提供了基础。无论发现什么异常，它都会提醒用户，并且目前提供对 NodeJS 模块和 Ruby Gems 的支持。
*   **深入了解 Visual Studio 的热重装功能**:你可能已经听说了，微软最近发布了 Visual Studio 2022 的第二个预览版。第一个预览版主要展示了它的 64 位功能，而第二个则引入了许多功能。其中一个突出的特性是无需重启应用程序就能应用代码更改。本周，微软提供了一个更深入的关于你如何能[加速你的。在 Visual Studio 2022](https://devblogs.microsoft.com/visualstudio/speed-up-your-dotnet-and-cplusplus-development-with-hot-reload-in-visual-studio-2022/) 中使用热重新加载的. NET 和 C++开发，这将“包括我们对在您的 ASP.NET web 应用程序中编辑 Razor 页面的初始支持，对调试器体验期间热重新加载 C++应用程序的支持，以及使用。使用 CTRL-F5 启动应用程序时，无需调试器即可进行. NET 热重新加载，并支持更多类型的编辑”，以及错误修复和稳定性改进。如果 Visual Studio 是您的日常 IDE，那就去了解更多关于这个即将推出的特性的信息，以及如何立即试用它。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>