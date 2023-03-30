# HAProxy Kubernetes 入口控制器移出集群

> 原文：<https://thenewstack.io/haproxy-kubernetes-ingress-controller-moves-outside-the-cluster/>

自 2019 年[发布 HAProxy 2.0](https://thenewstack.io/haproxy-2-0-adds-kubernetes-pushes-polyglot-extensibility/) 以来， [HAProxy Kubernetes Ingress 控制器](https://github.com/haproxytech/kubernetes-ingress)一直存在，在此后的一年半时间里，该项目进行了近 40 次小更新，现在随着 [HAProxy Kubernetes Ingress 控制器 1.5](https://www.haproxy.com/blog/announcing-haproxy-kubernetes-ingress-controller-1-5/) 的发布，该项目迎来了首次重大更新。

产品总监 Daniel Corbett 说: [HAProxy](https://www.haproxy.com/?utm_content=inline-mention) 引入了不同类型的认证、配置和在 Kubernetes 集群外部运行控制器的功能，这标志着该软件的新发布节奏。

“当我们第一次发布入口控制器时，我们迭代得非常快。Corbett 说:“在次要版本中引入新功能并不总是理想的，你可能不会想到会发生这种变化，或者你不会想到在升级过程中会遇到新功能，所以我们决定切换到核心软件的工作方式，次要版本只修复错误，然后我们认为主要版本将获得新功能。”。“它确保了整个项目的稳定性，这样当您还没有准备好在环境中引入这些变化时，就不会对新功能措手不及。”

展望未来，该项目将每季度提供主要版本，与 HAProxy 本身的总体时间表相同。

目前，Kubernetes 的默认入口控制器是基于 NGINX 的[，而 HAProxy](https://kubernetes.github.io/ingress-nginx/) [Kubernetes 入口控制器](https://thenewstack.io/kubernetes-ingress-for-beginners/)，顾名思义，是基于 [HAProxy](http://www.haproxy.org/) ，一个专注于速度和高可用性的开源负载平衡器和代理。

HAProxy Ingress 控制器提供了更丰富的功能[和 1.5 版引入的一个特性，该特性能够向 Kubernetes Ingress、Service 或 ConfigMap 文件添加注释，并将其应用于 kubectl，而不是手动编辑 HAProxy 的配置文件。Corbett 解释说，该功能允许 HAProxy 入口控制器用户更容易地访问默认情况下不可用的 HAProxy 功能。](https://thenewstack.io/how-haproxy-streamlines-kubernetes-ingress-control/)

“它非常灵活。它为你提供了做任何事情的基础，无论事情有多小或多复杂。Corbett 说:“很难用入口控制器以可管理或合理的方式支持这一点，所以我们挑选我们认为最有用的注释和配置选项。“有些人可能有一个非常独特的环境，他们希望能够提供一些定制的东西，这些东西不会通过入口控制器公开，所以现在我们公开了该功能，以提供一个 HAProxy 配置片段。”

v1.5 引入的另一个重要特性是能够在 Kubernetes 集群外部运行 HAProxy Ingress 控制器。虽然这种部署方法意味着入口控制器不会直接与 Kubernetes 一起扩展，而是需要外部管理可扩展性，但它进一步减少了在延迟敏感环境中运行的用户的任何开销，因为它消除了对外部负载平衡器或代理的需要。Corbett 解释说，HAProxy Ingress 控制器的一个好处是，它能够在不导致停机的情况下重新配置，从而提供高可用性。

“他们不想引入额外的代理层。他们希望他们的负载平衡器监视 Kubernetes 的变化，并基于此在负载平衡器中进行配置更改。用户将能够在 Kubernetes 之外运行 Ingress 控制器，它将能够通过 Kubernetes API 监控变化，然后根据这些变化重新配置其本地负载平衡器，”Corbett 说。“它允许客户通过 HAProxy 运行时 API 实现零停机。当 Kubernetes 环境中发生变化时，Ingress 控制器能够动态地重新配置 HAProxy 的大部分功能，例如后端应用服务器或 pod、向上扩展或向下扩展。”

最后，v1.5 还增加了基本的身份验证功能，在任何内部服务和外部访问尝试之间提供网关，并支持入口控制器和它将流量路由到的后端服务器之间的相互 TLS 身份验证(mTLS)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>