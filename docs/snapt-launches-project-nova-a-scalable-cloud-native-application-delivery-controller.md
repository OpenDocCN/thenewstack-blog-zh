# Snapt 推出 Project Nova，这是一款可扩展的云原生应用交付控制器

> 原文：<https://thenewstack.io/snapt-launches-project-nova-a-scalable-cloud-native-application-delivery-controller/>

应用交付控制器提供商 [Snapt](https://www.snapt.net/) 发布了 [Project Nova](https://nova-adc.com/) ，这是一项从浏览器管理的云原生托管 ADC 服务，以应对 Kubernetes 在其软件定义的 ADC 上日益增长的使用。

Snapt 首席执行官[戴夫·布拉基](https://za.linkedin.com/in/daveblakey)向新堆栈解释说，Nova 是对客户以从未想过的方式使用现有 ADC 设备的回应。Kubernetes、云原生应用、微服务和超大规模架构的兴起导致了对能够在大规模环境下工作的高性能 ADC 的需求。

“由于情况发生了变化，我们发现我们的许多客户都在运行 200 或 300 台 Snapt 设备，这不是我们的初衷。部署和查看您的所有统计信息和数据变得很麻烦。由于微服务类型部署和多云等原因，人们需要如此之多的服务，它们正在不断增长，”Blakey 说。“让价值留在数据层面已经没有意义了。单一容器没有任何价值。”

Blakey 谈到了 Nova 与传统 ADC 的不同之处，它位于控制层，而不是数据层。对于数据层中的传统 ADC，配置和管理是基于每个器件或虚拟机进行的，这会抑制可扩展性和性能。相反，Project Nova 驻留在控制平面中，提供集中的编排并实现完全自动化，包括实例化、扩展和恢复。

Blakey 解释说，通过重新设计 ADC 的位置，Project Nova 可以位于应用架构的多个层中，既可以作为初始网关位于边缘，也可以位于 sidecar 部署中的各个微服务之中和之间。然后，Nova ADC 的单个实例向 Snapt 托管的单个管理面板报告，用户可以在其中管理配置并深入了解应用性能和统计数据。

[https://www.youtube.com/embed/oRe93Qfr-VI?feature=oembed](https://www.youtube.com/embed/oRe93Qfr-VI?feature=oembed)

视频

虽然 Project Nova 可能与服务网格有一些相似之处，但 Blakey 解释说，服务网格实际上是 ADC 的另一端。

“有趣的是，服务网格非常注重微服务之间的通信，它几乎提供了最少量功能的最低点。比如，当你不能拿走任何东西的时候，服务网几乎是完美的，而不是当你不能增加任何东西的时候。它试图变得非常高效、非常快速、非常有针对性，”Blakey 说。“但举个简单的例子，它们不提供任何应用程序防火墙，因此不包括针对 SQL 注入或拒绝服务攻击、漏洞扫描的保护，所有这类东西都不包括在内，而这就像是所有这些的单个视图，以及您边缘的附加功能。在流量真正进入网络的地方，我们将提供应用防火墙、缓存、内容加速，所有这些都是人们过去获得的传统 ADC 价值。”

目前，Project Nova 只接受邀请，但感兴趣的客户可以请求访问，社区版提供多达五个部署节点的免费访问。在发布时，Project Nova 提供了对 Kubernetes、Docker、Rancher、Consul 等上的本地服务发现的支持，以及使用 REST API 的全自动化。

Blakey 表示，他们预计 Project Nova 的测试版将于 11 月中旬推出，并于 12 月中旬与服务网格完全集成，“真正的想法是成为这种应用交付结构，它只是负责跨您运行的任何基础设施交付您的应用。”他说，预计将于 2020 年初全面上市。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>