# 微软推出开发盒预览版

> 原文：<https://thenewstack.io/microsoft-launches-dev-box-preview/>

微软为开发者发布了 Dev Box 托管服务的公开预览版。

微软 Dev Box 于 5 月份在该公司的 [Build 2022](https://docs.microsoft.com/en-us/events/build-2022/) 开发者大会上推出，它是“一项托管服务，使开发人员能够在云中创建按需、高性能、安全、现成代码、特定于项目的工作站”，[微软 Visual Studio Core 的首席团队项目经理 Anthony Cangialosi](https://www.linkedin.com/in/acangialosi/) 在[的博客文章](https://azure.microsoft.com/en-us/blog/announcing-microsoft-dev-box-preview/)中说。

## 将开发转移到云

微软开发部门负责产品、设计、用户研究和工程系统的公司副总裁[阿曼达·斯尔沃](https://www.linkedin.com/in/amandaksilver)称，将开发转移到云的过程是她最喜欢的主题之一，她在 Build 的一次演讲中说，“将开发盒转移到云托管并通常容器化，使我们能够在开发团队之间创建一致的环境，优化交互式使用的计算可用性，并使我们能够利用云的力量，以便我们可以增加智能和规模来提高您的生产力”。

使用 Dev Box，开发人员可以专注于编写他们可以编写的代码，而不必设置基础架构来构建和运行代码。开发盒是现成的代码，并由团队预先配置了开发人员项目和任务所需的所有工具和设置。

## 任何 IDE、设备、平台

此外，Dev Box 支持任何运行在 Windows 上的开发人员 IDE、SDK 或工具。坎加洛西说，开发者可以针对任何可以从 Windows 构建的开发工作负载，包括桌面、移动、物联网和网络应用。微软 Dev Box 支持通过 Linux 的 Windows 子系统和 Android 的 Windows 子系统构建跨平台应用。此外，远程访问允许开发人员从任何设备安全地访问 dev boxes，无论是 Windows、macOS、Android、iOS 还是 web 浏览器，他说。

“因此，我们的想法是，你使用 Azure 虚拟桌面，并为开发人员定制它，这样开发人员就不必坐在那里启动他们的开发工作站，而是让一切都完美地对齐，以便开始编码。这一切都是在云和虚拟机中为您预先配置的，您可以开始自动工作，”微软长期观察家 Mary Jo Foley[在回顾微软构建大会的头条新闻时说。“我认为这是 Azure 虚拟桌面的第一个非常有趣的垂直案例研究。”](https://en.wikipedia.org/wiki/Mary_Jo_Foley)

Microsoft Dev Box 基于 Windows 365 构建，这意味着 IT 管理员可以通过 [Microsoft Intune 和 Microsoft Endpoint Manager](https://thenewstack.io/how-attackers-move-from-azure-active-directory-to-on-prem-ad/) 管理 Dev Box 以及物理设备和云电脑。

“Dev Box 是一个 VDI[虚拟桌面基础设施]解决方案，具有 Windows 云 PC 的所有优势，如 Intune 的管理服务，但针对开发人员的需求进行了优化，”Silver 说。“它包括能够与他们的监管环境相匹配的策略，以保护敏感的源代码和客户数据，并定期对他们的机器进行重新映像。游戏和 Windows 桌面应用是更适合 Microsoft Dev Box 的两个应用工作负载示例。”

## 其他基于云的开发环境

微软 Dev Box 是少数基于云的开发平台中的最新一个，这些平台包括 [AWS Cloud9](https://www.theserverside.com/news/450433105/AWS-Cloud9-IDE-threatens-Microsoft-developer-base) 和 [Eclipse Che](https://www.theserverside.com/news/252470913/Eclipse-launches-Che-7-IDE-for-Kubernetes-development) 等。

英特尔公司的分析师杰森·彭博说:“我相信这三种工具都具有开发人员已经开始欣赏并期望从现代工具中获得的整体成熟度和特性集。“这将是一个基于选择环境的偏好选择。Dev Box 在微软环境中运行良好(例如，与微软 365 紧密集成)，而 Cloud9 非常适合以 AWS 为中心的开发，Che 则适合在 Kubernetes 上构建应用。”

## 可用性和定价

Microsoft Dev Box 现在可以从 Azure 门户获得预览版。在此期间，组织每月免费获得前 15 个小时的 dev box 8vCPU 和 32 GB 内存 SKU，以及前 365 个小时的 dev box 存储 SSD 512 GB SKU，Cangialosi 说。

“除此之外，组织只为他们使用的基于消费的定价模式付费，”他说。在这种模式下，组织根据消耗的计算和存储数量按小时计费

除了 Dev Box 使用基于消耗的计算和存储定价模型，以便用户只为他们使用的东西付费之外，组织还可以设置自动计划，在一天开始时预热 Dev Box，并在一天结束时停止它们，让它们处于闲置状态。坎加洛西说，有了新的即将到来的休眠功能，开发者可以恢复停止的开发盒，并从他们停止的地方重新开始。

微软没有透露任何关于 Dev Box 何时上市的信息。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>