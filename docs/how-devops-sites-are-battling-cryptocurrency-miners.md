# DevOps 网站如何对抗加密货币矿工

> 原文：<https://thenewstack.io/how-devops-sites-are-battling-cryptocurrency-miners/>

本周 [GitLab](https://about.gitlab.com/) [宣布](https://about.gitlab.com/blog/2021/05/17/prevent-crypto-mining-abuse/)其基于网络的 DevOps 生命周期工具的政策发生了微妙但重大的变化。今后，所有希望使用持续集成作业的新试用帐户都将被要求提供有效的信用卡或借记卡号码。“不会收取任何费用，也不会转移任何资金，”公告强调。但 GitLab 希望这一变化将使其更难滥用其平台，因为它称之为加密货币开采的“大规模上升”。

这是加密货币矿工和一些最大的持续集成/持续交付平台之间正在升温的更大战争的一部分。

在其他地方，荷兰安全工程师[贾斯汀·珀多克](https://twitter.com/JustinPerdok)描述了他自 2020 年以来一直看到的一种涉及 GitHub 行动的策略。今年 4 月，Perdok 告诉 Record，他在自己的存储库[上经历了触发自动化测试](https://therecord.media/github-investigating-crypto-mining-campaign-abusing-its-server-infrastructure/)的拉请求，测试后的代码将在 GitHub 的基础设施上临时创建一个运行加密货币挖掘软件的虚拟机——有时一次会有 100 个加密矿工。Perdok 发现至少有一个帐户创建了数百个这样的 pull 请求，记录显示这些攻击“似乎是随机和大规模发生的”。

4 月下旬，GitHub 的一篇博文承认“行为上的密码挖掘并不新鲜”，并补充道“我们从一开始就一直在打击滥用者。”(2018 年推出的 GitHub 行动。)”然而，随着硬币价格的上涨，滥用者的数量也在不断升级。我们已经花费了数千小时来打击滥用，并实施了几十种不同的缓解措施来检测和防止滥用。”

所以现在 [GitHub](https://github.com/) 也做了一些新的改变，上个月更新了它的策略，要求来自第一次贡献者的 pull 请求首先由具有写访问权限的存储库协作者[手动](https://docs.github.com/en/actions/managing-workflow-runs/approving-workflow-runs-from-public-forks)批准。该公司 4 月份的博客文章称赞了其 CI/CD 服务的用户提高生产力的方式，但补充说，“不幸的是，我们也看到了各种各样的不良行为者滥用行为，影响服务性能，并导致开源项目拒绝服务。”

## 横行无忌

但是，在记录的文章之后，上周有更多的服务站出来报告类似的攻击。在[的一篇后续文章](https://therecord.media/crypto-mining-gangs-are-running-amok-on-free-cloud-computing-platforms/)中，记录还引用了 GitLab、[微软 Azure](https://azure.microsoft.com/) 、 [TravisCI](https://travis-ci.com/) 、 [LayerCI](https://layerci.com/) 、 [CircleCI](https://circleci.com/) 、 [Render](https://render.com/) 、 [CloudBees CodeShip](https://www.cloudbees.com/products/codeship) 、 [Sourcehut](https://sourcehut.org/) 、 [Okteto](https://okteto.com/) 。(他们文章的标题？"密码挖掘团伙在免费的云计算平台上横行霸道.")

该网站还报道了一种新策略:在平台上创建免费试用账户来运行加密货币挖掘应用程序——一次又一次，“将提供商的服务器保持在其使用上限，并减缓其正常运营。”(他们提供的受影响公司名单几乎相同:微软 Azure、LayerCI、TravisCI、Sourcehut、CloudBees CodeShip 和 CircleCI。)

今年 2 月，微软的 Azure Pipelines 甚至[终止了其新 CI/CD 项目的免费管道](https://devblogs.microsoft.com/devops/change-in-azure-pipelines-grant-for-public-projects/)，抱怨滥用行为，特别是加密货币矿工，“变得越来越严重”，占“Azure DevOps 中新公共项目的很高比例……除了从团队中消耗越来越多的能量，这还使我们的托管代理池面临压力，并降低了我们所有用户的体验——包括开源和付费用户。”(在收到一封电子邮件请求后，Microsoft Azure 已经更新了策略以允许这一功能，该邮件请求包含预期用途的描述和到构建库的链接。)

“我们很抱歉这将为希望使用 Azure Pipelines 进行 CI/CD 的开源客户带来不便，”该公告称。“不幸的是，我们认为这是我们继续为所有客户提供高水平服务的必要条件。”

GitLab 的博客文章还强调，高负载加密货币矿工的问题正在困扰另外几个也提供免费 CI/CD 管道的平台，引用了托管 DevOps 平台 LayerCI 的首席执行官兼联合创始人 Colin Chartier4 月份的一篇博客文章。警告“[加密矿工正在扼杀免费 CI](https://layerci.com/blog/crypto-miners-are-killing-free-ci/) ，”Chartier 分享了更多受影响的 CI 提供商的故事，包括 TravisCI 和 ship able([现在由](https://jfrog.com/press/jfrog-acquires-shippable-delivers-complete-devops-pipeline-automation-from-code-to-production/?utm_source=thenewstack&utm_medium=website&utm_campaign=platform) [JFrog](https://jfrog.com/) 拥有)，它们也“由于加密货币采矿攻击而恶化或关闭了它们的免费层。”

TravisCI(一家托管持续集成服务公司)在 11 月份的一份声明中强调说:“我们热爱我们的开源软件团队……我们非常想支持这个社区。但该公司补充说，“最近几个月，我们遇到了严重滥用这一产品的意图，”理由是加密货币矿工的活动增加，以及“TOR 节点运营商等”。…滥用者一直在占用我们的构建队列，导致每个人的性能下降。”

## 引发讨论

沙特尔 4 月份的博客文章认为，加密货币价值的上升加剧了这一问题。“不良行为者全职攻击平台即服务提供商的免费层变得有利可图。”该公司提供了具体的案例研究:一名用户显然每月收入 77 美元，“这在许多国家都是一笔不小的数目，尤其是考虑到所需的唯一工具是一台笔记本电脑和一个互联网连接。”

帖子继续写道，“提供商可以尽最大努力执行服务条款，但只要进行这种攻击有利可图且无法追踪，他们就会继续变得更加复杂并规避措施。”

GitLab 的帖子列举了加密货币矿工的真实日常影响。“除了成本增加之外，这种滥用还会给 GitLab.com 用户带来间歇性的性能问题，需要我们的团队全天候工作，以便为我们的客户和用户提供最佳服务。”

但这引发了更大的讨论。 [Docker](https://www.docker.com/) CTO [贾斯汀·科马克](https://twitter.com/justincormack) [在推特上与他的 11500 名粉丝分享了](https://twitter.com/justincormack/status/1386614703145852929) LayerCI 的博客帖子，引起了一些有趣的反应。“我们必须将‘免费等级’重新定义为‘让秘密采矿无利可图的价格’，”DevOps 顾问伊斯梅尔·巴斯金打趣道。

当 LayerCI 的博客文章出现在黑客新闻上时，引起了更多的讨论。在[的一条评论中，](https://news.ycombinator.com/item?id=26937578)费城的程序员[德鲁·德沃](https://github.com/ddevault)，Sourcehut 背后的维护者/系统管理员，警告这个问题正在蔓延。“我和 CI 行业的许多其他人都有过接触，在过去的几个月里，这已经成为我们所有人的一个大问题。整个行业都成立了知识共享工作组，以应对加密挖掘的流行。”

Sourcehut 最近还宣布了一项计划，要求所有项目维护者[为他们的持续集成服务 builds.sr.ht 保留一个付费账户](https://man.sr.ht/ops/builds.sr.ht-migration.md)，抱怨恶意用户“一直在故意在几十个频繁注册的账户下提交大量工作，并故意绕过我们的滥用检测，以尽可能多地使用我们的资源来挖掘加密货币。

"这耗尽了我们的资源，并导致普通用户的长构建队列."

德沃在《黑客新闻》上的评论继续反对加密货币本身——除其他外，声称它“向整个技术领域引入了不正当的激励。”这是 LayerCI 的 Chartier 在他的博客文章中提出的观点:云平台上的免费层受到许多加密货币奖励“工作证明”的方式的威胁。

“是的，我们正在 CodeShip 上处理这个问题，”Hacker News 上的另一个评论补充道，“我非常确定所有的 CI 服务都被免费账户或欺诈性付费账户淹没了。”

一位 CodeShip 工程师说，“不仅仅是免费账户。有时他们为我们的账户支付小额费用，这比直接在 AWS 上租赁要便宜得多，并以最大容量开采加密货币。”

在黑客新闻的讨论中， [Anurag Goel，](https://www.linkedin.com/in/anuragoel/)Render 的创始人兼首席执行官，一个托管应用和网站的统一云平台，[也同意](https://news.ycombinator.com/item?id=26948311)“不仅仅是 CI 提供商:我们在 Render 上看到了同样的事情。”

或者，正如记录所描述的，“如果它是一个提供免费访问高计算系统的网络服务，密码挖掘团伙现在很可能已经试图滥用它了。”该网站报道称，一些加密货币论坛甚至包括教程，分享如何在[甲骨文云](https://www.oracle.com/cloud/)或[阿里云](https://us.alibabacloud.com/)上使用免费试用账户进行挖掘。

最终，这变成了基础设施提供商的技术解决方案和试图绕过它们的矿工军团的技术伎俩之间的战斗。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>