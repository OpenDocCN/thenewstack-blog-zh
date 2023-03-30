# 微软的开源标量带来了对 Git 的大型存储库支持

> 原文：<https://thenewstack.io/microsofts-open-source-scalar-brings-large-repository-support-for-git/>

对于像微软这样的公司，规模与软件交付生命周期的每个部分都相关，而不仅仅是处理来自全球用户群的流量高峰。这意味着即使是代码库也必须能够处理超过 10 万名开发人员和跨越数百万个文件的库的需求，上周，微软通过开源项目 [Scalar](https://github.com/microsoft/scalar/) 的[版本](https://devblogs.microsoft.com/devops/introducing-scalar/)朝着这一目标迈出了一大步。Scalar 是一个用于 Windows 和 Mac (Linux 待定)的. NET 核心应用程序，它支持非常大的代码库，通过设置推荐的配置值和运行后台维护来最大化 git 性能。

根据[微软 Azure DevOps 的首席软件工程师德里克·斯托利](https://www.linkedin.com/in/derrickstolee)的说法，git 是微软“最常用和最重要的”DevOps 工具之一，分布式代码库用于构建微软 Office、Azure 和 Windows 等产品，他说他们认为这是现存最大的 git 回购。

这项工作实际上始于一个更早的项目，git 的[虚拟文件系统(VFS ),它使用虚拟化的文件系统让 Git 认为文件存在，当它们不存在时，管理 Git 的内部状态，只考虑被访问的文件，确保快速执行状态和签出等命令。微软一直使用 Git 的 VFS(以前的 g VFS)来支持 Windows 仓库，但是在这个过程中发现了性能瓶颈。随后，负责为 Git 创建 VFS 的团队开始研究消除对虚拟文件系统和创建标量的需求的方法。](https://vfsforgit.org/)

“这是精神的延续，因为它旨在解决类似的问题，但使用不同的方法，”Stolee 在接受新堆栈的电子邮件采访时解释道。“git 的 VFS 使用虚拟化文件系统，而 Scalar 利用 Git 核心和其他解决方案中的一些改进来绕过虚拟化文件系统的需求。Scalar 的核心思想是通过研究 Git 的 VFS 是如何工作的，以及考虑如果我们移除虚拟化的文件系统会发生什么而产生的。通过将 git 稀疏校验特性替换为虚拟化文件系统，我们能够很快获得标量的原型。”

Stolee 在博客中详细解释了“指导 Scalar 设计的三个重要经验”，将它们列为关注文件的[、](https://devblogs.microsoft.com/devops/introducing-scalar/#lesson-1)[减少对象传输的](https://devblogs.microsoft.com/devops/introducing-scalar/#lesson-2)和[不等待昂贵的操作的](https://devblogs.microsoft.com/devops/introducing-scalar/#lesson-3)。因此，Scalar 为 Git 做了几件类似于 VFS 的事情，但是没有虚拟化的文件系统。Stolee 说，与 Git 的 VFS 相比，Scalar 架构的“一些重大转变”使他们能够将项目完全转移到。NET Core 3.0，结合放弃虚拟化的文件系统，帮助 Scalar 支持更多的平台。

对于拥有大型 git 存储库的 git 用户，“scalar register”告诉 scalar 配置某些设置和挂钩以优化性能，并在后台运行定期维护以在需要时保持快速运行。Stolee 说，这些功能利用了 git v2.25.0 中已经存在的常规 git 功能，但需要专业知识才能正确设置。同时，他说 Scalar 提供了一些 git 中没有的附加功能。

“为了支持微软内部的大型工程团队，我们需要一些 git 中没有的功能。其中大多数都围绕着减少数据传输，Azure Repos(Azure devo PS 的一部分)通过 GVFS 协议解决了这一问题。' **scalar clone** '命令创建一个新的本地存储库，并使用 GVFS 协议下载比完整 git 历史记录更小的一组对象，包括历史记录中每个文件的每个版本；这些版本可以按需下载。它还用一个稀疏检验定义初始化存储库，这样在开始时就不会填充所有文件。Stolee 写道:“稀疏检出和按需下载的结合允许用户开始使用非常大的存储库。

GitLab 的高级产品营销经理乔迪·蒙(Jordi Mon )在评估 Scalar 的发布时似乎持谨慎乐观的态度，回忆了用 Git 大文件存储(LFS )解决大型存储库所带来的问题的另一次尝试的历史。他说，最初由 Atlassian 和 GitHub 等人开发的解决方案最终被发现不容易集成，需要自己的命令，并且能够大大降低性能。

“这是微软的一个大胆举措。本质上，他们说的是我们没有等待 git 中的本地大文件支持，我们自己已经做到了。在用户对性能和 UX 的反馈公开之前，很难说这一举措会有多成功，”Mon 在一封电子邮件中写道。".NET Core 似乎是从。NET 框架在许多方面，我相信标量只会证明这是真的。”

事实上，在博客中，Stolee 明确表示团队“有意让 Scalar 做得更少，并投资让 git 做得更多”，他通过电子邮件详细阐述了这一点。

“虽然我们为 git 贡献了许多功能，使其能够处理比以前更大的存储库，但在我们所有的工程师完全依赖 git 之前，仍有一些主要障碍需要清除，”Stolee 写道。“标量是我们弥合这一差距的方式，直到我们能够贡献足够多的功能来让标量变得不必要。我们预计这项工作需要几年时间，但我们需要支持微软内部大型工程团队的需求。”

Stolee 说，标量显示了后台维护等功能的价值，git 中的任何实现看起来都可能非常不同。他将这比作 VFS Git 中用于动态获取对象的额外 HTTP API，这最终激发了由微软的 Jeff Hostetler 和谷歌的 Jonathan Tan 构建的部分克隆功能，该功能随后由社区进行了改进。Stolee 说，他希望通过将 Scalar 的特性引入 git 来获得同样的社区支持。

“在一起，我们通常会发现对我们最初方法的改进，我们期待着在功能上的开放合作，这将允许我们从标量转移到 git 本身，”Stolee 写道。

当然，通过在上游 git 上工作，Scalar 的特性可能会影响下游项目，如 GitHub 和 GitLab。Stolee 表示，该团队目前正在向 G\git 上游发送补丁，以支持 Scalar，但不是 Scalar 本身，以包含在官方版本中。然而，该公司尚未宣布 GitHub 将如何支持 Git 或 Scalar 的 VFS。Jordi Mon 解释说，Scalar 最终整合到 GitLab 将是其标准流程的结果。

“我不能代表产品团队发言，但如果它的开源和社区需要它，它可能会出现在 GitLab 的路线图中。不像微软或 GitHub，他们提供封闭源代码软件，不公开他们的路线图，我们的大多数功能都是社区驱动的，并最终包括在我们公开发布的路线图中，”Mon 写道。

GitLab 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>