# 谷歌为 Kubernetes 开发的新“自动驾驶仪”

> 原文：<https://thenewstack.io/googles-new-autopilot-for-kubernetes/>

像大多数的 Kubernetes 版本和服务一样，[谷歌 Kubernetes 引擎](https://cloud.google.com/kubernetes-engine) (GKE)仍然需要相当多的手工组装和修补来优化你的需求。但是最近，谷歌推出了 [GKE 自动驾驶](https://g.co/gkeautopilot)，这是一个更容易接受管理的 Kubernetes。它的工作是:让你专注于你的软件，而自动驾驶仪管理基础设施。这到底意味着什么？Kubernetes 最知名的领军人物之一、谷歌云主要开发者的倡导者凯尔西·海托华(Kelsey Hightower)向新的堆栈解释了 Autopilot 的情况。

谷歌表示，随着 Autopilot 的推出，GKE 用户可以从两种不同的操作模式中进行选择——每种模式都有自己对 GKE 集群的控制水平以及与 GKE 相关的相对责任。一方面，你有 GKE 标准，这就是 Kubernetes 如何从一开始就致力于谷歌云。另一方面，你有自动驾驶仪。

“Autopilot 代表了高级用户在安全性和正常运行时间是重中之重时采用的许多最佳实践。这需要权衡，”高塔解释道。"默认情况下，需要提升特权的应用程序被阻止。这确保了 GCP 可以在应用和集群级别提供服务级别协议。”

简而言之，自动驾驶仪是带有额外护栏的 GKE，而不是辅助轮。“Autopilot 是一个更受管理的 Kubernetes，而不是 PaaS，”他说。该服务支持与常规 GKE 相同的配置对象，包括部署、作业、配置映射和机密。这意味着大多数用户可以保留他们现有的工作流和高层抽象，比如 Helm。

有了 Autopilot，所有的节点管理操作都省去了。这最大限度地提高了您的集群效率，并有助于提供更强的安全性。

## Kubernetes 发行版

Hightower 看到 Autopilot 沿着 Linux 的历史轨迹前进。“Kubernetes 已经进入发行版时代，就像 Linux 以前一样，”他说。

单个 Linux 发行版关注一组用例。例如，CoreOS(Hightower 在 Red Hat 收购 CoreOS 之前工作的地方)专注于运行容器和安全性。 [Ubuntu](https://ubuntu.com/) 专注于消费者桌面，而[红帽](https://www.openshift.com/try?utm_content=inline-mention)本身专注于企业服务器应用。

上游的 Kubernetes 将更接近于类似 [Gentoo](https://www.gentoo.org/) 的东西，这是超级灵活的，但正如 Hightower 指出的，“一旦你添加了 [ingress 控制器](https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/)和其他 IaaS 集成使其工作，你实际上是在推出你自己的 Kubernetes 发行版。”

在这种情况下，Autopilot 将更接近 CoreOS——高度专注于在安全和完全自动化的操作系统上运行 Kubernetes 工作负载。

在竞争方面，Hightower 继续说道，“GKE 自动驾驶仪与其他托管的 Kubernetes 产品竞争。”

但是 Google 自己的[云运行](https://cloud.google.com/run)呢？那不是竞争对手吗？不，Hightower 说，“我们提供许多计算产品来满足广大客户群的需求。 [Google Compute Engine](https://cloud.google.com/compute) 服务于希望利用虚拟化和熟悉的 IaaS 原语(包括防火墙、负载平衡器和虚拟机)来构建自己的应用平台的客户的需求。”

"库伯内特就是库伯内特"高塔继续说道。“自动驾驶仪是 GKE 的一种固执己见的配置。人们使用 Kubernetes 作为 IaaS 之上的一层来构建自己的应用平台。Kubernetes 提供了一套更高的抽象，但你仍然在这里推出自己的平台，即使自动驾驶消除了对底层 Kubernetes 基础设施的思考。”

Hightower 补充道，“Cloud Run 是不同的。云跑是一个应用平台。Cloud Run 集成了最好的 [Google 云平台](https://cloud.google.com/)，包括 IAM、服务对服务认证和通信以及流量管理，同时为运行容器化应用程序提供了更高层次的抽象。”

在某些方面，自动驾驶提高了 GKE 的安全性。例如，Autopilot 为您一直使用的其他安全工具(如 TLS 证书签名工具)强制实施安全性，如容器隔离和禁止特权 pod。

Autopilot 还禁止不安全的行为，比如闯入你的集装箱。Hightower 认为“完全消除`ssh`提高了 GKE 自动驾驶仪的安全姿态。没有办法登录到底层服务器，这意味着少了一个需要担心的攻击媒介。`ssh`的缺失也使得其他托管服务，包括 [AppEngine](https://cloud.google.com/appengine) 、 [BigQuery](https://cloud.google.com/bigquery) 和 [Pub/Sub](https://cloud.google.com/pubsub/docs/overview) 具有吸引力。”

至于 [TLS 证书签名](https://thenewstack.io/mutual-tls-microservices-encryption-for-service-mesh/)，Hightower 表示，这是“Kubernetes 生态系统的重要组成部分，但如果没有正确的防护栏，特定的 API 可能会被滥用来访问底层基础设施，包括自动驾驶仪很难抽象出来的节点。我们的计划是添加适当的护栏，使非特权身份能够通过 TLS 证书 API 生成。”

至于应用层秘密加密，它使你能够利用 [GCP 的密钥管理(KMS)](https://cloud.google.com/security-key-management) 服务来加密 Kubernetes 的静态秘密，Hightower 说，“这是一项正在进行的工作。由于像这样的集成利用外部服务，我们必须确保定价是透明和可预测的。TLS 证书签名和应用层机密加密都在近期的自动驾驶路线图中。”

一个问题是，就目前而言，你无法将标准的 GKE 星团转换为自动驾驶仪，反之亦然。这使得模式之间的移植变得不可能。Hightower 说，这是真的，但是“GKE 标准支持广泛的集群配置和客户想要运行的几乎任何 Kubernetes 工作负载和扩展。根据设计，Autopilot 支持一个非常特殊的 Kubernetes 配置。虽然我可以看到一种工具来帮助客户评估在 GKE 标准和 GKE 自动驾驶仪之间迁移的可行性，但我不认为我们会在 GKE 这样做。”

Hightower 补充说，如果 GKE 用户“遵循 Kubernetes 最佳实践并从外部管理他们的 Kubernetes 配置，这不仅可以更容易地在 GKE 标准集群之间进行灾难恢复或[蓝/绿升级模式](https://thenewstack.io/primer-blue-green-deployments-and-canary-releases/)，也是在 GKE 标准和 GKE 自动驾驶之间移动 Kubernetes 工作负载的有效方法。”

“最好的想法是，”Hightower 继续说道，“Autopilot 建立在 GKE 之上，具有自以为是的配置，同时继续支持 Kubernetes 的工作负载。Autopilot 针对这些工作负载设置了一些限制和约束，以优化安全性和可支持性。”

在花太多时间在自动驾驶上之前，有一组限制你应该知道。你唯一的操作系统/容器选择是谷歌自己的云 Linux 和 [containerd](https://containerd.io/) 。目前，这些将是你唯一的选择。因此，如果你的软件栈坚持说[红帽企业 Linux (RHEL)](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux) 和[波德曼](https://podman.io/)，自动驾驶可能不是一个好的选择。

Hightower 解释说，这是因为“Autopilot 的目标是抽象出节点的概念，并选择正确的底层配置来支持向客户承诺的 SLA。根据我们在 GKE 标准方面的经验，当前的 Linux + containerd 组合是实现这一目标的最佳方式。我们将继续学习并扩大我们可以支持的 Kubernetes 工作负载的数量，但无论我们做什么，都必须符合我们为自动驾驶设定的安全性和 SLA 标准。”

听起来很有趣？如今，自动驾驶仪通常可以通过命令行界面使用。谷歌正逐步将其推广到所有 GCP 地区的谷歌云控制台。你今天可以用[免费等级](https://console.cloud.google.com/freetrial?_ga=2.129559947.684668266.1613671353-510775544.1613671353)试试看。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>