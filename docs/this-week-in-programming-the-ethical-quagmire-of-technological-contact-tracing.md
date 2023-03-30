# 本周编程:技术接触追踪的伦理困境

> 原文：<https://thenewstack.io/this-week-in-programming-the-ethical-quagmire-of-technological-contact-tracing/>

作为开发人员，本能是寻找问题的技术解决方案。在疫情的情况下，[接触追踪](https://www.who.int/news-room/q-a-detail/contact-tracing)是一种试图防止疾病进一步传播的传统策略，通常通过采访受感染的个人来了解他们在最近一段时间内与谁接触过，然后与这些人取得联系，以便他们可以自我监测和隔离，以进一步防止传染病的传播。

像任何事情一样，联系追踪也有其局限性——你说你“接触过”的人可能不包括前一天在商店排队时站在你旁边的人，你可能不希望那些询问你的人知道你因为这样或那样的原因接触过谁。例如，在应对非洲的埃博拉疫情时，无国界医生组织(T2)遇到了这种不信任，并发现只有当合同追踪是社区努力的结果时，它才更成功。

在过去一周于 [Snyk](https://snyk.io/) 的 [All The Talks 虚拟会议](https://www.allthetalks.org/)上举行的“黑暗时代的技术伦理”小组讨论会上，技术专家、工程师和作家 [Anne Currie](https://www.annecurrie.com/) 谈到了亚洲国家在利用技术监控其公民方面取得的成功，但也谈到了同样的技术实施在西方国家会出现的隐私问题。柯里谈到无人机在城市上空盘旋，测量人们的体温，使用面部识别来识别他们，然后将他们强制隔离。

“现在，我们可能不想在西方使用这种方法有两个原因。一，这是非常重手。在一个民主社会里，我们可能很难做到这一点，但更重要的是，我们可能做不到——几年来，中国在内部监控上的支出一直相当于其整个对外国防预算。我们还没有，我们还没有到那个地步，”柯里说。

虽然这种特殊的想法对美国来说可能不是一个现实的解决方案，但已经出现了两种值得注意的努力([和其他](https://covid-global-hackathon.devpost.com/submissions/search?utf8=%E2%9C%93&terms=contact+tracing&sort=))来通过使用匿名化的蓝牙信号来解决这些问题。首先，麻省理工学院提议[在保护隐私的同时自动追踪新冠肺炎联系人](http://news.mit.edu/2020/bluetooth-covid-19-contact-tracing-0409)，使用蓝牙“啁啾声”和功能非常类似于苹果的“查找我的”手机功能。

[https://www.youtube.com/embed/yuXzAh4slNw?feature=oembed](https://www.youtube.com/embed/yuXzAh4slNw?feature=oembed)

视频

麻省理工学院的具体解决方案[PACT:Private Automatic Contact Tracing](https://pact.mit.edu/)是“任何人都可以在任何智能手机上部署的技术标准/规范”，它承认，它的成功需要“一种可信的、保护隐私的方法”，以实现广泛采用，以及在所有智能手机平台上的可用性，“以确保广泛和公平的部署。”

这就是第二个建议发挥作用的地方，谷歌和苹果，他们已经[联手](https://www.apple.com/newsroom/2020/04/apple-and-google-partner-on-covid-19-contact-tracing-technology)宣布了一项基于相同技术理念的努力，但增加了被烘焙到 Android 和 iOS 的额外好处，这样两个主流移动操作系统不仅可以相互通信，还可以在后台运行这样一个软件。

我知道，现在你对隐私的感觉很敏锐，但两家公司都保证该技术提供完全匿名，根据 Vox 上一篇关于隐私问题的文章 T11，这是一个“在疫情结束时淘汰联系人跟踪工具的计划，尽管具体哪些软件功能将会消失以及什么被视为‘疫情的终结’仍需解释。”

虽然这些担忧肯定是有根据的，但即使是电子前沿基金会(EFF)，一个数字隐私权利和限制的坚定捍卫者，[告诉 Recode](https://www.vox.com/recode/2020/4/10/21216675/apple-google-covid-coronavirus-contact-tracing-app) 这是一个“非常时期”，他们“会接受一些 EFF 通常不会认可的非常非常的事情”[美国公民自由联盟](https://www.aclu.org/) (ACLU)也向[提供了一份对该提案的评论](https://www.aclu.org/press-releases/aclu-comment-applegoogle-covid-19-contact-tracing-effort)，这份评论在很大程度上给予了它前进的动力，写道“苹果和谷歌已经宣布了一种方法，似乎可以减轻最糟糕的隐私和集中化风险，但仍有改进的空间。我们将保持警惕，确保任何接触者追踪应用程序保持自愿和分散，仅用于公共卫生目的，并且仅在疫情期间使用。”

当然，除了围绕隐私的最基本的担忧之外，还有很多其他的担忧，正如彭博的一篇观点文章中所说，标题很简单:“新冠肺炎的追踪应用无法工作”为什么？围绕收入、医疗保健、种族不平等等等的无数其他因素。

“为了有效，它必须帮助最易受伤害的人——由于种族、收入、年龄和职业等特点，这些人不成比例地暴露于危险之中并正在死亡。然而，他们中的许多人根本没有智能手机。他们无家可归，在疗养院，在监狱。这是同一个古老的访问故事，类似于谷歌母公司 Alphabet 的一个部门 Verily 如何帮助人们找到并安排冠状病毒测试——但前提是他们必须有一个谷歌账户。最需要服务的人被关在门外。”

## 本周的节目中

*   **GitHub 将核心功能扩展到所有人:**本周，GitHub 终于解决了用户最大的抱怨之一，[通过向所有 GitHub 账户(而不仅仅是付费账户)提供无限合作者的私人存储库，使其服务对团队免费](https://github.blog/2020-04-14-github-is-now-free-for-teams/)。该公司写道，“地球上的每个开发人员都应该能够访问 GitHub”，“价格不应该成为障碍”，还指出，它已经将团队计划的价格从每个用户/月 9 美元降至每个用户/月 4 美元，立即生效。为了不被排除在对话之外，GitLab 迅速发起了一项社交媒体活动，使用 [#GitChallenge 标签](https://twitter.com/hashtag/gitchallenge)对 GitLab 和 GitHub 进行比较，并指出 GitHub 团队计划现在的成本与 GitLab 的青铜/入门产品相同。如果您自己的比较遗漏了任何细节，GitLab 还列出了使用 GitHub 的免费版本而不是 GitLab 会遗漏的功能，包括受保护的分支、PRs 草案和私有存储库中的 Wikis。
*   **回馈 Kubernetes？**如果你想对 Kubernetes 开源项目有所回报，你可以随时[加入 Kubernetes 发布团队](https://cloudblogs.microsoft.com/opensource/2020/04/11/join-kubernetes-release-team-roles-responsibilities/)——微软会给出具体的方法、期望和涉及的内容。随着每一个新的 Kubernetes 发布，一个新的 [Kubernetes 发布团队](https://github.com/kubernetes/sig-release/tree/master/release-team#kubernetes-release-team)由社区成员组成，他们处理发布本身的后勤工作，成员们充当领导者并执行诸如 bug 分类、编写发布说明、处理通信等任务。除了发布团队之外，还组建了一个影子团队来学习每次的流程。当前版本团队阴影的申请期刚刚结束，但总有下一次！

*   **IBM 提供免费的 COBOL 培训:**不，该公司不仅仅是与当今的时髦新语言脱节，只是当涉及到为失业系统的后端提供动力时，时髦的新语言与 COBOL 毫无关系，而失业系统有相当长的时间来跟上当前的流量。《输入》杂志[写道](https://www.inputmag.com/tech/ibm-will-offer-free-cobol-training-to-address-overloaded-unemployment-systems)[IBM 下周提供免费培训](https://newsroom.ibm.com/2020-04-09-IBM-and-Open-Mainframe-Project-Mobilize-to-Connect-States-with-COBOL-Skills)，同时还有“一个[论坛](https://community.openmainframeproject.org/c/calling-all-cobol-programmers/15)，在那里那些掌握语言知识的人可以与需要帮助维护其关键系统的公司相匹配。”除此之外，像 COBOL 这样的语言已经被证明可以获得丰厚的薪水，因为对 COBOL 程序员的需求仍然很高，而供应往往很低——正如最近的[编程紧急事件](https://www.cnn.com/2020/04/08/business/coronavirus-cobol-programmers-new-jersey-trnd/index.html)所示。该培训目前[可在 GitHub](https://github.com/openmainframeproject) 上获得。
*   **所有新冠肺炎开发者的需求都在一个地方:** ProgrammableWeb 已经[推出了](https://www.programmableweb.com/news/programmableweb-launches-covid-19coronavirus-developer-resource-center/brief/2020/04/13)一个[新冠肺炎开发者资源中心](https://www.programmableweb.com/coronavirus-covid-19)来帮助在一个地方展示“顶级的新冠肺炎相关 API 和其他 appdev 资源”。策划的内容大致分为五类，包括 API、仪表板和数据源、黑客马拉松和其他相关事件的列表、开源项目，以及相关新闻。此外，如果你碰巧知道没有列出的 API 或 SDK，你可以通过点击任何页面上的“添加 API&更多”按钮来添加它们，或者通过电子邮件将详细信息发送给[editor@programmableweb.com](mailto:editor@programmableweb.com)。如果一个地方还不够好，波兹曼还开放了[波兹曼新冠肺炎 API 资源中心](https://cts.businesswire.com/ct/CT?id=smartlink&url=https%3A%2F%2Fcovid-19-apis.postman.com%2F&esheet=52194497&newsitemid=20200326005142&lan=en-US&anchor=Postman+COVID-19+API+Resource+Center&index=1&md5=0a34058005dcd35226b915e97596b0a1)，它列出了来自州政府和组织的 API 集合。

GitLab 和 Snyk 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>