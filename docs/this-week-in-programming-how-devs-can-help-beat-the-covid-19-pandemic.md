# 本周节目:Devs 如何帮助击败新冠肺炎疫情

> 原文：<https://thenewstack.io/this-week-in-programming-how-devs-can-help-beat-the-covid-19-pandemic/>

虽然你们中的许多人可能忙着管理一份全职工作，这份工作突然变得完全没有任何规划，一个充满宠物、伴侣和需要照顾和关注的孩子的房子，以及全球疫情的情感重量真正开始占据主导地位，但还有其他人仍然有一些之前充满社交活动和新冠肺炎之前一般生活的空闲时间(比如你们中的一些人的工作)，他们正在寻求帮助。

如果你碰巧属于后一种类型，并且正在寻求充分利用你的技能、知识和业余时间，你很幸运；在过去的一周里，我们见证了无数的黑客马拉松、倡议和文章的推出，它们总结了各种各样的努力，如果你在努力保持工作和理智的过程中错过了所有这些，我们决定将它们带到这里。对于你们中的其他人来说，这里有一个网站，是某个开发者利用所说的空闲时间创建的，让你可以方便地与不能再来的朋友和家人一起看电影。

至于与他人的物理隔离、有效的在线交互以及在自己家中的舒适环境中高效工作，开发人员最终可以满怀信心地卷起袖子说:“我们明白了——从 BASIC 很酷的时候起，我们就一直在训练社交距离。”

信不信由你，自从我们第一次[询问开发人员是否可以帮助拯救世界](/this-week-in-programming-can-developers-help-save-the-world/)，引用 IBM 的 2020 年代码呼吁作为参与的一种方式，已经过去了一个月，现在该公司[已经将目光转向新冠肺炎](https://developer.ibm.com/callforcode/getstarted/covid-19/)，写道它正在“扩大 2020 年代码呼吁全球挑战，以解决除气候变化之外的世界对新冠肺炎的反应。”但这仅仅是新冠肺炎黑客马拉松热潮的开始，它现在包括由科技巨头、[州政府、](https://www.ny.gov/programs/new-york-state-covid-19-technology-swat-team)和草根倡议等组织的努力。

例如，世界卫生组织联合 AWS、脸书、Giphy、微软、Pinterest、Salesforce、Slack、抖音、Twitter 和微信等技术公司和平台，发起了[新冠肺炎全球黑客马拉松 1.0](https://covid-global-hackathon.devpost.com/) ，目前正在进行，提交截止日期为太平洋标准时间 3 月 30 日上午 9 点。如果你太迟了，不要担心，因为还有更多，比如我们上周提到的 [CODEVID-19 黑客马拉松](https://codevid19.com/)，它有一个每周滚动的截止日期。撇开最后期限不谈，[美国对新冠肺炎的数字响应](https://www.usdigitalresponse.org/)正在努力将技术、数据和政府专业人员与那些需要他们的人配对，以一种全国性的技术互助[的形式。](https://en.wikipedia.org/wiki/Mutual_aid_(organization_theory))

对于您，我们热爱开源的新堆栈读者，我们想强调一些我们认为您可能会特别喜欢的工作。首先，[新冠肺炎开源帮助台](https://covid-oss-help.org/)是“一个快速通道‘堆栈溢出’，在那里你可以从编写你所使用的软件的人或者是使用该软件的专家那里得到答案。”如果你碰巧是开源作者或专家，请随意回答问题。第二， [FOSS Responders](https://fossresponders.com/) 是一个志愿者运行的合作项目，旨在帮助开源维护者和类似的人实现新冠肺炎的效果。虽然该项目表示仍在寻找帮助的方法，但目前表示，它可能会提供“关于如何取消和谈判活动合同的建议，如何管理数字活动，以及个人或组织的财务支持。”

似乎这些还不够，还有许多其他的努力和资源可供你参与或利用。例如，在开放数据方面，GitHub 提供了一个关于在新冠肺炎开放合作的指南，而 StackOverflow 则着眼于在家里帮助对抗新冠肺炎的无数方法。ProgrammableWeb 有一个[开发者对抗新冠肺炎](https://www.programmableweb.com/news/developer-hackathons-to-combat-covid-19/review/2020/03/26)的黑客马拉松列表，甚至 Golang 团队也为 [Go、Go 社区和疫情](https://blog.golang.org/pandemic)提供了一些指导，其中 [Erlang 也加入了](http://erlang-solutions.com/blog/coronavirus-community-support-and-how-you-can-help.html)。

说到这里，让我们来看看过去一周在编程领域发生的事情，这些事情可能与流行病之类的事情没有直接关系。

## 本周的节目中

*   **Piranha 自动删除陈旧代码:**技术债务可以以多种形式出现，从过时的代码版本和依赖关系到过时的功能标志。后者是困扰优步的一个变种，它使用特性标志来处理实验和本地化特性。因此，公司[创建并开源了](https://eng.uber.com/piranha/)一个叫做 [Piranha](https://github.com/uber/piranha) 的工具，它可以自动删除与陈旧或过时的功能标志相关的代码，从而产生一个更干净、更安全、性能更好、更易维护的代码库。该项目目前可用于 Objective-C、Swift 和 Java 程序，该公司表示，它希望开源贡献者将“将 Piranha 应用于其他语言或提高其执行深度代码重构的能力”。“有关开始使用食人鱼的更多详细信息，请查看下面的[文档](https://github.com/uber/piranha)和介绍视频。

[https://www.youtube.com/embed/V5XirDs6LX8?feature=oembed](https://www.youtube.com/embed/V5XirDs6LX8?feature=oembed)

视频

*   **GitHub Desktop 简化了代理设置:**正如你已经听过无数次的那样，有很多人以前不在家工作，甚至包括你这种开发人员。好吧，GitHub Desktop 2.4 已经[引入了代理支持和问题创建](https://github.blog/2020-03-25-github-desktop-2-4-introduces-proxy-support-and-issue-creation/)，它说这应该有助于对抗“可怕的话，‘无法解析主机’。”“总之，GitHub Desktop 2.4 现在会自动处理这个设置。这也使得现在制造问题变得更加容易。哦，也许最重要的是，黑暗模式现在已经出测试版了，你们这些穴居的穴居开发者，你们。当我们谈论 GitHub 时，该公司已经为存储库管理员引入了[更简单的组织和更高的可扩展性](https://github.blog/2020-03-24-easier-organization-and-increased-scalability-for-repository-administrators/)，这基本上是以重新设计的页面的形式出现的，以显示管理员可以访问他们的 repo 和他们的访问级别，并允许他们改善对他们的存储库的访问管理。

*   **Google 的 Docs 季回归:**作为一个偶尔仍在编写代码的作者(开发者的[家庭烹饪种类)，这个项目吸引了我，所以我写信给你带来了关于 Docs 2020](/this-week-in-programming-what-kind-of-developer-are-you-anyway/) 季的[公告，它“将技术作者和开源项目聚集在一起几个月，致力于开源文档。”这仅仅是它的第二年，去年这个项目创造了](https://opensource.googleblog.com/2020/03/announcing-season-of-docs-2020.html) [44 个成功的文档项目](https://developers.devsite.corp.google.com/season-of-docs/docs/2019/participants)。所以，如果你需要一个技术作家来创建文档，这是你的机会。查看[时间表](https://developers.google.com/season-of-docs/docs/timeline)了解详情，准备申请吧！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>