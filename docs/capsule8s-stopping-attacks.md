# 胶囊 8 是关于实时阻止攻击的

> 原文：<https://thenewstack.io/capsule8s-stopping-attacks/>

在众多关注网络、应用程序、容器甚至 API 调用的安全方法中，[致力于在攻击发生时阻止攻击。它可以实时自动响应，并为以后的手动调查提供深入的可见性。](https://capsule8.com/)

联合创始人兼首席技术官[迪诺·戴·佐维](https://www.linkedin.com/in/dinodaizovi/)说:“这是模仿谷歌、亚马逊和网飞这样的大公司在内部做安全工作的方式。

“就像 GIFEE(Google infra structure for everybody)一样，Kubernetes 正在为其他所有人带来这种类型的基础设施，我们正在为其他所有人构建在这些环境中构建的安全方法。”

它从位于每个节点上的轻型传感器开始。无论您是在虚拟化中运行还是在虚拟机管理程序上运行，它都能够检测到针对该主机的攻击。这使用 Linux 内核的内置机制来收集高速遥测数据。根据 Dai Zovi 的说法，这是一个用 Go 编写的静态二进制文件，在一个加载的系统上，它会给你的工作负载带来 1%到 2%的开销。

胶囊 8 飞行记录器与这些传感器一起运行，在本地记录遥测事件，可用于以后的取证。关键事件数据被流式传输到分布式实时分析引擎，该引擎专注于检测正在进行的攻击的证据。

“它完全在您的环境中运行，没有 SaaS 组件，无论是在内部还是在云中，都不会向我们发回任何东西，”他说。“这个模型变得更加智能。你得到的不是更多的干草来找针，而是一块磁铁。”

Capsule8 Protect 的分析涵盖网络、系统和应用程序级数据。

Capsule8 背板是一个用 Go 编写的实时消息总线，它连接所有部署在任何地方的传感器，以流式传输请求的实时事件以及来自飞行记录器的历史事件。背板确保网络不会被胶囊 8 遥测事件淹没。

“构建分布式系统的挑战之一是以安全的方式管理高吞吐量事件(以提供)高速度、低延迟和弹性。…Kafka 之类的替代产品——通常 JVM 上的任何东西都需要大量的调整，用容器运行(JVM)会带来其他复杂性——我们确保避开所有这些，但仍能获得与 Kafka 相同的系统设计优势，”他说。

当 Capsule8 在无状态工作负载中检测到可疑活动时，它使用“先拍摄，后提问”的方法，自动冻结任何受感染的组件并替换它。对于有状态的工作负载，Capsule8 可以立即向响应者发出警报和/或隔离组件，以防止可能的攻击。据该公司称，这两种情况都不会影响性能。

“当我们有迹象表明一个容器已经被破坏，无论这是一个主动攻击还是来自一个后台来源，如从您环境中运行的上游开源组件引入，或者开发人员是否做了一些事情，如将某种远程访问外壳放入他们在生产中运行的容器，以便他们可以直接进入该系统，而不经过正常的检查——我们可以在实时流中检测到所有这些，”他说。

系统可以重启容器内的一个进程，重启整个容器，或者进行 orchestrator 级别的重启。他演示了针对 Kubernetes 中运行的容器的攻击，以说明一些安全问题。

[https://www.youtube.com/embed/9vuUr5UWKO0?feature=oembed](https://www.youtube.com/embed/9vuUr5UWKO0?feature=oembed)

视频

无论客户是希望与工具(包括 SIEMs、流程编排工具、Splunk、Slack 或大数据存储)集成，还是将其与自己的安全实践相结合，Capsule8 都使用其所谓的封装器作为系统扩展机制。通过封装器，组织可以获得跨集群的实时可见性以及查询飞行记录器数据的能力。

Capsule8 API 服务器为管理数据提供了一致的界面。

gRPC API 服务器还包括一个 HTTP/JSON 网关，可以轻松测试和支持没有 gRPC 支持的语言。它的控制台提供了一个特定于 Capsule8 的仪表板和过滤功能。

它运行在托管的 Linux 上，支持 Kubernetes 和裸机安装，这些安装不是精心安排的，甚至不使用容器，独立于云提供商或内部。

这家总部位于纽约布鲁克林的公司成立于 2016 年秋季。它在 7 月推出了测试版的 Protect。它在 9 月宣布了一轮 600 万美元的融资，使总融资额超过 850 万美元。

集装箱安全技术市场是一个越来越拥挤的空间，有多家供应商，包括 [Twistlock](https://thenewstack.io/creating-automated-model-container-security/) 、 [Aqua Security](https://thenewstack.io/manifesto-aqua-securitys-new-open-source-container-metadata-tool/) 和 [NeuVector](https://thenewstack.io/container-security-vendor-neuvector-zeroes-network/) ，尽管戴·佐维称 [Stackrox](https://thenewstack.io/stackrox-zeros-container-security/) 是该公司最接近的竞争对手。

它在攻击中断方面有别于代码分析和配置管理。

“强化(修复漏洞和安全配置)对于安全性来说是必要的，但还不够。定制代码中存在漏洞，公司的整个基础架构都有过时的软件，……但更重要的是检测和阻止攻击。其他一切都支持这一点。这是我们认为人们应该开始的地方，”他说。

Aqua Security、Stackrox 和 Twistlock 是新堆栈的赞助商。

特征图片:[马蒂亚斯瑞普](https://www.flickr.com/photos/56218409@N03/)的[红灯](https://www.flickr.com/photos/56218409@N03/16273496076/in/photolist-qN2Vqy-XwyKYj-meV2Ni-Xbs1uW-ag4zkN-P5JJA-eikynP-frFjs-nk9E5P-5SoAgm-6aGtU5-8NyMdA-8e8o2n-2gTUrj-5v6BJj-o4dtkv-9tzm43-6npsuU-2Z85kc-RL71v7-8vhVbv-ny9DwV-QzU8aD-f2oZSp-djE8k9-qppmLd)，在 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>