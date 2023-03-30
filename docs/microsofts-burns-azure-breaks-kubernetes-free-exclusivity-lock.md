# 微软将 Kubernetes 带到 Azure

> 原文：<https://thenewstack.io/microsofts-burns-azure-breaks-kubernetes-free-exclusivity-lock/>

“我认为人们在生态系统中有很多价值，我们不一定想要，甚至不认为有必要绑定到一个特定的操作系统上，”微软的合作伙伴架构师兼谷歌 Kubernetes 的最初首席开发人员之一 Brendan Burns 表示，[微软上周在 Azure Container 服务](https://thenewstack.io/new-updates-making-azure-container-service-applications-run-not-containers-run/)上全面发布 Kubernetes 支持之前，他谈到了新的堆栈。

Burn 的断言可能是你期望在 Linux 基金会或云本地计算基金会的一位研究员的新堆栈中找到的那种声明。但是，微软单方面宣布脱钩的唯一重要之处在于:首先，是谁说的。接下来，就是他从哪里来到现在的位置。然后是他发表声明的背景。

“我们只是想确保人们能够使用这种技术，如果他们也在. NET 或 Windows 操作系统环境中部署他们的应用程序，”Burns 继续说道。“我们不想让它成为唯一的选择。我们不想让人们不得不做决定。我们想让人们找到适合他们的地方。”

## 没有区别的区别？

微软目前的政策，正如包括伯恩斯在内的多位公司官员所说，是同时启用多种工作负载部署选项，所有这些都由 Azure 作为底层平台提供支持。这是一种将该公司描绘成首选代理商的方式，也是一个难得的机会，让它在历史上一直是“首选”公司。

然而，它去年 6 月从谷歌挖走了伯恩斯，他在谷歌是 [Kubernetes](/category/kubernetes/) 容器编排引擎的联合创始人，随后它授权伯恩斯作为数据中心异构性的倡导者和微软作为其推动者，缺乏过去该公司特有的烟雾和屏幕的指示性组件。

“在我来到这里之前，每个人都很清楚[*开源软件*和 Linux 将成为 Azure 非常重要的组成部分，”伯恩斯在最近的一封电子邮件中告诉新的堆栈。“我的经验让我关注如何同时参与公共云和上游开源社区，以及这看起来像什么。我们有许多活跃的开源社区，例如 [Visual Studio Code](https://code.visualstudio.com/) 。你如何参与两者——构建你的产品和参与 OSS 社区——有点独特，我们正在扩展。例如，我的一个同事正在开发 Kubernetes 1.6 版本，以确保它是 Azure 的高质量版本，但这项工作也使 Kubernetes 整体上变得更加强大。”

这里有一个不太容易解释的目标，即使对微软的人来说…即使对帮助建立容器生态系统，然后进入微软的人来说。从表面上看，这一想法是为了在开发可部署到公共云的服务时为开发人员提供更多的选择——在这种情况下，显然是部署到 Azure。本质上，策略是使平台之间的差异达到以下任何程度:a)可以忽略不计；b)不太明显；c)多余的；d)开发者个人品味的问题。在上述任何一种情况下，也许微软都无法获得超过竞争对手的优势，但反过来也是如此。

Burns 是这样对我们说的:“我们交谈过的大多数客户都对在混合和/或多云环境中运营感兴趣，并且正在寻找容器编排。我们很高兴能够通过开源来实现为他们服务的混合服务。”

## 开发人员可以看到的差异

