# D2iQ，前身是 Mesosphere，为 Kubernetes 带来了企业管理

> 原文：<https://thenewstack.io/d2iq-formerly-mesosphere-brings-enterprise-management-to-kubernetes/>

Mesosphere 更名为 D2iQ，反映了将云功能引入企业的新战略。

D2iQ 战略包括一个新的 Kubernetes 产品类别，称为 Konvoy，旨在帮助组织快速启动 Kubernetes，并在他们成长时提供支持。该公司还将提供对云原生数据服务的支持，如 Kafka，Cassandra 和 Spark，[在一个名为 Datasphere](https://d2iq.com/solutions/datasphere) 的包中。它将继续支持基于 Mesosphere 的[数据中心操作系统](https://d2iq.com/solutions/mesosphere) (DC/OS)的 Apache Mesos 的大规模生产部署，该操作系统保留了 Mesosphere 的名称。

“我们研究了我们的客户在他们的云原生之旅中处于什么位置。他们来得很早。D2iQ 联合创始人兼首席技术官[鸢·克纳普](https://github.com/guenter)说:“他们仍然需要很多帮助来学习云原生技术。

“他们需要帮助规划他们的第一个项目，选择正确的技术。Knaup 说:“随着他们的成熟和增加更复杂的工作负载，例如 Kafka 或 Cassandra，以及他们扩大部署和运行许多 Kubernetes 集群，他们在此过程中会有不同的需求-他们需要部署、培训和支持的技术。Konvoy 采用[中间层 Kubernetes 引擎(MKE)](https://d2iq.com/blog/introducing-d2iq-kubernetes-engine-mke) 来管理多个 Kubernetes 集群。

“这不仅仅是你在第一天安装的一个产品，然后你必须解决其余的问题。我们着眼于整个体验，”Knaup 说。

## Kubernetes 只需一个命令即可升级

Konvoy 的核心包括普通的 Kubernetes 以及用于联网的印花棉布； [Traefik](https://traefik.io/) 为入口；使用 [Prometheus](https://prometheus.io/) 、 [Grafana](https://github.com/grafana/grafana) 和 [Telegraf 进行监控和度量；使用](https://wiki.archlinux.org/index.php/Telegraf) [Fluent Bit](https://fluentbit.io/) 、 [Elasticsearch](https://www.elastic.co/products/elasticsearch) 和 [Kibana](https://www.elastic.co/products/kibana) 进行测井；和 [Velero](https://github.com/heptio/velero) 来备份和恢复 Kubernetes 集群资源和持久卷。该公司还宣布了一款名为 Kommander 的新产品，该产品被称为管理 Kubernetes 集群的单一控制台。

Knaup 说，对于组织来说，很难对云原生环境中的所有技术进行分类，所以 Konvoy 为他们做了这件事。

“我们希望这是企业级的和生产就绪的，所以我们不只是提供安装了这些软件包的群集，我们还使用最佳实践来配置它们。…这已经完成，也是 Konvoy 的一部分。您可以获得预配置的仪表板，允许您跟踪 kubelet、pods 和堆栈的任何组件的指标，”他解释道。

[https://www.youtube.com/embed/6vDRpWs7j6Y?feature=oembed](https://www.youtube.com/embed/6vDRpWs7j6Y?feature=oembed)

视频

如果你运行在云上，你使用一个单一的命令，“Konvoy up”，它使用 [Terraform](https://www.terraform.io/) 来提供实例，Red Hat 的 [Ansible](https://www.ansible.com/) 来安装 Kubernetes、Calico 和集群上的其他组件。

如果你在本地运行，基本上你提供一个机器列表，Ansible 就会接管并安装 Konvoy。

Knaup 表示，“第 2 天”支持(该公司新名称中的“D2”是指“T1”)包括该公司的生命周期管理功能，只需一个命令就能实现升级。Knaup 提到了 Kubernetes 的[安全问题，该问题在去年 12 月，也就是 KubeCon 在西雅图召开的前几天进行了审查。](/critical-vulnerability-allows-kubernetes-node-hacking/)

“我问 KubeCon 的人他们是如何处理安全问题的，他们是如何升级的。Knaup 说:“与我交谈过的每个人——非中间层客户——基本上都告诉我，他们的最后一周简直是地狱。“他们发现了所有这些他们甚至不知道正在运行的群集，这些群集都是使用不同的工具集部署的，不是以一致的方式，所以他们不得不通宵达旦地升级所有这些群集来解决安全问题。”

借助 D2iQ 的 Ksphere，只需一个命令即可完成修复。“我们在不到 24 小时内解决了一个问题，我们的客户只需一个命令就可以升级到新版本。我们在幕后处理所有的流程编排，以便在不中断集群的情况下实现这一点。这是我们为第 2 天运营所做的一个很好的例子:可升级性、故障恢复、扩展和缩减。我们已经在 DC 操作系统上做了很多年了，”他说。

该公司还推出了一个名为 [KUDO](https://kudo.dev) 的开源项目，这是一个基于 DC/OS 之上的最佳实践和经验教训的工具包，旨在使构建和管理 Kubernetes 运营商变得更加容易。它已经发布了一个由工藤建造的卡夫卡操作系统。

红帽是新堆栈的赞助商。

特写图片:[芭芭拉·迪厄](https://www.flickr.com/photos/bee/)的[集群](https://www.flickr.com/photos/bee/10723023/in/photolist-WXzH-keBjz-22xsqFC-4XXkgq-nNDsW3-dAnS5B-3hUrc1-8CKHs6-a9Q14a-5Andiq-MFCrW-h9meKz-48nGqw-7kKJ2m-acpWWY-4g7oxv-c5uqcu-6cbqJg-p7ShS2-eeUXbP-6tm8wB-4HK9S-a6peF-6k5uqt-7GbJNx-7bp765-dyHF31-51xjjt-5DF31-crLdjy-pkmgmZ-6Tv5iP-kL1Zt-6u3uH-zfqCm-ckaksL-7wpNZ-7wCXja-6tm8oz-2ahx2pG-bWWBVD-ZBENMj-EpWW7-EpNEZ-a6pb5-GafEKQ-ainfW-bnhkWw-4JQYkJ-2ecA1VF)。根据 CC BY-SA 2.0 获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>