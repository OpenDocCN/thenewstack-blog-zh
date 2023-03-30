# MongoDB Atlas(最终)获得了一个命令行界面

> 原文：<https://thenewstack.io/mongodb-atlas-finally-gets-a-command-line-interface/>

命令行界面是开发人员每天生活和呼吸的地方，所以毫不奇怪的是， [MongoDB 为其](https://www.mongodb.com/blog/post/mongodb-announces-new-atlas-cli) [Atlas 数据库服务](https://www.mongodb.com/atlas)开发的新命令行界面 (CLI)在有限发布期间受到了客户的热烈欢迎，并在上周 MongoDB 世界大会的主题演讲中受到了热烈欢呼。

[Atlas CLI](https://www.mongodb.com/docs/atlas/cli/stable/) 是 Atlas 新的专用命令行界面，允许客户通过命令行而不是 GUI 来管理 Atlas 的服务，这在过去是一项要求。不要与 [mongo shell](https://www.mongodb.com/docs/mongodb-shell/) 混淆，后者是另一个已经存在的命令行工具，但仅限于数据查询、更新和更多管理任务。Atlas CLI 与 Mongo shell 携手合作，它们一起发布。

随着发布日期目标定在会议开始，团队在内部进行了更早的试发布，开始测试功能，编写文档，并改进/添加功能。CLI 最早的功能之一是 OIDC 身份验证。

“以前，你必须使用 API 密钥，而进入这个过程很麻烦，所以我们从 Atlas 登录体验开始，现在它是无缝的；MongoDB 产品经理 Jakub Lazinski 在接受新堆栈的采访时说:“你只需输入你的用户名和密码，然后在 CLI 中进行认证。

CLI 团队着手的下一件事是入职体验，即 Atlas 设置；MongoDB CLI 现在使开始使用 Atlas 变得更加容易。

Lazinski 在谈到 CLI 如何简化 Atlas 的工作流程时说:“有了 onboarding 体验，最酷的部分是我们配置了许多以前必须手动完成的事情。过去需要几个步骤才能启动和运行的工作，现在只需在命令行上击几下键就可以完成。

CLI 功能丰富，包括创建数据库、创建集群、加载示例数据、部署到测试环境以及许多其他选项。CLI 将随着 Alas 的发展而发展，该团队打算保持 CLI 的最新状态。

创建 CLI 的 MongoDB 工程师古斯塔沃·巴赞说:“当一个新特性出现在 Atlas 中时，只需要一天，也许两天就可以添加到 CLI 中。

## **由开发者提供给开发者**

像 MongoDB World Conference 2022 上发布的大多数产品一样，Atlas CLI 是一个开发人员工具，尽管它确实只是开发人员为开发人员开发的一个工具。

当被问及这个项目是如何开始的时，巴赞大声说道:“CLI 是我的宝贝！”巴赞大约三年前开始在 MongoDB 工作。他最初的工作职责之一是一项重复的任务，要求他使用 GUI，并促使他四处询问，以查看是否有 CLI 或任何自动化的方法来让他将精力集中在其他地方。没有。

快进到 MongoDB 的年度黑客马拉松，Skunkworks。这是 MongoDB 员工有指定的一周时间跨团队工作，处理不关注关键路径的项目和想法。

巴赞选择利用他在 Skunkworks 的时间构建一个功能非常有限的原始 CLI 原型。虽然精简，但它有足够的能力获得产品和工程领导团队的支持。

## **工程团队和技术挑战**

CLI 项目的早期挑战之一是在日历上获得专用时间，但这确实是工程领导和产品团队发挥作用的地方。在支持项目后，投入了四分之一的时间和一名额外的工程师，使全职投入项目的工程师总数达到两名。

但是挑战并没有就此停止，正如巴赞所说的“我知道 CLI 是什么，但从未构建过。”

团队选择用 golang 编写并使用 [Cobra CLI 框架](https://cobra.dev/)，这对每个人来说都是新的。因此，有一个技术学习曲线，但慢慢地一切都走到了一起。

最初的 MVP 功能是创建一个集群和一个数据库用户。这是一个缓慢的循序渐进的学习过程，“这就是你如何创建一个集群，这就是你如何做这些事情，这就是他们如何走到一起，”巴赞说。

一个关键的学习收获是 CLI 体验需要非常人性化。巴赞说。“在某个时候，我们花了大量时间来改进错误处理和显示方式，因为我们基本上只是丢弃了从服务器返回的 JSONs。”

现在有四名工程师全职致力于 CLI，更多功能正在开发中，不过目前还没有其他功能的官方发布日期。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>