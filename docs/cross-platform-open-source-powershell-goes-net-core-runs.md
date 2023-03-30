# 微软的 PowerShell 核心提供跨平台自动化

> 原文：<https://thenewstack.io/cross-platform-open-source-powershell-goes-net-core-runs/>

Microsoft PowerShell 任务自动化和配置管理框架长期以来一直与核心 Microsoft 工作负载相关联；它提供了从 [Azure Stack](https://azure.microsoft.com/en-us/overview/azure-stack/) 到 Windows 10 的一切访问。但自 2016 年年中以来，它也成为了一个跨平台的开源外壳和脚本工具，一个独特地适合新兴的 API 和结构化对象世界的工具。

微软的客户越来越不仅仅使用 Windows 和 Windows Server 他们使用 Linux 和 MAC(一端是 Raspberry Pi，另一端是多种云服务)。为了支持这种多样性， [PowerShell Core](https://github.com/powershell) 在 Windows 7、8.1 和 10、Windows Server 2008 R2、2012 R2、2016、Windows Server 半年度频道、Ubuntu 14.04、16.04 和 17.04、Debian 8.7+和 9、CentOS 7、Red Hat Enterprise Linux 7、OpenSUSE 42.2、Fedora 25、26 和 macOS 10.12+上运行，并带有不支持的 AppImage 软件包

> “越来越多的 Linux 世界变得基于 API，并返回结构化对象，即 JSON 对象，我们将其转换为文本，无需任何解析就可以做各种奇妙的事情。”—杰弗里·斯诺弗

PowerShell 的 Linux 版本不再是单独的代码库；随着 macOS 和包括物联网在内的越来越多的平台，它是 PowerShell 项目的一部分，具有共同的特性和功能。“该公司正在成为一家跨操作系统的公司。我喜欢说‘海纳百川’；微软研究员[杰弗里·斯诺弗](https://twitter.com/jsnover)说:“我们希望成为所有人的公司，不管你使用什么平台。

但是，PowerShell Core 6 在 Windows、macOS 和 Linux 上的普遍上市，并不仅仅意味着微软用于管理企业中常见的异构系统组合的解决方案已经可以在生产中使用。它还为 Windows 上的 PowerShell 带来了一些重大变化，因为 PowerShell 的跨平台、开源、社区驱动、“get-it-from-GitHub”核心版本是所有新开发都将发生的地方。

## 真正的跨平台

过去十年我们一直称之为 PowerShell 的现在被命名为 Windows PowerShell，因为它是基于。只在 Windows 上可用的. NET 框架。PowerShell Core 基于微软的(也是开源和跨平台的)。NET 策略，使用。NET Core 2.0 运行时和[。NET Standard 2.0](https://github.com/dotnet/standard/blob/master/docs/faq.md) 通用库和 API。

“我们对 PowerShell Core 所做的就是点击刷新按钮，”斯诺弗告诉我们。“我们保留了所有伟大的东西，我们有勇气抛弃那些不能带我们去我们想去的地方的东西。我们希望成为一种工具，让公司可以从任何地方管理任何事情。”

这意味着 PowerShell Core 现在可以处理 Windows 不支持的常见 Linux 文件名字符，如冒号和逗号，以及带有正斜杠或反斜杠分隔符的路径。默认编码是没有字节顺序标记的 UTF-8；这是 Linux 和 macOS 上的默认设置，在 Windows 上也越来越常见。

为 GA 添加了日志记录支持，但它使用了一组不同于 Windows PowerShell 设置的组策略对象(这将简化两者的并行使用，但这是在。ADMX 名单公布了)。在 macOS 上，PowerShell 使用原生 os _ log APIs 登录苹果的统一日志系统；在 Linux 上，它使用 Syslog。对于远程处理，PowerShell Core 使用 SSH 作为本地传输协议。向基于 OpenSSH 的 SSH 服务器注册 PowerShell，现有的基于 SSH 的身份验证机制(如密码或私钥)使用传统的 PSSession 语义。

PowerShell Core 并不试图取代 Bash、Python 或任何现有的工具；它所做的是将结构化数据的自动化和处理引入 Linux，而这一点正变得越来越重要。

“越来越多的 Linux 世界变得基于 API 并返回结构化对象，JSON 对象，我们将其转换为文本，无需任何解析就可以做各种各样的事情，”斯诺弗指出，声称“Linux 正在向 PowerShell 的最佳位置移动。在 Linux 上，我们是一个工具，我们是另一个外壳，就像任何其他外壳一样，并且有无数的外壳存在。如果你的世界只是文本解析，我们做得很好，但我们没有比其他人更大的优势。但如果你有结构化数据，我们会领先一大截。”

PowerShell 在安全性方面也为 Linux 提供了一些优势。“我们现在有了世界上第一个运行在 Linux 上的[安全透明外壳。斯诺弗说:“我们从 Windows PowerShell 中获取了尽可能多的可以在 Linux 上运行的安全内容，所以你可以配置完全透明的脚本块日志记录等等，而 Linux 以前从未有过这种功能。”。](https://twitter.com/Lee_Holmes/status/951228529806475264)

PowerShell 项目经理 [Joey Aiello](https://github.com/joeyaiello) 证实，结构化数据解析和云编排一样，在 Linux PowerShell 用户中很受欢迎。

“总的来说，我认为人们正在使用大量的云流程编排模块；我们有 AzureRM 和 VMware 的核心版本，AWS 已经发布了一些人们正在使用的模块。但是我也经常看到 PowerShell 被用作测试编排和一般 REST API 自动化的一部分。我们有 [PSSwagger](https://github.com/PowerShell/psswagger) ,这使得从描述 REST API 的开放 API 文档中生成 PowerShell 模块变得更加容易，这使得针对 REST API 编写脚本变得非常容易，我们认为这是 API 争论的下一个级别。我们在堆栈中向上移动了一层；PowerShell 在作为所有这些不同 API 的漏斗和真空方面做得很好，我们认为它在云和 REST API 领域有很多机会再次做到这一点。”

## 肩并肩

对于 Windows PowerShell 用户来说，PowerShell Core 的含义略有不同，因为他们已经有了一个他们已经习惯并投入精力学习的工具，还有这个新工具，它的功能略有不同，不会自动安装。事实上，只是在最近两个月，Windows 对 PowerShell Core 的使用才变得重要起来；“在那之前，大量的使用是 Linux，”斯诺弗告诉我们(让他吃惊的是)。

PowerShell 5.1 可以与 PowerShell Core 并行运行，PowerShell Core 有自己的 pwsh.exe 可执行文件，并以 ZIP 包的形式提供，因此管理员可以安装多个版本，脚本可以固定到他们需要的特定版本。Windows PowerShell 将继续作为 Windows 10 和 Windows Server 的一部分提供和支持，并将获得错误修复。但它不会获得新的功能，如 JSON 和 Web cmdlets 中的增强功能，以简化针对 Web 服务的脚本编写，或[新的 Docker 支持](https://hub.docker.com/r/microsoft/powershell/)，允许您使用 docker pull microsoft/powershell 来获得 powershell 核心。

“Windows PowerShell 5.1 是一个非常强大、非常有能力的工具，它将继续得到支持，我的猜测是永远得到支持，但它不会得到增强，”斯诺弗告诉我们。“我相信，任何需要用 Windows 特有的方式做事情的人都可以很好地使用 Windows PowerShell。但我们将把所有投资放在新的跨平台工具上。”换句话说，Windows PowerShell 不会消失，就像 CMD.EXE 为了那些觉得它有用的人而留在 Windows 中一样。

这仍然在 Windows PowerShell 用户中引起了一些关注，特别是关于模块和工具的兼容性，以及功能上的差异。目标是尽可能兼容。“为了能够跨平台。斯诺弗指出:“为了更好地适应 UNIX 世界，我们必须做出一些小小的改变，而事实是这些都是突破性的改变，所以核心 PowerShell 和 Windows PowerShell 之间是有区别的。”。“实际上，当现有的 cmdlets 工作时，绝大多数人的事情都会正常工作。NET 核心，但有一些变化。"

如果。PowerShell 模块所依赖的. NET 功能在。NET 标准 2.0，该模块将与 PowerShell 核心一起工作，他解释说。“[windows pmodulepath](https://www.powershellgallery.com/packages/WindowsPSModulePath/)模块改变了您的模块路径并引入了现有的模块，而事实是大多数模块都工作得很好；有些人不喜欢，但大多数人喜欢。更重要的是，虽然团队(建立那个模块)没有签署支持他们，他们没有做全面的测试。”

作为 Windows 的一部分提供的大多数模块(如 Hyper-V、NetTCPIP 和 Storage)或其他微软产品(如 Azure 和 Office)尚未明确移植到 PowerShell Core，也不受支持，但许多模块似乎可以工作。PowerShell 自带的许多内置模块都有错误修复和新功能，但有时它们也会失去功能。网芯不支持。

根本不支持管理单元(较旧的、很少使用的模块版本)，这意味着 Windows 上的 ActiveDirectory 和 DnsClient 模块还不能工作(PowerShell 和 Windows Server 团队已经在开发 AD 模块)。PowerShell 工作流建立在 Windows 工作流基础之上，需要。NET 框架，这样就只剩下 Windows 了；“我们询问了社区，我们没有听到响亮的‘这很重要’”，斯诺弗告诉我们。最受欢迎的工作流用途是并行性，因此微软正计划为 [PowerShell Core](https://github.com/PowerShell/PowerShell-RFC/issues/85) 支持并发性，尽管它要到 PowerShell Core 6.1 才能实现。

有一个 [Windows PowerShell 兼容包](https://github.com/PowerShell/WindowsPowerShellCompatibilityPack)计划恢复 PowerShell 核心中缺失的一些 Windows PowerShell 功能，如别名、WMI 和 perf cmdlest，以及自动设置模块路径。像 Get-wmio object 这样的 WMI v1 cmdlet 已经不起作用了；它们都被 WMI v2 cmdlet 所取代，后者通常会添加额外的功能，但这仍然是一个需要做出的改变。第三方也需要更新他们的模块——如果那些供应商还在经营的话。

到目前为止，PowerShell Gallery 上只有一个简短的兼容模块列表(在 30 个模块中，有 3 个已被否决，只有三分之一不是来自微软)，但当 PowerShell Standard 5.1 和 Core 6.0 库在本月晚些时候发布时，开发人员将更容易创建与这两者兼容的模块。

虽然斯诺弗不能评论各种微软团队何时会正式支持微软工作负载的 PowerShell Core，但他指出“不仅 Windows 人员能够管理你的东西，Linux 人员也能；当一个跨平台的价值主张很重要时，[微软的]人们会全力以赴。Azure 已经完全进入市场，并将很快进入市场。”

Azure PowerShell 团队有几个预发布模块，用于在 PowerShell Galley 中将 [Azure 资源管理器](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-overview)与 PowerShell 核心一起使用，并且正在简化用于 Azure 的 PowerShell cmdlets 的语义。PowerShell 核心支持是 Azure Automation 的“路线图”,但不要期望在测试或更新大量 cmdlets 之前看到它。

从长远来看，这种变化当然会带来很大的好处。“现在最大的挑战是 cmdlets 需要在两种框架中都得到支持；如果你链接了。NET 标准库，那么您可以同时使用完整的。NET 和。网芯。这意味着 cmdlets 可以与 Windows PowerShell 和 Windows 上的 PowerShell Core 一起工作，如果您将这些代码移植到 Linux 上，它们也可以在 Linux 上运行，因此我们需要获得整个社区的支持。网标。”

微软的[期望状态配置](https://redmondmag.com/articles/2017/09/12/powershell-desired-state-configuration-core.aspx)正在获得和 PowerShell 一样的深度更新，尽管它没有走得那么远。“理想状态配置从一开始就一直是跨平台的，它可以在代理端的 Windows 和 Linux 上使用，但实际上，我们有一个 Linux 代码库和另一个 Windows 代码库，我们将统一这个代码库，”斯诺弗说。

“我们正在我们的 Azure 资产中广泛部署所需的状态配置。如果你看看 Azure 门户，你会看到我们有配置管理，我们将使它在 Azure 中无处不在。当我们这样做的时候，我们会获得一组新的需求，我们会推出一个新的设计。它将是一个分层的期望状态配置工具；换句话说，将会有一个定义良好的接口，能够首先与本地代码代理进行对话，该代理类似于引导代理等一系列东西。从那里，它将能够引导到一个基于. NET 核心的代理，并从那里获得一个完整的托管代码代理。”

斯诺弗证实,[JEA PowerShell 安全控件可以在 PowerShell Core 的 Windows 上运行，也将进入 Linux。“我们需要在 Linux 方面增加很多东西，但这是我们的目的。事实上，只要 Linux 允许做一些事情，我们就会尝试用 PowerShell Core 来做。”](https://msdn.microsoft.com/en-us/library/dn896648.aspx)

PowerShell 正在成为另一个微软开源的成功，新版本中一半的变化来自 PowerShell 社区。那就是去哪里寻找他告诉我们的 PowerShell 的方向。“我们现在是一个基于社区的项目，这意味着它是完全开放的。我们在 GitHub repo 中有一套项目和优先级；没有第二套书，这些是我们的书，社区可以说‘我们认为你在这一点上是错误的’。它是一件完全敞开的和服。社区可以把它带到任何他们需要的地方。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>