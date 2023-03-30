# Kubernetes 能协调基础设施吗？

> 原文：<https://thenewstack.io/can-kubernetes-orchestrate-the-infrastructure/>

在 Kubernetes 上管理有状态的应用程序会比处理容器最初设计的无状态应用程序更容易吗？ [Portworx](http://www.portworx.com) 的首席执行官 Murli Thirumale 说，这是顾客告诉他的。

当谈到鼓励在企业环境中的生产中采用 Kubernetes 时，这是一个好消息，但不是每个人都会同意的。在最近由 [The New Stack](https://thenewstack.io/ux-is-kubernetes-biggest-short-term-challenge/) 进行的民意调查中，10%的受访者认为改善 Kubernetes 与存储的集成是社区面临的最大挑战，仅次于对用户体验和多租户支持的担忧。

但是 Thirumale 并不是唯一一个认为 Kubernetes 生态系统已经为有状态工作负载做好准备的人。华为 Futurewei Technologies 的技术副总裁 [Quinton Hoole](https://www.linkedin.com/in/quintonhoole/) 在最近一期的 [The New Stack Makers 播客](https://thenewstack.io/how-storage-and-databases-can-catch-up-with-kubernetes/)中表示:“人们开始在云和 Kubernetes 中执行严重的有状态工作负载。

[存储和数据库如何赶上 Kubernetes](https://thenewstack.simplecast.com/episodes/how-storage-and-databases-can-catch-up-with-kubernetes)

收听更多剧集，订阅[simple cast](https://thenewstack.simplecast.com/)|[fireside . FM](https://thenewstackmakers.fireside.fm/)|[Pocket Casts](https://pca.st:443/6Ltf)|[Stitcher](https://www.stitcher.com/podcast/the-new-stack-makers)|[苹果播客](https://apple.co/2Dj1tv8) | [阴天](https://overcast.fm/itunes915443155/the-new-stack-makers)|[Spotify](https://spoti.fi/2DYrLEf)|[tune in](https://tunein.com/podcasts/Technology-Podcasts/The-New-Stack-Makers-p989517/)

事实上，Portworx 的许多客户在 KubeCon 谈论他们使用 Kubernetes 管理数据丰富的应用程序的方式，通常规模令人难以置信。Kubernetes 正被用于管理来自边缘设备的数据馈送的实时数据分析，为全球 100 万名学生提供免费的计算机科学课程，并帮助拥有数千个传统应用程序的老牌公司在云和内部实现现代化。

“我认为 Kubernetes 将从管理应用程序转向管理基础设施，如存储，”Thirumale 说。“我认为，2020 年是 Kubernetes 成为数据中心和云的新控制计划的开始，它将向上管理应用程序，向下管理基础架构。”

未来会是什么样子？

## 实时大数据分析

ESRI 的地理空间绘图应用程序为客户提供了一种处理来自边缘设备的数据并翻译其可视化仪表板(通常是地图)的方法。ESRI 的物联网平台从客户在田间使用的传感器和其他边缘设备中获取数据——有时实际上是在田间，用于农业用途，但它也用于机场、天气和其他环境监测、执法和数十种其他用例。

ESRI 实时和大数据 GIS 能力主管 [Adam Mollenkopf](https://www.linkedin.com/in/adammollenkopf/) 解释说:“我们使用 Portworx 的应用程序使客户能够将传感器连接到他们的 GIS 应用程序，这样他们就可以看到数据在移动，并从现场的传感器中实时看到发生了什么。

在开发这个 SaaS 平台之前，ESRI 帮助公司建立了一个内部场所，从物联网设备进行实时数据分析。Mollenkopf 说，虽然客户普遍对该系统感到满意，但它的安装成本也非常高，这促使 ESRI 寻找一种方法，以基于云的 SaaS 格式提供相同的功能，以便更多的客户可以访问。

ESRI 的应用程序名为 ArcGIS 管理控制台，位于热门数据存储之上，提供流数据分析和大数据分析。当提要进来时(提要的类型取决于数据源，有 50 多种不同的类型)，它们被写入 Kafka 集群。ArcGIS 随后使用 Spark 进行实时分析，然后写入 Eslasticsearch 数据库。

这种堆栈显然涉及一系列有状态的服务，所有这些服务都通过 Portworx 的开源 STORK(Kubernetes 的存储编排)连接到 AKS，并连接到 Portworx 的数据平台，以确保高可用性和灾难恢复，以及管理所有数据加密。

此外，ESRI 使用 [Portworx 的 Autopilot](/portworx-autopilot-wants-to-cut-cloud-storage-costs-with-automated-capacity-planning/) 根据预先确定的规则自动调整永久卷声明、磁盘和池的大小。这确保了在调配额外存储时不会停机，同时消除了手动调配卷的需要。

## 免费教一百万学生

对于分布在全球各地的 30，000 名同时在线的用户，你如何运行一门需要 24 小时不间断运行的在线计算机科学课程？哈佛的 CS50 课程在剑桥的校园里有大约 1000 名学生，在网上有 100 万注册学生。该课程自 1989 年开始运行，并于 2015 年转移到基于云的 IDE。即使将 AWS Cloud9 与 EC2 实例和 EBS 一起直接用于存储，也存在一些挑战，尤其是(但不仅限于)与成本相关的挑战。

“我们必须为每个用户分配一个 EC2 实例和一个 EBS 卷，”哈佛大学软件工程师[卡里姆·齐达内](https://www.linkedin.com/in/kzidane1/)解释道。“我们还必须为每个用户分配一个可用性区域，这意味着如果有一个实例可用，但它位于不同的可用性区域，我们就无法使用它。”对于一个拥有一百万用户的免费课程来说，这显然产生了一个成本问题。

将 CS50 应用程序迁移到 Kubernetes 解决了许多与管理计算资源相关的问题，而不是为每个用户分配一个 EC2 实例，每个学生都将获得一个容器，该容器会在他们活动时启动，并在他们结束时自动终止。Kubernetes 每次都会包装多个容器。Kubernetes 能够抽象出运行容器所需的大部分管理，但没有解决存储挑战。有了 Portworx 和 Kubernetes，Harvard 可以精简地配置存储和计算，由 Kubernetes 处理 EC2 实例，Portworx 管理 EBS 卷。

从最终用户的角度来看，Portworx 解决了一些额外的棘手问题。上传和下载既慢又脆弱，但是使用 Portworx 卷解决了这个问题。此外，Portworx 会自动将学生的作业推送到 GitHub，因此如果一个 pod 出现故障，也不会丢失任何作业。

## 传统应用的现代化

诚然，ESRI 是一家科技公司，哈佛的 CS50 是由计算机科学家运营的。在一个领导者不太懂技术的公司里，将 Kubernetes 用于有状态服务会是什么样子？

福特汽车公司的技术专家萨迪什·普拉纳姆在 [theCUBE](https://www.youtube.com/watch?v=8ztM8Z9Pobw) 上解释道:“云原生是伟大的，但云原生在某处有状态。“我们能用 Kubernetes 做到这一点吗？我认为我们做得相当不错。我们生产中有相当多的工作负载是有状态的。”这些包括数据通信应用程序和数据库。

像许多公司一样，福特开始了数字化转型之旅，努力降低成本，提高应用交付速度。Puranam 说，全新的应用程序都被编写为云原生的，包括那些需要有状态的应用程序。不过，很明显，福特也有遗留应用要考虑——成千上万的遗留应用，其中许多都是普拉纳姆所说的“桌面应用”随着福特努力偿还其技术债务，将这些应用程序转移到 Kubernetes，包括那些需要存储的应用程序，是该公司的技术优先事项之一。

“这个想法是越来越重的工作负载将登陆 Kubernetes，”Puranam 说。“这是我们在 2020 年要关注的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>