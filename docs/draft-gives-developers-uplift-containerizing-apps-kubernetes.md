# 微软草案为开发者提供 Kubernetes 支持

> 原文：<https://thenewstack.io/draft-gives-developers-uplift-containerizing-apps-kubernetes/>

容器使得部署应用程序及其所有库和依赖项变得更加容易，尽管在许多情况下组织不得不改变他们的工作流来适应新技术。微软 Azure 上容器的首席项目经理 Gabe Monroy 指出，当变化是由运营驱动时，这可能会导致组织内部对容器技术的采用停滞不前。

Monroy 相信一个叫做[草案](https://github.com/Azure/draft)的新开源 Kubernetes 部署工具可以解决这个问题。Monroy 是 Deis 的前首席技术官，Deis 是一家[微软正在收购](https://deis.com/blog/2017/deis-to-join-microsoft/)的公司。该公司在本周于旧金山举行的 CoreOS 用户大会上公布了这项技术。

“草案解决了我认为那些试图大规模采用容器的组织所面临的首要问题。当一家公司的运营和 IT 团队接受了容器的想法，他们建立了 Kubernetes 集群并取得了一些初步的胜利，他们转身准备将这一想法发布给一个由一千名 Java 开发人员组成的团队——他们得到的反应就像是车灯前的鹿。太复杂了，概念开销太大；这对我们来说太难了。

换句话说，运营团队需要让 Kubernetes 对软件团队来说更容易、更容易接受。

草稿通过消除使用 Kubernetes 的大部分需求，减少了概念上的开销；开发人员甚至不需要在他们的笔记本电脑上安装 Docker 或 Kubernetes 只需要二进制文件草案。

“你开始用任何语言编写你的应用程序，比如 Node.js，你开始搭建它，当你准备好看看它是否可以在 Kubernetes 环境中运行时，在沙箱中，你只需键入‘draft create ’,工具就会检测出这是什么语言，并将 Dockerfile 和 [Helm chart](https://github.com/kubernetes/helm) 写出到源代码树中。所以它为你搭建了应用程序的框架，并将其容器化。”

[Helm](https://helm.sh/) 是由 Deis 开发和支持的 Kubernetes 包管理器。

该语言检测基于可配置的草稿“包”，其中包含检测脚本、docker 文件和 Helm 图表。默认情况下，Draft 附带了 Python、Node.js、Java、Ruby、PHP 和 Go 的包。微软很可能会推出更多的包——TypeScript 正在考虑中——但 Monroy 希望社区能构建更多的包来支持不同的语言、框架和运行时。

“微服务的好处之一是允许团队为工作选择正确的语言和框架。包非常简单，所以团队可以并且愿意为他们的环境定制它们。大客户希望能够说‘这是我们的 Java 7 环境和节点环境，它们得到了运营团队的支持，我们不希望开发人员做任何其他事情。’草稿包允许这种定制和控制。"

容器可以是 Windows 或 Linux Docker 容器；“我们的目标是所有的平台，”Monroy 证实，随着时间的推移，这将包括直接通过 Hyper-V(而不是在虚拟机中)运行在 Windows 10 和 Windows Server 2016 上的 Linux Docker 容器。

开发人员的第二个新命令是“起草”该命令将源代码(包括封装应用程序的新位)发送到 Kubernetes，远程构建 Docker 映像，并使用 Helm chart 将其部署到开发人员沙盒中，”Monroy 说。开发者获得一个 URL 来访问他们的应用程序并观看直播。”

作为向开发人员提供草案的一部分，运营团队已经建立了所需的 Docker 注册细节。

“现在你进入你的 IDE，不管那是什么 IDE，做一个改变并保存你的代码。蒙罗伊说，保存发生的那一刻，Draft 会检测到它，并将其重新部署到 Kubernetes 集群，几秒钟内就可以使用。这些命令可以很容易地直接集成到 IDE 中，但无论哪种方式，与直接针对 Docker 或 Kubernetes 相比，对开发人员工作流的改变都要小得多。

## 构建和测试

Monroy 说，对于开发者来说，这感觉更像是使用平台服务。“有了 PaaS，开发人员只需编写代码，这些代码就会传到云端。这几乎就像客户端 PaaS 将您的部署和配置信息写入 repo。但是因为 Kubernetes 可以建模任何东西，你可以用它来支持 Cassandra 或 WordPress 或 PaaS 系统很难处理的东西。有状态组件的东西可以用草稿写；它可以像云应用程序一样轻松地对卷进行建模。”

Monroy 说，草案旨在开发人员工作流程的“内循环”;在开发人员编写代码时，但在他们将更改提交给版本控制之前。一旦他们对自己的更改感到满意，他们就可以将这些更改提交到源代码控制中。”

将构建和部署配置写入源代码树使得 Draft 比 PaaS 更适合驱动开发运维的持续集成和开发管道，尤其是在构建测试方面。

通常，PaaS 系统没有与持续集成和部署管道很好地集成，在持续集成和部署管道中，开发人员将代码签入源代码控制，然后持续集成系统取出代码并构建它，测试它并对它进行分级，然后将其投入生产。

“草案解决了这个问题，因为它将配置放入源代码控制回购中，持续集成管道可以从那里获得它，”Monroy 说。

很少有其他工具能够像 Draft 一样帮助 Docker 融入开发人员的工作流程。“我们看到很多人使用 Docker Compose，但问题是需要在笔记本电脑上安装 Docker，而不是每个组织都愿意在他们的整个车队中推广，”他指出。Docker Compose 和 Bitnami Kompose 之类的工具使用 Docker 数据模型；草稿使用了 Kubernetes 数据模型，Monroy 称之为“更丰富、更高保真”。

Draft 将整个源代码树运送到 Kubernetes 集群，并在那里构建容器，这就是它如何绕过在开发人员的系统上安装 Docker 的需求。“如果有大规模回购，可能会有一些延迟，”蒙罗伊警告说。如果这是一个问题，Draft 可以在笔记本电脑上与 Kubernetes 集群一样好地工作，对于一些组织来说，它将取代更慢的过程。

一家大型公司希望将其 10，000 多名 Java 开发人员转移到 Kubernetes，该公司一直在使用 Cloud Foundry 和 cf push 他们很想用汇票来代替。

## 开发人员生产力

草案向解决 Azure 容器服务架构师 [Brendan Burns](https://github.com/brendandburns) 称之为“空编制者综合症”的问题迈出了一步；“我们完全部署了 Kubernetes，我们已经部署了 Kubernetes，现在怎么办？”"

“我认为真正的问题是，构建应用程序仍然太难了。我们有很多碎片，但我们还没有开始实际展示一种可以将这些东西组合在一起的方法，”伯恩斯说。Draft 非常适合服务代理和管理容器中应用程序的秘密等开发，并通过云中的[远程调试](https://thenewstack.io/understanding-azure-container-service-azure-service-fabric/)等功能提高开发人员的生产力。

不过，草稿只是可组合系统中的一个构件。“我们想建立一个工具，做一件事，一个工作流程，并且做得很好，”Monroy 告诉我们。“它确实有助于促进宇宙的管道视图，对于 CI 系统获取代码的工作流的其他部分，我们还有其他想法。”

云计算原生计算基金会是新堆栈的赞助商。

专题图片:CoreOS 的 Alex Polvi 和微软的 Gabe Monroy(部分隐藏)在 CoreOS Fest 上演示草稿。亚历克斯·威廉姆斯的照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>