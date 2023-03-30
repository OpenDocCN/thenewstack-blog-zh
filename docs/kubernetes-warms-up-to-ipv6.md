# Kubernetes 为 IPv6 热身

> 原文：<https://thenewstack.io/kubernetes-warms-up-to-ipv6/>

公共 IPv4 地址的数量是有限的，而 IPv6 地址空间是在大约 20 年前为解决这个问题而指定的，远在 Kubernetes 出现之前。但是因为它最初是在谷歌内部开发的，而且像谷歌和 AWS 这样的云服务直到最近才开始支持 IPv6，所以 Kubernetes 开始只支持 IPv4。

对于已经承诺使用 IPv6 的组织来说，这是一个问题，也许对于需要太多 IP 地址的物联网设备来说也是如此。“物联网客户拥有使用 IPv6 部署在各处的设备和边缘设备，”微软首席软件工程师[哈立德(Kal)赫尼达克](https://github.com/khenidak)指出，他为 Azure 提供容器服务，并协调微软对 Kubernetes 的上游贡献。

运营商和电信公司也对采用 Kubernetes 感兴趣——美国电话电报公司正在使用 Kubernetes 作为飞艇项目的[基础，该项目将用于运行 5G 和公共安全网络服务——但他们已经部署了大量的 IPv6，特别是针对移动网络。大约 90%的 T-Mobile 美国和威瑞森的无线流量已经通过了 IPv6 对于康卡斯特和美国电话电报公司来说，这一比例约为 70%。](https://www.airshipit.org/)

截至 2017 年，全球注册服务商只能分配 3800 万个新 IPv4 地址(这些地址都不在美国，所以任何需要更多 IPv4 地址的人都必须找到愿意出售他们不使用的地址的人)。

谷歌云的首席软件工程师 Tim Hockin 告诉新的堆栈，这意味着即使是那些因为可以使用 NAT can 等技术解决地址短缺而缓慢迁移 IPv4 的企业也会遇到问题。“Kubernetes 非常自由地使用 IP 地址(每个 Pod 一个 IP)，这简化了系统，使其更容易使用和理解。对于非常大的安装，使用 IPv4 可能会很困难。大型企业已经“瓜分”了其网络中的私有 IPv4 空间，这种情况并不少见，因此为 Kubernetes 集群寻找空间可能很困难，甚至是不可能的。IPv6 使得 IP 空间实际上是无限的，所以这不是什么大问题。”

在 Kubernetes 1.9 中增加了对仅支持 IPv6 的集群的支持，作为 alpha 特性，在 1.13 版本中，Kubernetes 默认 DNS 服务器[更改为完全支持 IPv6 的 CoreDNS](https://thenewstack.io/kubernetes-team-pushes-toward-shorter-release-cycles-with-1-13-release/) 。

Hockin 说:“阻碍[IPv6 支持]进展到 beta 和 GA 的唯一因素是与我们的自动化测试更深层次的集成，这是由我们的开发人员社区推动的。”。

Kubernetes 中内置的桥接网络是使用 Linux iptables 特性实现的；“iptables 支持 IPv6 已经有一段时间了，”Henidak 指出。如果你使用一个容器网络接口(CNI)栈来联网，像[项目 Calico](https://www.projectcalico.org/) 这样的插件可以让你禁用 IPv4，而[为 pods 启用 IPv6】。](https://opsnotice.xyz/kubernetes-ipv6-only/)

他指出，迁移到 IPv6 集群不应该需要做很多工作，但是有一些事情需要注意。“对于 Kubernetes 的用户(开发人员或运营人员)来说，将 Kubernetes 更改为使用纯 IPv6 应该不会特别困难，前提是您的网络基础设施和应用程序已经为 IPv6 做好了准备。每个主要的操作系统都已经支持 IPv6，而且大多数开源应用程序都可以在 IPv6 环境下运行。做网络相关事情的定制应用程序可能需要被审计，以确保它们对于 IPv6 是安全的。例如，IPv4 地址通常存储在 32 位整数变量中，但 IPv6 地址不适合。”

## 双栈

但是，无论是 IPv4 还是 IPv6，仅仅支持单个地址族是不够的，因为 Kubernetes 不容易适应它需要集成的所有其他基础设施。

“Kubernetes 不是孤立运行的；它在需要与其他应用程序交互的地方运行，或者——大多数情况下——在云上运行，”Henidak 指出。“如果我有一个应用程序，并通过一个负载平衡器将它暴露给外部世界，我有一个外部 IP，如果我的 Kubernetes 集群是 IPv4 或 IPv6，该地址将仅为 IPv4 或 IPv6。如果我的网络只使用一个地址空间和一个地址族，那么所有东西都需要在同一个地址族中。如果我的节点是 IPv6，那么该节点的客户端必须是 IPv6，数据库也必须是 IPv6，这就产生了问题，因为很少有人真正使用 100%的 IPv6。”

将 IPv6 用于设备的物联网客户可以运行 IPv6 Kubernetes 集群进行连接，但正如他指出的那样；“但这些集群还需要连接到在本地或另一个集群中运行的后端应用程序，甚至连接到仅支持 IPv4 的云服务。”

在网络中没有复杂的 IPv4/IPv6 转换机制的情况下实现这一点需要双栈网络，其中每个 pod 都分配有一个 IPv4 和一个 IPv6 地址，因此它可以与 IPv6 系统以及使用 IPv4 的传统应用和云服务进行通信。

Amazon Web Services 拥有最广泛的 IPv6 支持，但它没有覆盖所有服务；15 个 AWS 区域支持针对 EC2 实例的 IPv6，以及用于弹性负载平衡的公共可路由 IPv6 地址，通过双栈端点访问 S3 桶，支持从设备向 AWS 物联网服务传递消息的 IPv6，支持通过直连的公共和私有虚拟接口的双栈，支持通过 Route 53 对 IPv6 端点进行 IPv6 DNS 查询和健康检查，以及支持 CloudFront、Web 应用防火墙和 S3 传输加速的 IPv6。

自 2016 年以来，大多数 Azure 地区通过负载平衡器支持双栈虚拟机[，并且有完整 IPv6 双栈支持的私人预览；一旦可用，Henidak 说它将与 AKS 和工具](https://docs.microsoft.com/en-us/azure/load-balancer/load-balancer-ipv6-overview)[一起可用，如 AKS 引擎](https://github.com/Azure/aks-engine)(它使用 Azure 资源管理器模板来引导 Azure IaaS 上的 Kubernetes 集群。

“GCP 在 VPC 网络中还没有 IPv6 支持，”Hockin 告诉我们，但一名谷歌员工在 GitHub 关于双栈支持的讨论中指出，该服务正在 GCE 中测试一些原型双栈配置。

为 Kubernetes 添加双栈支持比单独支持 IPv6 需要更多的工作，社区已经为一个 [Kubernetes 增强提案](https://github.com/kubernetes/enhancements/issues/563)工作了一段时间。这是一种真正的双堆栈实施，支持 pod 和服务的 IPv4 和 IPv6，而不是采用更简单的方法，即只为 pod 和节点提供双堆栈地址，而是对集群中的服务 IP 使用单个系列(全 IPv4 或全 IPv6)。

因为应用程序使用完全合格的域名进行服务发现，所以集群中的 DNS 需要知道它是运行 IPv4、IPv6 还是双栈(核心 DNS 中的 IPv6 支持对此有所帮助)。

增强项目将测试双栈功能与桥梁和 PTP CNI 插件和主机本地 IPAM 插件。“有多个网络提供商拥有自己的基于 CNI 协议栈的解决方案，”Henidak 指出。“他们可能依赖于本机 Linux 内核功能或自己的实施，当 Kubernetes 迁移到 IPv6 双协议栈时，他们将需要提供自己的双协议栈实施。”

NGINX 这样的入口控制器也需要提供双栈支持；在这两种情况下，网络提供商可能已经在其他环境中支持 IPv6，但之前没有将其引入 Kubernetes，因为它不是双栈。

“目前的想法是，服务将有一个 ID，上面写着‘我希望将其公开为 IPv4 或 IPv6’”，他解释道。这是您为实现互操作性而做出的选择。“如果我有 Kubernetes，它的应用程序运行在双栈模式下，它们有来自不同家族的多个 IP 地址；如果我将其公开为 IPv4，这意味着只有支持 IPv4 的客户端才能与此服务通信，对于 IPv6 也是如此。这样，人们可以从指向同一个应用程序的两个不同家族获得两个 IP 地址，从而支持多个客户端。无论客户端能够做什么，它们都能够进入群集。”

目的是在不中断现有实现和部署的情况下添加新功能。“主要原则是不要破坏任何东西，”赫尼达克说。“有些工具是在 Kubernetes 之上编写的，有很多客户调用 Kubernetes API，他们希望从服务中获得某些输入和输出。我们希望在不破坏任何功能的情况下，迁移到新的双堆栈产品，同时为客户提供最大价值。”

这意味着该项目将在 Kubernetes 的未来版本中经历通常的 alpha、beta 和 GA 阶段，以便为测试留出时间——但这需要一些时间。Hockin 说:“Kubernetes 的双栈 IPv6 支持或多或少是设计完成的。“我们有一个非常好的 Kubernetes 增强提案，但这项工作有点停滞不前。在这项工作完成之前，最好的情况是发布几个版本。”

如果您需要在 Kubernetes 发布版本之前支持双栈 IPv6(heni dak 估计这还需要 9 个月)，您可以在 IPv6 模式下运行集群，并通过设置有状态 NAT64 和 DNS64 服务器来处理地址转换，以连接到外部的仅支持 IPv4 的服务器，设置双栈入口控制器来对集群中仅支持 IPv6 的端点进行负载平衡，并设置无状态 NAT64 服务器，使仅支持 IPv4 的外部客户端能够访问它们公开的 Kubernetes pods 或服务。

Henidak 预测，新提议的最早采用者将是重度物联网用户。“我的客户说‘我想要 IPv6，我现在就想要’。这些人会立即接受它，甚至在早期阶段进行测试并提供反馈，社区中的每个人都依赖这些人。”

“还有一些人现在对 IPv4 还满意，但他们知道将来他们会需要 IPv6，所以他们一直在关注这个提案。他们告诉我们‘我网络上的 IPv4 空间快用完了；我已经将我的内部网络转换为 IPv6，我需要双栈来与我的云托管 Kubernetes 集成。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>