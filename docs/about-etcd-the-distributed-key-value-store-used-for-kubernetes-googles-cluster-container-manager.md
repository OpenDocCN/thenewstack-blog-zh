# 关于 Etcd，用于 Kubernetes 的分布式键值存储，Google 的集群容器管理器

> 原文：<https://thenewstack.io/about-etcd-the-distributed-key-value-store-used-for-kubernetes-googles-cluster-container-manager/>

我花了很多年开发分布式系统。在我来到 CoreOS 之前，我是 Heroku 的第一批雇员之一，从事研究、开发和分布式系统工程。2011 年，我和 Heroku 的同事 Keith Rarick 一起写了 [Doozer](https://github.com/ha/doozer) ，这是 [etcd](https://github.com/coreos/etcd) 的灵感。

Etcd 是一个开源的分布式键值存储，通过为集群协调和状态管理提供一个规范的中枢——真实的系统来源，它充当了分布式系统的主干。虽然 etcd 是专门为运行 CoreOS 的集群构建的，但它可以在各种操作系统上工作，包括 OS X、Linux 和 BSD。

今天有很多关于 [Kubernetes](https://googlecloudplatform.blogspot.com/2014/07/welcome-microsoft-redhat-ibm-docker-and-more-to-the-kubernetes-community.html) 的新闻，它是来自 Google 的开源容器集群管理器，恰好构建在 etcd 之上。Kubernetes 利用了 etcd 分布式键值存储。它负责存储和复制 Kubernetes 在整个集群中使用的数据，由于 Raft consensus 算法，etcd 可以从硬件故障和网络分区中恢复。除了 Kubernetes，Cloud Foundry 还使用 etcd 作为他们的分布式键值存储。

集群通常由大量能够在任何给定时间运行任何工作负载的机器组成。为了让集群高效运行，我们需要在集群中的所有机器上适当地分配工作负载。那么集群就需要一种相互协调的方式。

例如，作业调度程序需要通知机器它有工作要做。一旦这项工作完成，机器可能需要将这一事实传达给集群中的其他组件。分布式系统需要可靠的协调机制，因此及时可靠地进行这种通信以保持一切顺利运行非常重要。本质上，必须有某种东西来管理集群的状态——真实的来源。

这就是 etcd 的用武之地。

跨任何分布式系统管理集群状态是困难的问题所在。集群经常遭受网络分区和恶劣的竞争条件的困扰，需要在某个地方解决。我们避免在我们的应用程序或单个机器级别处理这种复杂性，因为维护将成为一场噩梦，所以我们在堆栈的更高层处理它，在那里 etcd 可以真正发挥作用。

Etcd 用 Go 编写，使用 [Raft 协议](http://raftconsensus.github.io/)。Raft 是用于多个节点维护状态改变命令的相同日志的协议，并且 raft 节点中的任何节点都可以被视为主节点，并且它将与其他节点协调以就状态改变发生的顺序达成一致。

https://www.youtube.com/watch?v=06cTPhi-3_8

**支持分布式系统**

Etcd 被设计成任何分布式系统的支柱，这就是为什么像[谷歌 Kubernetes](https://github.com/GoogleCloudPlatform/kubernetes) ，Cloud Foundry 和 [Fleet](http://coreos.com/using-coreos/clustering/) 这样的项目依赖于 etcd。借助 etcd，您可以轻松管理集群协调和状态管理。如果你想在 CoreOS 上尝试 Kubernetes，可以去我们的博客[看看例子。](https://coreos.com/blog/running-kubernetes-example-on-CoreOS-part-1/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>