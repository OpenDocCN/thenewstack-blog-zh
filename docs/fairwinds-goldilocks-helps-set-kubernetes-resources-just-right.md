# Fairwinds 的金发女孩帮助设置 Kubernetes 资源刚刚好

> 原文：<https://thenewstack.io/fairwinds-goldilocks-helps-set-kubernetes-resources-just-right/>

Fairwinds 的一个新的开源工具 Goldilocks 旨在帮助团队为他们的 Kubernetes 部署分配资源，并使其恰到好处。

这是一个帮助团队为他们的 Kubernetes 工作负载设置资源*请求*和*限制*的工具。据该公司称，知道如何设置它们并不容易，一些团队根本没有设置它们，从而产生了不良影响。

“每当你在 Kubernetes 中创建一个工作负载时，你必须指定该工作负载将使用多少内存和多少 CPU，”该公司开源总监 Robert Brennan 解释道。

“做好这件事有两个方面。如果你把请求设置得太低，那么一个普通的应用程序看起来会占用太多的内存，太多的 CPU，Kubernetes 会杀了它。这将导致你的应用程序变得非常不可靠。这可能会导致停机，而且肯定会导致您的工程师的寻呼机在半夜响起，这总是一件痛苦的事情。

“另一半是，如果你把它设置得太高，这是人们倾向于做的，那么你(分配)更多必要的计算，你的云账单将比它需要的高得多，”他说。

Goldilocks 采用 Kubernetes [垂直 Pod 自动缩放器](https://github.com/kubernetes/autoscaler/tree/master/vertical-pod-autoscaler) (VPA)，其中包含一个基于您的 Pod 中当前使用的资源量的推荐引擎，以提供指导。

“VPA 的主要目标是真正为你设置这些，但该公司对其这样做的方式感到不安，更喜欢主要用于推荐，”金发女孩的创造者安迪·苏德曼在一篇博客文章中写道。

“我们利用 VPA 推荐引擎的方式很简单。我们在集群中运行一个控制器，监视标有**goldilocks.fairwinds.com/enabled=true**的名称空间。在这些启用的名称空间中，我们查看每个部署对象并创建相应的 VPA 对象。VPA 设置为**模式:关**并且实际上不修改您的资源请求和限制；它只是坐在那里，提供建议，”他写道。

要查看这些建议，您必须使用 **kubectl** 来查询每个 VPA 对象，如果您有中型到大型的部署，这可能会很快变得乏味。

Goldilocks 的另一部分是一个仪表板，根据您所寻求的服务质量，在一个地方提供两种类型的建议:

*   *保证，*这意味着应用程序将被调度到资源得到保证的节点上。
*   *Burstable，*这意味着应用程序将保证最低水平的资源，但如果可用，将会得到更多的资源。
*   *Best effort* ，这是不推荐的，意味着不设置任何请求或限制，只有当所有其他请求都被满足时，应用程序才会被分配资源。

金发女孩软件可以在 GitHub 上下载。

这家总部位于波士顿的托管基础设施提供商之前发布了一款名为 [Polaris](https://github.com/FairwindsOps/polaris) 的[开源工具，它可以进行大约 20 次检查，以确保 Kubernetes 的部署符合最佳实践。](https://thenewstack.io/polaris-points-the-way-to-kubernetes-best-practices/)

图片来自 Pixabay 的 congerdesign。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>