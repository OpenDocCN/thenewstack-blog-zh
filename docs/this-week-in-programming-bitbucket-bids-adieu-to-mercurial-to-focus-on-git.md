# This Week in Programming: Bitbucket Bids Adieu to Mercurial to Focus on Git

> 原文：<https://thenewstack.io/this-week-in-programming-bitbucket-bids-adieu-to-mercurial-to-focus-on-git/>

Atlassian, announced this week that it would be [sunsetting Bitbucket’s Mercurial support](https://bitbucket.org/blog/sunsetting-mercurial-support-in-bitbucket). [Mercurial](https://www.mercurial-scm.org/), in case you weren’t aware, is an alternate version control repository to the open source [Git](https://git-scm.com/), which has served as the basis for the code-hosting repositories GitHub, GitLab, and Bitbucket itself. Bitbucket, however, started out in 2008 with support only for Mercurial, in contrast to GitHub, which also started in 2008, but with Git instead.

Git adoption has grown over the years to become the default system and that “as we surpass [10 million registered users](https://bitbucket.org/blog/celebrating-10-million-bitbucket-cloud-registered-users) on the platform, we’re at a point in our growth where we are conducting a deeper evaluation of the market and how we can best support our users going forward,” Atlassian noted in a statement. The decision the company made was to remove Mercurial support from Bitbucket Cloud and its API, with all Mercurial features and repositories to be officially removed on June 1, 2020.

With any product sunset, you’re likely to find some unhappy users out there and this is no exception. While confusion and anger are common reactions, others see it as a decision based simply on common business sense. After all, Bitbucket cites a [Stack Overflow Developer Survey](https://insights.stackoverflow.com/survey/2018#work-_-version-control) showing 90% of developers using Git as compared to 3% for Mercurial. Atlassian says Bitbucket’s own Mercurial use has “fallen to less than 1%.”

The real problem for many, it seems, is not Bitbucket’s removal of support, but rather the fact that as of June 1, 2020, “[all Mercurial repositories will be removed](https://twitter.com/IanColdwater/status/1163871863568850945).”

Of course, Atlassian can see the writing on the wall, with both GitHub and GitLab focusing ever more on everything to do with managing the entire software development lifecycle — building out CI/CD tooling, for example — and the company states that “this deprecation will enable us to focus on building the best possible experience for our users.” Some feel, however, that forcing Mercurial users to completely migrate their repositories will be the death knell for their Bitbucket accounts:

该公告为用户如何使用 [hg-fast-export](https://github.com/frej/fast-export) 和 [hg-git mercurial 插件](https://hg-git.github.io/)将现有的 mercurial 回购文件迁移到 Git 提供了许多建议，还提到了[许多免费和付费的 Mercurial 托管服务](https://www.mercurial-scm.org/wiki/MercurialHosting)。GitLab——在这样的情况下总是很慢地吸引用户——很快评论说 [Heptapod](https://heptapod.net/) 提供了“社区驱动的努力，将 Mercurial 支持带到 GitLab”，这被认为是 git lab 社区版的友好分支。然而，买家要小心，正如七足动物自己指出的那样，“尽管不再仅仅是一个原型，七足动物仍然处于实验阶段。”SourceForge 也希望那些不开心的 Bitbucket 用户知道[他们也可以在那里找到一个家](https://twitter.com/sourceforge/status/1163853960437878784)。

对许多人来说，Bitbucket 对 Mercurial 的淘汰将是一个麻烦，但不会太多。然而，对其他人来说，它看起来像是 Mercurial 的 Bitbucket 的结尾作为云的真实本质的象征——这就是生活。

## 本周的节目中

*   **Kotlin 1.3.5 改进了 Java 转换:** Android devs， [Kotlin 1.3.50 已经发布](https://blog.jetbrains.com/kotlin/2019/08/kotlin-1-3-50-released/)，它带来了一个新的持续时间和时间测量 API，现在可以预览，还有一个用于调试 kot Lin/本机代码的插件，多平台项目中的 Java 编译支持，以及一个改进的 Java-to-Kotlin 转换器。关于最后一点，该团队表示，他们希望通过基于代码中的 Java 类型用法更好地推断可空性，来“最大限度地减少转换后必须手动修复的‘红色代码’的数量”。有关变更的完整列表，请查看[变更日志](https://github.com/JetBrains/kotlin/blob/1.3.50/ChangeLog.md)。
*   **Project Marble 以 Android Studio 3.5 达到高潮:**Android Studio 被称为 Project Marble，一直处于非华丽的功能开发阶段，在此期间，开发 IDE 的团队“从大型功能工作后退了八个月，转而专注于产品质量[……]通过查看三个核心领域:系统健康、功能完善和错误，使 Android Studio &模拟器的基本功能和流程坚如磐石。”嗯，他们的工作已经到了一个停止点(因为，关于 bug 和稳定性的工作真的会结束吗？)足够发布 [Android Studio 3.5 进入稳定](http://android-developers.googleblog.com/2019/08/android-studio-35-project-marble-goes.html)。更具体地说，该团队表示，他们已经修复了 600 多个错误、50 个内存泄漏和 20 个 IDE 挂起，以及“打磨和修复了核心的面向用户的功能区域。”当然，也有一些普通的错误需要解决。想要更深入的了解，请看视频。

[https://www.youtube.com/embed/OJ3K90FpQ6A?feature=oembed](https://www.youtube.com/embed/OJ3K90FpQ6A?feature=oembed)

视频

*   **Git 2.23 增加了 Switch & Restore:** GitHub 概述了 Git 2.23 中的[亮点，它“为现有命令套件带来了一对新的实验性命令:git switch 和 git restore”，这两个特性“旨在最终为众所周知的 git checkout 提供一个更好的接口。”根据 JAXEnter](https://github.blog/2019-08-16-highlights-from-git-2-23/) 的说法，这两个新命令旨在“将 git 签出的职责明确定义为两类:git switch 负责改变分支的操作，git restore 负责改变文件的操作。”还有更多的，但你必须点击通过其余的。
*   **GitHub 升级其令牌游戏:**去年，GitHub 开始提供[令牌扫描](https://help.github.com/en/articles/about-token-scanning)，该功能将扫描任何推送的提交，以确保您不会意外共享任何凭据。一年后，[又签约了五个合作伙伴](https://github.blog/2019-08-19-github-token-scanning-one-billion-tokens-identified-and-five-new-partners/)——Atlassian、Dropbox、Discord、Proctorio 和 Pulumi——他们加入了阿里云、AWS、Azure、谷歌云、Mailgun、npm、Slack、Stripe 和 Twilio。当检测到这些合作伙伴之一的凭据时，在任何人可以恶意使用它们之前，它们将被吊销，并且您会得到通知。GitHub 表示，每天有近 900 万次提交被推送到 GitHub，去年已经处理了超过 10 亿次潜在的令牌泄露。与此同时，该公司恳求其他使用令牌的云和 API 服务提供商[了解更多关于成为 GitHub 令牌扫描合作伙伴的信息](https://developer.github.com/partnerships/token-scanning/)。

*   **GitHub Student Developer Pack 继续与 21 个新合作伙伴合作:**如果开始觉得我们本周学习的唯一内容是版本控制系统，那么…我支持你。当然，现在这些东西远不止这些，对吧？例如，GitHub 正在[带回其 GitHub 学生开发者包](https://github.blog/2019-08-20-the-github-student-developer-pack-is-back/)，该包自六年前推出以来，迄今为止已经“为超过 150 万名学生免费提供了最好的现实世界开发者工具和培训”，并将继续向在校学生免费提供 [GitHub Pro](https://github.com/pricing) 。TechCrunch 的 Frederic Lardinois 也注意到“超过 150 万的学生已经注册了这个项目，其中大约有 75 万人是活跃的”, GitHub 现在“通过增加 21 家公司使学生开发者包项目的合作伙伴数量翻倍”Lardinois 还评论说，“今年夏天，GitHub 的新所有者微软也将其 Azure 云计算服务添加到学生 Pac 中，”强调“这是该公司保持开放的承诺的一部分，即使在被微软收购后。”
*   **…然后还有 GitHub 企业服务器 2.18:** 最后一个，我发誓。GitHub 已经[发布了 GitHub Enterprise Server 2.18](https://github.blog/2019-08-20-github-enterprise-server-2-18-is-here/) ，它提供了项目管理工具、安全特性和开发者体验的更新。在项目管理标题下，更新包括存储库模板、可分配的评论者和项目卡上的里程碑，而安全性带来了对依赖关系图中 yarn.lock 文件的支持和对审计日志数据的访问，而开发人员将自动监视他们创建的用户拥有的存储库，接收关于 gists 上发生的新对话的通知，并查看评论者的全名……如果他们选择这样做的话。

*   **你为什么不支持 OOP？**我们必须告诉你一个比世界上所有 GitHub 新闻都好的消息，所以我们不能更强烈地推荐阅读 David Cassel 在 New Stack 上的文章[研究为什么这么多开发人员讨厌面向对象编程](https://thenewstack.io/why-are-so-many-developers-hating-on-object-oriented-programming/)。和大多数事情一样，要点是“一些开发人员喜欢它，但一些人讨厌它”，讨厌它的人的主要例子是 [Ilya Suzdalnitski，](https://github.com/suzdalnitski)“一位高级全栈工程师，上个月发表了一篇 6000 字的文章，称 OOP [是一场‘万亿美元的灾难’。”不管你喜欢还是讨厌面向对象编程，卡塞尔提供了一个对面向对象编程和函数式编程的矛盾感受的完整旅程，尽管你可能会很快猜到苏兹达尔尼茨基会站在哪一边。](https://medium.com/better-programming/object-oriented-programming-the-trillion-dollar-disaster-92a4b666c7c7)

https://Twitter . com/ThatEricAlper/status/1164182929687363584

GitLab 是新堆栈的赞助商。

由 [Mantas Hesthaven](https://unsplash.com/@mantashesthaven?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/search/photos/goodbye?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>