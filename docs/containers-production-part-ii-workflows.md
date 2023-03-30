# 生产中的容器，第二部分:工作流

> 原文：<https://thenewstack.io/containers-production-part-ii-workflows/>

点击

[here](https://thenewstack.io/containers-production-part-case-studies/)

系列的第一部分。

许多公司已经在大规模生产中使用容器。在前一章中，我们研究了 Spotify、DramaFever、Built.io 以及教育调查、创新和研究生院(IIIEPE)如何以及为什么使用容器。现在，让我们深入了解一下每个组织的工作流。

## 构建应用程序和管理拉取请求

在生产中使用容器的一个吸引力是能够创建一个无缝的从开发到生产的环境，这个环境可能来自开发人员的笔记本电脑，并且可以大规模地转移到测试和部署，而不会由于基础设施环境的变化而引入错误。

### IIIEPE 使用什么

教育调查、创新和研究生研究学院的首席开发人员路易斯·埃利宗多表示，在 Docker 之前，将应用程序从开发转移到生产是他们最大的问题之一。现在，开发人员构建基础映像，并公开发布到 Docker Hub。所有应用程序都有一个标准结构，包括应用程序、日志和文件子目录。这些是开发人员最常使用的子目录，而 Dockerfile、Docker Compose 的 YAML 文件和 Makefile 隐藏了开发人员不需要了解的应用程序容器环境的复杂性。

### DramaFever 使用什么

视频流媒体网站 DramaFever 将 Python 和 Django 框架用于其主站点，并致力于微服务处理功能，如图像大小调整、播放器书签和 DRM。在任一种情况下，版本化的可部署工件都作为容器映像存储和部署。

对于 DramaFever 的前运营工程师 Bridget Kromhout 来说，使用容器有助于确保位于世界各地的开发团队有一个标准的开发环境。她说容器“有助于我的团队的分布式性质。这有助于我们减少问题，因为它减少了降低我们速度的不一致的数量。”

### Spotify 使用什么

在 Spotify，开发人员被鼓励在构建期间在本地机器上使用 Java、ZooKeeper 和 VirtualBox。工程师使用 GitHub 存储和共享他们的代码和拉请求，使用 [Bintray](https://bintray.com/) 存储容器图像。

## 持续集成工作流配置

一旦开发人员编写了代码或合并了拉请求，就需要构建一个新的基础映像，然后通过 QA 的各个阶段进行测试。对于许多在生产中使用容器的应用程序环境来说，这是通过使用持续集成工具来完成的，特别是 Jenkins，以尽可能多地自动化这个过程。

### IIIEPE 使用什么

埃利宗多坚持认为，开发人员不应该在容器环境之外进行开发，然后为部署构建映像。“让詹金斯帮你做吧，”他说。

如前一章所述，IIIEPE 有两个服务器:一个运行 MaestroNG，处理 stock Docker 容器，另一个运行 Jenkins，自动执行重复的任务。

“詹金斯还允许你有一个未能取代你的 Cron 提交的历史，我对詹金斯编程，使它在每个应用程序上运行 Cron，所以你有一个日志和所有出错的历史，”埃利宗多说。

### DramaFever 使用什么

像埃利宗多一样，Kromhout 使用 Jenkins 构建所有的容器映像。“我们每周都会创建基础构建，因为 Python-Django 构建可能会花费很长时间，”她说。因此，相反，如果他们已经创建了每周的基础构建，那么开发分支的持续集成构建的时间就会减少；主 www 项目的 Dockerfile 使用“来自 www-base”。在本地工作时，开发人员从 GitHub 中的 master 获取代码，并将其安装到 docker 获取的容器中，以获得最新的构建环境。Kromhout 说这比用游民快。“詹金斯只是为整个平台构建了一个图像，它只是构建并标记了一个图像，”她说。“一致性真的很好。”

### Spotify 使用什么

戈尔丁说，Spotify 获取 Bintray 中内置的图像，然后将其部署到 AWS。然后，Helios 可以用于服务发现，但也可以与更具体、功能更全的服务发现工具(包括 SkyDNS 和 Consul)相连接。

## 编排和管理

随着公司发现容器的更多用途，编排和管理挑战也在增加。从技术上讲，这里有三个过程:首先，容器如何连接通常被称为编排。然后，需要一个调度和放置引擎来决定这些容器应该在哪些主机上运行。最后，容器管理包括注意容器是否关闭，在部署时声明服务的状态以及类似的功能。然而，这两个术语之间经常有很多模糊之处，编排经常被用作这三个功能的统称。

### IIIEPE 使用什么

埃利宗多的许多潜在的编排选择受到了限制，因为他的机构需要选择一个也可以与 Drupal 一起使用的开源解决方案，许多 IIIEPE 的 web 应用程序都是在 Drupal 框架中构建的。功能集的缺点也限制了埃利宗多的选择，尽管他从许多选项中拼凑了一些功能。例如，虽然造船厂缺乏自动管理集装箱的能力，但它作为一个查看器很有用，IIIEPE 使用它来监控其集装箱和码头服务的状态，以确定集装箱何时崩溃，并重新启动死亡的集装箱。

[cyclone slider id = " ebook-2-赞助商"]

MaestroNG 被选为他们的核心编排工具，因为它具有多主机功能、命令行界面，并使用 YAML 文件来描述一切。为了安全起见，MaestroNG 被安装在一个服务器上，并且是唯一连接到 Docker 的服务。一旦 Jenkins 完成了对新映像构建的测试，它将被推送到 IIIEPE 的私有注册中心，然后 Jenkins 使用 SSH 安全协议连接到 MaestroNG 服务器，并完成生产部署。

### DramaFever 使用什么

DramaFever 的配器目前非常简单。因为 drama fever 100%在 AWS 中，他们使用 DNS 和 ELBs，在特定的自动缩放组中启动实例，执行 docker pull 来运行必要的容器，并以特定的 ELB 进行响应。

新映像由 Jenkins 构建，经过自动和手动测试后，标记为暂存，然后通过基于 Python 的工具 fabric 生产。因此，通过 QA 的同一个 Docker 映像被推出到生产中(从分布式私有 Docker 注册中心)。

### Spotify 使用什么

编排是 Spotify 构建和使用 Helios 的核心原因。戈尔丁说，Helios 解决了一个问题，而且解决得非常好:本质上是决定在云集群网络中的何处部署容器实例。虽然 Helios 是开源的，但 Spotify 也有一个内部助手工具。为了帮助持续交付，Spotify 目前正在扩展 Helios 的功能集，以便能够显示部署了什么、由谁部署以及在哪里部署。

### 其他选择

[build . io](http://built.io/)还为他们的移动后端即服务(MBaaS)容器架构创建了自己的编排/管理层。这个管理层使用一个 REST API 作为主要的通信通道来管理新容器的设置，并且还可以检查客户配置文件并为高收入客户创建更大的容器。通过使用通过 API 连接的管理层，他们还可以让客户直接从 Built.io 产品的用户界面访问一些编排和管理功能。

## 服务发现和负载平衡器

生产中应用程序的维护需要服务发现——也就是说，洞察跨应用程序基础架构运行的容器的当前状态。然后，负载平衡器确保应用程序流量分布在多个服务器上，以确保应用程序在生产中的高性能。

### IIIEPE 使用什么

埃利宗多说，IIIEPE 使用 Consul 进行服务发现，因为 etcd 仍然需要大量的额外学习。Consul 存储应用程序的 IP、端口和状态。当 Consul 识别到应用程序的变化时，埃利宗多已经建立了一个触发器来创建一个 [Consul-template](https://github.com/hashicorp/consul-template) ，它反过来可以重新配置负载平衡器的配置。

埃利宗多一直使用 NGINX 作为负载均衡器，但计划切换到更复杂的 HAProxy。“NGINX 很棒，”他说。“我知道如何解决 NGINX 抛给你的 80%的问题。但是 NGINX 是一个 web 服务器。它可以充当负载平衡器，但这不是它最擅长的。”

### DramaFever 使用什么

Kromhout 在 Jenkins 作业中使用通过 Packer 运行的 Chef 客户端，为使用必要的 upstart 模板填充的主机实例生成 Amazon 机器映像，以便从特定的自动伸缩组启动的实例作为特定的弹性负载平衡器(ELB)的成员，获取并运行正确的 Docker 映像。Kromhout 说，使用 NGINX 的 proxy_pass 到每个微服务的不同上游 elb，允许 DramaFever 推迟更复杂的动态服务发现问题。“我们将 HAProxy 用于一些数据库连接池，但 ELBs + NGINX 在流量路由领域简化了很多。她解释说:“当你能预测集装箱将在哪里起航时，定位块就能发挥很好的作用。“当然，这意味着我们的利用率不是最佳的。如今，DramaFever 的现任运营主管 Peter Shannon 正在研究更动态的服务发现选项。应用容器集群化就是如何实现高效利用。”

## 把这一切联系在一起

现在编纂最佳实践还为时过早，但这些是新兴方法的几个例子，展示了容器生产工作流程可能是什么样子。本文中提到的一些工具不是特定于容器的技术；相反，容器使得部署代码变得几乎微不足道。

在所有情况下，最终选择的工作流将容器与一些新兴的生态系统开源工具相结合。这种方法与一些私人解决方案和自行创建的解决方案一起存在，这些解决方案解决了单个企业的应用程序编程语言、数据服务器基础架构、安全策略和持续交付承诺。

Docker 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>