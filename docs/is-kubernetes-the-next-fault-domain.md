# Kubernetes 是下一个断层域吗？

> 原文：<https://thenewstack.io/is-kubernetes-the-next-fault-domain/>

[](https://www.linkedin.com/in/keithmcclellan/)

 [基思·麦克莱伦

基思·麦克莱伦是蟑螂实验室](https://www.linkedin.com/in/keithmcclellan/) [](https://www.linkedin.com/in/keithmcclellan/)合作伙伴方案工程总监

如今，大多数应用程序架构都是默认分布式的:在云环境中的[容器](https://thenewstack.io/category/containers/)中运行的互联[微服务](https://thenewstack.io/category/microservices/)。大大小小的组织现在每天都要部署数千个容器，其复杂程度几乎令人难以理解。绝大多数组织依靠 [Kubernetes (K8s)](https://thenewstack.io/category/kubernetes/) 来协调、自动化和管理所有这些工作负载。

那么，当 Kubernetes 发生什么事情时，会发生什么呢？

当基础设施或网络服务的关键部分出现问题时，故障域是分布式系统中受到影响的区域。Kubernetes 是否已经成为下一个故障域？

考虑与 Kubernetes 相关的应用程序失败的灾难是 [DevOps](https://thenewstack.io/category/devops/) 噩梦的内容。但在灾难中，也有机会:Kubernetes 有可能帮助我们获得跨数据中心、云区域甚至云的通用操作体验，成为我们设计高可用性(HA)应用的容错域。

## Kubernetes 作为通用操作系统

许多分布式应用程序需要尽可能靠近用户分布，所以假设我们要构建一个三区域集群。

如果没有 Kubernetes，即使是在单个云中，也意味着要管理所有这些虚拟机，并在每台服务器上设置一堆脚本来进行自我修复。如果服务器关闭或重启，我们必须编写一堆 Terraform 或 Ansible(或 [Puppet](https://puppet.com/?utm_content=inline-mention) 或 Chef 或 Pulumi)脚本来重新生成我们的服务器。

然后，如果我们想成为跨云，我们必须以三种不同的方式完成所有的事情！我们必须知道做这件事的方法。我们必须知道蓝色的方法。我们必须知道谷歌的做法。

然而，使用 Kubernetes，我们需要知道的唯一一件特定于 AWS、Azure 或 Google 的事情是如何获得 Kubernetes 集群……然后如何配置该集群，以便能够供应基础设施并能够相互通信，无论是通过专用网络、VPN 还是互联网上的 TLS。一旦完成了这一步，不管我们的基础架构位于何处，其余的管理工作基本上都是一样的。

Kubernetes 有效地为我们提供了一个通用的操作系统，不管我们在哪里运行基础设施。它就像我们的操作系统一样，抽象出我们运行的任何可用性区域或地区或云的复杂性。无论我们在哪里部署，我们都有一个通用的操作语言，并且我们获得了 Kubernetes 的所有强大的自我修复功能。

这很好，但这也是 Kubernetes 成为容错域的原因:因为我们的 K8s 集群的周长现在等于我们所在的基础架构的周长，所以我们可以将每个 Kubernetes 集群视为一个数据中心或云区域，以实现高可用性。因此，如果该地区或 Kubernetes 集群出现故障，我们的应用程序会以同样的方式处理该故障。

通过使它们等价，我们减少了从可用性角度来看必须管理的维度数量。这极大地简化了分布式应用程序的前景，因为它成为我们必须考虑的唯一故障域。

问题是 Kubernetes 并没有真正被设计成一个容错域。

## K8s 的下一代问题

这是我们现在需要解决的下一个大问题:为了能够轻松地将 Kubernetes 视为多区域/多站点集群的故障域，Kubernetes 本身需要提供许多额外的构造来促进这种模式。

K8s 生态系统和社区已经解决这个问题很长时间了。这导致了为特定应用程序或应用程序堆栈构建多区域解决方案的各种不同方式，但是对于这一问题领域还没有一个统一的策略或解决方案。

这些定制解决方案领域中最重要的是[网络](https://thenewstack.io/category/networking/)和[安全](https://thenewstack.io/category/security/)，但在基础设施、故障恢复、[可观察性和监控](https://thenewstack.io/category/monitoring/)领域也有需求。联网是至关重要的，因为需要集群之间的连接，以及集群之间的服务发现和流量路由。安全也很重要，因为你需要确保你没有访问蔓延，你需要一个中央信任机构。

### 建立工作关系网

目前有跨集群交流平台，如 [Cilium](https://cilium.isovalent.com/getting-started?utm_term=cilium%20kubernetes&utm_campaign=Getting+started+with+Isovalent+Cilium+Enterprise+-+Google+ads+-+04/06/2022+8:45+AM&utm_source=adwords&utm_medium=ppc&hsa_acc=8789909260&hsa_cam=16800372928&hsa_grp=136720639673&hsa_ad=591665333261&hsa_src=g&hsa_tgt=kwd-1517455096983&hsa_kw=cilium%20kubernetes&hsa_mt=p&hsa_net=adwords&hsa_ver=3) 、 [Tigera 的](https://tigera.io/?utm_content=inline-mention)、 [Project Calico](https://www.tigera.io/project-calico/) 、 [Submariner](https://submariner.io/) 和 [Skupper](https://skupper.io/) 。每一种都有优缺点，但是没有一种是你所希望的万能解决方案。

### 负载平衡和服务发现

一旦集群可以相互通信，它们就需要能够发现跨站点运行的不同服务的实例。还需要全局负载平衡，允许用户被路由到最近的可用实例，而不管他们从哪里进入应用程序。

### 安全性

如果您正在管理一个 K8s 集群，一般来说，您将拥有非常低级别的安全权限。实际上，您需要在每个集群中拥有相同级别的安全权限，如果您不小心管理它，您可能会在特定集群中获得比您需要的更多或更少的安全性。

不幸的是，K8s 中的安全管理通常仍然是一个相当手工的过程，随着应用程序变得越来越分散，这变得越来越困难。

### 信任和身份

现在，在多个 Kubernetes 集群之间共享一个信任和身份源是一件有些痛苦的事情，这加剧了在多个 Kubernetes 集群之间运行应用程序时可能遇到的其他一些安全问题。当您在跨站点的 pod 之间进行交互时，这变得更加重要，在这种情况下，管理员可能需要同时连接到多个 Kubernetes 集群以进行故障排除。

### 基础设施和性能

目前，提供 pods 的 Kubernetes 原语只允许您声明您得到的东西的“多少”,而不考虑基础设施的性能如何。例如，您可以请求 CPU 或特定大小的卷，但您不能请求特定的处理器或保证驱动器的性能特征。这意味着必须仔细调整和监控每个站点，以确保没有性能热点或冷点。

### 故障恢复

无论一个系统有多分散，仍然有可能发生灾难，因为环境不是为生存而设计的。减轻这种可能性的灾难恢复策略需要应用程序到达故障域之外来存储和检索备份，这对于 Kubernetes 和一般的云来说都是一项重要的活动。

### 可观察性和监控

运行多站点应用程序时，重要的是能够监控整个系统的运行状况、性能和行为，从而允许管理员在问题发生之前进行干预，并进行容量规划，以管理对系统不断增长的需求。

我们在蟑螂实验室高度意识到了这一点，Kubernetes 是 CockroachDB 和我们的托管数据库服务的关键。下面是我们如何使用 Kubernetes 作为多区域集群或多站点集群的故障域。

## 让控制飞机着陆

您可能不认为您正在构建的应用程序是全局的，但它确实是全局的。跨两个或三个站点的部署与跨全球的多区域部署面临相同的挑战，因此应用程序必须使用相同的架构原语来构建。

除非你有一个非常本地化的商业模式，否则无论是现在还是在不久的将来，你都将采用这种方式。令人惊讶的是，活动无处不在的工作负载越分散，在任何特定故障中幸存下来的成本就越低。

例如，在传统的双站点灾难恢复场景中，如果数据中心或区域出现故障，您必须拥有 2 倍的设备才能继续运行。有了分布在三个站点的 CockroachDB，您只需要 1.5 倍的一切就可以无中断运行。这是因为即使失去了一个站点，你还有两个剩余。

当您将一个应用程序分布到更多站点时，从一个站点故障中幸存下来的实际成本甚至会降低更多。例如，当分布在五个站点时，您只需调配 1.25 倍的基础架构，就能在一个站点出现故障时继续无中断运营。

当您部署多区域/多站点时，我们建议为每个站点部署一个 Kubernetes 集群，然后我们在这些站点之间部署 CockroachDB。这就是为什么在缺乏这种下一代解决方案的情况下，我们不得不为我们的托管 CockroachDB 服务做一些定制工作，以便能够将 Kubernetes 视为容错域。

我们通过构建一个控制平面来为我们管理这一点，在 CockroachDB 专用和无服务器中解决了这个问题。我们使用 Google 或 Amazon 中的网络来允许不同地区的 Kubernetes 集群之间的路由，然后我们使用控制平面来一致地应用所有安全设置，并检查以确保它们得到更新。它还为我们提供了支持数百个集群并发所需的各种可观察性信息，并帮助客户解决他们可能遇到的问题。

控制平面还做其他事情。我们创建了一个集中的密钥管理库，这样管理员密钥就不必小心翼翼地运送到每个单独的区域。我们也花了很多时间思考持久性。

当然，我们所构建的是为 CockroachDB 定制的，就像其他任何人今天必须构建来管理这些类型的边缘一样。

当我们最初构建 cocroach db 数据库本身时，我们经常谈到 Kubernetes，因为即使在单站点配置中，cocroach db 和 Kubernetes 的结合也给了数据库比单独的数据库更好的弹性特征。

这些天，如果你看一下我们的网站，你会发现我们很少提到 Kubernetes。但在内部，它仍然是最重要的:所有的 cocroach db 专用，所有的 cocroach db 无服务器，以及我们的一些自托管集群都运行在 Kubernetes 中。只是控制平面处理复杂性。

## 结论

混合、多区域甚至多云部署不仅越来越普遍，而且对于需要横向扩展、保证可用性和最大限度减少延迟的企业来说也越来越必要。Kubernetes 有潜力帮助我们获得跨数据中心、云区域甚至云的通用操作体验，成为我们设计 HA 应用的容错域。

我们认为，最好的方法是在每个位置都有一个 Kubernetes 集群，然后有某种共享机制将它们有效地连接在一起，以便能够共享安全配置信息，设置网络路由和解决下一代问题所需的所有其他部分。

这个星球上的每一个软件即服务公司，以及每一个跨国公司，都有这个确切的问题。在蟑螂，我们每天都看到这种情况，因为许多这些公司和平台都是我们的客户。

发明允许 Kubernetes 分布在多个地区的机制:这是整个 Kubernetes 生态系统和社区现在面临的挑战。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>