# 超越 Bash:微软改进了 Linux 的 Windows 子系统

> 原文：<https://thenewstack.io/windows-10-creators-update-means-windows-subsystem-linux/>

微软对 Windows 10 的最新更新[被称为 Creators Update](https://www.microsoft.com/en-us/windows/upcoming-features) ，将包含用于 Linux 的 [Windows 子系统](https://msdn.microsoft.com/en-us/commandline/wsl/about)，这一工具可能会使 Windows 10 对越来越多考虑从 Mac OS 转移的开发人员更具吸引力，因为他们发现 MacBook Pro 无法满足他们的需求。

微软的 [Rich Turner](https://github.com/bitcrazed) 告诉新堆栈，WSL 通常被称为“Windows 上的 Bash ”,因为 Bash 是入口点，而“类似 Bash 的体验”是最初的目标之一。他负责 Windows 控制台和 WSL，但是 WSL 远不止将 Bash 作为 Windows 上的替代 shell。Bash 只是打开 Linux 命令行所有工具的一个起点。

他解释说，WSL 是“一个与 Linux 兼容的环境，看起来和行为都像 Linux，允许你运行所有的 Linux 代码——你的 Linux 构建系统、你的 GNU 工具和你运行、构建和测试你的应用程序所需的一切，而不必启动虚拟机。”WSL 仍然使用 Windows 内核；它只是使用它来运行 ELF64 Linux 二进制依赖的系统调用，通过一个 pico 驱动程序与微软的 [Linux syscall 接口](https://blogs.msdn.microsoft.com/wsl/2016/06/08/wsl-system-calls/)的 clean room 实现。

微软将 WSL 放在 Windows 中主要是为了开发人员，因为许多开源工具、语言和库都认为开发人员在使用 Linux。“其中许多都与 Linux 行为、Linux 文件系统层、Linux 网络套接字交互机制等有着很强的依赖性，这使得其中一些东西很难在 Windows 上很好地工作，因为 Windows 做这些事情的方式略有不同。”

像 node、Python 和 Ruby 这样的核心语言和运行时在 Windows 上已经足够好了。但是，如果你想访问你在 Linux 上使用的相同的 gems、包、库和模块，那么你可以使用完全相同的工具链，你需要更基本的兼容性，而不仅仅是像 [Cygwin](http://cygwin.com/) 和 [MSYS](http://mingw.org/wiki/msys) 那样将一些 X Windows 或 GNU 库移植到 Windows，因为这在二进制包方面没有帮助。

“许多 Ruby gems 都是编译过的，人们依赖这些编译过的 gem，然后他们在 Windows 上遇到了问题。很多 gem 希望文件在一个特定的位置，在 Windows 上看起来完全不同。我们需要能够不加修改地从 Linux 加载和运行二进制文件，”特纳说。

这个想法不是把 Windows 变成 Linux，而是把开发人员依赖的 Linux 工具和 Windows 工具放在一起，比如 Visual Studio(以及 Office 等生产力应用程序)。

Canonical 负责微软 Ubuntu 开发的技术主管 Dustin Kirkland 对新的 Stack 说，这也不是要放弃 Linux 桌面的想法。“我认为这是引入 UNIX 和 Linux 通过命令行与计算机交流的一种很好的方式，是通向数以万计的开源工具的一个入口。向数十亿 Windows 用户提供 Linux 方式和开源方式的机会太好了，不能错过。”

当他使用 Visual Studio 为 WSL 构建 Ubuntu 映像时，他自己的灵感出现了，当时他必须在大约 17 个不同的文件中更改一个特定的术语。他意识到他可以像在 Ubuntu 上一样，在 Windows 的 Documents 文件夹中对项目使用递归 grep 和 sed，而不是寻找一个不熟悉的 GUI 命令。

“这两者配合得非常好。我在 vi 中比在任何图形编辑器中更得心应手，所以能够弹出到 vi 窗口，创建和编辑文件，并在系统上本地执行 ssh，这是非常强大的，”他说。

## 日常司机

如果您很早就尝试过 WSL 并且感到失望，那么是时候换一种方式了。在 [Windows 10 周年更新](https://blogs.windows.com/windowsexperience/2016/06/29/windows-10-anniversary-update-available-august-2/)中的 WSL 版本是一个早期版本，以获得开发者关于他们需要 WSL 运行什么工具的反馈。“这是我们前进方向的快照，”特纳强调说，指出它有明显的差距。

“你不能 ping，你不能查看你的 ifconfig 来了解你的网络是如何配置的。我们无法运行 Java，我们无法运行 npm，因为它无法枚举网络配置。这些现在都可以运行了，我们可以运行 MySQL、Postgres、Apache、Nginx、node、Ruby、Java 和 Python，甚至核心 CLR 现在也可以运行 ASP.NET。”

在 Creator 的更新中，像 SSH 和 GDB GNU 调试器这样的关键工具工作起来更加可靠。你甚至可以在 Visual Studio 中将 WSL 配置为 Visual C++ for Linux 的目标，这样你就可以可视化地编辑和调试，然后[在 WSL](https://blogs.msdn.microsoft.com/vcblog/2017/02/08/targeting-windows-subsystem-for-linux-from-visual-studio//) 中编译和构建。

他说，让这些工具发挥作用意味着“在新的系统调用中添加大量新的功能，或者通过扩展我们系统调用实现的广度和深度，允许更多的工具和库运行”。向现有系统调用添加新的系统调用或新的功能通常可以修复 20 或 30 个问题，从而实现快速改进。

柯克兰称这一进展是杰出的。“我们已经看到 Windows 内核团队填充了更多的 WSL，捕获了更多的系统调用，并确保您期望在 Linux 中工作的任何东西都能继续工作。我们看到像 Screen、Tmux 和 Byobu 这样的东西现在工作得非常好。我们开始看到提供初始化过程的一些小东西，这样我们就可以在不久的将来开始做一些事情，比如容器。”

Canonical 维护着你第一次运行 Bash 时 Windows 10 系统下载的用户模式映像。到目前为止，这些都是 Ubuntu 14.04，大约每三个月就有一个新的图像(这是微软建议 Windows 用户可以接受的频率，Kirkland 指出)。随着 Creators 的更新，这将切换到 Ubuntu 16.04 (Xenial，去年 4 月发布的版本。)

这是一个很大的改进，因为这意味着常用库、编译器和实用程序的更新版本，所有这些都是原生打包的，只需安装一个打包的应用程序。

如果 Creators Update 是你第一次在 PC 上使用 WSL，Ubuntu 16.04 将被默认安装。如果你已经有了 14.04，Windows 不会更新你的发行版。Turner 说这是因为来自社区的强烈反馈，他们不希望更新是自动的)。你可以使用`sudo apt dist-upgrade`进行就地升级，如果你想要一个干净的 16.04 实例，使用`lxrun /uninstall /full`移除你的 Ubuntu 实例，然后用`lxrun install.`重新安装

Creators Update 还修复了一些简单的问题，比如控制台中的鼠标支持(以及添加 24 位颜色)。它还更紧密地集成了 Windows 和 WSL 环境。“你可以在 Ubuntu 系统上运行一个影响 Windows 系统的命令，”Kirkland 解释道；“因此，您可以实时编辑文件，并在记事本和 vi 中更新文件，或者您可以从 Linux 启动一个应用程序，在 Windows 中触发一个事件，反之亦然。”

这种集成也意味着您可以在 Windows 任务管理器中看到 Linux 进程。“支持 Tmux 允许你有多个窗格，每个窗格都运行自己的 Bash，所以如果你在任务管理器中查看，你会看到 Bash 的多个实例，主实例是 init 的子实例，以及每个 tiles 的实例，”Turner 解释道。"如果你运行 MySQL，你会在任务管理器中看到它."

这为您提供了一种处理失控的 Linux 进程或容易出错的 Bash 脚本的简便方法。您可以在任务管理器中右键单击它们并终止该进程。网络和系统监控工具也可以看到 WSL 进程，因为它们暴露于 Windows 管理界面，并且使用 Windows 网络堆栈和 Windows 防火墙。企业可能希望这样做，以便他们可以将现有的安全监控工具用于 WSL 流程和 Windows 流程。

这也为企业解决了一个大的管理问题，这些企业的开发人员可能会使用数十台虚拟机，而这些虚拟机无法像 Windows 工具那样受到监控。“他们可以让开发人员摆脱 Hyper-V 和 VMware 虚拟机，这些虚拟机绕过大多数 Windows 网络堆栈，直接与网卡对话，”Turner 解释道。

## 坚持使用命令行

现在，WSL 平台覆盖了大多数主流开发人员场景，重点正在转移到 Turner 所说的更深奥和边缘的情况，以及更多的开发人员请求，并将继续有更多的更新和改进。

你不应该期望 WSL 做的一件事——官方的——是支持 Linux 桌面。用户一直在尝试这一点，从 Ubuntu 桌面到 Firefox 都在运行。Turner 说，它们工作的事实纯粹是使 WSL 与其设计的开发工具兼容的副产品。

“我们非常清楚，我们构建 WSL 的原因是为开发人员提供一个完成工作的环境。开发人员使用一些 Linux GUI 工具，但是总的来说，他们希望能够运行的大多数工具是编译器、调试器和构建引擎等等。我们只专注于命令行工具和场景。”

然而，微软并没有阻止这些实验者。“我们看起来很有趣，”他说，“我们没有做任何事情来阻止它，但这不是我们努力的方向。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>