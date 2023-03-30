# 谷歌为 Anthos 确定了 Kubernetes-Ready 存储

> 原文：<https://thenewstack.io/google-identifies-kubernetes-ready-storage-for-anthos/>

本周， [Google Cloud](https://cloud.google.com/) 扩展了 [Anthos 管理的 Kubernetes](https://cloud.google.com/anthos/) 功能集，增加了 [Anthos Ready Storage](https://cloud.google.com/partners/anthos-ready/) ，这是一种识别符合 Anthos 内部特定标准的存储合作伙伴的资格。迄今为止，获得批准的合作伙伴包括[戴尔 EMC](https://www.delltechnologies.com/en-us/index.htm) 、 [HPE](https://community.hpe.com/t5/Around-the-Storage-Block/HPE-Nimble-Storage-now-certified-for-Google-Anthos-Ready-Storage/ba-p/7079617?altcid=sm_C1200218#.XkyGC5NKh25) 、 [NetApp](https://blog.netapp.com/hybrid-kubernetes-workloads) 、 [Portworx](https://www.prnewswire.com/news-releases/portworx-joins-google-clouds-anthos-ready-storage-initiative-301005618.html) 、Pure Storage 和 Robin.io

“Anthos 为客户提供了一个‘一次编写，随处运行’的云平台，允许他们以一致的方式构建应用，这包括他们对存储解决方案的偏好，”谷歌产品经理 Manu Batra 写道。

在[博客文章](https://cloud.google.com/blog/topics/hybrid-cloud/announcing-the-anthos-ready-storage-qualification)中，Batra 确定了每个存储包必须满足的三个主要标准，以便与 Anthos on-prem 配合使用:

*   演示了 Kubernetes 的核心功能，包括通过开放和可移植的 Kubernetes 本地存储 API 动态供应卷。
*   经验证的跨集群纵向扩展和横向扩展场景自动管理存储的能力。
*   遵循 Kubernetes 实践的简化部署体验。

Batra 在一封电子邮件中进一步解释说，第一点谈到了 Anthos 对可移植性的核心承诺，写道“应用程序可移植性是 Anthos 的基石”，这是通过 Kubernetes 存储 API 和容器存储接口(CSI)实现的。它允许开发人员“为他们的应用程序编写一次部署 YAML，并将其部署在任何兼容的 Kubernetes 集群上。”至于可扩展性，Anthos GKE 本地集群能够动态扩展，并且该认证还确保存储系统能够妥善处理这一问题。

Batra 说，通过这些经认证的存储包，部署在 Anthos Google Kubernetes 引擎(GKE)上的工作负载可以轻松配置新的存储，并且无论工作负载计划在哪里，工作负载都可以使用该存储。Anthos 存储就绪容器存储接口(CSI)驱动程序将实现这种无缝集成。CSI 驱动程序的部署就像部署一个新的 Kubernetes 工作负载一样简单(CSI 驱动程序被打包为 Kubernetes 工作负载)。

去年 9 月，谷歌云[在其 Anthos 产品中增加了无服务器和服务网格](https://thenewstack.io/google-cloud-expands-its-managed-kubernetes-service-anthos-with-serverless-service-mesh/),

Batra 在电子邮件中解释说，从那时起，该公司已经在金融服务等高度监管的行业中采用了 Keybank 等客户，并在制造行业中采用了压缩空气产品和服务提供商 Kaeser Kompressoren 等客户。该公司还对零售领域感兴趣。

戴尔、NetApp 和 Portworx 是新堆栈的赞助商。

由 [Joshua Hoehne](https://unsplash.com/@mrthetrain?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/s/photos/storage?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的专题图片

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>