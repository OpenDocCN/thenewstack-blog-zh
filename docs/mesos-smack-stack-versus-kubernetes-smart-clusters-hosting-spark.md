# 这是 Mesos 的 SMACK Stack 与 Kubernetes 的 Smart Clusters 托管 Spark

> 原文：<https://thenewstack.io/mesos-smack-stack-versus-kubernetes-smart-clusters-hosting-spark/>

这似乎是不止一个支持者在洛杉矶举行的上一次 2017 年中尺度会议上提出的一个非常有说服力的论点: [Apache Mesos](http://mesos.apache.org/) ，他们说，比任何其他 orchestrator 都更适合大规模运行 [Apache Spark](https://spark.apache.org/) 流数据引擎。有人说 Mesos 更适合提供一个能够运行 Spark 并行任务的框架。但是，他们几乎毫无例外地表示，Mesos 跨多个基础架构配置文件管理工作负载的能力赋予了它优势。

在上面的段落中，你可以很容易地用“Kubernetes”来代替“任何其他管弦乐队”

“我们不得不重新设计我们的软件，我们经历了一个容器化的过程，”Esri 的实时和大数据首席开发者 Adam Mollenkopf 在去年 9 月在[的中尺度会议上说。“因此，我们没有开发一个单一的应用程序，而是将它分解成一些小型的微服务。我们的摄入途径已经被分解成了一些东西，它们坐在那里收集数据。”](https://thenewstack.io/architectural-requirements-customers-require-processing-millions-events-per-second/)

## 重量级

Mollenkopf 展示了 SMACK 栈在工作中的一个关键例子:一组由 Spark 领导的开源组件，并由 Mesos(更具体地说， [Mesosphere DC/OS](https://d2iq.com/) )、用于 Scala 和 Java 的 [Akka 消息传递框架](https://akka.io/)、作为 NoSQL 数据库组件的 Cassandra(尽管有些已经切换到 MariaDB)和用于消息传递的 Kafka 支持。在这个堆栈中，地理空间数据提供商 Esri 添加了作为可视化和搜索引擎的 ElasticSearch，以及用于 Java 和 Scala 应用程序的 Apache Play Web framework。

“这使我们能够根据客户需求横向扩展系统的任何方面，”Mollenkopf 说他的观点是，对于一个企业来说，仅仅为了满足对一种资源的近期需求而扩展整个应用程序环境并不总是可行的。Esri 的实施现在被称为 Trinity 托管服务堆栈。

“在 DC/OS 内部要容易得多——这是一种非常确定的交付这些经纪人的方式，”他告诉一位提问者。“它通过 DC/OS 和 Mesos 的调度系统来实现，实际上它运行在具有可用性的节点上。所以我们真的不需要考虑，“这台机器是给卡夫卡的，”或者，“这台机器是给弹性搜索的。”我们可以有一个通用的框架，可以更好地利用这些系统。如果我们想给调度程序一些提示，比如说，“我实际上希望这是一个数据节点，这是一个接收节点，”你也可以通过 DC/操作系统和 Mesos，通过所谓的*放置配置*来做到这一点。或者如果我不希望两个 Kafka brokers 依赖于同一台机器，我可以给它唯一的托管约束，这样它只在一台机器上运行。我对如何做到这一点有很大的灵活性。"

在[与我们在 meso son](https://thenewstack.io/the-smack-stack-on-mesospheres-dcos-gives-retailers-a-path-to-leave-amazon/)的采访中，天文学家工程副总裁 Aaron Brongersma 告诉我们，除了在“M”上运行“S”、“A”、“C”和“K”组件之外，另一种选择是分别配置这些组件，包括可扩展性策略。这意味着，也要解决如何单独管理和扩展 DNS 服务的问题。

Brongersma 说:“DNS 往往是那些正常工作的服务之一，但是当它们不正常工作时，对每个相关的人来说都是痛苦的。做对是非常困难的。服务发现成为下一个，然后当你开始向上移动堆栈时，我们如何调度我们的容器？所有这一切都将是一吨 R&D 的工作，只是得到一些屈指可数的组件，更不用说我们从一开始就得到的东西，也就是'点击一个按钮，得到一个卡夫卡'。点击一个按钮，得到一个卡珊德拉。我们仍然有能力调整这些服务，但大多数服务对我们来说都是现成的，不需要去寻找最佳实践。"

## 猛打下去

“我不知道为什么有人会说 Spark 的并行需求不能在 Kubernetes 上得到满足，”[首席技术官和](https://twitter.com/ssuchter) [Pepperdata](https://www.pepperdata.com/) 的联合创始人肖恩·苏克特在接受 New Stack 采访时说。在 2008 年被微软挖走领导必应搜索技术中心之前，Suchter 是雅虎前搜索技术副总裁。

在今年的大部分时间里，Suchter 一直忙于演示一个管道系统，他声称该系统不仅集成了 Spark 和 Kubernetes，而且有效地使它们成为 Kubernetes pods 中分析密集型容器调度的合作伙伴。Kubernetes 是一个由[云本地计算基金会](https://www.cncf.io/)管理的开源项目。

“可能他们的意思是，从历史上看，如果你想在 Kubernetes 上运行 Spark，你必须以 Spark 独立的方式这样做——这意味着 Spark 是 Kubernetes 的一层，不知道如何告诉 Kubernetes 启动许多工人，并让他们相互通信，”Suchter 继续说道。“基本上，要么你必须自己完成所有这些工作——这是一个非常高的技术壁垒——要么你的 Spark 应用程序必须是一个容器，因此显然不是并行的。但有了原生的 Spark-on-Kubernetes 工作——它只存在了不到一年，但现在完全可以访问，并将出现在 Spark 的下一个正式版本中——现在 Spark 可以与 Kubernetes 进行原生交互，它可以请求它需要的任何并行度，它可以进行 [Spark 动态分配](https://spark.apache.org/docs/1.6.1/configuration.html#dynamic-allocation)，这允许它随着应用程序的需求而动态变化。”

Spark 已经有了一种方法，可以指示引擎根据自己对当前工作负载的评估需求，来调整它所使用的执行器数量。因此，在 Suchter 看来，任何声称只有 Mesos 能够独立地动态扩展堆栈中的一个组件的说法，都可能忽略了开源社区的其他成员在 Spark 上所做的最近几个月的工作。

去年 8 月，Spark 社区批准向 GitHub 发布最新 Spark 2.2.0 版本的分支，演示用 Kubernetes 替换 Spark 的原生集群管理器。一开始就不应该是开胸手术。Spark 在 Mesos 上运行的事实已经表明 Spark 对这个问题漠不关心。

然而，正如在最近的 Spark 峰会上不止一次[所展示的那样，Kubernetes 和 Spark 不会完全表现为“解耦”的组件。事实上，它们是真诚合作的:通常的 **spark 提交**脚本会将作业发送给 Kubernetes 调度程序，后者通过调度特定于 spark 的驱动程序来响应。当司机请求包含 Spark 执行者的 pod 时，Kubernetes 会根据需要遵守(或拒绝)。执行者将依次运行 Spark 任务，就像以前一样。火花驱动器将处理清理。](https://www.youtube.com/watch?v=0xRHONrWwvU&feature=youtu.be)

这是一个复杂的事件链:从提交过程，到驱动程序，到执行者，最后到任务本身。但这也意味着 Spark 容器可以与包含其他任务的 pods 共享基础设施。我们的目标是 Spark 可以与已经在那里运行的任何基础设施共享。

这个目标需要 Kubernetes 运行任何特殊的配置吗？不，Pepperdata 的 Sucher 说。

“当我们在 Kubernetes 上实现本机 Spark 支持时，我们遇到的部分好处(这是 Kubernetes 令人印象深刻的)是，Kubernetes 为我们提供的原语足够丰富，允许这些大数据、高度并行、高度占用资源的应用程序与其他非大数据服务共存，并且根本不知道这些 Spark 容器或它们的语义——在同一个集群上，无需修改 Kubernetes 或这些其他应用程序。”

Pepperdata 是否解释了协同处理硬件日益流行的原因，例如 [FPGA 加速器](http://www.datacenterknowledge.com/archives/2016/11/14/xilinx-unleashes-fpga-accelerator-stack-supporting-caffe-openstack)和[通用 GPU](http://www.datacenterknowledge.com/archives/2016/11/11/nvidia-become-data-center-accelerator-company)(gp GPU)，它们独特地利用了并行化？Suchter 无法对 Spark 上的 Kubernetes 作出回应。但是对于他的公司现有的 YARN 数据库优化器的发布版本，他们已经监控了并行数据作业如何在各种硬件配置上运行，包括加速器。CTO 告诉我们，为了提供 Hadoop 用户(就 YARN 而言)所期望的确定性和可靠性，这是非常必要的。

## 准备好战斗吧

如果你经常阅读新的堆栈，你已经看到，包括 Mesos 和 Kubernetes 在内的多个 orchestrators 的支持者是如何支持[开发容器存储接口](https://thenewstack.io/containerization-leaders-explore-possible-data-storage-interface-initiative/) (CSI)的。这是一种为容器提供对持久存储的访问的机制，理论上支持对持久数据库甚至是大型数据湖的有状态连接。

因此，当你听说 Pepperdata 的 Suchter 认为，在涉及 Hadoop 或 Spark 的高度并行的场景中，这样的连接可能是不必要的，甚至是不可取的，你会感到惊讶。事实上，他和他的团队一直在研究其他东西:通过 Kubernetes 现有的存储抽象，将 HDFS 文件系统与容器直接集成的方法。

“对于大数据系统，你不会真的想将数据加载到一个卷上，一次装载到一个地方，”CTO 告诉新堆栈，“可能会四处移动。你只需要考虑你想读的数据。这是分布式文件系统的全部前提:您不必仅仅将数据看作是被某人使用的卷。这是一种更抽象的思维方式。当然，Kubernetes 有一些原语，允许您在任一抽象级别上考虑数据。因此，我们添加了一个非常高性能的分布式文件系统——HDFS，没有 Hadoop 部分——作为一个持久存储后端，它可以在 Kubernetes 系统内部使用，并且可用。”

他解释说，这将是集群上的存储，使用 HDFS 语义，以 Hadoop 速度执行。但是如果追溯的话，它可以被视为 orchestrator 的原生文件系统。他认为，有了这种本地级别的集成，实际上就不需要消息队列来协调各层之间的数据重新分发。“如果你真的在解决非玩具类的问题，那么用这种方式来使用信息系统是很没价值的，”他说。您不希望有更多的系统中介体可以直接相互通信，因为每个中介体——尤其是消息传递系统，以及它们所有的上下文切换——都会让您损失很多性能。如果不需要中介，就不要。”

这是一个资深(也是有价值的)搜索系统开发人员的强有力的论点，它为 SMACK 栈提供了一个很大的漏洞。Sean Suchter 说，如果组件在更深的层次上合作，你可能不需要在它们之间做太多。两个交织在一起的元素可以做五个堆栈的工作。然而，Spark 2.2.0 上个月才发布，这是一个等待确凿证据的论点。

云本地计算基金会和 T2 中间层是新堆栈的赞助商

专题图片:1893 年的一次事故，一个蒸汽机[的锅炉爆炸，整齐地落在另一个](https://commons.wikimedia.org/wiki/File:Locomotive_engineering_-_a_practical_journal_of_railway_motive_power_and_rolling_stock_(1897)_(14761379935).jpg)的上面(没有人受伤)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>