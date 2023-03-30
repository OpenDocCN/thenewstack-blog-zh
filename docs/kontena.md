# Kontena，受 Docker Swarm 和 Kubernetes 的影响，但程度不同

> 原文：<https://thenewstack.io/kontena/>

用他们自己的话说，“Kontena 是一个开源系统，用于在任何云基础设施上的多个主机上部署、管理、扩展和监控容器化的应用程序。它的主要目标是运行由多个容器组成的应用程序，比如弹性的分布式微服务。”

在 Docker 编排霸权的持续战斗中，我们已经看到了许多不同的参与者，如 Google 及其 Kubernetes Docker 编排平台，Docker 及其新的编排工具，以及许多其他人。虽然 Docker-land 中出现的大多数工具都是开源的，但它们通常都是由更大的公司支持的。这不一定是一个问题，除非有大型企业支持者的开源项目通常会变得更难让企业以外的人做出贡献——正如最近的 io.js / Node.js 问题 中所看到的——并且它们可能会朝着企业赞助商的特定需求过度设计。

与此相反，Kontena 是由最近成立的位于芬兰的 Kontena 公司创建的。代码库比 Kubernetes 小一个数量级，架构也更简单。Kontena 的架构受到 Docker Swarm 和 Kubernetes 的影响，因此它有机会从这些项目的错误和成功中学习。

解锁 Docker Swarm 和 Kubernetes，Kontena 是用 Ruby 而不是 Go 编程语言实现的。由于 Kontena 受到 Ruby 的影响——也可能受到 Rails 社区协会的影响——它重视约定胜于配置。因此，您会看到 Kontena 配置文件相当简洁明了。像 Kubernetes 一样，它在比容器更高的抽象层次上工作；Kontena 的原始构建组件被称为服务。Kontena 架构的其他主要组件是网格、服务、主节点、主机节点和 Kontena CLI。

## 网格

网格是 Kontena 系统的最外层容器。它使用 Weave 和 OpenVPN 提供了一个覆盖网络，允许跨主机的服务间通信。开箱即用——至少在 Kontena 发布时，因为 Docker 目前正在开发一个网络解决方案——Docker 没有提供跨主机通信的方法。同一台机器上的容器可以使用 Docker 链接相互通信，但是让容器跨主机通信更加特别，因此需要像 Weave 这样的覆盖工具。VPN 组件非常有用，它允许您直接连接到 Kontena master 进行管理。简而言之，网格允许您将所有节点视为在同一个本地网络上。

## 服务

服务是 Kontena 使用的另一个构造。对于那些熟悉 Kubernetes 的人来说，您将会看到对 Kubernetes 的服务构造的许多熟悉之处。在 Kubernetes 和 Kontena 中，服务背后的思想是容器为现代软件应用程序提供的抽象不够。这是因为大多数现代软件应用程序都是多容器的，这些容器之间的特定关系通常非常重要。

容器的另一个问题是它们本质上是短暂的，因此你不应该对特定的容器有任何严格的依赖。即使容器获得了单独的 IP 地址和端口，当单独的容器离线时，这也没有多大帮助。使用 Kontena，您可以启动服务而不是容器。然后，Kontena 将管理和扩展作为服务一部分的单个容器。

服务的另一个很好的特性是你可以声明你的服务是有状态的还是无状态的。虽然无状态架构有很多好处，并且通常更容易理解和管理，但是它们通常是不切实际的。数据库服务本质上是有状态的。大多数其他 Docker 编排系统都没有针对有状态组件的特定设施。在实践中，Kontena 将自动安装和管理有状态服务的 Docker 数据卷。这是一个非常好的特性，因为使用 Docker 的本地工具管理卷会变得相当复杂。此外，Kontena 使您能够将服务链接在一起，这非常适合基于现代微服务的架构。

## 主节点

与 Kubernetes 类似，Kontena 采用主从架构。您可以通过一个主节点管理 Kontena，还有几个从节点运行您的底层服务/容器。这个想法是，一个组织或团体将有一个主节点，通过它完成所有的管理任务，如果需要的话，创建多个网格。简而言之，这意味着主机到网格是一对多的关系。与其他一些容器编排解决方案不同，这个主节点不提供任何底层处理能力，其目的纯粹是为了管理和提供审计日志。Kontena 的下一个构造称为主机节点，它提供处理能力并运行物理 Docker 容器。

## 主机节点

每个主机节点都是一个实际的裸机或虚拟 Linux 机器，比如 AWS EC2 实例或 DigitalOcean Droplet。每个主机节点被分配给一个(且仅一个)网格，并通过安全的 web 套接字与主节点通信。Kontena 可以配置为在需要额外容量时自动供应和分配新节点到网格。当流量降低时，Kontena 也可以释放主机节点。所有日志记录和统计数据都由主节点保存，因为主机节点也可能是短暂的。

## Kontena CLI

让我们快速了解一下 Kontena 是如何定义应用程序架构的。如果你玩过 docker-compose 或者 fig，你会发现配置 Kontena 非常直观。虽然不是一对一的匹配，但 Kontena 的 kontena.yml 文件非常接近 docker-compose.yml 文件。事实上，您甚至可以有一个基本的 docker-compose.yml 文件，然后您可以使用 kontena.yml 文件来扩展和引用它。例如，假设我们有一个从本地 docker 文件构建的应用程序，想要链接到一个 mySQL 数据库映像:

```
app:  
  build:  .
  links:
    -  db:db
db:
  image:  mysql:5.6

```

然后我们可以使用并扩展上述 docker-compose.yml 文件到一个 Kontena 服务:

```
app:
  extends:
    file:  docker-compose.yml
    service:  app 
  image:  registry.kontena.local/app:latest
db:
  extends:
    file:  docker-compose.yml
    service:  app
  image:  mysql:5.6

```

在一个日益复杂的容器编排软件世界中，看到一个注重直观性和简单性的解决方案令人耳目一新。看到 Kontena 为该领域带来的一些新特性也是令人兴奋的，比如它对有状态容器的内置支持。现在说它是否会成为容器编排领域的下一件大事还为时过早，但我对它在容器领域掀起波澜寄予厚望。

Docker 和 Weaveworks 是新堆栈的赞助商。

特征图片:[opensource.com](https://www.flickr.com/photos/opensourceway/)的[参与式架构](https://www.flickr.com/photos/opensourceway/7496799718/)在 [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 下获得授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>