# TNS 教程星期五:CoreOS rkt 容器引擎，它是什么，它与 Docker 相比如何

> 原文：<https://thenewstack.io/tns-tutorial-friday-exploring-coreos-rkt-container-engine/>

在本周的新堆栈[教程星期五](https://thenewstack.io/podcasts/tutorials/)中，我们探索 CoreOS 的容器引擎 [rkt](https://coreos.com/rkt/) ，讨论开发者的选择和灵活性如何影响容器生态圈，并深入了解 rkt 和 Docker 之间的良性竞争。新堆栈的创始人[亚历克斯·威廉姆斯](https://www.linkedin.com/in/alexwilliams2)在 [CoreOS](https://coreos.com/) 与文档运营部的[乔希·伍德](https://www.linkedin.com/in/joshua-wood-a453aa90)坐下来讨论这些话题以及更多。

Wood 通过深入研究使 rkt 从其他容器管理工具中脱颖而出的特性开始了演示。首先，rkt 没有强加一个守护进程，这个守护进程会在系统的后台空转，站在容器和它们的管理工具之间。一旦环境启动，rkt 将退出并允许用户与他们的容器完全交互。Rkt 使用一种 [ACI](https://coreos.com/rkt/docs/latest/app-container.html) (应用程序容器映像)格式来构建它的映像，Kubernetes 也是如此。Wood 指出，虽然这与 Docker 的容器格式不同，但 rkt 完全支持 Docker 图像，可以轻松地直接缓存 Docker Hub。

[https://www.youtube.com/embed/hdiVlkOY1ME?feature=oembed](https://www.youtube.com/embed/hdiVlkOY1ME?feature=oembed)

视频

打开终端后，Wood 在 rkt 中输入一个 *sudo* 命令来启动 Alpine Linux 的一个实例。rkt 和 Docker 的另一个区别是 rkt 使用了 pod，Kubernetes 集群也是如此。“这种一对一的映射不仅方便，还意味着当你构建真正最小的容器时，pod 为你提供了一种围绕它们共享资源的方式，从而使那些真正微型的架构变得有意义，”Wood 说。

为了更好地了解 rkt 的权限结构，Wood 导航到 Alpine Linux 容器 CLI。这允许他通过在终端中输入命令 *rkt list* 来访问信息，比如哪些容器当前正在运行。Wood 指出， *rkt 列表图像*将列出用户从哪些特定的容器中拉出。接下来，Wood 输入命令 *ps axf* 来查看 Alpine Linux 容器的主机上的进程树内部。“我们可以找到我们刚刚开始运行的外壳，它实际上是我们称之为高级流程模型的分层术语的一个示例。Rkt 在容器系统内部旋转一个初始化的存根系统来管理流程生命周期，因此您不必重新实现 init 来管理容器内部的流程，”Wood 解释道。

尽管 rkt 和 Docker 之间存在良性竞争，但 Wood 很快指出 rkt 支持 Docker 图像，可以直接从 Docker Hub 获取并转换图像。为了演示这一点，Wood 开始使用命令*Sudo rkt run docker://Josh IX/Caddy*启动一个 [Caddy web 服务器](https://github.com/joshix/caddybox)。在 rkt 中，管理网络操作的任务由另一个 CoreOS 项目处理，即[容器网络接口](https://github.com/containernetworking/cni) (CNI)。除了作为 Kubernetes 的网络插件模型之外，Wood 指出，CNI 还可以直接与 rkt 集成。

与 CNI 相反，Docker 使用 [libnetwork](https://github.com/docker/libnetwork) 来管理容器中的网络。虽然 libnetwork 对于那些希望快速入门的人来说仍然是一个可靠的选择，但 Wood 指出，“使用 libnetwork，你会被迫进入本地与全球的二分法，以及他们看到的网络模型。很多时候，那个选择才是正确的选择。但是，你越是向平台构建者、集成商和将工具组装成自己的解决方案的人靠近，你就越需要灵活性。”

当对话接近尾声时，Wood 强调了在围绕标准化容器的讨论中要考虑的一个重要因素，“我们觉得我们以前可能学到的一个教训是，不要让任何类似于单一供应商控制某些东西的规范的事情发生。我们认为有一个标准是很重要的，这个标准是我们，整个互联网用户群体所拥有的，并且能够感受到真正的所有权。集装箱是什么，你可以堆多高，你可以在里面放多少负载，这些都是标准化的。”

CoreOS 和 Docker 是新堆栈的赞助商。

特征图片: [Tylana](https://www.flickr.com/photos/tylana/ "Go to Tylana's photostream") 的: [Rocketscape(版本:2011 Dark)](https://www.flickr.com/photos/tylana/6046796016/in/photolist-adkpMJ-hv29Q-aBAxmj-mwrhZX-p783KS-J9oq1U-9VmTQy-cnc1H5-9ViWAZ-bsoyhu-6QsoFs-9Vj8d4-a5kjB6-2tWXZy-8vuowe-71Wkn1-9EkRN-oM94XV-fNGoaY-62EXLu-5ySPUZ-dNMTCS-bF1TAS-rp8CF-abUkoV-2xQHwY-cN5fBq-8LaVVo-bYk2Rw-G1pdd-8vthyF-a88h1P-8vsRwt-8vv6gX-8vvoRi-8vsUSp-8vwbrN-dVL3Af-g2GAet-9ruwYc-8vwdWd-dpNbER-8vti9t-8vvYZS-8vvCuo-8vuFTD-8vw5Kb-jCEJd-adBYBe-8vvZMw) 在 [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 下获得授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>