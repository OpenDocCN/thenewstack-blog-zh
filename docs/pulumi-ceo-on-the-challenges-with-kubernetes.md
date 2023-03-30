# Pulumi 首席执行官谈 Kubernetes 面临的挑战

> 原文：<https://thenewstack.io/pulumi-ceo-on-the-challenges-with-kubernetes/>

Pulumi 赞助了这个播客。

[普鲁米 CEO 切入金龟子，描述了你与 Kubernetes](https://thenewstack.simplecast.com/episodes/pulumi-ceo-cuts-through-the-chafe-describes-your-real-relationship-with-kubernetes) 的真实关系

在巴塞罗那 [KubeCon + CloudNativeCon](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2019/) 会议期间录制的本集 [The New Stack Makers](/podcasts/makers) 播客中，[Pulumi](https://www.pulumi.com/)CEO[Joe Duffy](https://www.linkedin.com/in/joejduffy/)讨论了开发人员和运营人员与 Kubernetes 和多云环境的关系。达菲说，大多数开发人员“不希望必须考虑，甚至是在 Kubernetes 的水平上，或者发现是…这是…这是一套非常低级的指令，供开发人员考虑，忘记集群”。“这只是应用模型。”

Duffy 描述了基础设施管理工具和 Kubernetes 管理工具之间的分歧。达菲对播客主持人、TNS 创始人亚历克斯·威廉姆斯说:“人们正在为此挣扎。“如果你打算建立一个 Kubernetes 集群，你需要考虑一下 [CloudWatch](https://www.amazonaws.cn/en/cloudwatch/) 或者‘也许我不想自己托管数据库，也许我只想使用 [RDS](https://aws.amazon.com/rds/) 、Azure 的 [Cosmos DB](https://azure.microsoft.com/en-us/services/cosmos-db/) 或者谷歌的[Cloud Spanner](https://cloud.google.com/spanner/)’——这些托管数据服务真的很丰富，而且比我管理自己的数据更容易使用。”

与此同时，许多组织仍在苦苦挣扎，例如云基础设施、托管服务和 Kubernetes。达菲说:“例如，我们听到人们在 YAML 的墙壁上挣扎，或者在 YAML 的各种模板和解决方案上挣扎，或者在 YAML 的各种融合方式上挣扎，我们听到，在大规模上，它正在崩溃，不能正常工作。”。

具体到他的公司，Duffy 描述了 Pulumi 的软件如何使用非常广泛的编程语言在一系列云和内部环境中部署和管理基础设施。它“是一个基础设施代码解决方案，以一流的方式拥抱了 Kubernetes。”

“因此，我们可以在任何云上调配资源。达菲说:“除了提供云原生资源，你还知道 Kubernetes 的资源。“因此，我们处于一个有趣的有利位置，我们实际上是在帮助客户进入所有这些不同的托管云和本地云。”

Duffy 说，他的客户面临的另一个关键挑战是“从没有 Kubernetes 集群到真正拥有一个安全、“可调试”和可靠的全功能 Kubernetes 环境，我的团队可以使用，这是一个困难的部分，因为每个云提供商都有很大的不同。”

当然，对于 DevOps 中的开发和运营团队来说，安全性及其许多方面仍然是一个挑战。但安全管理的源头，在达菲眼里，可以追溯到“一个一直经受住时间考验的原则，那就是最小权限原则。”达菲说:“除非明确请求或明确要求，否则你不会授予执行某项活动的权限，因此默认情况下，任何内容都不应暴露在互联网上。任何未经身份验证的用户都不能在集群中做任何事情，然后您继续工作并说，“好吧，我要加入我的团队，我要给他们尽可能少的权限来完成他们的工作。”"

然后，有必要锁定连续部署(CD)环境。“事实证明，CD 环境往往是最有特权的—没有多少人意识到这一点，因为 CD 环境通常是进入生产、操纵资源和配置的环境。达菲说:“通常，除了超级用户之外，你不会给你团队中的任何人这种能力。"所以这个想法是，如果你尽可能地锁定一切."

Duffy 拒绝推荐一家云提供商而不是另一家，特别是在 AWS、谷歌和 Azure 之间，并指出 Pulumi 是这三家公司的合作伙伴。然而，达菲指出，Kubernetes 是如何“从谷歌和 GKE 走出来的，是非常可靠的。”

“我团队中的一个人，迈克，曾经是一个核心操作系统，喜欢讲述他如何在他们推出 GKE 集群的第一天就启动它的故事，从那以后，他一直在按升级按钮，从来没有失败过，”达菲说。“它总是升级到最新版本，我认为，你知道，亚马逊肯定会从客户那里听到他们想使用 Kubernetes，所以他们正在投资，他们会实现这一目标。”

[https://www.youtube.com/embed/fDKslnUtFjw?feature=oembed](https://www.youtube.com/embed/fDKslnUtFjw?feature=oembed)

视频

### 在这个版本中:

[1:55:](https://thenewstack.simplecast.com/episodes/pulumi-ceo-cuts-through-the-chafe-describes-your-real-relationship-with-kubernetes?t=1:55) 关于普鲁米。
T3:52:不同云提供商的细微差别。
[8:55:](https://thenewstack.simplecast.com/episodes/pulumi-ceo-cuts-through-the-chafe-describes-your-real-relationship-with-kubernetes?t=8:55) 联网安全。
[16:04:](https://thenewstack.simplecast.com/episodes/pulumi-ceo-cuts-through-the-chafe-describes-your-real-relationship-with-kubernetes?t=16:04) 赫尔姆和 YAML。
[16:47:](https://thenewstack.simplecast.com/episodes/pulumi-ceo-cuts-through-the-chafe-describes-your-real-relationship-with-kubernetes?t=16:47) 集群为代码。
[20:56:](https://thenewstack.simplecast.com/episodes/pulumi-ceo-cuts-through-the-chafe-describes-your-real-relationship-with-kubernetes?t=20:56) 以后的工作。

KubeCon + CloudNativeCon 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>