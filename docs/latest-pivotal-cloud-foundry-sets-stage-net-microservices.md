# 最新的 Pivotal Cloud Foundry 为。网络微服务

> 原文：<https://thenewstack.io/latest-pivotal-cloud-foundry-sets-stage-net-microservices/>

上周， [Pivotal](https://pivotal.io/) 正式发布了其商业 [Cloud Foundry](https://pivotal.io/platform) 软件服务平台的最新版本 1.10，宣传了一些重大的——或许是姗姗来迟的——改进，包括对姐妹公司 [VMware 的 NSX](http://www.vmware.com/products/nsx.html) 虚拟网络层的支持。对于一些希望跨云平台安装 Cloud Foundry 资产并需要在所有平台上扩展单一安全和访问控制层的组织来说，仅此一点就可能改变游戏规则。

但是这一轮最引人注目的创新可能涉及到对一个你可能没有听说过的库的支持: [Steeltoe](http://steeltoe.io/) 。这是一项开源工作，由 Pivotal 管理，旨在构建一个受网飞启发的微服务模型。NET 框架应用——不仅仅是[。NET Core](https://www.microsoft.com/net/core#windowsvs2017) ，不是 [Xamarin](https://www.xamarin.com/) ，而是完整的 enchilada。

Pivotal 的产品高级主管 Richard Seroter 在谈到新的堆栈时承认:“我已经做了 15 年的. NET 开发人员，我还没有见过大规模运行 Windows 的平台。

“您可以进行潜在的配置管理。我可以用厨师，我可以用木偶。但是，在拥有由 Windows 提供支持的基础架构方面，您可以将它视为一种服务…现在，我们正迈向另一个层次。我认为这是一件期待已久的事情。”

## 流行的桌子

今天，尽管 Windows Server 仍然作为 Windows 客户端的管理平台和客户端/服务器整体的过渡平台而存在，但最新的云原生服务正在 Linux 上托管。这造成了一个技能缺口——一个多年无人问津的缺口，正在变成一个鸿沟。这并不是说 Windows 的原生架构依赖于集中化，而微服务依赖于分布，尽管这显然是正确的。而是那些合法的语言，包括 C#， [F#，](http://fsharp.org/)，[托管 Jscript](https://blogs.msdn.microsoft.com/gauravseth/2007/08/16/difference-between-jscript-jscript-net-and-managed-jscript/) ，我敢说，Visual Basic (VB。NET)，因为在一个独立于使软件定义的基础设施成为可能的生态系统之外的生态系统中成长而面临着不适当的惩罚。

“在 Pivotal，我们谈论了很多关于*重新平台化*，并决定移动什么，”Seroter 说，实际上并不需要填写从什么移动到什么的细节。

“坦率地说，我认为我们的心态是，仅仅将你的旧东西装箱通常是不值得努力的，”他继续说道。“有一大堆东西在它们所在的地方可能还不错。它们不是业务关键型的，或者可能是，但是它们的变更率非常低，并且您在特性速度方面没有问题。您确实想在分布式系统中拥有的一些东西可能需要一些轻微的重构，这样它们就可以利用水平伸缩或新的数据存储。但是有一个好的变化，如果这些记录系统没有太大变化，它们可能仍然与另一个想要使用它们数据的微服务相关。所以，虽然这东西没什么变化，但其他人需要它来做事。我认为，随着越来越多的系统无法孤岛化，为了他们的生态系统，他们将不得不进行现代化，即使不仅仅是为了他们自己。”

换句话说，Seroter 认为，来自客户机/服务器领域的一些应用程序需要在一个新的架构中重新搭建平台，以便与云服务和世界上的其他应用程序共存，这种需求虽然不总是明确的，但也是可以衡量的。至少在某种程度上，这种转移确实需要一个熟练的开发人员，他了解客户机/服务器平台的工作方式或过去的工作方式。

## 什么留下什么离开

我们之前在新堆栈中讨论过 [Spring Cloud](https://thenewstack.io/video-service-discovery-made-easy-spring-cloud-config/) ，它是 Pivotal 的框架，用于分布式系统和微服务的快速模式化和原型化。它包括现成的微服务，处理每个分布式应用程序将需要的功能——例如，使用[网飞尤里卡](https://github.com/Netflix/eureka)模型的服务发现；以及用于维护状态的[配置存储器](https://github.com/SteelToeOSS/Configuration)。

“我需要将配置存储在机器外，”Seroter 解释道。“我不希望我的文件夹中有任何 **web.config** 文件。NET app 我不希望它出现在本地配置中。我需要一份服务登记表。我所有的服务都是可扩展的，IP 是流动的，我不能在我的应用程序中硬编码对服务的引用。这是运行时查找。”

您可能知道，Spring 是围绕 Java 构建的。Steeltoe 有效地有意地将这种关系从 Java 转移到. NET。

从系统的角度来看，事情是这样的:Pivotal Cloud Foundry 1.10 支持在 Windows 主机上暂存分布式工作负载。对于容器化，Pivotal 使用 [Garden Windows](https://github.com/cloudfoundry/garden-windows) ，这是一套用于生产 OCI 格式容器的开源 Go 库。PCF 的容器调度器是 Windows 的 [Diego，它的部署机制使用 BOSH 命令行工具——同样是为 Windows 重写的——来安装 Windows *单元* (PCF 的登台平台)和](https://docs.pivotal.io/pivotalcf/1-7/opsguide/deploying-diego.html)[推送。这些细胞的网络应用](https://docs.pivotal.io/pivotalcf/1-8/windows/push-windows-apps.html)。

“围绕配置、服务发现、断路器、 [OAuth](https://oauth.io/home) 的许多这些模式—所有这些功能都是 Spring Cloud 的一部分。每月下载数百万次。Steeltoe 的出现是因为我们的成长。净练说，怎么来的。NET devs 上不去这种乐趣？这个生态系统中没有任何东西有所帮助。NET devs 构建微服务。因此，Steeltoe 是一组让您能够接入该生态系统的组件。它延伸了。网芯和传统。NET Framework，并允许您挂接到配置子系统以使用远程配置服务器。”

## 移居

这不是一个微不足道的转变，甚至不是你典型的心态转变。对于一个资深的 Windows 开发者来说，这是一次大脑移植。与所有程序一样，Visual Studio 中构建的 Windows 应用程序有一个*范围*的概念。但即便如此。为了向下兼容，公共语言运行时为*全局范围*提供了静态变量，其值和引用超越了应用程序中的所有子部分。为了在应用程序之间交换数据，仍然有 COM，它依赖于单个全局注册表的持久性(大写的“R”)。随着时间的推移，使每一个 Windows 安装运行得更慢的东西…就是注册表。

直到最近，整个想法。NET 开发是为了在 Windows 环境中运行一个表现得像客户机一样的应用程序，在这里一切都很舒适，共存不是问题，就像某些前全球化主义者的乌托邦式的愿景。因此，任何学习像 C#这样的语言的人都可以深入了解各种 Windows 基础(取代 Win32 API 的库)。学习一门. NET 语言，同时也是不可分割的，就是为 Windows 编程。

对于一个. NET 开发人员来说，使用 Windows CLR 语言为 Cloud Foundry 构建微服务意味着放弃她所学的一些东西。但不是全部，这就是吸引人的地方。拥抱网飞风格的建筑不再意味着放弃 20 年的技能，从“你好，世界！”开始

Pivotal 的 Seroter 说:“现在，一个. NET 开发人员可以进行服务发现，并成为这个动态注册表的一部分——不是这个静态的、过时的、陈旧的集成管理数据库，而是一个依赖于心跳和健康检查的动态外观。我们在 Steeltoe 中有额外的连接器，所以我可以与流行的开源软件如 Redis、MySQL、Postgres、RabbitMQ、OAuth 进行交流。这些。NET 开发者和其他人一样在生态系统中玩，没有那么多的摩擦。”

虽然 Cloud Foundry 开发人员已经对 Steeltoe 框架进行了几个月的修补，但 Pivotal 1.10 版现在提供了商业支持。对于 PCF 和 Steeltoe 来说，试验阶段已经结束。

现在所有的东西都重新组装好了，可以说从噪音和灰尘中显露出来的东西看起来不太像窗户。此外，它是使用为 Windows 开发的语言重申的云原生模型。毫无疑问，老兵。NET 开发人员可能会在这个领域中度过最初的几个月，感觉像是在异乡的移民。他们是感到受欢迎还是被推到一边，就像自助餐厅的另一端，将取决于你读到的所有这些开放是否像人们所说的那样开放。

Cloud Foundry 是新堆栈的赞助商。

特征图片:[弗拉·布尔迈斯特奥格·韦恩的铸铁厂](https://en.wikipedia.org/wiki/Foundry#/media/File:Burmeister_og_Wain_(1885_painting).jpg)，1885 年由佩德·塞弗林·克勒耶绘制，在公共领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>