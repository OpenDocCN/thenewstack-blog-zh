# 关于开源服务网格 Istio 的 5 件事

> 原文：<https://thenewstack.io/5-things-to-know-about-istio-the-open-source-service-mesh/>

Istio 是一个连接、管理、监控和保护微服务的开放平台，由 IBM、谷歌和 Lyft 于去年 5 月推出。在过去的九个月中，为了升级到当前版本 v0.7.1，我们增加了许多新特性和改进。

以下是我支持 Istio 的五大理由:

## 1.自动边车注射

Istio 需要 Kubernetes v1.9 或更新版本，因为有[定制资源](https://kubernetes.io/docs/concepts/api-extension/custom-resources/)和[变异 webhooks](https://kubernetes.io/docs/admin/admission-controllers/#mutatingadmissionwebhook-beta-in-19) 支持。如果您的集群启用了变异 webhook 特性，我建议您安装 Istio 自动边车注入器，它会为您希望 Istio 为您管理的所有微服务部署自动注入 [Envoy](https://www.envoyproxy.io/) 边车。 [IBM Cloud Container Service](https://www.ibm.com/cloud/container-service?cm_mmc=OSocial_Blog-_-Cloud_Cloud+Platform-_-WW_WW-_-Istio&cm_mmca1=000023UA&cm_mmca2=10007995&) 集群(v1.9 或更新版本)默认启用了变异 webhooks 特性，这与 Istio automatic sidecar injector 配合得很好。由于这还是 Istio 开发整体方案中的一个新特性，所以我建议大家谨慎使用。

## 2.交通管理改善

 [孙林，IBM 高级技术人员

Lin 是 Istio、IBM Cloud Container Service 和其他云的核心贡献者和维护者。她对新技术充满热情，喜欢尝试新技术。她是一位发明家大师，目前拥有 100 多项专利文件或正在美国专利商标局申请专利，以及在 IP.com 发表的数百篇文章。](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2018/attend/register/) 

在 Istio v0.1 中，您可以使用入口路由规则来指定希望通过您的微服务进入的流量类型。现在，您还可以使用出口路由规则来指定哪些类型的流量可以流出服务，以及它可以与哪个外部服务进行通信。例如，您可以轻松地配置您的服务来与 IBM Cloud 中的 IBM Watson 服务进行对话，从而为您的服务提供机器学习功能。我最近更新了 Kubernetes 留言簿示例，以自动生成基于机器学习的表情符号，并了解到交通管理确实帮助我测试和推出了新版本。我强烈建议您在开发和试运行环境中探索流量管理，这样您就可以对测试充满信心。

## 3.改进的遥测技术

作为一名 Istio 用户，我不需要做任何事情来启用各种指标或跟踪，这为我节省了宝贵的时间。我可以部署我的微服务应用，并让 Istio 管理它，而无需更改我的应用或部署的任何部分。yaml 文件。Zipkin 或 [Jaeger](https://github.com/jaegertracing/jaeger) 跟踪工具为进入我的应用程序的每个请求提供详细的跟踪信息，并允许我深入每个请求，以查看流量如何在服务网格中端到端地流动。如果您希望为每个给定的请求将跟踪范围捆绑在一起，您需要更新代码来传播一些头。我强烈建议您考虑将遥测作为第一个在您的生产环境中使用的 Istio 特性。

![](img/da985f7aaec0fe2f939b9cc34063e060.png)

## 4.多环境支持(Consule、Eureka 和 VM)

Istio 的最初目标之一是实现多环境支持，因为你不能要求所有工作负载都在微服务架构中的 Kubernetes 上运行。您的一些应用程序可能运行在 Kubernetes 中，而一些可能运行在 Docker Swarm 或 VMs 中。自去年 10 月以来，Istio 已经发展到为虚拟机提供早期支持，与一些更流行的服务发现系统(如 Consul 和 Eureka)集成，并扩展到支持其他运行时环境。该社区还致力于对多云和多集群的支持。我非常高兴看到 Istio 扩展到多个供应商云。

## 5.相互 TLS (mTLS)及其灵活配置

这是我个人的最爱！Istio 增强了微服务通过 mTLS 进行安全通信的能力，无需对您的微服务进行任何代码更改。我发现最有趣的是，社区通过引入每个服务的 mTLS 启用或禁用，使其变得灵活和易于使用，因此您可以在每个服务的基础上调整此配置。此外，任何用户都可以插入任何现有的 CA 证书和密钥，或者为每个服务配置基于角色的访问控制(RBAC)。尽管我很喜欢这些安全特性，但我还是建议首先采用不带 mTLS 的 Istio，然后逐渐启用 mTLS。当允许使用 mTLS 时，故障排除会更加困难，因此您需要确保您的微服务可以在不启用 mTLS 的情况下使用 Istio。

最后，我希望这五个亮点能让你对 Istio 感到兴奋。社区欣欣向荣，我们吃自己的狗粮。Istio 控制面板本身在 Istio 上运行，因此通信是安全的，操作员可以在控制面板周围看到一个漂亮的 Grafana 仪表板。我推荐在 IBM Cloud Container Service 上安装最新版本，试一试！请随时在 [Istio 用户的邮件列表](https://istio.io/community/)上给我们反馈。

*林将于 2018 年 5 月 2 日至 4 日在丹麦哥本哈根举行的 KubeCon 和 CloudNativeCon EU 大会上，与 Istio【一起探讨如何对您的微服务进行观察和故障排除。*

本文由 IBM 代表 [KubeCon 和 CloudNativeCon Europe](https://www.cncf.io/kubecon-cloudnativecon-events/) 投稿，将于 2018 年 5 月 2-4 日在丹麦哥本哈根举行。管理 KubeCon 和 CloudNativeCon Europe 的 Cloud Native Computing Foundation 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>