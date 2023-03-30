# 要避免的云本机迁移陷阱

> 原文：<https://thenewstack.io/cloud-native-migration-traps-to-avoid/>

[NS1](https://www.ns1.com/) 赞助本帖。

DevOps 团队获得了将其 CI/CD 流程和运营迁移到云原生环境的许可，并意识到这一过程可能充满危险。尽管云本身有“一桶金”——表现为更高的敏捷性、更快的软件发布节奏和更稳定的部署——但事情很快就会变糟。

在 NS1 的 [INS1GHTS2020](https://thenewstack.io/baptism-by-fire-ns1-insights2020-surveys-the-current-challenges-of-devops/) 虚拟峰会期间，[NS1 首席技术官兼联合创始人 Jonathan Sullivan](https://www.linkedin.com/in/jonathansullivan1) 在其主题演讲中表示，寻求通过迁移到云并利用微服务和容器环境提供的机会来实现基础设施现代化的组织“正在为他们公司的未来奠定基础”

他说，随着“软件继续占据一切”，企业将更有弹性，并为技术不可避免的持续发展做好准备。

然而，迁移到具有容器化和微服务环境的云环境当然也不容易。沙利文说，数字化转型过去涉及“迁移到云”并确定“这对你的业务意味着什么”。“我们今天发现的是，一切都比这复杂得多，”他说。

在本帖中，根据来自 [NS1 虚拟峰会](https://www.businesswire.com/news/home/20200528005227/en/NS1%E2%80%99s-INS1GHTS2020-Virtual-Summit-Brings-Industry-Leaders)和其他来源的演讲和主题演讲，我们来看看组织在向云原生环境转移时可以避免的一些陷阱。

## 不要独自走进那片云

当然，这个想法是为了帮助支持 DevOps 的关键任务，即安全地开发和部署软件，同时花费更少的时间和更少的资源来管理更多与运营相关的任务，依靠云提供商，如[谷歌云平台](https://cloud.google.com/)、[亚马逊网络服务(AWS)](https://aws.amazon.com/) 或[微软 Azure。](https://azure.microsoft.com/en-us/)然而，对于许多组织来说，从内部迁移到云环境时弥补差距的工具选择流程是一项重大挑战。

沙利文在 2020 年的炉边聊天会上说:“这个过程永远不会简化为，‘我们将能够把所有东西都迁移到内部，阅读剧本，然后把它放到一个云中。’”。

例如，DevOps 必须找到合适的“现代应用交付堆栈服务，以便利用和利用您已经做出的投资，”Sullivan 说。“如果没有这一点，你可以拥有这个奇妙的混合云战略，如果你没有办法智能地协调流量，你就不会看到投资回报，”沙利文说。

在迁移到容器化的 Kubernetes 环境时，有必要投资于诸如 VMware 的 Tanzu 这样的框架。Sullivan 说，这使得 DevOps“可以把你的东西放在任何地方，只需要弄清楚如何利用这种复杂的基础设施和复杂的基底”。

Clive Longbottom and Associates 的分析师 [Clive Longbottom](https://www.linkedin.com/in/clivelongbottom/?originalSubdomain=uk) 说，最终，这种转变需要“智能编排，沿着整个 DevOps 流的良好集成”，对平台的强大监控和管理，以及自动更新、补丁和错误补救。

## 不要复制和粘贴遗留系统

数据中心不能在云环境中复制。虽然主要目标大体保持不变，但基本的运作框架将有所不同。IT 人员可能不必太担心维护他们的内部服务器和数据中心基础架构，但是新的云环境并不是数据中心的镜像。简而言之，应用程序需要“云设计”，隆巴顿说。

“大型单片应用程序试图做所有事情的时代已经结束了，”隆巴顿说。“那些试图将其整体应用迁移到云上的供应商不是在进行云计算，他们本质上是在迁移到托管应用模型，而没有弹性资源和精细功能使用级别的优势。”

Longbottom 说，对于那些希望“将自己开发的应用程序迁移到云上”的组织来说，他们所做的一切更有可能是将它们迁移到虚拟化服务器上。

“为云设计和开发，确保更新、补丁和全面升级可以在不关闭整个服务的情况下完成，并且这些行动可以在较小的有效载荷和对整个平台的低影响下进行，”隆巴顿说。

![](img/ea929047f1d3747fb8e42b5ff679e6ed.png)

## 获得正确的配置

云没有无限的能力。虽然云服务器和计算很容易被忽视或遗忘，但一般来说,[会增加二氧化碳排放量](https://cleantechnica.com/2019/07/10/what-is-the-carbon-debt-of-cloud-computing/),而云的容量实际上是有限的。归根结底，云服务器与运行在私有数据中心的服务器是一样的。这意味着在迁移到云原生环境时，也必须考虑容量管理。

虽然使用云资源调配来增加容量变得越来越容易，“因为我们可以出去购买更多的计算，但这也让我们更容易忽略一些事情。” [Heidi Waterhouse](https://www.linkedin.com/in/heidiwaterhouse) ，[launch ryly](https://launchdarkly.com/)的高级开发者代言人，在 2020 的[演讲“突破压力:一个关于能力和测试的故事”中说道。](https://thenewstack.io/baptism-by-fire-ns1-insights2020-surveys-the-current-challenges-of-devops/)

“我们没有太多的早期预警信号表明我们的计算能力即将耗尽，如果每个人都需要同时购买计算能力，那么我们的能力就只有这么多。沃特豪斯说:“当我和为主干网做网络供应的朋友交谈时，我感觉‘我们仍然在使用仍然来自制造地的计算机，我们仍然需要电缆、光纤和交换机来运行云’。“云只是别人服务器房里的服务器。因此，当我们考虑增加容量时，我们需要有一个合理的预期，即我们要么建设它，要么购买它。”

Waterhouse 说，弹性容量云供应可以解决一些，但不是所有的容量问题。“当你在建立一个强大的系统时，你还需要能够灵活地做出反应，你可以拐弯真的很重要，因为如果你有一个大型系统，只有在道路上有东西时才能前进，你会有很多麻烦，”沃特豪斯说。

亚马逊网络服务和 VMware 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过推特[或脸书](https://twitter.com/thenewstack)[访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈:](https://www.facebook.com/thenewstack/)[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>