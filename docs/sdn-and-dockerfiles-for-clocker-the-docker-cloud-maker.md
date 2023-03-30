# Docker 云制造商 Clocker 的 SDN 和 Docker 文件

> 原文：<https://thenewstack.io/sdn-and-dockerfiles-for-clocker-the-docker-cloud-maker/>

Clocker 的最新预发布版本现已发布，版本为[0 . 7 . 0-快照](https://github.com/brooklyncentral/clocker)，以及稳定发布版本 [0.6.2](https://github.com/brooklyncentral/clocker/releases/v0.6.2/) 。Clocker 是一个 [Apache Brooklyn](http://brooklyn.io/) 应用，它简化了云中 [Docker](http://docker.io/) 上应用蓝图的部署、管理和编排。要阅读 Clocker 的介绍，请参见 Cloudsoft 博客上的 clock er——用 Apache Brooklyn 创建 Docker 云文章。

### 新功能

0.7.0 版本建立在之前稳定的 0.6.2 版本的基础上，该版本包含了许多基于用户反馈的错误修复和改进，并纳入了一些新功能，如亲和力策略和对底层 Docker 引擎和容器的更好控制。特别是 0.6.2 充分利用了本地 Docker 映像库，以便利用快速启动时间，这是容器技术优于虚拟机的一大优势。Clocker 的有用之处在于，这个特性对于任何 Brooklyn 实体都是自动可用的，而不必为每个服务或应用程序组件手工创建新的映像。

### 自动生成 Docker 图像

Clocker 在部署实体时在后台创建映像。Brooklyn 实体的正常流程是从下载的`.tgz`档案中安装它们，或者运行一些 APT 或 Yum 命令来设置环境，这对于该类型实体的所有实例都是通用的，然后为特定位置定制环境并启动服务。使用 Clocker，在安装阶段之后，我们执行`docker commit`命令并保存图像数据以备再次使用。这意味着特定 Docker 主机上的第二个和更多 dome 类型实体的容器将使用该映像并对其进行定制，从而节省网络流量和安装时间。目前，这仅限于在主机内共享，但 Clocker 0.8.x 还将包括将图像`docker push`到远程存储库的能力，以及从相同或通过 jFrog 的 [Artifactory](http://www.jfrog.com/confluence/display/RTF/Docker+Repositories) 、 [Docker Hub](http://hub.docker.com/) 、 [quay.io](http://quay.io/) 等的`docker pull`能力。如果您有一个预先配置了一组 Docker 映像的映像(比如 AMI ),那么您也可以在启动一个实体时使用它们的 id，达到类似的效果。

### Dockerfile 文件支持

Clocker 0.7.0 还允许部署仅由 Dockerfiles 定义的应用程序，而不需要使用可能不可用的特定 Brooklyn 实体。这是通过将 Docker 文件和相关资源打包到一个归档文件中实现的，该归档文件可以部署到 Docker 主机并用于构建映像。有用的是，这个归档文件可以从 GitHub 上的 [Docker 注册表](https://github.com/docker-library/)的签出文件中自动生成。使用这种技术的应用蓝本示例将在 0.7.0 版本中提供。

### SDN 支持

0.7.0 中最有趣的新特性可能是增加了软件定义网络或 [SDN](https://en.wikipedia.org/wiki/Software-defined_networking) 功能。我们使用的是来自 Zettio 的家伙们的 [Weave](https://github.com/zettio/weave/) 开源项目，它是专门为 Docker 设计的。

> Clocker 跟踪部署的每个容器，并将它们连接到 Weave 网络，控制 IP 地址的分配并配置部署的实体，以便它们可以使用这些信息。

由于 Weave 充当基于软件的网络交换机，通过 TCP 和 UDP 用户空间网络连接所有 Docker 主机，因此即使在对网络控制最少的云虚拟机中，也可以获得 SDN 的优势。Weave 允许不同主机中容器上的服务无缝通信，即使存在中间代理实体，如 Erlang portmapper 守护程序，它很难通过 Docker 正常进行端口转发。因为 Clocker 负责分配 Weave 网络 IP 地址，所以它可以确保容器的地址保持不变，即使在重新启动或移动到不同的主机后也是如此，从而使应用程序在面对故障时具有更强的恢复能力。Clocker 还使用 [DNSmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html) 服务在私有名称空间中提供名称解析，这使得通过 Docker 的端口转发访问服务器更加有效。

### 基于策略管理

Clocker 环境还更多地利用了底层 Brooklyn 平台的功能，0.7.0 将包括处理重启故障容器及其相关服务的策略，以及扩展 Docker 主机集群以为新容器提供持续空间的能力。目前，在 0.6.2 版本中，当新的 Docker 容器需要创建新的 Docker 主机时，部署必须阻塞，直到底层云可以提供合适的虚拟机，这一过程需要几分钟而不是几秒钟。

### 布鲁克林 YAML 支持

Brooklyn 提供的另一个新机制是在 CAMP blueprint YAML 文件中指定和配置任意对象的能力。这在另一篇博文中有所描述，并且是 0.7.0 中使用的供应和放置策略配置的基础。以前版本的 Clocker 只允许为每个实体或整个基础设施定义单个布局策略。

多种策略的使用允许对容器供应等式的供应侧采取更加细致入微的方法。例如，可以使用定义每台主机最大容器数的策略来配置基础架构，并防止部署到 CPU 负载过高的主机。然后，各个实体可以通过指定它们的 CPU 内核和 RAM 需求或亲缘关系和地理限制来扩充这种策略。放置策略由供应策略加入，当没有为容器找到合适的主机时，供应策略修改用于创建运行 Docker 引擎的虚拟机的标志。

### 时钟进化

Clocker 的下一个版本将扩展 Docker Hub 和存储库集成，以允许访问私有存储库，这将通过对现有 jclouds-labs 驱动程序的扩展而不是 CLI 来提供。jclouds 驱动程序是 Clocker 的重要组成部分，它允许容器以与虚拟机相同的方式暴露给 Brooklyn。

另一个与核心 Brooklyn 软件的改进一起开发的特性是自托管时钟实例的能力。这将允许启动一个 Clocker 实例，该实例使用一个已经在本地主机(或云中)上运行的 Docker 引擎，并且可以选择在该 Docker 实例上的一个新容器内运行 Brooklyn 控制平面本身。我们从用户那里得到的许多要求之一是使初始体验更容易，我们希望这将是朝着正确方向迈出的一步。
[![Alice-in-wonderland-clock-cool-photography-Favim.com-630749](img/40c9031c4c74131cd25c1ab85b837f3c.png)](https://thenewstack.io/wp-content/uploads/2014/10/Alice-in-wonderland-clock-cool-photography-Favim.com-630749.jpg) 
在最近一次硅谷开发者大会上，我做了一个[演讲](http://speakerdeck.com/grkvlt/clocker-evolution)，我问了几个与 Clocker 未来发展相关的问题。Weave 集成是一个很大的进步，但它不是 Docker 唯一的 SDN 解决方案。Fig 和 Kubernetes 表明，Clocker 在容器领域并不孤单，可能还有更多服务来满足各种需求。然而，正如 Dockerfiles 用于定义单个容器一样，描述多主机容器集的标准将是一件有用的事情。对于 Clocker 和 Brooklyn 来说，答案是 [Oasis CAMP](https://www.oasis-open.org/committees/camp/) ，但谷歌可能有其他想法。

最后，软件的用户与设计和构建软件的工程师不是同一批人，Clocker 和 Docker 中总会缺少一些可以改善用户体验的功能，所以请告诉我们这些功能是什么:

*   Docker 网络将走向何方？
*   Docker 编排的未来如何？
*   Docker 还有其他可以提高可用性的缺失特性吗？

保持这些想法并通过 [@grkvlt](https://twitter.com/grkvlt) 联系我。

### 了解更多信息

更多关于布鲁克林的详细文档和信息可以在 Apache Brooklyn 的主网站上找到。Clocker 托管在 GitHub 的 [brooklyncentral/clocker](https://github.com/brooklyncentral/clocker/) 上，clocker.io 上有一个快速入门指南。您可以在[孵化器-brooklyn-dev](https://mail-archives.apache.org/mod_mbox/incubator-brooklyn-dev/) 邮件列表上提供任何意见或问题的反馈，或者将[问题](https://github.com/brooklyncentral/clocker/issues/)添加到 Clocker GitHub 资源库。如果你有一个改进或新特性的想法，只需[分叉](https://github.com/brooklyncentral/clocker/fork)代码并发出一个拉请求！

Andrew 是云软的高级软件工程师，是开源项目(包括 jclouds 和 Apache Qpid)的贡献者，也是 Apache Brooklyn 项目的创始人之一。感兴趣的领域包括分布式系统、虚拟化、消息传递、信息安全和 LOLcats。在加入云软之前，Andrew 曾在多家投资银行担任软件工程师和安全顾问，在 IT 行业拥有二十多年的工作经验。