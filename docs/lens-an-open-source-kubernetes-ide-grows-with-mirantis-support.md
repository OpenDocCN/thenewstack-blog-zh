# 开源的 Kubernetes IDE lens 在 Mirantis 的支持下成长

> 原文：<https://thenewstack.io/lens-an-open-source-kubernetes-ide-grows-with-mirantis-support/>

Kubernetes 的集成开发环境(IDE)的最新版本 [Lens](https://www.mirantis.com/blog/lens-3-6-released/) 已经发布，这是自开源项目与 [Mirantis](https://thenewstack.io/?s=AND+Mirantis) 找到新支持者以来的第一次。

最值得注意的是，该更新增强了 Lens 使用 kubeconfig 文件和其他智能终端配置选项管理 Kubernetes 集群访问的方式。

Lens 使开发人员能够轻松地在他们同时拥有的多个集群之间切换。无需在集群本身上使用代理，其内置终端就可以访问 Kubernetes 命令行工具 kubectl，并与 [Prometheus](https://prometheus.io/) 集成以可视化监控统计数据。对于每个集群，终端维护正确的 kubectl 版本和上下文。

它还使开发人员能够在单一环境中的任何云上使用多个 Kubernetes 集群。

> 有了内置的智能终端，它会自动切换 kubectl 的版本以匹配当前选择的集群 API 版本，现在您可以定义您想要使用哪个目录。

[Lens 3.6](https://www.mirantis.com/blog/lens-3-6-released/) 使用 kubeconfig 文件直接作为集群引用来管理 Kubernetes 集群访问，这意味着您不再需要复制粘贴这些文件的内容来更新它们。

Lens 团队发现，许多开发人员正在使用来自托管 Kubernetes 服务提供商的第三方工具来生成他们的 kubeconfig 文件，这不一定会使它们保持更新。

有了内置的智能终端，它会自动切换 kubectl 的版本以匹配当前选择的集群 API 版本，现在您可以定义您想要使用哪个目录。受限环境中的用户发现无法使用，因为智能终端捆绑的二进制文件限制了目录访问。另一方面，可以完全关闭智能终端，并为要使用的 kubectl 二进制文件创建一个自定义路径。

### 成长中的社区

Lens 从一家芬兰公司 [Kontena](https://thenewstack.io/kontena/) 发展而来，专注于在任何云基础设施上的多个主机上运行容器化的应用程序。Lens 是 Kontena 内部开发的，作为一种管理大型在线服务的方式，它运行在 Kubernetes 发行版 Pharos 之上。

“很快，我们意识到实际上相当多的人喜欢这个用户界面。他们要求使用这种用户界面技术，也许还有其他口味的 Kubernetes。因此，实际上，我们决定去掉所有对我们自己的 Kubernetes 风格的依赖。Kontena 创始人兼前首席执行官 Miska Kaipiainen 说。但它没有获得足够的吸引力，公司资金告罄。

去年秋天雇佣了 Kontena 团队的 Mirantis 也加入了进来，当时它收购了 Docker 的企业业务 T1，作为其在公司内提高 Kubernetes 能力的努力的一部分。该公司当时表示，Kontena 的加入将“加速其在多集群管理、集群可见性和洞察力以及应用程序开发工具方面的产品路线图”。Mirantis 将利用从 Kontena 获得的知识产权为 Docker Enterprise 现有的 Kubernetes 技术服务，包括 Docker Kubernetes 服务(DKS)和万能控制飞机(UCP)。”

今年 3 月，Lens 作为开源软件在麻省理工学院的许可下发布，自此之后，它已经发展成为一个拥有 35000 名用户和 7000 名“T2”git hub“T3”天文爱好者的社区。最初的 Kontena 负责人能够保留知识产权的版权，现在已经掌握在 Mirantis 的手中，但据 Kaipiainen 说，这些都是开源的。

它的用户包括苹果、Zendesk 和 Adobe。

分析公司 Forrester 在其最近一份关于[多云容器开发平台](https://reprints2.forrester.com/#/assets/2/1681/RES157266/report)的报告中指出，该公司需要提高云原生开发人员的能力，该报告基于 Docker Enterprise 3.0 评估了 Mirantis，该平台于 2019 年发布，而不是最新版本。它对 Lens 的[支持](https://www.mirantis.com/blog/forrester-multi-cloud-container-development-platforms-wave-report-reimagined-with-docker-enterprise-container-cloud/)是它处理这个问题的一种方式。

[https://www.youtube.com/embed/epw_MjxjMYI?feature=oembed](https://www.youtube.com/embed/epw_MjxjMYI?feature=oembed)

视频

最初设计为基于网络的工具，Lens 被重新设计为一个桌面应用程序，运行在作为独立二进制安装的 macOS、Windows 和 Linux 操作系统上。

“我们发布这种系统是作为一种可以部署在集群中的系统，基本上是在任何通过网络浏览器提供这种类型的用户体验的 Kubernetes 集群之上，”Kaipiainen 在谈到 Kontena 最初的低下载率时说。

“实际上，我们联系了大多数试图安装它的用户和成功安装它的人。我们发现，实际上真正的爱好者希望使用该软件，[但]他们不一定有管理权限或角色来管理他们正在处理的群集。因此，这些群集是由他们的企业 IT 部门创建的…他们无法控制可以在群集中安装哪种类型的控制面板。

“所以对我们来说，这是一个‘啊哈’的时刻。我们意识到，实际上，有一大群人实际上是 Kubernetes 的最终用户，他们不是管理员，”Kaipiainen 说。

该公司了解到，Spotify 和 Slack 等公司一直在使用 [Electron](https://www.electronjs.org/) 包装基于网络的应用程序，以便它们可以作为原生桌面应用程序运行。

“所以我们已经想出，好吧，我们可以将 Lens UI 技术打包到一个电子应用程序中，并使用 Kubernetes APIs 与 Kubernetes 集群进行通信，”他说。

如果我们有一个能够访问 kubeconfig 文件的开发人员，我们实际上能够为用户提供这种美妙的用户体验。"

### 统一可见性

使用命令行工具 Kubectl 和其他工具，开发人员可以针对不同的技术使用 20 种不同的仪表板，显示他们希望从集群中看到的信息。

凯皮艾宁说:“基本上，我们一直试图用镜头做的是将 Kubernetes 技术和工具的所有精华打包，将它们集成起来，以真正简化 Kubernetes 开发人员的活动，如部署、运行、管理、调试、检查和观察。”。

他指出来自 VMware 的 [Octant](https://octant.dev/) 可能是其最接近的竞争对手，尽管不是 IDE，另一个流行的工具是 [K9S](https://k9scli.io/) 。Mirantis 的联合创始人兼首席执行官 Adrian Ionel 还将它与微软的 Visual Studio 进行了比较，看它能否在任何公共或私有云上轻松编写、测试和运行 Kubernetes 应用程序。

Mirantis 现任工程总监 Kaipiainen 表示，Lens 4.0 将于 10 月初问世。

该公司还将开始与其他云原生技术供应商集成插件架构，以集成他们的产品。

“我们只是刚刚触及这个工具的表面潜力，”他说。“通过扩展 API 和一切，我认为我们有无限的可能性来改善开发人员的生活。”

VMware 是新体系的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>