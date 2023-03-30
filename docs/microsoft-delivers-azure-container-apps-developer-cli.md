# 微软发布 Azure 容器应用，开发者 CLI

> 原文：<https://thenewstack.io/microsoft-delivers-azure-container-apps-developer-cli/>

在上周举行的年度 [Build](https://news.microsoft.com/build2022/) 开发者大会上，微软[宣布](https://aka.ms/Build22/Scalecloudnativeapps)正式推出 [Azure Container Apps](https://azure.microsoft.com/en-us/services/container-apps/) ，这是该公司的无服务器服务，用于构建和部署容器化应用，无需管理复杂的基础设施。

除了 Azure 容器应用，微软还宣布了一个新的 [Azure 开发者 CLI](https://microsoft.qualtrics.com/jfe/form/SV_0wui6ibiHEJZ6Tk) ，它使云原生开发者能够进入广泛的微软开发者工具生态系统，从 Visual Studio 到 VS 代码再到 GitHub 和 Azure。

“Azure Container Apps 是一项以应用为中心的服务，使开发人员能够专注于他们应用的差异化业务逻辑，而不是云基础设施管理，”Azure Functions 和 Azure Static Web Apps 的首席 PM 经理 Daria Grigoriu 在一篇博客文章[中写道。“Azure Container Apps 执行打包在任何基于 Linux 的容器中的应用代码，而不强制执行固执己见的运行时或编程模型。”](https://techcommunity.microsoft.com/t5/apps-on-azure-blog/azure-container-apps-general-availability/ba-p/3416885)

## 实现云原生的更简单方式

微软负责 Cloud + AI 的执行副总裁 Scott Guthrie 在 build 的主题演讲中表示，总的来说，Azure Container Apps 是一种更简单的方式，让企业开始转向云原生，并使用他们选择的编程语言更新他们的代码和构建应用。

“Azure Container Apps 是一种无服务器、基于容器的托管服务，让你可以专注于你的应用，而不必担心管理底层的云基础设施，”他说。“它支持事件驱动的扩展。事实上，您甚至可以缩减到零个实例。如果你不使用它，你就不用为在它上面运行的应用支付任何费用。如果您突然收到大量请求，您可以快速、动态地扩展到数千个实例来处理这些负载。”

## 基于开源

普遍可用的服务是基于开源技术的。包括[云原生计算基金会(CNCF)](https://www.cncf.io/) 项目如 [Kubernetes 事件驱动自动缩放(KEDA)](https://keda.sh/) 、[分布式应用运行时(Dapr)](https://dapr.io/) 、运行在 [Azure Kubernetes 服务(AKS)](https://azure.microsoft.com/en-us/services/kubernetes-service) 上的[特使](https://www.envoyproxy.io/)。

“开发人员可以利用 Dapr 来封装微服务和 KEDA 的最佳实践，以实现事件驱动的规模，而无需管理复杂的清单或 Kubernetes 运营商，”Grigoriu 说。

微软看到了一个巨大的机会，使企业能够在 Kubernetes 上运行，但仍然让他们的开发人员不必关注 Kubernetes 背后的所有基础设施，微软 Azure 开发者体验产品副总裁 Scott Hunter 说。

“Azure Container 应用程序的好处是您可以获得 Kubernetes 的好处，但我们会为您进行所有管理。在许多情况下，它比 Kubernetes 便宜得多，”Hunter 告诉 New Stack。“我们是如何做到这一点的，基本上只是试图将 Kubernetes 这样的东西提供给大众。世界上有很多非常非常大的公司肯定想运营他们自己的 Kubernetes，但也有很多公司不想运营他们的 Kubernetes。”

## 产品特性

与此同时，Azure Container Apps 使用户能够通过部署到虚拟网络来保护他们的应用程序，使用[托管身份](https://docs.microsoft.com/azure/container-apps/managed-identity?tabs=portal%2Cdotnet)来访问其他 Azure Active Directory (Azure AD)保护的资源，并为他们的外部 ingress-enabled 应用程序配置[集成身份验证和授权](https://docs.microsoft.com/azure/container-apps/authentication)。

此外，“你的应用程序可以通过定制域名和证书来实现个性化，”Grigoriu 说。"[健康探测器](https://docs.microsoft.com/azure/container-apps/health-probes?tabs=arm-template)可用于心跳、准备和启动。您可以通过实时[日志流](https://docs.microsoft.com/en-us/azure/container-apps/observability?tabs=bash#log-streaming)查看 stdout 和 stderr 日志消息，连接到[容器控制台](https://docs.microsoft.com/azure/container-apps/observability?tabs=bash#container-console)，查看[指标](https://docs.microsoft.com/azure/container-apps/observability?tabs=bash#azure-monitor-metrics)，以及设置[警报](https://docs.microsoft.com/azure/container-apps/observability?tabs=bash#azure-monitor-alerts)来观察您的应用程序的运行状况和性能

Azure 容器应用可能有用的一些场景包括构建微服务、事件驱动的处理以及管理 web 应用和公共 web API 端点。

Grigoriu 说，Azure 容器应用和 Dapr 集成为开发者提供了一组可选的 API，简化了应用和微服务的创作。此外，Azure Container Apps 无服务器应用可以处理来自许多 [KEDA](https://keda.sh/) 支持的事件源的事件，并且可以基于每种事件类型的定制洞察进行扩展。

## 未来计划

微软正致力于使 Azure 容器应用程序用户能够将容器应用程序移动到 AKS，并将容器从 AKS 移动到容器应用程序。

“我们不想让这成为‘我选择了 A 门，我再也不能回头选择 B 门’的情景，”亨特说。

此外，微软的 Azure Arc(Azure 的未来)将支持 Azure 容器应用。Azure Arc 使用户能够在任何地方运行任何基于 Kubernetes 的工作负载。

“你会看到未来支持在 Arc 上运行容器应用，想想这种灵活性，”亨特说。“我可以在本地硬件上运行一个容器应用程序。我可以在 Azure 上运行一个容器应用，如果有必要，我甚至可以在第三方云中运行一个容器应用。”

## 开发者 CLI

微软还推出了 Hunter 所称的新 Azure 开发者 CLI，以简化平台上的开发者体验。

“Azure 容器应用程序使开发人员能够最大限度地减少研究和编写 YAML 代码的时间，这些代码是定义部署指令以使应用程序环境在特定的 Kubernetes 集群中运行所必需的。相反，他们通过 CLI 请求应用服务，而不必担心入口、负载平衡、机密管理或任何其他 Kubernetes 特有的考虑因素，”Enterprise Management Associates 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk/) 说。

Volk 进一步指出,“使开发人员能够通过 CLI 命令定义应用程序环境具有 GitOps 的优势，只需轻触一个按钮就可以部署或回滚整个应用程序堆栈。虽然所有这些新获得的自由听起来很棒，但该组织需要将 Azure Container 应用程序纳入其整体治理战略，以确保运营一致性和合规性。”

Azure Container 应用和 Azure Developer CLI 帮助微软简化了其客户处理容器和 Kubernetes 的方式，而亚马逊等竞争对手至少有 [17 种方式在 AWS](https://www.lastweekinaws.com/blog/the-17-ways-to-run-containers-on-aws/) 上运行容器——可能[甚至更多](https://www.lastweekinaws.com/blog/17-more-ways-to-run-containers-on-aws/)。

亨特说，在 Build 上介绍或展示的技术中，Azure Container Apps 和 Azure Developer CLI 对他来说非常突出。

“让我给你一个快速纲要，为什么这是重要的，”他说。“我们已经为 Azure 提供了一个 [CLI。为什么有两个 CLI？我们今天为 Azure 开发的 CLI 主要是一个在云中创建资源的工具，”他解释道。“对于试图开发 SQL 数据库、虚拟机和容器应用程序之类的东西的运营人员来说，这太棒了。但是作为一名开发人员，这并不是我真正要做的。作为一个开发者，是的，这是一部分。我需要去做一些东西，但我也非常关心如何让我的应用程序在那里运行，以及如何配置我的应用程序在那里运行。”](https://docs.microsoft.com/en-us/cli/azure/)

在一次客户访问中，亨特说他目睹了开发人员需要 30 分钟来配置他们开始使用 Azure 云所需的所有工具。

“对我来说，这很尴尬，”他说。“因此，开发人员 CLI 背后的理念是它是一个单一的。你可以在大约五秒钟内复制到你的机器上。零到整装待发应该不到一分钟。”

Hunter 说，Azure Developer CLI 为开发人员做的下一件事是它理解约定。

“想象我们在 GitHub 中有一个样本。您希望该示例运行容器应用程序。将会有一个文件夹，我们将把所有用于创建应用程序的文件放在那里。应用程序中有一个文件夹，我们把所有需要从本地运行改为在云中运行的环境变量放在那里，”他说。“开发人员 CLI 知道如何利用所有这些东西，让应用程序在本地机器上运行，然后让应用程序在云中运行。”

从一开始，工具就是微软的强项。“这就是微软的魅力所在，不仅仅是服务。它还与开发人员和开发工具有关，”亨特说。

事实上，这就是好的工具可以为开发组织做的事情。

Guthrie 说:“通过 Azure Container 应用程序，我们已经使云原生和基于微服务的开发变得简化，并且对于任何经验或技能的任何开发人员都是高效的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>