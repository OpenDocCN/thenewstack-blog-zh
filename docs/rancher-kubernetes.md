# 牧场主集装箱管理平台全靠 Kubernetes

> 原文：<https://thenewstack.io/rancher-kubernetes/>

过去，Kubernetes 供应商帮助客户建立集群就足够了，但现在已经不行了。Rancher 联合创始人兼首席执行官 [Sheng Liang](https://twitter.com/shengliang?lang=en) 表示，设置和运行开源编排引擎已经变得更加容易，供应商必须通过帮助客户更好地管理他们的集群来寻找增加价值的方法。

该公司刚刚公布了 Rancher 2.0 集装箱管理平台的[技术预览](https://rancher.com/)，该平台将于明年年初正式发布。[牧场主](http://rancher.com)以前使用自己的[管弦乐](https://thenewstack.io/unleash-cattle-rancher-container-platform-reaches-general-availability/)，称为“牛”,并支持其他管弦乐队，但自那以后已经全力以赴将 [Kubernetes](/category/kubernetes/) 作为市场领导者。

在 2.0 中，该公司宣传其管理任何 Kubernetes 集群的能力，不管它们来自哪里。

“有了 2.0，我们真的需要像过去几年那样，从一个安装、管理和升级的工具成长起来，”梁说。

“我们的许多客户拥有所有这些 Kubernetes 集群，但他们没有理想的同构、谷歌范围的设置。他们需要一个工具来控制访问——哪个团队，哪个项目，哪个应用程序在什么上，”他说。

“他们需要一架中央控制飞机。他们需要处理不同类型的基础设施。很多时候，这些 Kubernetes 设置就像一片小雪花:它有自己的监控配置，自己的一套网络驱动程序。因此，他们需要一种通用的方式来理解这一切，一种通用的方式来聚合日志。”

他说，一些客户希望在云和本地 Kubernetes 部署中一切都完全相同，Rancher 可以满足这一要求。

使用 2.0，用户可以设置自己的主机，或者从 Google Container Engine、Azure、Bluemix、Ubuntu、Kops 或其他地方导入集群。

它提供了一个重新设计的用户界面，“完全基于 Kubernetes 之上”，[联合创始人兼工程副总裁 Chan](https://www.linkedin.com/in/will-chan-630ba4/) 在一个视频中解释道。他谈到以前的版本时说:“我们对它上线运行后如何与 UI GUX 的其他部分相结合感到不满意。”

https://vimeo.com/235444669

他说，有了 2.0，用户就可以获得以牧场主 UX 为基础的原生 Kubernetes，包括 CLI、UI、API 和 Docker Compose。

其他新功能:

*   管理所有集群的单一控制平台，包括集中式身份验证、访问控制、监控、运行状况检查以及其他了解和控制集群的方式。
*   通过模板添加主机的能力，减少了运行 Kubernetes 集群所需的资源。每次您从 Rancher UI 添加主机时，它都会被自动保存，以便在您想要添加更多主机时可以重复使用。
*   一个更新的应用程序目录，包括 100 多个社区贡献和牧场主认证的 Docker Compose 应用程序模板以及 Kubernetes 模板、 [Helm charts](http://blog.kubernetes.io/2016/10/helm-charts-making-it-simple-to-package-and-deploy-apps-on-kubernetes.html) 和 YAML 文件。Rancher 已经完成了确保这些应用程序良好扩展的工作，因此用户不必从头开始构建一切。

用户界面中的新功能包括:

*   从 execute shell 选项卡，您可以调整 shell 的大小，Chan 称之为最常见的特性之一。
*   多选—您可以选择多个容器并启动/停止它们。
*   过滤器。
*   改进的搜索，包括应用程序目录中的增强搜索。
*   回滚，包括回滚到前一版本之外的功能。

借助集群管理功能，它将集群定义为一组物理或虚拟计算资源，将环境定义为一个命名空间，在其中定义应用程序、服务和容器，并在其中启动容器。现在，多个环境可以共享相同的物理资源。

Chan 说，更多的功能正在计划中，包括改进的卷管理和基于角色的访问控制。

目前，该公司敦促客户将 1.6 版本用于生产工作负载，但要尝试即将到来的升级。

管理 Kubernetes 的[云本地计算基金会](https://www.cncf.io/)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>