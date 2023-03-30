# Docker 的未来在编排上

> 原文：<https://thenewstack.io/the-new-stack-analysts-dockers-future-is-in-the-orchestration/>

Docker [今天将 DotCloud 出售给一家德国公司](http://gigaom.com/2014/08/04/docker-parts-ways-with-its-dotcloud-business/)，摆脱了该公司作为 PaaS 提供商的痕迹。这笔交易发生在[收购多主机 Docker 编排技术 Fig 的制造商 Orchard](http://gigaom.com/2014/07/22/docker-acquires-orchard-laboratories-to-beef-up-its-tool-collection/) 之后。Docker 已经成为几个新的 PaaS 提供商的核心。但是，为了多台主机之间的可移植性和通信而编排容器，确实可能是一个关键的转变，影响了多年来一直使用虚拟机来移动和编排应用程序的公司的基本工作流程。

在 DockerCon 上个月的一份新的 Stack Analyst 记录中，有明确的迹象表明 Docker 和许多其他公司认为编排在容器技术的未来具有重要意义。

加入我们的是 Docker 的詹姆斯·特恩布尔；Brandon Philips， [CoreOs](https://coreos.com/) 的首席技术官；[新遗物](http://newrelic.com)的保罗不以为意；世纪链接实验室的卢卡斯·卡尔森。

[#7: Docker 的未来在编排](https://thenewstack.simplecast.com/episodes/7-dockers-future-is-in-the-orchestration)

*   *   收购 Orchard 的消息反映了 Docker 仍然非常年轻的状态，以及编排如何在容器及其不断发展的功能的演变中发挥关键作用。此外，它还显示了 Docker 既是技术提供商，也是提供编排平台的公司的潜在竞争对手。
    *   但是，考虑到从 Docker 的单主机功能到多容器主机模型所产生的复杂性，这是一种高度的合作。
    *   CoreOs 是一个底层，与 [etcd](https://thenewstack.io/about-etcd-the-distributed-key-value-store-used-for-kubernetes-googles-cluster-container-manager/) 打包成一个 Linux 操作系统，用于配置的开源分布式键值存储和用于调度管理的 Fleet。码头集装箱运行在顶部。时间安排是这里的大问题，其他人也在解决这个问题。 [Mesos](http://mesos.apache.org/) 是一个编排平台，使用 [Apache Aurora](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0CB8QFjAA&url=http%3A%2F%2Faurora.incubator.apache.org%2F&ei=Lx_gU8WZB6bAigKEnYDACQ&usg=AFQjCNEWFPO0wZv1DKFNSNIqVvEaKaTmHg&bvm=bv.72389368,d.cGE) 作为调度器。zookeepeer 是另一个做服务器配置的 Apache 项目。这是两种可以与 CoreOs 技术集成的调度技术。
    *   考虑操作系统市场，很明显，减轻工作负载的新的轻量级系统对用户有巨大的吸引力，当容器服务大规模工作时，编排是至关重要的。等待操作系统提供商更新的时间可能长达数月甚至数年。CoreOS 正在通过在分布式环境中自动更新操作系统来攻击操作系统市场的软部分。红帽正在适应它的原子项目。
    *   应用生态系统随着这些新的编排技术而发展。例如，Deis 正在使用 CoreOS 作为其平台即服务。他们用它来抽象和管理应用程序开发的方式。正是这个软件交付管道是公司面临的最大的痛点。Deis 的工作不需要操作人员将代码从笔记本电脑转移到网络上。New Relic 正在以类似的方式使用 Docker，开发自己的 PaaS。对于 New Relic，这是一个自助式测试和试运行环境。它甚至在某些方面允许自助式生产环境。
    *   这与连续交付过程有很大的相关性。如果着眼于持续部署，历史上您需要聪明的工程师来构建和运行它们。现在你不需要成为一个摇滚明星。使用 Docker 的平台如 Shippable、Drone 和 Travis CI 都有 Docker 项目正在进行中。詹金斯多年来一直在研究最先进的技术。像 CloudBees 这样的公司现在处于一个竞争更加激烈的世界。
    *   谷歌对 Docker 的兴趣来自于大规模运行容器。时间安排仍然是最大的挑战。
    *   CenturyLink 实验室正在建立一个教育公众如何使用 Docker 的系统。认识上有巨大差距。正如卡尔森所说:“在‘hello world’方法和更复杂的用法之间有很大的区别。”
    *   Docker 开发了 [Docker Hub](https://hub.docker.com/) 作为对 GitHub 的敬意，并使其成为 DevOps 专业人员有效使用 Docker 的一种方式。
    *   PaaS 最大的缺失之一是协同工作的能力。Docker 和 Docker Hub 的社交方面使它成为 it 前所未有的东西。
    *   Docker 离简单性还有很长的路要走，如 Docker 服务器间通信中所示。例如， [Libswarm](https://github.com/docker/libswarm) 就是朝着这个方向迈出的一步。多个 Docker 主机无法通信。它缺乏对编排的抽象。例如，看到容器在三种环境中运行仍然很复杂。如果一家公司想在 DO 和 Google 之间转移容器，通过网络并扩大规模，这表明了 Docker 想要做什么。这种可移植性和跨云的东西将在短期内成为现实。
    *   保罗说:“Docker 攻击那些按照 Rube Goldberg 的方式拼凑起来的碎片，并使它们变得可行和有效。”“为什么我们要建造所有这些复杂的东西？目标是:重写管道系统。”
    *   比喻:互联网有技术问题，但它是放在那里的技术的健壮选择之一。作为一种解决方案，它是可靠的，也是 100 年后唯一会被记住的技术。应该有一些容易使用的工具，它们可以很容易地修理东西而不会使它散架。
    *   Libswarm 的强项是一个很好的起点。你如何定义一个 Mesos？如何定义一个 etcd 以便它们是可组合的？在大多数情况下，管道被视为字节流。它是什么并不重要。互联网只关心它是一个字节流。因此，我们继续探讨调度程序是什么，以及它所公开的接口是什么。什么是有效的键值存储，它公开了什么？
    *   重要的是微服务。Docker 把它带到了另一个高度。这将有助于将应用程序过渡到微服务方法。Docker Hub 以同样的方式帮助协作。它是一个等待微服务出现的培养皿。
    *   假设你有 WP，MySQl 等。在单个主机上运行。它有复杂的相互作用。一个简单的变化可能会对整体服务产生更广泛的影响。我可以清楚地定义它。微服务可以大大简化管理。微服务的组合应该更容易管理。
    *   追踪是一个大问题。你如何检查并洞察这些服务中发生的事情，以帮助开发人员或管理员了解系统中的问题？
    *   Nagios 曾经是最有效的监控工具。下一波监控将是一件大事。可以通过 New Relic 跟踪事务，但如果有人构建了一个更通用的模型，它就可以进行事务。下一波浪潮将是与监控相关的。
    *   可以在容器中追踪的微小微服务将是有益的。Monitoring 是另一个可以添加到应用程序中的微服务。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>