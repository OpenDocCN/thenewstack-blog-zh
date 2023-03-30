# 交叉平面:一个 Kubernetes 控制平面来滚动你自己的 PaaS

> 原文：<https://thenewstack.io/crossplane-a-kubernetes-control-plane-to-roll-your-own-paas/>

云原生商店的理想状态是运行一个开发和部署管道，可以无缝地将应用程序从开发人员的笔记本电脑移动到数据中心(或边缘)，而无需任何人工干预。虽然有许多工具可用于促进这种自动化——Helm、Operators、CI/CD 工具链、GitOps 架构、基础设施即代码工具(如 Terraform)——但很多时候，边缘情况和异常仍然需要个人关注，这导致 DevOps 管道陷入停顿。

在最新一集的[新堆栈环境](/podcasts/context)播客中， [Upbound](https://upbound.io/) 的主要产品经理 [Phil Prasek](https://www.linkedin.com/in/philprasek2/) 断言，拼图中缺少的部分是控制平面和控制平面运行的统一应用模型。Prasek 设想有一天，组织可以构建自己定制的平台服务，开发人员可以从自助服务门户中获取他们需要的构建模块，无论是容器化的应用程序还是第三方云服务，并让最终的应用程序在多个环境中统一运行。

“在一个企业控制平面内，你基本上可以有自己的抽象，然后你可以发布它们，”Prasek 说。

TNS 编辑和营销总监 [Libby Clark](/author/libby/) 主持这一集，TNS 高级编辑 [Richard MacManus](/author/richard/) 和 TNS 执行主编 [Joab Jackson](/author/joab/) 提供帮助。

[第 133 集:cross Plane——一个 Kubernetes 控制平面滚动自己的 PaaS](https://thenewstack.simplecast.com/episodes/episode-133-crossplane-a-kubernetes-control-plane-to-roll-your-own-paas)

Prasek 解释说，对控制平面的需求，如 Upbound 自己的开源交叉平面，来自于那些希望构建自己的私有平台即服务(PaaS)的组织，如 Heroku 或 Cloud Foundry，但他们坚持自己的特定要求。对于开发人员来说，控制平面管理软件为构建应用程序提供了一组构建模块——容器化的数据库、托管云存储服务等等。控制平面知道所有要调用的云 API，容器化应用和云 API 调用的安全和组织策略可以嵌入平台本身。

需要一个应用程序模型来标准化应用程序的配置设置，以便可以在多种环境中部署它们。去年，微软和阿里巴巴联手创造了一个，即[开放应用模型](/open-application-model-build-the-next-generation-of-cloud-native-applications/)。一个应用程序模型只是详细描述了应用程序需要运行的所有不同需求，包括密码指针、配置设置、硬件需求、集群设置(如果是 Kubernetes 应用程序的话)等等。

Prasek 说，虽然 T2 Kubernetes 运营商 T3 也提供了一种自动获取这些信息的方法，但它没有明确区分管理员和开发人员的责任，让开发人员去搞清楚网络设置等。

在采访 Prasek 之后，我们讨论了过去一周出现在新堆栈上的一些播客和帖子:

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>