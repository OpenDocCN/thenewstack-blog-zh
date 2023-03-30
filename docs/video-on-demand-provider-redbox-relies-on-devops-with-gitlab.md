# 视频点播提供商 Redbox 依靠 DevOps 和 GitLab

> 原文：<https://thenewstack.io/video-on-demand-provider-redbox-relies-on-devops-with-gitlab/>

[GitLab](https://about.gitlab.com/) 赞助本帖。

 [布雷因·马特罗

Brein 是 GitLab 的高级内容营销经理和客户，是一位经验丰富的软件技术作家和编辑。她与丈夫和两个儿子住在新罕布什尔州，教授 Vinyasa 瑜伽，并拥有一家 Ben & Jerry's。](https://www.linkedin.com/in/brein-matturro-081a801/) 

Redbox 主要以通过自动零售亭提供电影和视频游戏租赁而闻名，最近已经扩展到提供流媒体服务。在 GitLab Connect Chicago 上，Redbox 的[云开发经理 Joel Vasallo](https://www.linkedin.com/in/joelvasallo) 和[移动应用经理 Nicholas Konieczko](https://www.linkedin.com/in/nick-konieczko-42895354) 在他们的演讲“像狐狸一样交付软件”中描述了他们是如何实现应用交付目标的

Redbox On Demand 是该公司最新的流媒体平台，建立在。NET 核心在云中的 Linux 上的容器中。这家视频零售公司在构建其最新平台时有几个目标，特别是专注于云计算流程和移动应用程序开发。

在这篇文章中，Vasallo 和 Konieczko 分享了他们创建成功流媒体服务的三个主要目标:现代化软件开发、快速交付到云以及代码所有权。他们还讨论了为什么云和移动团队决定放弃他们现有的四个工具并选择迁移到 GitLab，以及这一步骤如何为不同的团队创建一致的工作流。

## **目标#1:使软件开发过程现代化**

移动和开发团队希望能够使用最新技术创建平台，以便为客户提供最好的产品。“[他们做的方式没有错，但从某种意义上说，这个世界已经从传统的 Windows 服务器……在数据中心运行……走了很长的路。NET 框架之类的东西，我们真的想让开发者能够使用容器，”瓦萨洛说。

***成果:*** 移动和开发团队现在使用 GitLab CI，利用浪子。“我们选择 GitLab 是因为我们想使我们的软件开发过程现代化，”Vasallo 说。GitLab 的强大功能及其与其他工具协同工作的能力有助于创建一个现代化的无缝开发工作流。

## **目标 2:加速向云的交付**

提供随需应变的服务意味着应用程序必须在需要的时候准备好。作为流媒体领域的新手，Redbox 转向云计算非常重要。“我们还希望利用云的力量，并拥有云的扩展视角。我们想在云中，就像现在每个人都想的那样。我们还希望确保我们的功能更快地推出，因为在流媒体业务中，最重要的是率先将您的功能推向市场，”瓦萨洛说。

*结果:*团队现在使用 GitLab CI 和 Spinnaker。“我们希望增加软件交付，做对团队最有利的事情。我不想规定开发人员在他们的日常工作流程中应该做什么，”Vasallo 说。为了做对所有团队最有利的事情，并允许个人规划他们自己的过程，GitLab 和 Spinnaker 一起帮助确保安全和及时的交付。

## **目标 3:让开发者拥有自己的应用**

希望开发人员能够在任何时候通过点击一个按钮将代码部署到生产环境中。开发人员将有能力只写代码，一个工作工具将能够挑选错误。“代码是基于一个批准过程而发布的，”Vasallo 说。"从本质上讲，开发者能够拥有和操作他们的代码."

***结局:*** 目的达到了，据瓦萨洛说。“最终，开发者拥有自己的应用。GitLab Enterprise 允许团队拥有自己的垂直市场，以及 Spinnaker，这允许他们将其部署到他们选择的任何云提供商，”Vasallo 说。通过使用 Spinnaker 和 GitLab，开发人员现在可以轻松地将代码部署到生产中，基本上拥有自己的代码。

## **关键要点**

### 将“版本”置于版本控制中

Vasallo 说，有大量不同的 Git 和源代码控制工具可用。“也就是说，我们有一个内部 Git 服务器，我不知道它实际上在运行什么，还有 GitHub.com。我们还有 Team Foundation Server 和 Azure DevOps，”Vasallo 说。“因此，有了所有这些东西…团队真的无处不在，他们都有不同的源代码-访问这些东西简直是一场噩梦。”

解决方案是尝试另一个版本控制系统。瓦萨洛说，GitLab 是“从我们的角度来看最可靠的解决方案”。“GitLab 支持一些东西，像本地的，以及在云上的。瓦萨洛说。“但是，更重要的是，最终它让开发人员能够在一个大型组织中控制他们的名称空间。”

### GitLab 致力于移动开发

红盒子的移动团队是第一批试用 GitLab.com 的。“这很简单，非常容易上手。那里有很多文档，都是我喜欢的东西，”Konieczko 说。“这非常划算，我们可以免费试运行，公开回购，测试不同的东西，不同的功能等。看看它是否能为我们的团队工作——它确实做到了。”

### 是的，你也可以用詹金斯

Konieczko 说，GitLab 只是希望红盒子的开发过程能够成功。“有许多很棒的工具，如 GitLab CI、GitLab 问题板……以及 GitLab 的工件库，这些都内置在平台中，”Konieczko 说。“GitLab 的 CI/CD 流程管道，所有这些都包括在内。但如果你不想用它，它会适应你的商业模式。”

例如，瓦萨洛的团队使用詹金斯，并且“仍然可以使用 GitLab，”瓦萨洛说。“不存在说‘哦，你在用詹金斯’的屏蔽事件。你不能和我们说话。错误。封锁，’”科涅茨科说。

相反，瓦萨洛说，他的团队成员可以毫无障碍地键入“吉拉，带我们进入 GitLab ”,并可以无缝地使用 JFrog artifactory 和 Spinnaker 进行软件交付，瓦萨洛说。“再说一次，GitLab 转变为你所需要的业务，这是我真正欣赏的事情，站在 DevOps 一边，”Vasallo 说。

最终，Redbox 的分布式团队成功地脱离了分散的工具链，并成功地完全迁移到 GitLab。GitLab 确保现代化的软件开发工作流程，快速交付到云，开发人员现在拥有自己的代码。凭借 GitLab 与 Jenkins 的轻松集成，Redbox 也能够无缝过渡到一个新平台。

要了解 GitLab 如何帮助移动和开发团队实现他们的平台目标(以及更多)，请[观看演示](https://about.gitlab.com/compare/github-actions-alternative/)。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>