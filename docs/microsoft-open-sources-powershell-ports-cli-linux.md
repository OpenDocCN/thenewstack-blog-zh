# 微软开源 PowerShell，将 CLI 移植到 Linux

> 原文：<https://thenewstack.io/microsoft-open-sources-powershell-ports-cli-linux/>

微软为管理员开放了 Windows 命令行 shell，称为 PowerShell，并将其移植到 Linux 和 MacOS 上。

“Linux 上的 PowerShell 现在使客户能够使用同样的工具，同样的人，从任何地方管理一切，”微软技术研究员兼该公司企业云小组首席架构师杰弗里·斯诺弗在宣布发布的博客文章中写道。

像 Bash for Unix/Linux 一样， [PowerShell](https://powershell.org/) 被设计成 Windows Server 的丰富命令行界面。它建在。Net 框架，所以它享有一个[丰富的脚本环境](https://www.microsoft.com/en-us/download/details.aspx?id=36389)。

斯诺弗在随后的采访中告诉 TNS，展望未来，PowerShell 的新版本将同时面向 Windows 和 Linux 发布。“Linux 将成为一个完全的一等公民，”他说。

这项工作是基于早期的和微软的移植。NET 核心到 Linux。代码可在 [GitHub](https://github.com/PowerShell/PowerShell) 上获得。这些软件包最初将适用于 Ubuntu、CentOS、Red Hat Enterprise Linux 和 Mac OS X。该公司还移植了在 Windows 上运行的 [OpenSSH](http://www.openssh.com/) ，因此用户可以为 PowerShell 的所有用途部署一个单一的远程访问协议。

开放 CLI 源代码的动力来自客户，据斯诺弗称，他们来自那些希望在 PowerShell 上实现标准化的客户，但由于它不能在 Linux 上运行而受到限制。

PowerShell 不仅可以提供 Windows 和 Linux 的接口，还可以通过模块的方式扩展到第三方平台。Amazon Web Services 和 VMware 都有可用的 PowerShell 扩展，Google 和 Chef 也正在开发它们。

“客户将能够编写一个脚本来管理 VMware、Azure 或 AWS，并在 Windows、MacOS 或 Linux 上运行，无需修改，”斯诺弗说。

https://youtu.be/VsThrkdlKpE

## 反斜杠和区分大小写

微软最初[开发](https://blogs.msdn.microsoft.com/powershell/2007/03/18/monad-manifesto-the-origin-of-windows-powershell/) PowerShell 时就考虑到了 Unix。该公司希望为 Windows 提供一个强大的命令行界面(CLI ),就像 Unix 提供的许多 shells 一样，管理员可以用它来控制应用程序和脚本进程。

虽然开发团队(斯诺弗是其中的一员)想要模仿 Unix，但他们采取了一种稍微不同的方法。Unix/Linux 的部分强大之处在于，在命令行中，所有的操作都可以被编写成脚本，并在一个操作管道中绑定在一起。

斯诺弗说，Unix 管道是围绕文本字符串构建的，而 PowerShell 则更多地针对对象进行了优化。斯诺弗承认，当前的开发团队仍有一些工作要做，以达到基于文本流的处理的完全保真，以及其他高级 Unix shell 方法，如 [globbing](http://www.tldp.org/LDP/abs/html/globbingref.html) ，这是一种文件名扩展的形式。

另一方面，PowerShell 基于对象的方法可能会带来一些 Bash 没有的优势(3 月份，微软[将](https://thenewstack.io/microsoft-plants-bash-windows-freaks-everyone/) Bash 嵌入 Windows)。“我们的亮点在于结构化数据，”斯诺弗说。

斯诺弗说，出于自动化的目的，管理界正在从文本流处理转向读取配置文件等任务，并转向表面结构化对象，如 REST APIs。

“调用一个 REST API，得到的是一个 JSON 文件。我们将它们转换成结构化的对象，”他补充道。

当然，Windows 管理员必须适应 Linux 的某些方面，尤其是区分大小写，Unix 尊重这一点，而 Windows 不尊重。此外，Unix 和 Windows 处理斜线以区分文件路径的方式也有所不同:Unix 使用正斜线，Windows 使用反斜线。斯诺弗说，那些对编写跨平台脚本感兴趣的人仍然必须考虑这些差异。

该公司还增加了许多新功能，以帮助交叉兼容性。一个是 PowerShell 编辑器服务，它为外部代码编辑器提供了编辑 PowerShell 文件的钩子，并支持[智能感知](https://msdn.microsoft.com/en-us/library/hcw1s69b.aspx)和其他调试工具。最初， [VS Code](https://code.visualstudio.com/) 和 [Sublime](https://www.sublimetext.com/) 是为 PowerShell 配备的，以后还会有更多的编辑器。

该公司还内置了对 PowerShell 的 OpenSSH 支持，允许用户使用 PowerShell Remoting 协议( [MS-PSRP](https://msdn.microsoft.com/en-us/library/dd357801.aspx) )通过 SSH 进入远程 PowerShell 环境。实际上，微软已经将 OpenSSH 移植到了 Windows 上。用户还可以部署现有的 [Windows 远程管理支持](https://msdn.microsoft.com/en-us/library/aa384426(v=vs.85).aspx)。

https://youtu.be/Mx1bgIjO8SM

## 管理所有的事情

虽然将 CLI 扩展到其他平台似乎是一个令人愉快的特性，但这一举动可能会产生强大的反响。斯诺弗说，在 Linux 和 Windows 上运行的 PowerShell 现在可以“为所有需要管理的东西提供一个通用的管理堆栈”。

例如，它可用于启动 VMware 虚拟机，在部署时对其进行配置。PowerShell VMware 模块包含用户可以在 vCenter 中执行的每个操作的命令。

https://youtu.be/kh5nTvELwfo

PowerShell 是使用微软的[期望状态配置](https://msdn.microsoft.com/en-us/powershell/dsc/overview) (DSC)的关键，该公司的 IT 自动化脚本语言可用于配置和管理资源。PowerShell 还为该公司的云管理服务提供了一个接口，[运营管理套件](https://thenewstack.io/microsofts-jeremy-winter-qa-automation-new-visualization/) (OMS)，该套件提供了 Azure 和其他云之间工作负载的可见性和控制。实际上，这允许用户从命令行管理他们的云资源。

https://youtu.be/O–d_F5A7aA

OMS 还提供了一个集中的位置来管理 PowerShell 操作手册、DSC 配置和 DSC 节点配置。

IDC 软件开发研究项目主管[阿尔·希尔瓦](https://twitter.com/AlHilwa)在一封电子邮件中写道:“我认为，在继续巩固 PowerShell 的成功和普及的基础上，这对微软来说是正确的事实上，可以说，很难为任何至少部分针对开发者的专有技术进一步建立生态系统和社区。是时候让[PowerShell]在 Linux 系统上可用了，Linux 系统占了今天运行在云中的大部分内容。"

特写图片由 [Jorge Lascar](https://commons.wikimedia.org/wiki/File:Troy_(and_a_trojan_horse)_(8709942456).jpg) ，CC BY 2.0。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>