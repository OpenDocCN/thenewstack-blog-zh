# StackPointCloud 用 Istio 服务网格扩充了 Kubernetes

> 原文：<https://thenewstack.io/stackpointcloud-drops-istio-service-mesh-integration/>

为了将 Kubernetes 带给更多的组织，StackPointCloud 将 [Istio](https://istio.io) 服务网格集成到基于开源容器编排引擎的托管平台中。

“我们认为 Kubernetes 是一个很棒的平台，但它不是端到端管理的，”StackPointCloud 创始人兼首席执行官[马特·鲍德温](https://twitter.com/baldwinmathew)说。他说，客户可能不知道他们需要一个早期的服务网络，但他们会很快找到答案。

[StackPointCloud](https://stackpointcloud.com/) 提供这套服务，让 DevOps 团队更容易使用 Kubernetes 部署、监控和维护基于云和微服务的应用。一旦启动，开发人员可以从 Stackpoint.io 控制面板监控应用性能问题、微服务之间的依赖关系以及微服务策略。

随着企业从整体结构转向微服务，他们发现使用覆盖旧的整体结构和新分布的微服务的服务网格势在必行。

Istio 等服务网格本质上是一组联网的微服务，最终可以包括负载平衡、故障恢复、发现、金丝雀释放、速率限制、访问控制和端到端身份验证，当然还有指标和监控，这是大多数服务网格的起点。

这本身就造成了复杂性。Istio 提供了涵盖所有这些功能的完整解决方案，将运营控制和行为洞察作为一个整体添加到服务网格中。Istio 是谷歌、IBM 和 Lyft 的合作项目。

“我们不认为 Kubernetes 是堆栈的末端，而是一个公司整个云原生环境可以生存的平台，”Baldwin 说。“为此，用户需要一个服务网络。我们相信 Istio 将成为事实上的服务网格，我们的目的是继续丰富 Stackpoint.io 对它的支持。”

Lyft 开源了它的[特使服务网格](https://thenewstack.io/building-lyfts-new-application-service-mesh-envoy/)，现在已经合并到 Istio 中。其他公司，包括 nginx 和 Tigera 也采用了 Istio。

## 堆栈点云

鲍德温在接受采访时说，StackpointCloud 正专注于 Kubernestes 的部署和管理方面。只有两年历史的 Kuberetes 拥有很强的容器编排能力，但是学习曲线很陡。鲍德温的任务是缓和这一曲线。这款新产品无疑是朝着这个方向迈出的一步。

最近由 StackPointCloud 在旧金山主办的一次会议“Istio 之夜”上，Tigera 的解决方案架构总监 Karthik Prabhakar 做了专题介绍，他演示了如何通过几行代码快速地将网格添加到 Kubernetes 容器中。谷歌对 Istio 的主要贡献者之一 Zack Butcher 展示了一些 Istio 更酷的功能。出于好奇，他们将在下个月的某个时候把这个节目带到路上或广播上。查看该公司的博客和 [Twitter feed](https://twitter.com/StackPointCloud) ，了解关于确切日期和参与方式的公告。

捆绑包中包括用于日志记录和监控的 Elasticsearch Fluentd Kibana(一个“EFK”堆栈)、Prometheus 和 Sysdig、用于实施网络策略的 Calico 和用于容器运行时安全性的 Twistlock。还包括冗余管理以及自动管理和扩展节点的能力。或者手动，如果你想去老学校，可以抽出时间。

一个简单的点击就能把网拉在一起并升级 Kubernetes。Istio 和 Envoy service mesh 的加入使微服务之间的依赖关系更容易观察，识别问题，自动执行策略，并使用 mTLS 维护加密。

它适用于所有领先的云基础架构平台。StackpointCloud 还确保 Istio 可以与其他预配置的系统一起工作，包括 GitLab EE、Fabric8 和 Kubeless。

托管 Istio 产品现在可以作为 Stackpoint.io 平台的订阅附件购买。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>