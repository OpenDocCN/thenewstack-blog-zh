# Linkerd 通过选择加入扩展来减肥

> 原文：<https://thenewstack.io/linkerd-goes-on-a-diet-with-opt-in-extensions/>

浮力已经发布了 2.10 版本的 [Linkerd](https://github.com/linkerd/) 开源服务网格，这个版本比前一个版本少了 300MB。新调整的版本并没有以牺牲功能为代价，而是增加了扩展，几个以前默认的工具现在作为可选扩展提供。

“Linkerd 已经是市场上最快、最小的服务网格，但我们更进一步，使默认安装成为您拥有服务网格功能所需的最低要求。其他并非绝对必要的东西都被打包成这些选择加入的扩展，”[浮力](https://buoyant.io/)的首席执行官[威廉·摩根](https://www.linkedin.com/in/wmorgan/)在接受采访时说， [Linkerd](https://linkerd.io/) 背后的公司。“分机基本上是一个 Kubernetes 控制器或操作员。我们尽可能地依赖 Kubernetes 原语，但我们正在做的是，发生了一点包装器魔术，使这些扩展感觉像 Linkerd 的其余部分。”

在这些以前默认的功能中，现在作为扩展提供的是 multicluster 扩展，它包含跨集群通信工具、 [Jaeger](https://www.jaegertracing.io/) 分布式跟踪收集器和用户界面扩展，以及一个包含集群上指标堆栈的可视化扩展，它由 Grafana、dashboard、Prometheus 等组成。虽然节省 300MB 的内存正是为了这个目的，但 Morgan 也表示，运行 Prometheus 的开销对于一些用户来说是不必要的，而且在扩展时也是一个难点。

“Prometheus 组件是在您的集群接收流量时扩展最迅速的组件。所以，如果你有一个流量很大的非常大的集群，这是集群中最难管理的部分，”摩根说。“无论如何，许多 Linkerd 采用者正在运行他们自己的基于 Prometheus 的度量堆栈，因此并不总是有理由在集群上使用这些 Prometheus。”

每当我们在这种情况下谈论运营规模时，在边缘运行的想法经常出现，摩根说，再次，除去普罗米修斯“只会使边缘的采用更容易。”然而，扩展不仅仅是为了消除违约和缩小运营规模，摩根说他希望 Kubernetes 生态系统也能加入进来。

“从默认安装中删除一些东西并拥有这个真正极简的功能集是很好的，但我们也希望允许第三方能够构建扩展，而不必使用核心的 Linkerd CLI。因此，如果你构建一个 Linkerd 扩展，你实际上只是在现有 Kubernetes 原语的基础上构建，Linkerd 会让它感觉像 Linkerd 体验的其余部分，”Morgan 说。

“Linkerd 存在于 Kubernetes 这个非常丰富的生态系统中，其中许多东西与 Linkerd 结合使用是有意义的。所以我希望的是，我们将看到入口控制器、网守等人们经常与 Linkerd 一起使用的东西，它们也将成为 Linkerd 的扩展。然后，您可以通过预先配置的方式部署这些东西，以便与 Linkerd 配合使用。”

Linkerd 用户可以期待的一个扩展是浮力的内部产品，摩根称之为“beta 浮力扩展”，这将使 Linkerd 与该公司托管的 Linkerd 仪表板[浮力云](https://buoyant.cloud/)集成变得容易。

除了扩展之外，Linkerd 2.10 还扩展了 2.9 中引入的一个特性[，该特性为所有 TCP 连接启用默认 mTLS。Linkerd 2.10 现在将此扩展到跨集群的所有 TCP 连接，这意味着 Linkerd 可以跨集群边界安全地连接 Kubernetes 服务。同样，Linkerd 2.10 增加了一个不透明端口特性，使 Linkerd 能够为所有 TCP 流量提供 MTL。例如，如果您正在运行一个未加密的 MySQL，您可能会绕过 Linkerd 代理。有了不透明端口，就不需要绕过 Linkerd，现在 Linkerd 可以提供 MTL，以及其他功能，比如 TCP 级度量。](https://thenewstack.io/linkerd-adds-default-mtls-to-kubernetes-to-enable-zero-trust/)

## 孔网 1.2 增加了 OPA，FIPS 支持

在其他服务网格新闻，[孔网格 1.2](https://konghq.com/blog/kong-mesh-1-2) 是出于类似的重点是增加新的安全功能。Kong Mesh 1.2 建立在基于 Envoy 的服务网格的开源[库马](https://kuma.io/)通用控制平面上，增加了对[联邦信息处理标准(FIPS)](https://www.nist.gov/itl/current-fips) 、多区域安全和[开放策略代理(OPA)](https://www.openpolicyagent.org/) 的本机集成的支持，Kong CTO Marco Palladino 表示，与其他服务网格相比，OPA 在 Kong Mesh 上的使用显著增加。

“Kong mesh 是第一个也是唯一一个在服务 Mesh 本身内部提供内置 OPA 本地支持的服务 Mesh。为了在其他服务网格中使用 OPA，除了服务网格边车代理之外，用户还需要在每个服务旁边部署一个带有 OPA 代理的附加边车代理。然后，用户需要编写 OPA 策略，并将它们存储在某个地方，以便可以对它们进行解析。最后，如果在跨多个集群的服务网格中使用，用户需要在服务网格支持的每个集群、云或区域中分发 OPA 策略，”Palladino 在一封电子邮件中写道。“有了 Kong Mesh，这些都不再需要了(嗯，除了编写需要强制执行的减压阀政策)。”

至于 FIPS 支持，这似乎是最近服务网格功能增加的一种趋势，上个月， [Tetrate 的 GetIstio 项目](https://thenewstack.io/tetrates-getistio-promises-to-simplify-management-of-a-istio-service-mesh/)和 [Solo.io 的 Gloo Mesh Enterprise](https://thenewstack.io/solo-io-launches-gloo-mesh-enterprise-to-general-availability/) 都增加了对该标准的支持。Palladino 将 FIPS 支持与 OPA 归为一类，指出它可能很难部署。

“如今，在 Envoy 中默认情况下不支持 FIPS，因此部署起来很困难，尤其是在拥有多个平台(Kubernetes、虚拟机等)的企业组织中。)，云和操作系统都在运行。在这个新版本中，Kong Mesh 通过在我们支持的所有发行版的每个数据平面代理中捆绑 FIPS 支持，无需用户采取任何行动，从而加快了安全合规性，”Palladino 写道。“默认情况下，实施 Kong Mesh 1.2 意味着我们正在部署一个支持 FIPS 的服务网格，以在 Kong Mesh 支持的所有环境中提高安全性和合规性。与 OPA 一样，这使得 Kong Mesh 1.2 成为在整个组织内加快 FIPS 合规性的最简单方法。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>