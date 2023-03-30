# Monki Gras、北欧开发社区以及为什么数据科学对系统管理员很重要

> 原文：<https://thenewstack.io/new-stack-analysts-show-28-monki-gras-nordic-dev-communities-data-science-matters-sysadmin/>

新堆栈是的媒体赞助商

[Monki Gras](http://monkigras.com/)

由 RedMonk 举办的开发者活动，今年的主题是关于北欧工艺、文化和技术。RedMonk 将为该活动提供一张免费入场券和 15%的折扣。尝试免费 newstack 有机会获得免费机票，或在标价的基础上享受 15%的折扣。

New Stack 创始人亚历克斯·威廉姆斯(Alex Williams)和 RedMonk 的共同主持人唐尼·伯克霍尔茨(Donnie Berkholz)期待着一个充满会议活动的日程，通过比较他们的旅行规划工具，轻松进入新 Stack 分析师的第一集。

更多剧集，请查看新堆栈的播客部分[。](https://thenewstack.io/podcasts/)

[#28: Monki Gras、北欧开发社区以及为什么数据科学对系统管理员很重要](https://thenewstack.simplecast.com/episodes/28-monki-gras-nordic-dev-communities-and-why-data-science-matters-to-the-sysadmin)

RedMonk 的 [Monki Gras](http://monkigras.com/) 将于本月晚些时候首次推出，其主题是“北欧工艺文化和技术”

唐尼解释了选择关注北欧和斯堪的纳维亚对技术的影响背后的动力。“大量真正重要的互联网基础设施来自北欧国家——很多是我以前没有意识到的。”

“许多人都知道编写 Linux 的 Linus Torvalds 在芬兰长大，”Donnie 说，“但人们可能不知道的是，像 SSH、IRC、MySQL、Skype 以及最近的 Spotify 和 Varnish 这样的工具都来自北欧国家，这些互联网基础设施的许多核心部分确实为我们其他人带来了沟通和技术的平等……”

Alex 想知道他们的区域移动电信提供商(如诺基亚和爱立信)如何帮助塑造应用程序开发人员社区。

Donnie 认为这些公司的影响肯定是巨大的，尤其是考虑到诺基亚是该地区最大的雇主之一。“随着诺基亚大量裁员，那里的创业文化出现了复苏，”唐尼说。这种复兴源于“受过良好教育、长期从事有趣的移动工作的技术人员”，他们现在开始自己的事业。

Alex 引用 Docker 对市场的影响以及对云基础设施的影响，揭示了分布式应用程序的开发和管理是新堆栈在未来一年将关注的主题。

Donnie 将此与影响配置管理的不同趋势进行了比较，这些趋势在可伸缩性中发挥了作用。这就引发了对可组合性的讨论，以及对工具的讨论，比如来自 HashiCorp 的 [Apache Brooklyn](https://brooklyn.incubator.apache.org/) 、 [Cloud Formation](http://aws.amazon.com/cloudformation/) 和 [Terraform](https://hashicorp.com/blog/terraform.html) 。Donnie 希望在接下来的几年里看到这个领域的更多发展。

此外，Donnie 说，应用程序开发者正在寻求跨集群的良好同步体验。“如今，只有当您拥有一个所有东西都同时启动和运行的实时集群时，它才是有价值的。人们不再寻找热备份或冷备份。他们希望拥有一个动态同步的整个集群。无论是 Riak 和 CRDTs，还是 Cassandra，这种技术对人们构建应用程序的方式越来越重要。”

Alex 想知道跨多个云服务运行应用程序的能力，例如 SoftLayer、Amazon Web Services、Google Compute Engine 和 OpenStack。他想知道，OpenStack 会不会是一种充当中间云层的媒介？

Donnie 认为这种媒介非常重要，因为形势要求公共云和私有云需要同步。“没有人希望根据运行软件的位置来维护软件的多个版本。它不能有效地扩展，当你试图在它们之间同步时，你总是会遇到奇怪的问题，”他说。

“像 OpenStack 或 CloudStack 这样可以由公共云提供商或托管提供商以及本地运行的产品，或者像 AWS 这样可以利用 Eucalyptus 的剩余部分并拥有兼容 API 的产品，我认为这将是真正混合云的先决条件，”Donnie 说。

“现在，人们真正做到这一点的最佳例子之一是 VMware 与[v cloud Air](http://vcloud.vmware.com/explore-vcloud-air/what-is-vcloud-air)，他们可以让人们运行超传统的 vSphere 部署，并实现到云的或多或少的无缝迁移。”

Donnie 说，客户服务也将是基础设施市场的驱动力之一。在这方面，他提到了“一个非常有趣的工具”——云提供商比较服务 [CloudHarmony](https://cloudharmony.com/) 。Alex 花了几分钟查看了一下，然后他问 Donnie 在新的一年里他最关心的话题是什么。

“趋同，”唐尼说；"开发、设计和数据科学的交叉点."当 Alex 要求深入这些漩涡时，Donnie 向我们介绍了他存档的博客帖子“[开发商和设计师碰撞的那一年](http://redmonk.com/dberkholz/2013/12/16/the-year-developers-and-designers-collided/)”，其中包括他用来说明他的想法的维恩图。

早些时候，在讨论分布式系统时，Donnie 提到了他最近的一篇文章“系统管理员学习数据科学的时间到了”，其中他认为数据科学在现代基础设施中是不可避免的，并提出了一些开始学习的方法。

“我们今天遇到的系统的规模意味着监控数据正在变得疯狂，”唐尼说。“许多这种分布式系统的问题是，我们不一定能预先定义所有故障点的样子。”

“我们以前从未这样做过，”他说。

图片(汉斯·弗雷德里克·古德的《哈丹格尔峡湾》)来自维基媒体[。](https://en.wikipedia.org/wiki/Hans_Gude#mediaviewer/File:Fra_Hardanger_Gude.jpg)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>