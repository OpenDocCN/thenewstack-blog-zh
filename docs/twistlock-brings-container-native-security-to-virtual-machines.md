# Twistlock 为虚拟机带来了容器原生安全性

> 原文：<https://thenewstack.io/twistlock-brings-container-native-security-to-virtual-machines/>

Twistlock 赞助了这个播客。

[扭锁为虚拟机带来了容器原生安全性](https://thenewstack.simplecast.com/episodes/twistlock-brings-container-native-security-to-vms)

许多传统安全软件提供商跟随淘金热，为云原生部署提供解决方案。但是，寻找一家既能应对与 Kubernetes 和微服务相关的技术挑战，又能很好地满足组织的特定需求的供应商可能是一项挑战，尽管承诺提供“精确匹配”的解决方案几乎呈爆炸式增长

然而，虚拟机(VM)的安全需求虽然作为一种技术更加成熟，但并不一定能得到第三方软件安全提供商应有的重视。结果是，组织努力寻找虚拟机的安全解决方案，以及运行在云原生平台上并与服务网格集成的 Kubernetes 和微服务所需的安全解决方案。

[Twistlock](https://www.twistlock.com/) 的首席技术官 [John Morello](https://www.twistlock.com/about-us/team/john-morello/) 表示:“许多客户向我们表达了一个令人沮丧的问题，即虚拟机安全的传统市场实际上是一个由为内部数据中心和传统类型的服务器数据中心端点保护而构建的传统技术定义的市场。“他们只是把它塞进一个新的营销术语、一种新的模式，并作为某种云安全产品来销售。但是，当您考虑人们在这些现代堆栈中操作虚拟机的方式时，这些产品并不真正有效。”

在新堆栈的创始人兼主编 Alex Williams 与 Morello 共同主持的播客中，讨论了虚拟机以及云原生部署和服务网格所需的堆栈级安全性。

例如，Twistlock 最新的 19.03 版本的想法是在单一产品中为主机、容器和无服务器提供该公司所描述的全面的云原生安全平台。

“我们正在扩展云原生安全平台，我们必须为您的虚拟机提供我们为容器和无服务器所做的相同类型的功能，”Morello 说。

在许多情况下，组织受制于 Morello 所描述的“经典虚拟机”安全解决方案，这些解决方案是手动安装和手动更新的。

“这是关于宠物与牛的整个概念，与我们今天谈论的内容不同，这是一种现代的虚拟机方法，在这种方法中，您将这些虚拟机和其上的工作负载作为牛来操作，就像一个容量舰队一样，”Morello 说。“您可以通过自动化来部署它，通过某种同样以自动化为重点的工具来管理它，您不必真正担心任何单个虚拟机，也不必担心设备群和整体应用程序的运行状况。”

Morello 说，使用传统的安全工具,“在管理这些工具时，通常会有两个很大的缺口。”。Morello 说，第一个差距是传统安全工具“对自动化不太友好”。

Morello 说，第二大差距是“这些工具在本质上通常是单一用途的”。“你知道，你可能有一个专注于漏洞管理的工具，你运行不同的工具进行合规性评估，你运行第三个工具进行某种运行时防御。因此，你最终会遇到许多企业都很熟悉的问题，突然有六个代理在你的每个虚拟机上运行，占用了一大堆容量，并相互争斗，”Morello 说。

有了 Twistlock 19.03，“你就有了一个单一的平台，它本身就是一个云原生应用。你仍然可以在 Kubernetes 或[Docker] Swarm 或你的容器中的任何地方部署和操作它。“它仍然是完全可编程访问的，如果你愿意，你可以将你的安全性作为代码来管理。你可以通过 CI/CD 流程将规则推送到 it 部门，并将其存储在 Git 中，等等，”Morello 说。

Morello 表示，Twistlock 19.03 旨在“帮助我们回答一年多来我们从客户那里听到的很多请求。”

“随着[客户]开始整个云原生之旅，他们将更多的东西放在容器中，并在环境中使用更多的无服务器设备，他们仍然有很多东西在虚拟机中运行，”Morello 说。“虚拟机中的这些东西通常有很好的实际业务原因，比如供应商可能只将它作为虚拟机来支持，它已经在那里了，它只是在工作，所以没有真正的理由去改变它。或者它可能有更适合虚拟机的特定工作负载。”

### 在这个版本中:

[凌晨一点:](https://thenewstack.simplecast.com/episodes/twistlock-brings-container-native-security-to-vms?t=1:00)公告。
[5:26:](https://thenewstack.simplecast.com/episodes/twistlock-brings-container-native-security-to-vms?t=5:26) 探索 Twistlock 19.03 中的新特性，并将这些特性与服务网格技术和分布式架构相关联。
[8:15:](https://thenewstack.simplecast.com/episodes/twistlock-brings-container-native-security-to-vms?t=8:15) 请告诉我服务网格的角度，以及它如何与我们听到的云原生故事以及越来越多的容器安全故事相吻合？
[13:19:](https://thenewstack.simplecast.com/episodes/twistlock-brings-container-native-security-to-vms?t=13:19) 探索 Twistlock 19.03 中主机的新雷达视图。
[14:43:](https://thenewstack.simplecast.com/episodes/twistlock-brings-container-native-security-to-vms?t=14:43) 说说 RASP Defender 吧。
[18:17:](https://thenewstack.simplecast.com/episodes/twistlock-brings-container-native-security-to-vms?t=18:17) 讨论 Twistlock 19.03 中可用的其他特性以及最近的 runc 漏洞。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>