# Instana 使用 eBPF 来检测“异常进程终止”

> 原文：<https://thenewstack.io/instana-uses-ebpf-for-detecting-abnormal-process-termination/>

构建一个在 Kubernetes 上运行的应用程序的主要好处之一是，当一个进程崩溃时，Kubernetes 会自动在其位置上重新构建一个新的进程，几乎不会跳过一个节拍。同时，这意味着问题可能会被忽视，微服务提供商 [Instana](https://www.instana.com/) 的应用性能管理(APM)引入了一项新功能，该功能可以检测和报告异常进程终止，以帮助解决可能导致您完全没有意识到的问题的表面崩溃。

“它不像一个整体系统，如果某个东西崩溃了，你必须重启一些机器。Instana 的技术总监 [Chris Farrell](https://www.linkedin.com/in/chrisefarrell) 在接受新堆栈采访时表示:“这是关于随着时间的推移不断改进您的系统，而不是避免严重的故障。“异常终止流程的问题之一是它在整体操作中被掩盖了，但在您的客户体验中不一定会被掩盖。虽然，是的，该系统旨在当一个进程崩溃时启动一个新的进程并填补空白，但这可能会造成延迟高峰，可能会出现负载问题和其他类型的问题。”

这项新功能可以在所有运行 Linux 内核 4.8 和更高版本的 Linux 机器或容器上工作，并使用[扩展的 Berkeley 数据包过滤器(eBPF)](https://thenewstack.io/linux-technology-for-the-new-year-ebpf/) 来获得一些额外的信息，以帮助它确定这些崩溃的根本原因。Farrell 解释说，虽然 Instana 已经与内核挂钩，但 eBPF 提供了额外的信息来确定进程是否异常终止。

“我们将 eBPF 视为堆栈中的任何其他技术部件，因此我们实际上在它上面放置了一个传感器。当崩溃发生时，我们实际上是使用 eBPF 来获取终止代码等信息。这个想法是首先查看任何终止错误代码，以确定它是预期终止还是异常终止，”Farrell 说。“通过使用错误代码，我们可以了解崩溃的真正原因是什么？有杀人指令吗？还是就这么发生了？是不是内存用完了？它是否有无效的操作码？”

根据一篇[博客文章](https://www.instana.com/blog/never-miss-another-crash-instanas-crash-detector-brings-real-time-abnormal-process-termination-analysis-to-linux/)，eBPF 传感器“近乎实时”地报告异常进程终止，“从一个重要进程崩溃到在瞬间看到其死亡的准确诊断，需要一到两秒钟。”传感器是用 Rust 编写的 Instana 的第一部分，他们注意到“它确实名副其实地赢得了令人敬畏的声誉”，并且可以在任何有 eBPF 的系统上开箱即用。然而，Farrel 强调 eBPF 只是一个更大图景的一部分。

“这不仅仅是来自 eBPF 的数据，而是我们从 eBPF、Linux 和其他传感器获得的数据，这些传感器可能包括 Kubernetes、Docker、Rancher 或基础架构堆栈中的任何其他组件，然后是堆栈本身。如果它是一个应用服务器，我们将在应用服务器的水平，”法雷尔说。“我们有这种将所有这些信息联系在一起的细微差别，以开始了解到底是什么导致了这场崩溃，以及你需要从哪里开始寻找解决办法。”

Farrell 说，一旦识别出异常的进程终止，就可以向您发出警报，并且可以像处理任何其他问题一样处理问题，任何补救措施都由您为此目的连接 Instana 的任何系统来处理。在用户端，除了在兼容版本的 Linux 上运行之外，不需要任何东西就可以启动并运行新特性。

KubeCon + CloudNativeCon 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>