2015 年春天，一位名为[的后起之秀谷歌工程师布兰登·伯恩斯(Brendan Burns)首次演示了从 Linux 命令行运行 Kubernetes 集群的基本原理](https://www.youtube.com/watch?v=DC7NECq3Ghs):

[https://www.youtube.com/embed/DC7NECq3Ghs?feature=oembed](https://www.youtube.com/embed/DC7NECq3Ghs?feature=oembed)

视频

这个演示包括启动 NGINX 的一个工作实例。从 Linux 命令行，Burns 实例化了一个 [etcd](https://github.com/coreos/etcd) 容器，作为一个简单的存储组件。一旦实例化，他交付一个 **docker run** 命令来触发应用程序的主组件，并交付另一个 **docker run** 命令来启动服务代理，启用与这些组件的通信。从开发人员的角度来看，这是一个三步过程，但实际上，几个自动化步骤在后台发生，包括创建[kube let](https://kubernetes.io/docs/admin/kubelet/)——代表 Kubernetes 工作的 pod 端容器管理器。kubelet 自动生成了必要的 API 和调度器容器，并将它们绑定到 pod。从那里，kubelet 将负责管理其监护下的集装箱的健康状况。

(伯恩斯后来澄清说，他的演示涉及从 Visual Studio 代码创建标准的 Linux 容器，而不是 Windows 容器。)

随着通信过程的建立，Burns 可以使用 Kubernetes API 调用简单的、类似动词的命令，使用 **[kubectl](https://kubernetes.io/docs/user-guide/kubectl-overview/)** 命令行界面将它们传递给 orchestrator。通过这个通道，Burns 可以告诉 Kubernetes 调用并运行 NGINX。

快进 19 个月。在此期间，Kubernetes API 发生了几次变化，但如果有人睡了那么久，也不会让人认不出这个管弦乐队。微软的合作架构师 Brendan Burns 演示了如何使用 Azure 的资源调用和操作 Kubernetes 管理的 pod。

[https://www.youtube.com/embed/nhY9XdzNbbY?feature=oembed](https://www.youtube.com/embed/nhY9XdzNbbY?feature=oembed)

视频

Azure 中的命令行工具是 **az** ，所以 Burns 访问 [Azure 容器服务](https://azure.microsoft.com/en-us/services/container-service/)的方式是通过 **az acs** 。这里启动 orchestrator 的过程是通过命令 **az acs create** 完成的，值得注意的是，属性**orchestrator-type**是完全开放的。这是运营商可以指定 Kubernetes 的地方，而不是 Swarm 或 Mesosphere 的数据中心操作系统，后者是 Azure 也支持的其他 orchestrators。在指导 Kubernetes 收集在 Azure 上运行其容器所需的凭证后，他就可以与 **kubectl** 通信了。([微软的文档更详细。](https://docs.microsoft.com/en-us/azure/container-service/container-service-kubernetes-walkthrough))

但是从那里，伯恩斯没有坚持使用命令行，而是跳到了 Visual Studio Code (VS Code)控制台。如果您对历史悠久的基于 Windows 的开发工具的 Visual Studio 套件有些熟悉，请忘记您认为自己了解的一切——除了定性的相似性，VS 代码是一个非常不同的世界。

在后面的演示中，终端面板给了 Burns 一个更完整的 Azure 命令行连接——比每次都调用 **az acs** 更有效。但是当他需要向 Azure 上的 Kubernetes 发出命令时，他不必打开终端面板。

相反，他使用编辑器顶部的搜索行，通过名字向 **kubernetes** 发出命令(而不是 **kubectl** ),就好像这是一个网络浏览器，他正在谷歌上查找一个页面。这里的搜索行就像一个术语表，显示 Kubernetes 是如何寻址的，并让开发人员有效地浏览选项。

通过 VS 代码在 Azure 上使用 Kubernetes 有种无服务器的感觉。除了在最开始初始化 pod 之外(这可能很快就会改变)，单个控制台中功能之间的内聚性让人想起了过去编程是多么舒适，当时您正在编程的机器离您有 12 英寸远，您使用的工具是光滑、健壮和经过良好测试的。到 Git 的链接、主要源代码、JSON 部署和配置代码以及用于构造容器的 docker 文件都隐藏在 VS 代码控制台中指定的部分——而不是像彩弹锦标赛一样显示在桌面上的各个窗口中。

## 这一点也不疼

敏锐的观众不会忘记 Burns 的 VS 代码演示是在 Linux 桌面上进行的。然而，被掩盖的是这个相当重要的信息:使用 Docker 构建并使用 Kubernetes 编排的容器，利用了微软的 [Windows Nano Server](https://blogs.technet.microsoft.com/windowsserver/2016/02/10/exploring-nano-server-for-windows-server-2016/) ，而不是最小化的 Linux。如果莎士比亚还在寻找众所周知的难题，这就是了。

“以前——老实说，这对 Linux 和 Windows 用户来说是真的——让他们能够构建云原生应用的东西是自主开发和定制的，”Burns 告诉 New Stack。“他们将有效地构建他们的编排系统，但它将与他们的应用程序紧密集成。

“现在有了容器，我们有机会构建一个每个人都可以使用的编排系统。你不必成为[*微软*Exchange 团队或 Xbox 团队的规模来构建你自己的编排层。通过构建这些容器，您可以利用云原生技术，而不必构建太多。这就是正在发生的转变，允许这些中小型团队专注于他们的应用程序，同时仍然获得云原生方法的好处。”

这是微软通过 Azure Container 服务和 orchestrator 选择瞄准的市场:不是 Linux 已经大量存在的超大规模、跨云的复杂系统，而是*新浪潮*尚未触及的较小企业——微软尚未被进化的力量所取代的领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>