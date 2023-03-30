# Rancher 支持跨多个 Kubernetes 集群运行应用程序

> 原文：<https://thenewstack.io/rancher-supports-running-apps-across-multiple-kubernetes-clusters/>

继去年 12 月发布对多集群、多租户监控工具 [Prometheus](https://prometheus.io/) 的支持之后，Rancher Labs 发布了针对 Kubernetes 上运行的应用的多集群管理软件。

“一旦我们的客户开始部署多个集群，非常有趣的新需求就开始出现了，”[盛亮](https://www.linkedin.com/in/shengliang/)、 [牧场主](https://rancher.com/)联合创始人兼首席执行官说道。

“我认为在未来，组织将不仅仅是建立一个巨大的 Kubernetes 集群，”梁写道。“他们为少量应用程序甚至一个团队创建一个集群。有时他们会为单个应用程序创建一个集群。如果他们在许多集群上运行一个应用程序，那么集群甚至可能比应用程序还多。Kubernetes 在这方面非常灵活。”

该公司指出了两种需要应用程序跨越多个集群的场景:

*   跨多个可用性区域部署时需要更高容错能力的应用程序。
*   边缘计算，可能涉及在数百个集群上运行的单个应用程序。

当你部署 Kubernetes 时，你希望使用 Kubernetes 使应用程序可靠，梁指出。虽然一些公共云允许跨多个可用性区域传播应用程序，但这并不理想。

他指出:“无论你是运行自己的 Kubernetes，还是依赖某个云提供商，在这些可用性区域和你的应用程序之间拥有这一相当复杂的软件技术层，实际上本身就成为了一个单点故障。”“如果我升级 Kubernetes 会怎么样？软件有 bug 怎么办？不管是什么原因，主节点崩溃了，这会影响应用程序。在 Kubernetes 中部署这种复杂的编排层总会有这种程度的不适。

“因此，人们开始在不同的可用性区域部署独立的集群。因此，如果软件出现故障或区域出现故障，不会影响到其他软件。

但是有多个集群需要管理。但是您不希望分别管理这两个集群。Rancher 的 [Ankur Agarwal](https://www.linkedin.com/in/ankur11/) 在一篇[博客文章](https://rancher.com/blog/2019/introducing-multi-cluster-apps/)中指出，在每个集群上手动维护应用既耗时又容易出错。

使用此多集群应用程序功能，您可以指定一次:此应用程序将转到这些集群。它在这些集群中的配置可能略有不同，但在一个镜头中，它们由 Rancher 部署和管理。

在将于三月底正式发布的 Rancher 2.2 中，您创建了一个掌舵图，然后您可以在大量集群中部署它。多集群应用程序使用运行在 Rancher 管理平面中的 Kubernetes 控制器来获取舵图并将应用程序部署到每个目标集群。然后，升级、回滚和维护都可以一次完成。

自动化网络运营管理供应商 B-Yond INFINITY 在电信环境中使用多集群功能来实现高可用性。

“这有利于生命周期管理和我们在 5G 边缘云中看到的边缘部署。有了 Rancher 2.2，我们现在可以完全自动化流程，并与我们的生命周期管理流程相集成，减少时间和风险，同时保持符合电信级要求，”其首席产品官 [Rikard Kjellberg](https://www.linkedin.com/in/rikardkjellberg/) 说。

虽然 Kubernetes 中有[本地集群管理特性](https://www.altoros.com/blog/managing-multi-cluster-workloads-with-google-kubernetes-engine/)并且也可以使用 [Istio](https://istio.io/docs/setup/kubernetes/multicluster-install/) 服务网格，但 [Mirantis](https://www.mirantis.com/blog/kqueen-open-source-multi-cloud-k8s-cluster-manager/) 也一直在通过其 [KQueen](https://github.com/Mirantis/kqueen) 项目解决这个难题。

Rancher Labs 的重点和即将推出的功能集中在使 Kubernetes 更容易为不精通它的人使用。

“他们应该只关心他们的应用程序的部署，”梁说。“我们想知道人们喜欢使用什么样的界面，但也不想让它太抽象，以至于人们不能用它做任何有用的事情。”

11 月，该公司宣布将其 Kubernetes 平台的可用性扩展到中国三大云提供商。它还与 Arm 合作，将 Kubernetes 管理引入运行在边缘和低功耗数据中心节点上的集群。

在 12 月的一集[中，新堆栈制造商](https://thenewstack.io/how-rancher-discovered-the-kubernetes-vulnerability/)，[联合创始人兼销售副总裁香农·威廉姆斯](https://www.linkedin.com/in/smw355/)谈到了该公司如何发现最近的 Kubernetes 漏洞( [CVE-2018-1002105](https://github.com/kubernetes/kubernetes/issues/71411) )。

特征图片:[倍数](https://www.flickr.com/photos/uniform-studio/4668959508/in/photolist-87zCZS-ZjyuGr-48aftj-GJm7ea-5gSa5n-ZzGTib-f2FZG3-21EVoNZ-7zApoT-VXUPVq-oKmopN-ZjywvX-fTvxnB-9xE2Ar-dTAm15-5ntBKD-bm7tY5-ppMfaa-bzLMQv-UXVve2-q72qdf-WUtQPN-jbian-VUEFHh-JD2DuY-Xc5QRi-ZjxZui-ZzGsPw-A2KEyC-oCpfcU-4zczN1-WYJBc3-21C6SRb-9cWVtz-X2C6A2-ZzGQEW-ZzHb71-Xewb3T-4WYaAZ-GJkDp8-XaSMc5-4qqaUG-GJkGL8-GJkJpi-pb3qrx-4qqarb-VXUFW9-59oprN-X2CaqM-MB9kJu)作者[玛莎 W 麦奎德](https://www.flickr.com/photos/uniform-studio/)。根据 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>