# Kubernetes IDE Lens 为云原生扩展添加了一个 API

> 原文：<https://thenewstack.io/kubernetes-ide-lens-adds-an-api-for-cloud-native-extensions/>

[Honeycomb](https://www.honeycomb.io/) 正在赞助新 Stack 对 Kubecon+CloudNativeCon 北美 2020 的报道。

[Lens](https://www.mirantis.com/blog/lens-3-6-released/) ，Kubernetes 的集成开发环境(IDE)，在过去的一年里有了一些快速的增长，自从它对其部署模式进行了一些改变，[找到了 Mirantis](https://thenewstack.io/lens-an-open-source-kubernetes-ide-grows-with-mirantis-support/) 的支持，该公司在 2019 年收购了 Docker。在本月的 [KubeCon+CloudNativeCon 北美](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)大会上，Lens 团队[发布了一个扩展 API](https://www.mirantis.com/blog/lens-4-0-blog/) ，以及几个来自流行的云原生产品的预建扩展，这些扩展[由 Lens OSS 项目的联合创始人兼 Mirantis 的高级工程总监 Miska kaipainen](https://www.linkedin.com/in/miskakaipiainen/)提供。

“开始考虑扩展的主要动机是，大概在半年前，我们开始收到一些请求，比如‘我们想看看你能否为 Istio、Traefik 或 Kong 构建一个可视化系统？’所以我们认为，如果我们坚持核心核心镜头项目，并为这些 Kubernetes 原语提供上下文可见性，同时为希望将可视化扩展到这些海量技术的第三方提供丰富的 API，这似乎是一个不错的方法。我们没有足够的资源来支持 Istio 和其他数百个不同的开源项目。这就是我们如何加强与整个 CNCF 生态系统和供应商的关系。"

[https://www.youtube.com/embed/X-bhVwmp2l4?feature=oembed](https://www.youtube.com/embed/X-bhVwmp2l4?feature=oembed)

视频

关于这种增长的话题，凯皮艾宁解释说，这是一个简单的变化，使所有的差异。

“在第一个版本中，Lens 是您必须部署在集群中才能使用的东西。我们意识到，并非我们的大多数用户都没有这些集群的管理权限。“让 Lens 能够与任何 Kubernetes 一起工作，使用标准的 kubeconfig 文件进行身份验证，就像您将与您的 kubectl 一起使用一样，我想说，这真的是我们解锁采用的重大成就之一。”

现在，该项目增加了创建扩展的能力，很像流行的 Visual Studio 代码 IDE，为任何有兴趣为 Lens 用户提供额外上下文的项目和公司提供扩展 API。在发布时，安全公司 Aqua 和 Carbonetes、API 网关制造商 Ambassador Labs 和 AIOps pioneer Carbon Relay 已经提供了扩展，nCipher、Kong 和 StackRox 正在积极开发扩展。

在用户方面，目前在最新版本的 Lens 的新菜单下可以获得扩展。对于那些对开发扩展感兴趣的人，Lens 提供了许多例子，Kaipiainen 说可以在该项目的 [Slack channel](https://k8slens.slack.com) 中获得帮助。扩展本身必须打包成节点包，托管在 [npm](https://www.npmjs.com/) 仓库中。

随着扩展的增加，Kaipiainen 看到了 Lens 的未来，它远远超出了提供 CPU 使用和内存消耗等基本环境，自宣布以来，第三方的兴趣已经增长。

“我认为我们真的可以开始在 Kubernetes 以外的地方发展，”Kaipiainen 说。“到目前为止，Lens 一直只使用 Kubernetes 原语。我们可以开始看到一些扩展，使您不仅能够看到您的端口正在运行，而且，例如，让我们假设您正在运行一个 Redis 集群，只需单击一下按钮，您就可以开始检查您的 Redis 数据库并进行查询。所有这些类型的可能性现在都在我们的能力范围之内，真正从纯粹的库伯内特发展到基本上它周围的世界。”

根据 Kaipiainen 的说法，Lens 现在在 GitHub 上有超过 90，000 名活跃用户和 9，500 名观星者。

KubeCon+CloudNativeCon 和 Redis 实验室是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>