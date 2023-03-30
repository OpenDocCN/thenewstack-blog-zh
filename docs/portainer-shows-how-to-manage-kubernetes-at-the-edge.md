# Portainer 展示了如何在边缘管理 Kubernetes

> 原文：<https://thenewstack.io/portainer-shows-how-to-manage-kubernetes-at-the-edge/>

如果使用正确的工具进行部署，Kubernetes 在边缘是有意义的。

在上周的 [Civo Navigate](https://thenewstack.io/steve-wozniak-on-tesla-artificial-intelligence-apple/) 会议上， [Portainer](https://github.com/portainer/portainer) 展示了它是如何简化 edge Kubernetes 部署的，使用了它自称为[的通用容器管理工具](https://thenewstack.io/an-introduction-to-portainer-a-gui-for-docker-management/)。基本上，它可以与 Docker 和 Kubernetes 一起工作，使容器化应用和服务的部署和管理更容易，Jack Wallen 在去年的评估中说。

“Kubernetes 在边缘是有意义的，”Portainer 的联合创始人尼尔·克雷斯韦尔告诉 Civo 的观众。

“Kubernetes 的一个主要好处是，我们真的有一个配方或方法来声明我们希望我们的应用程序如何运行，这就是清单，”克雷斯韦尔说。“这份清单真的改变了游戏规则。在我的职业生涯中，这是我第一次看到这样一种方式，你可以基本上声明你的应用程序是如何运行的，它在任何地方都是这样运行的。”

他解释说，虽然这可能令人不知所措，但一旦你理解了它是如何工作的，这个清单就有意义了——它可以无限重复。

“无论你在哪里运行舱单，它几乎每次都以相同的方式运行，”他说，并补充说 Portainer 将其产品作为 Kubernetes 舱单运输。他说，使用 Portainer 运行清单意味着它将在几秒钟内以非常可预测的方式运行，并且它将以同样的方式部署。

为了演示的目的，克雷斯韦尔将边缘定义为网络的边缘。

“当我们说网络边缘时，我们在这里谈论的是让应用程序更接近用户，”他说。“我们这样做是为了减少网络延迟和带宽。但整个事情就是说，我如何让应用程序靠近我的用户，让他们获得快速响应的应用程序体验，并且我为我的用户和后端系统之间的带宽支付更少的费用。”

他举了一个例子来说明为什么这在今天比以往任何时候都重要——他有一个银行应用程序，当他去美国旅行时，因为它试图访问他在新西兰的银行的后端，所以遇到了额外的延迟问题。

“每当我在这里(美国)，我的网上银行应用程序完全无法使用，因为它试图向新西兰的后端服务器发出数千个 API 请求，”他说。“延迟会破坏应用程序。因此，通过让 API 端点离用户更近，您可以获得更快的应用体验。”

## 无状态服务和 Kubernetes

edge 依赖于无状态服务，Kubernetes 工作组在帮助它过渡到更有状态的服务方面做得非常好，但是 Kubernetes 主要是围绕无状态构建的，edge 应用程序也主要是无状态的。

“它们被设计用于摄取、调谐、缓冲和缓存。它们并不是真正为保存数据而设计的，”他说。“因此，Kubernetes 是一个无状态的协调器，而 edge——无状态的工作负载——确实是一个完美的组合。这很有意义。”

将应用程序迁移到 edge 使得减少用户和后端之间的带宽成为可能；减少整体延迟；提供更快捷的 app 体验；并支持数据分离。

也就是说，在边缘部署 Kubernetes 存在挑战，他说。虽然经过认证的 Kubernetes 发行版使用一个标准化的 API，但是许多提供者希望为原生的 Kubernetes API 增加价值，这导致了锁定。他补充说，这就是为什么要小心认证和负载平衡之类的事情很重要，这可能会将开发者锁定在特定的买家身上。

克雷斯韦尔展示了一张提供商的图表，指出 [Civo](https://thenewstack.io/new-at-civo-navigate-making-machine-learning-set-up-faster/) 、 [Linode](https://thenewstack.io/birth-of-the-cloud-a-qa-with-vint-cerf-and-linodes-christopher-aker/) 和 [Digital Ocean](https://thenewstack.io/tutorial-a-gitops-deployment-with-flux-on-digitalocean-kubernetes/) 都提供原始的 Kubernetes，而没有添加会锁定你的方面。他说，Azure 和谷歌也提供原始环境，尽管它们确实提供了一些附加值，但总体来说是相当兼容的。他补充说，其他供应商可能会让“拥有一个完全转变的工作场所”变得更加困难

## 多集群 Kubernetes 管理

克雷斯韦尔说，当你部署多个集群而不是单个集群时，Kubernetes 的管理挑战就来了。

“当你达到 3 个、4 个、10 个集群时，事情开始变得有点困难，”他说。“但是，当你谈论边缘时，你真的是在谈论标准，你真的必须改变你对我如何管理这一点的想法。”

需要考虑的问题包括:

*   如何集中管理集群？
*   如何集中执行身份验证？
*   用户如何自动传播到后端集群？
*   如何在某个地方集中定义后台角色并传播这些角色？

他说，开发者需要三个主要特性:

1.  集中访问；
2.  带有监控仪表板的访问控制；和
3.  集中式部署。

“你真的必须拥有所有这些，”他说，而且你必须大规模地这样做。虽然可以逐个集群地进行，但您仍然必须考虑用户身份验证。克雷斯韦尔说:“你真的必须说，‘我想要一个单一的 API 端点，每个开发者或消费者都可以连接到它，他们的代理也可以连接到后端这就是你大规模管理事物的方式。仪表板也是如此。"

## 一个控制面板来管理边缘

克雷斯韦尔说，每个人都认为他们可以安装[普罗米修斯](https://thenewstack.io/prometheus-at-10-whats-been-its-impact-on-observability/)或[格拉法纳](https://thenewstack.io/grafana-shows-new-observability-projects-at-observabilitycon/)并拥有一个监控仪表板——但你不想有 47 个不同的仪表板打开。

“你想尝试从宏观上全面了解集群的位置。你可以用普罗米修斯和格拉夫纳做到这一点，但你必须这样设计，”他说。“你不能只在每个集群中不安装它。是的，您必须安装 edge，即 Prometheus edge 代理，并将流发送回中央 Prometheus 实例。你必须正确配置。所以你必须换个角度思考。批量部署实际上相当复杂。”

他补充道, [GitOps](https://thenewstack.io/does-the-gitops-emperor-have-no-clothes/) 将会有所帮助，但它不会让你完全达到目的，他特别指出了一个[Chik-fil——一个由 1000 个集群组成的展示项目](https://medium.com/chick-fil-atech/enterprise-restaurant-compute-f5e2fd63d20f),他们在那里开始使用 GitOps，并且“很早就发现，你不能只是部署 GitOps 并祈祷它会更新，”他说。“实际上，您必须有一个集中的仪表板来查看所有这些部署的当前状态。”

他说，Portainer 面临着同样的挑战，并增加了工具来管理这些集群，以及身份管理和访问管理，从一个集中的仪表板，克雷斯韦尔说。

“Portainer 具有高度的抽象性；“我们努力让事情变得非常简单，”他说，“我们努力成为您管理 Kubernetes 所需的一个工具…因此，完整的 Kubernetes API 代理、多集群管理、集中式身份管理和仪表板，监控您需要的一切，以便基本上在大规模生产中使用 Kubernetes。”

克雷斯韦尔和 Portainer 的 IT 销售和业务发展主管 Adolfo Delorenzo 演示了 Portainer 如何在大约两分钟内通过 Civo 支持的三个不同地点(伦敦、纽约和法兰克福)向观众直播，从一个仪表盘管理优势。

“我们的客户拥有超过 50，000 个环境。克雷斯韦尔说:“我们的一个客户需要我们在今年年底前支持 125，000 个集群。

Civo 支付了 Loraine Lawson 参加会议的差旅费和住宿费。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>