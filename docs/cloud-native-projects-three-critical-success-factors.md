# 云原生项目:3 个关键成功因素

> 原文：<https://thenewstack.io/cloud-native-projects-three-critical-success-factors/>

[甲骨文](https://www.oracle.com/cloud-native/)赞助了这篇帖子。

根据最新的[云原生计算基金会调查](https://www.cncf.io/blog/2018/08/29/cncf-survey-use-of-cloud-native-technologies-in-production-has-grown-over-200-percent/)，云原生技术的生产使用年增长率超过 200%。事实上，人们对 Kubernetes 和 Docker 等技术的兴趣如此之高，以至于预计圣地亚哥的 [KubeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 活动将有 8000 多人参加。

云原生应用可以提高开发人员/开发人员的效率、可扩展性和可移植性，但是我们如何评估公共云的这些能力呢？这篇文章将详细介绍云原生项目的三个关键成功因素。

## 关注开发人员的效率

 [阿克谢·帕萨拉西

Akshai Parthasarathy 是 Oracle 的一名产品营销人员，专注于云原生服务。在过去的十年里，他一直在涉足企业软件和云计算。在此之前，他在佐治亚理工学院攻读学士和硕士学位。](https://twitter.com/akshai) 

云原生服务应该让开发人员的生活更轻松。如果计划和实施正确，组织应该使用:

*   容器来提供更好的环境一致性、更快的部署、可移植性和可伸缩性。
*   微服务使不同的团队能够同时构建和测试应用程序的不同部分，从而加速软件开发。
*   持续集成允许开发人员快速迭代软件构建。
*   将基础架构作为代码，以减少部署服务器、存储和网络所需的时间。
*   无服务器功能可自动执行重复性任务，例如为开发/测试环境创建和填充数据库。
*   流式处理，实时接收来自设备和 web 应用程序的数据流，以实现快速分析。

然而，并不是所有的 DevOps 和 IT 团队都有时间和技能来为容器、微服务、持续集成、基础设施即代码、无服务器功能等部署和维护各种平台。通过使用托管服务，这些组织可以利用公共云供应商的能力来部署、修补和升级这些云原生平台，从而使开发人员能够更快地开发和迭代。考虑这些例子:

*   一家基于人工智能的初创公司通过消除 Linux、Kubernetes、Docker Registry 和持续集成系统的配置和管理，将部署时间缩短了 14 倍。
*   一家大型金融服务组织通过使用基于微服务的架构和并行开发，满足了合规性的关键期限。
*   软件即服务供应商通过使用容器化的应用程序消除了不需要的系统并简化了管理。

## 规划可扩展性

选择一个云平台，该平台提供或即将提供对您想要的位置附近的数据中心的访问。如果你预计在世界上新的地区会有增长，寻找那些也能支持你在这些地区增长的供应商。

缩放可能涉及使用多云环境。[甲骨文和微软的合作关系](https://www.oracle.com/cloud/oci-azure.html)提供了一个“互联云”,供您在这两家公共云供应商之间部署云原生应用时选择。要考虑的混合云产品包括[微软 Azure 和 VMware](https://azure.microsoft.com/en-us/overview/azure-vmware/) 、[甲骨文云和 VMware](https://www.oracle.com/cloud/vmware/) 以及[谷歌云和 VMware](https://cloud.google.com/vmware/) 。

关于运行容器，客户可以计划使用裸机(BM)主机、基于虚拟机(VM)的主机或两者进行扩展。虽然所有供应商都提供虚拟机来运行您的微服务和容器化应用程序，但只有少数供应商，如 [Amazon Web Services](https://aws.amazon.com/about-aws/whats-new/2019/02/introducing-five-new-amazon-ec2-bare-metal-instances/) 和 [Oracle Cloud](https://www.oracle.com/cloud/compute/bare-metal.html) ，提供运行裸机 Kubernetes 主机的能力。裸机主机是单租户的，服务器上的资源不与其他租户的工作负载共享，这使得它们非常适合具有高 CPU 和内存需求的应用程序。它们还有助于满足不允许使用共享资源的严格法规和合规性要求。然而，虚拟机提供了其他优势，例如通过使用可共享的映像更容易打包和管理，以及更简单的版本控制(快照)和回滚。

## 便携性设计

对于 Kubernetes 来说，可以考虑选择一个云解决方案，它运行未经修改的开源代码，这些代码由云本地计算基金会认证符合。当您试图将 Kubernetes 工作负载扩展到本地部署和其他云时，使用不一致和修改/分叉的代码会造成障碍。

对于无服务器功能、基础设施(如代码、流、遥测和相关的“管理”服务),可以考虑使用开源项目或遵守行业公认标准的供应商。例如，利用基于开源的项目，如 [Fn 项目](https://fnproject.io/)和 [OpenFaaS](https://docs.openfaas.com/) ，使您能够更轻松地在公共云和内部环境上运行这些功能:这些平台可以部署在笔记本电脑、私有云或公共云上。如果你喜欢的云供应商的服务没有利用开源代码库，寻找兼容性，例如与 [Apache Kafka](https://kafka.apache.org/) 的流或与 [CloudEvents](https://cloudevents.io/) 的描述事件数据。兼容性将让您更轻松地利用云原生技术的现有投资。

## 结束语

应用程序开发环境正在快速变化，多达 [15%的组织](https://www.cncf.io/blog/2018/08/29/cncf-survey-use-of-cloud-native-technologies-in-production-has-grown-over-200-percent/)每天都在部署新的软件版本。根据托管服务的功能、可扩展性和开放性为云原生服务选择解决方案，可以显著提高开发人员的工作效率和组织灵活性。

请考虑 [Oracle 云原生服务](https://www.oracle.com/cloud/cloud-native/)和[今天开始免费](https://www.oracle.com/cloud/free/?source=:so:bl:or:dg:odv:RC_WWMK191113P00049:CloudNativeBlog&SC=:so:bl:or:dg:odv:RC_WWMK191113P00049:CloudNativeBlog&pcode=WWMK191113P00049)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>