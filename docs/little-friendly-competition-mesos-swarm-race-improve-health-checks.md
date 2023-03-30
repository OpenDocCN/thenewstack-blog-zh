# 梅索斯和码头工人竞相改善“健康检查”

> 原文：<https://thenewstack.io/little-friendly-competition-mesos-swarm-race-improve-health-checks/>

本月早些时候，中间层工程师[加斯顿·克雷曼](https://www.linkedin.com/in/gkleiman/)透露了 [Apache Mesos](http://mesos.apache.org/) 项目的[打算为即将发布的 1.2.0 版本实现一个本地健康检查机制](https://d2iq.com/blog/introducing-mesos-native-health-checks-apache-mesos-part-1)。克雷曼写道，这样一来，依赖于 Apache Aurora 和 Mesosphere 自己的马拉松([现在是 DC/OS](https://thenewstack.io/mesospheres-data-center-operating-system-now-includes-scheduler-orchestrator/) 的一部分)等 Mesos 的调度程序框架就不再需要“推出自己的”方法来跟踪分布式服务。

“我们的意图之一，”克雷曼写道，“是将框架作者从设计他们自己的健康检查 API 中解放出来。为了实现这一点，我们更新了 Mesos API，使得跨所有调度器和执行器一致地表达命令、TCP 和 HTTP(S)健康检查的定义和结果成为可能。”

[分布式应用通常使用心跳](https://thenewstack.io/containers-container-orchestration/)或健康检查来使它们的性能监视器、调度器和协调器能够跟踪大量服务。如果服务不能通过请求或定期 being 发送回某种“我还活着”的信号，它们的管理人员就很容易失去对它们的跟踪。包括物联网在内的所有类型的分布式架构都依赖于这些机制之一。~~~~

如果 Mesos 的健康检查工程师有时间回头看一眼，他们可能只是看到一张满是鲸鱼的脸。

去年 11 月，Docker 项目的贡献者透露，对于 1.13 版本——似乎是为 1 月 18 日的发布做准备——它正在更新它为 1.12 引入的健康检查机制。这一更新将使 Swarm 能够真正让系统投入工作——在这种情况下，根据它从健康检查中收到的数据来修改正在运行的应用程序的服务记录。通过这种方式，Swarm 可以更容易地移除不健康的容器，而不会影响负载均衡器。

## Mesos:授权治理

Mesos 传统上处理健康检查的方式是通过它的*调度器*。在高可用性(HA)场景中，可能有多达三个调度程序同时在网络中运行，其中一个被“选举”为领导者。调度程序维护与 Mesos 集群主节点的连接。至少有一个，可能更多的*执行器*充当在从节点上启动任务的组件。

Mesos 集群中的每个节点都包括一个代理，用于执行主节点指定的功能。如果你愿意的话，这种主人和代理人之间的联系是 Mesos 的“生命线”。它利用了 TCP 网络协议的“默认”功能，为多个 HTTP 请求保持开放。

在这个持久的 TCP 连接上，两个组件交换字面上描述的“ping”和“pong”在 Mesos 的情况下，被乒乓切换的信息是有意义的:它通常包含 Mesos 所谓的*检查点*数据，其中代理描述了它正在处理的内容，而主机将该数据与它期望看到的内容进行比较。就像一个编辑在等待一篇姗姗来迟的文章一样，一个站长可能会选择采取措施中止与代理的关系。

在一些人看来，这个协议可能没有什么特别的缺陷。但是正如 Mesosphere 的克雷曼指出的那样，当一个调度程序和按照该调度程序运行的任务位于不同的节点上时，乒乓游戏可能会消耗过多的网络流量。更重要的是，运行在 Mesos 上的其他框架——让我们面对现实吧，它们可能是同时运行的——对游戏的玩法都有不同的解释。

[GitHub 上的 Mesos 公共文档目前提供了关于 Mesos API 变化的细节](https://github.com/apache/mesos/blob/608e2006e394824f4b74261fcfa59bc8e33eac77/docs/health-checks.md)，这些变化将在 Mesos 版本 1.2.0 中引入。它解释了 Mesos 工程师如何引入一个用于所有健康检查的通用 API，无论是作为一个显式命令还是通过 HTTP(S)或 TCP 协议。

但也许更值得注意的是，执行这些健康检查的责任从调度者转移到了执行者。这样，当节点被广泛分区(包括跨域)时，Mesos 代理能够管理这个过程。

从数量上来说，文档解释说，这将减少分布式应用程序组件之间的流量，使它们更具可伸缩性。不过，这是有代价的:由这些远程代理将它们任务的明确健康状态消息发送回它们的主节点。更重要的是，目前还没有协议让外部资源手动指定一个任务为不健康，尽管可以想象这个问题可能会得到解决。

## Docker 确实改善了它的服务记录

Docker 工程师 [Nishant Totla](https://twitter.com/nishanttotla) 上个月展示了 Docker 的新健康检查(T1)，展示了以这样一种方式扩展分布式应用程序的能力，即一个服务的实例在被认为健康之前不会接收请求。这种能力发生在现在所谓的“Swarm 模式”(Docker，打开嵌入式 Swarm)中。

[https://www.youtube.com/embed/xTfEdoNhH9U?feature=oembed](https://www.youtube.com/embed/xTfEdoNhH9U?feature=oembed)

视频

当一个符号被自动添加到它们的类的服务记录中时，新添加的服务实例被认为是健康的。通过这种方式，Swarm 的负载平衡器不会将 HTTP 请求委派给新容器，直到它们完全正常工作，从而减少了请求无法接收响应并最终超时的情况。

Totla 接着展示了一个正在更新到新版本的服务，而它的旧版本正在运行。Swarm 以前可以做到这一点，但不是以同样的方式。这一次，负载平衡器将在任务的新版本和旧版本之间更均匀地分配并发请求，直到旧版本被删除。同样，服务记录将在后台使用健康检查数据进行修改，从而使过渡更加平稳。

根据 Docker 工程师 [Dongluo Chen](https://github.com/dongluochen) 的说法，任何向 [**containerd**](https://github.com/docker/containerd) 发出的声明容器健康(或不健康)的命令，都会将该声明推入网络数据库。该声明然后通过八卦协议传播到群集群中的所有其他节点(Docker 的选择是 [HashiCorp 的 Serf](https://www.serf.io/docs/internals/gossip.html) )。

## 保证与流言

正如长期的新堆栈读者将证明的那样，Apache Mesos 和 Docker 通常不被认为是相互竞争的。事实上，Mesosphere 以 Docker 容器的形式实现了 Mesos，并且 [Mesos 本身从版本 0.20.0 开始就支持](https://thenewstack.io/mesos-simplifies-support-container-formats-unified-containerizer/)启动 Docker 容器映像。

但去年，Mesosphere 开始采取明确的措施来区分其数据中心操作系统(DC/OS)和 Mesos 框架，宣布它们是他们称为“容器 2.0”的下一代打包系统(T2)的一部分

因此，随着越来越多的企业熟悉这种新的堆栈，套用一句话，将 Docker 和 Swarm 的优点与 Mesos 和 Mesosphere [马拉松](https://mesosphere.github.io/marathon/)调度程序的优点进行比较，他们将在某个时候调查各自消息系统的优点。

Mesos 的消息传递架构在设计上是不可靠的，尽管这在出版物中可能会显得很奇怪。主服务器和代理服务器等组件直接相互发送消息。虽然不能保证接收者会收到消息，但至少它收到的消息是有序的。这是为了权宜之计的权衡。然而，早期的任务状态更新是一个例外，它保证至少交付一次。

为 Mesos 1.2.0 实现的健康检查系统意味着健康消息将在主设备和代理设备之间交换，更接近这些消息所涉及的组件。这意味着调度器将管理失败任务的责任委托给了一个较低级别的组件，这也可能意味着任何中央编排者都必须乐于成为监督者而不是霸主。

相比之下，Docker 使用 gossip 协议确保了高可用性，以及更高的接收健康状态消息的概率。消息的接收可能是无序的，但是一个叫做 Lamport 时钟的时间戳有助于接收者按顺序重组它们。这里的权衡是，当应用程序的宽度线性扩展时，消息流量可能呈指数级扩展。

测试不同架构优点的最佳场所是在竞争激烈的市场中，最好是有成千上万尚未拿定主意的评委。

Docker 和 Mesosphere 是新堆栈的赞助商。

特征图片:[Usien 的专业杂耍师](https://commons.wikimedia.org/wiki/Category:Plate_spinning_in_France#/media/File:Juggling_aus_Frankreich_Teller.JPG)，在知识共享 3.0 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>