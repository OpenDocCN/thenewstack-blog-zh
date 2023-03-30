# CNCF 采用 Sysdig 的 Falco 容器运行时监视器

> 原文：<https://thenewstack.io/cncf-adopts-sysdigs-falco-container-runtime-monitor/>

深入研究安全性，云本地计算基金会已经接受 Sysdig 的 [Falco](https://sysdig.com/opensource/falco/) 容器运行时监视器作为早期沙盒项目。

CNCF 和 Sysdig 希望这个软件能够引发更多关于如何在新兴的云原生技术世界中解决安全问题的讨论，[迈克尔·杜西](https://twitter.com/mfdii)， [Sysdig](https://sysdig.com) 社区和福音传道总监说。

“人们只是不努力锁定东西，”Ducy 说。“有很多公开的 Kubernetes 仪表板，或公开的 Kubelet APIs，因为人们正在向互联网开放每个端口。”

Sysdig 在 2013 年创建了 Falco，作为其开源行为监控软件的核心，并在 2016 年将其分离出来，命名为“Falco”。到目前为止，该软件已经被 100 多万用户使用。

该软件旨在检测容器中的异常活动，通过将一个传感器模块附加到 Linux 内核来检测所有的[系统调用、它们的参数以及调用进程](https://github.com/falcosecurity/falco/wiki/About-Falco)的属性。

Ducy 说，因为容器的范围很广，包括应该在其中运行什么，应该操作什么文件，应该绑定到什么端口，所以开发人员可以为大型容器集制定一套通用规则。

通过部署过滤语言和规则引擎，用户可以从容器中创建接受行为的白名单。例如，运行 Node.js 的特定容器应该只打开端口 80 或端口 443，应该只运行一个进程，并且应该只读写特定的目录。Falco 还可以监视潜在的异常情况，比如外壳在容器中运行，或者二进制程序进行出站连接。

该软件会发出异常行为的通知，这可能会被 CNCF 的 NATS 等发布/订阅消息系统或 Kafka 等流处理引擎捕获。然后，管理员可以为其权限内的容器订阅这些消息队列。

将这种监控扩展到 CNCF 的 [Kubernetes](https://www.kubernetes.io) 容器编排引擎的工作正在进行中。目前，用户可以基于 Kubernetes 元数据创建规则，这些规则可以应用于特定的名称空间、部署或单个 pod。有了这些信息，管理员或脚本就可以杀死违规的容器或隔离有问题的 Kubernetes 节点。

该项目的领导人还计划使用 [OpenMetrics](http://OpenMetrics.io) 格式和另外两种 CNCF 技术进行普罗米修斯集成。

[https://www.youtube.com/embed/wFQOXMcZnQg?feature=oembed](https://www.youtube.com/embed/wFQOXMcZnQg?feature=oembed)

视频

Falco 不是唯一提供容器运行时监控的开源软件。美国国防部的 SELinux 项目提供了操作系统级的超级站点，尽管设置起来相当麻烦。Google 的 [gVisor](https://thenewstack.io/google-launches-gvisor-an-open-source-sandboxed-container-runtime/) 通过提供 Linux 系统调用的子集，将 Linux 内核从容器中分离出来，提供了一个额外的隔离层。

随着 CNCF 的采用，Sysdig 正在将 Falco 从 GPLv2 许可证转移到 Apache 许可证 v2，以使其对云原生社区更加开放。

云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>