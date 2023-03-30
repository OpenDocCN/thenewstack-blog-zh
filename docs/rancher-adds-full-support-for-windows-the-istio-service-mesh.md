# Rancher 增加了对 Windows、Istio 服务网格的全面支持

> 原文：<https://thenewstack.io/rancher-adds-full-support-for-windows-the-istio-service-mesh/>

Rancher Labs 的 Kubernetes 平台的最新版本 Rancher 2.3 增加了对 Windows 容器、Istio 服务网格集成以及用于大规模部署 Kubernetes 的集群模板的支持。

三月份，[对 Windows](https://kubernetes.io/blog/2019/04/01/kubernetes-v1.14-delivers-production-level-support-for-windows-nodes-and-windows-containers/) 的容器支持在 Kubernetes v1.14 中宣布稳定，为供应商管理基于 Windows 的 Kubernetes 应用程序打开了大门。

在 Rancher 的声明中，[微软容器平台首席项目经理 Taylor Brown](https://www.linkedin.com/in/taylorbro/) 称赞 Rancher 是第一批将其产品推向市场的公司之一。

据 IDC 的研究主管 [Sriram Subramanian](https://www.linkedin.com/in/sriramhere/) 称，它实现了 Rancher 的使命，使用户能够在任何地方运行 Kubernetes。

“组织正在 Kubernetes 上实现标准化，随着更多基于 Windows 的工作负载实现现代化，拥有一个专门针对 Kubernetes 的容器管理平台，同时为 Windows 提供支持是关键，”他说。

多家公司已经在测试版中支持 Kubernetes 上的 Windows，但 Rancher Labs 吹嘘自己是第一个发布企业级支持的公司。

微软和 Rancher Labs 将在 Windows 和 Kubernetes 上开展一系列活动，Rancher 的首席营销官 Peter Smails 表示。

Windows 上的 Kubernetes [文档](https://kubernetes.io/docs/setup/production-environment/windows/intro-windows-in-kubernetes/)指出了一些限制。其中:它仅适用于 Windows Server 2019，Windows 仅支持作为工作节点，这意味着用户仍然必须使用 Linux 主节点。

联合创始人兼首席执行官[盛亮](https://twitter.com/shengliang?lang=en)说:“我实际上不认为这是可取的，这就是 Windows 今天的现状。”他补充说，该公司正在积极努力消除这一限制。

“只是现在有一种被压抑的需求。Windows 对 Kubernetes 的支持已经以某种形式存在了将近三年。我认为最初，每个人都非常非常兴奋。很明显它还没准备好。….我觉得现在终于是时候将它实际应用到任务关键型企业生产中了。…我认为会有足够多的 Windows 商店不介意安装几个 Linux 节点。”

Rancher 2.3 还引入了集群模板，使组织能够在其整个基础架构中实施一致的集群配置。借助这些模板，运营商可以在其所有集群部署中创建和重用经过充分测试的 Kubernetes 配置。这也是消除配置偏差或错误配置的一种方式，随着更多集群的创建，这些偏差或错误配置可能会带来安全风险。

新版本还包括与 Istio 服务网格的更紧密集成。据梁说，虽然 Istio 在业内引起了相当大的轰动，但采用率并不高，那些试图使用它的客户一直在苦苦挣扎。Rancher 在其 [Rio 项目](https://thenewstack.io/rancher-rio-taking-care-of-the-first-half-of-the-developers-day/)中支持 Istio 和其他服务网格，但这种集成专注于使 Istio 更易于使用。

期待在 11 月的[kube con+CloudNativeCom 2019](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/)上听到更多关于里约的消息。

特征图片:[Smabs Sputzer(1956-2017)](https://www.flickr.com/photos/10413717@N08/)[竖窗](https://www.flickr.com/photos/10413717@N08/9255897859/in/photolist-f6UTXR-aBPnve-aMcbg8-S19haz-9v5yx4-4MdRZB-8PvUef-8HWdpv-fmjY3-Tvbjdh-48GYPV-dG8EhN-8X3NwD-73s2pQ-9tUEEs-sYxVT-dohhNV-dewjmk-e6BSds-o6uvxg-RBm2o-UBZGum-q8HbfM-86uuWz-WGGTS-8B4qg8-7tCN2c-2aaXyfW-oVWvEs-kRvX1-22xfPEP-4TsQYe-8C2tdL-ptkxgE-8vf2Rm-oeXmPo-8PqWuD-2Nsnxp-4qUa32-aCRgU-W6L2yW-ccY4sC-7ViQPg-TpjsaM-25iN9Bw-62Lcis-df9N9o-dYz4nb-4TtBpB-bY1UtG)。根据 CC BY-SA 2.0 获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>