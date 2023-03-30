# HAProxy 如何简化 Kubernetes 入口控制

> 原文：<https://thenewstack.io/how-haproxy-streamlines-kubernetes-ingress-control/>

2016 年，当[法国 Métropole Television](https://www.6play.fr/m6) (M6)的数字媒体部门直播欧洲足球锦标赛(UEFA Euro)并且法国队进入决赛时，随着越来越多的用户涌入观看，基础设施运营团队变得越来越紧张。

“我记得我们正在经历的巨大事件可能会使我们的平台崩溃的恐惧，”M6 行动负责人 [Vincent Gallissot](https://twitter.com/vgallissot) 和他的九名船员说，他[在 HAProxy 2019 上回忆道](https://youtu.be/NmStcGBkXmQ)。他们不停地观察 Grafana 仪表板，寻找潜在的异常点。

然而，最后什么坏事也没发生。“我们最后喝了啤酒，吃了披萨，”他说。但是 Gallissot 不想再次经历如此紧张的经历，因此启动了一项将 M6 迁移到云的计划。

像许多应对流量激增的组织一样，M6 决定将 Kubernetes 作为多云架构的平台，以简化轻松扩展和缩减流量的过程。Kubernetes 设置的最关键部分之一是将传入流量路由到适当的服务。

Kubernetes 本身提供了一个选项来捕获管理负载平衡所需的[信息](https://www.youtube.com/watch?v=GhZi4DxaxxE)，使用与管理其他资源相同类型的 Kubernetes 配置文件。Kubernetes 的入口功能充当第 7 层负载平衡器，提供了一种将面向客户的 URL 映射到后端服务的方法。用户在名为“入口资源”的 Kubernetes 定义文件中定义规则，然后由 [Kubernetes 入口控制器](https://thenewstack.io/kubernetes-ingress-for-beginners/)执行。

令人惊讶的是，[最终确定](/kubernetes-ingress-for-beginners) [Kubernetes 入口 API](https://kubernetes.io/docs/concepts/services-networking/ingress/) 的工作仍在进行中，这将为第三方负载平衡器和代理提供一种与 Kubernetes 接口的标准方式。因此，选择正确的入口控制器对于确保平稳运行至关重要。

## 简单

HAProxy 首席解决方案架构师 Baptiste Assmann 在接受 New Stack 采访时说:[说到管理分布式系统，简单是一个关键因素。Baptiste 一直在与移动信息和通知公司](https://twitter.com/baptisteassmann) [Batch](https://www.batch.com) 合作，该公司不得不扩大其负载平衡业务，以在新冠肺炎危机期间支持法国政府。

像 M6 一样，Batch 已经做好了应对流量激增的准备:选举、体育和其他受欢迎的活动通常会导致流量激增。法国政府需要让民众了解新冠肺炎，这给该公司带来了迄今为止最大的挑战，预计流量将增加 20 倍。

预见到这样的流量激增，M6 将服务组件打包在 Kubernetes pods 中，并通过 [HAProxy Kubernetes Ingress 控制器](https://www.haproxy.com/products/haproxy-enterprise-kubernetes-ingress-controller/)管理负载平衡，而 Kubernetes 则扩展服务以满足更高的需求。

运行 Kubernetes 的挑战在于，由于它动态地移动工作负载，服务本身的 IP 号也在不断变化，既包括内部“东西”流量，也包括来自外部用户的请求。因此需要某种代理服务器来跟踪服务单元。此外，随着流量的增加，Kubernetes 通过生成额外的服务副本做出响应，也需要管理额外的 pod 并向其发送流量。这可以很容易地通过代理服务器或负载平衡器来完成，它也可以作为 API 网关。

Baptiste 建议，默认的 Kubernetes 入口控制器是基于 NGINX 网络服务器的[，尽管这个设置有一些限制。“我们的客户部署 HAProxy Ingress 控制器，因为它比默认的 NGINX Ingress 控制器具有更好的性能和更丰富的功能，”他说。](https://kubernetes.github.io/ingress-nginx/)

HAProxy 入口控制器提供速率限制、IP 白名单、添加请求和响应报头的能力以及连接排队，以便后端 pod 不会过载。HAProxy 支持许多负载平衡算法——每种算法都适用于特定类型的负载分布——包括循环法、最少连接数、几种基于哈希的算法和随机选择。

Baptiste 说:“能够将这些功能卸载到入口控制器意味着您的所有服务都可以立即使用它们。HAProxy 入口控制器是一个 Golang 二进制文件，在每个 Kubernetes 集群中与 HAProxy 容器一起运行。它监视对象并相应地修改 HAProxy 配置。HAProxy 权限内的每个应用程序都有一个注释，用 YAML 代码定义并存储在应用程序的存储库中。

运行时 API 可以动态地在 HAProxy 配置中添加或删除服务端点(pods ),提供了在零停机时间内快速扩展 Kubernetes 服务的能力。HAProxy 还提供了一组关于流入集群的流量的丰富指标:跟踪请求率、响应时间、活动连接、成功与错误响应的统计数据，以及通过的数据量。

## 云迁移

在迁移到云之前，M6 的数据中心流量通过一组 Varnish 服务器路由，NGINX 服务器转发 HTTP、PHP-FPM 和 NodeJS 调用。总共约有 30 项微服务在 VMware ESX 管理的集群上运行。

为了转移到云，M6 部署了 Terraform 来控制 AWS 或谷歌云和 Kubernetes 中的资源，这些资源本身由 KOPS 管理。它还可以管理快速内容传递网络。在最好的基础设施即代码传统中，M6 的配置保存在 GitHub 存储库中。每个托管服务(如缩略图生成器)都有自己的 Terraform 文件。Jenkins 控制着 CD 管道和 Docker 映像测试。Helm 提供了在 Kubernetes 集群中部署映像的说明。当一个新项目需要数据库或其他资源时，开发人员可以简单地向存储库提交一个 pull 请求。

为每个应用程序运行 AWS 弹性负载平衡器被证明是非常昂贵的。该公司实际上最大限度地增加了每个账户可以使用的 elb 数量。因此，该公司转而使用 HAProxy Ingress 控制器。

“我们通过入口控制器监视 Kubernetes 集群，”他说。“我们知道集群内部运行的一切。我们能够使用 Prometheus exporter 在节点级、服务级和容器级观察指标。因此，如果某个东西失败了，我们知道它失败在哪里。

[https://www.youtube.com/embed/NmStcGBkXmQ?feature=oembed](https://www.youtube.com/embed/NmStcGBkXmQ?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>