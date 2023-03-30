# 云铸造峰会:开发者不必担心 Kubernetes

> 原文：<https://thenewstack.io/cloud-foundry-summit-developers-shouldnt-have-to-worry-about-kubernetes/>

[Cloud Foundry Foundation](https://www.cloudfoundry.org/) 的第一次虚拟峰会反映了该组织对 Kubernetes 的重视，并强化了其降低开发人员团队为云原生环境创建应用程序的门槛的使命。

随着 Cloud Foundry 将其两年一度的会议之一带到网上， [Cloud Foundry 北美峰会](https://www.cloudfoundry.org/events/summit/na-virtual-2020/)也恰逢 [Chip Childers](https://www.linkedin.com/in/chipchilders) ' [于 4 月](https://thenewstack.io/chip-childers-takes-executive-director-role-at-cloud-foundry/)被任命为 Cloud Foundry 的新执行董事，带来了 Kubernetes-for-DevOps 的焦点。这个想法是，Cloud Foundry 命令行界面(CLI)体验和其他工具应该使开发人员和运营团队在迁移到 Kubernetes 环境时变得更加容易。

“当我接任执行董事时，我意识到我们社区的能量正在围绕一个新的焦点增长，将世界级的开发人员体验云铸造带到 Kubernetes 基础设施的每个地方，”Childers 在他的主题演讲中说。

在许多方面，Cloud Foundry 仍然依赖于其在 cloud native 甚至 Docker 之前的根基，作为一个旨在优化 CI/CD 工作流的开源应用平台。随着它的发展，这个想法是继续“使开发人员的生活更容易”，而今天它“使他们更有效率，并帮助他们从几个月和几周的软件开发周期时间减少到几天甚至几个小时，”Childers 在活动前夕告诉新的 Stack。

Childers 说，对于 Kubernetes 来说，全球大多数大型企业都有云铸造和 Kubernetes 实例。“他们一直在并肩工作，解决不同的用例，”他说。

然而，Childers 说，Cloud Foundry 正试图为开发者提供更先进的功能，而不会“使他们过于复杂”。“我们希望尊重大多数开发人员的精神周期应该如何专注于他们正在解决的业务问题和他们正在构建的应用程序，而不是他们试图部署它的东西，”Childers 说。

为此，CFF 还在峰会上推出了两个新项目，包括 [KubeCF](https://www.cloudfoundry.org/kubecf/) 和版本 7 的 Cloud Foundry 命令行界面( [cf CLI v7](https://docs.cloudfoundry.org/cf-cli/v7.html) )。

KubeCF 作为 Kubernetes 的 Cloud Foundry 应用程序运行时(CFAR)的发行版，旨在改善开发人员的体验，同时为运营团队提供工具，包括用于在 Kubernetes 环境中部署的 API。

“KubeCF 旨在在 Kubernetes 的基础上提供您今天所知的完整云铸造体验，它通过打包 Cloud Foundry 并确保它可以在 Kubernetes 环境中部署和管理来实现这一点，”Childers 在他的主题演讲中说。

在峰会期间，[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉新堆栈，Cloud Foundry 命令行界面(cf CLI v7)第 7 版的发布提供了一些“有趣的功能，可以平坦化开发人员的学习曲线，并普遍减少开发人员在发布相关任务上花费的时间”。例如，滚动应用程序部署自动化了复杂和容易出错的部署工作流，而无需开发人员创建“完成此任务所需的”BOSH 作业，Volk 说。

“我还假设下一个 CLI 版本解决了滚动应用部署功能的当前限制列表，例如缺乏对数据库迁移和非 web 流程的支持，以进一步减少开发团队目前仍然存在的对跳入 CF 的保留，”Volk 说。

Volk 说，虽然滚动应用程序部署是列表中最有趣的功能，但这一版本“实现了云基金会的雄心，即让 Kubernetes 环境的平台和应用程序开发更加简单”。“所有其他新功能也朝着减少开发人员学习和持续执行以基础设施为中心的任务的需求的正确方向发展，”Volk 说。

然而，Volk 说，还有待观察“这个新版本离真正实现消除对编排任务的担忧的崇高任务有多近”。“在接下来的几周和几个月里，我们将密切关注这一点，因为在该平台过去两年失去人气后，看看 CF 是否能再次振作起来将是一件有趣的事情，”Volk 说。

CLI v7 传达的 Cloud Foundry 主要功能包括:

*   滚动应用程序部署:将更新推送到应用程序，而不会导致停机。
*   运行 cf 推送子步骤命令:更直接地控制 cf 推送过程。Cloud Foundry 表示，这些命令将 cf 推送过程分解为可以独立运行的子步骤。
*   使用多个进程推送应用程序:一个命令可以推送运行不同进程的应用程序。
*   使用 Sidecar 进程推送应用程序:在应用程序所在的容器中运行额外进程的能力。
*   使用元数据:元数据可以直接添加到空间和应用程序等对象中，无需监控和审核。

## 反对种族主义的真正行动

Childers 在他的主题演讲中对种族主义进行了坦率而真诚的评估，因为技术社区和世界的这一丑恶面继续展现出来。

“我们也正在经历一场早该进行的对系统性种族主义的必要而重要的清算。

现在，我们的社区一直以热情、包容和努力实现多元化而自豪。虽然作为一个社区，我们可能没有能力解决社会中的所有不公正现象。我们是一个谈话的地方。"

他说，Childers 建议“我们每个人都应该花时间去理解我们的显性和隐性偏见”。

Cloud Foundry 的高级营销经理凯特琳·奥康奈尔(Caitlyn O'Connell)在多样性午餐会上介绍了[Shakti Butler 博士的](https://www.world-trust.org/shaktibutler)演讲“我们是如何取得现在的成就的？种族不平等的制度。”从奥康纳在洛杉机的家中，每天支持黑人的命也是命的抗议声清晰可闻。

“我相信，今天多元化午餐会的内容一如既往地令人大开眼界、鼓舞人心、引人关注，希望你们大多数人已经注意到，美国正面临清算。事实上，你可能现在就能从你的扬声器里听到，汽车鸣笛声援黑人的命也是命的示威游行，在过去的几个星期里，这种示威游行每天都在我的街道拐角处发生，”奥康奈尔说。“该基金会支持黑人的命也是命，并相信种族平等，作为一个社区，我们有机会看看白人至上主义和科技产业以及其他领域，并学习如何消除它。我们必须对我们的同事首席执行官、朋友、家人、市长、州长和我们自己负责。”

巴特勒博士是一名教育家和电影制作人，也是[世界信托教育服务机构](https://www.world-trust.org/)的总裁，他采用了一种分析的方法来描述和揭露系统性的种族主义和种族不平等——或者说“种族化”，巴特勒博士说用这个词更合适——以及为什么它经常被忽视。

“我们没有人创造这个系统，当然也没有人创造历史。我们没有人创造殖民和资本主义，”巴特勒博士。“所有这些都是我们与生俱来的制度，但我们必须明白，为了让这个制度继续下去，我们必须否认种族主义的核心。我们不能忽视正在发生的事情。”

## 开始

如上所述，Cloud Foundry 的平台旨在简化开发人员的工作方式，尤其是在为 Kubernetes 环境创建代码时。开发者也应该从 Cloud Foundry 所说的源源不断的新工具和新功能中受益。许多操作工作仍在幕后进行，而与此同时，平台被配置为促进部署开发人员团队创建的代码和应用程序的操作工作。

NovaTec Consulting 的顾问 Mirna Alaisami 在她的演讲中演示了她所说的 Cloud Foundry 如何在不降低 Kubernetes 部署速度的情况下方便开发人员的任务。NovaTec Consulting 的 Mirna Alaisami 说,“神奇的 CF 推送命令……将应用程序从内部推送到平台上。”

“因此，开发人员使用神奇的 CF push 命令，将一段代码带到平台上，”Alaisami 说。"然后这个应用程序被从内部推送到平台."

Alaisami 展示了一旦通过 Cloud Foundry 界面创建了一个应用程序，就可以通过 CF 的“创建服务”命令将其连接到存储、数据库和消息服务。“这里最棒的是开发者不必关心任何连接设置的配置，”Alaisami 说。

Cloud Foundry Foundation 是新堆栈的赞助商。

由[蒂姆·莫斯霍尔德](https://unsplash.com/@timmossholder?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/s/photos/push?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过推特或脸书访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>