# AWS App Runner:一个容器原生平台即服务

> 原文：<https://thenewstack.io/aws-app-runner-a-container-native-platform-as-a-service/>

“易于使用”和“云原生计算”并不矛盾，但很接近。当然，还有 Heroku，这是一个基于容器的平台即服务(PaaS)云，以及许多初创公司。现在[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)，已经和 [AWS 应用程序运行者](https://aws.amazon.com/apprunner/)一起加入了这场竞争。

这是一个完全托管的容器应用程序服务。它的工作是让客户只需点击几下鼠标，就能更容易、更快地构建、部署和运行容器化的 web 应用程序和 API。在 AWS App Runner 的罩下，所有操作，如供应、扩展和管理容器编排、负载平衡和持续集成/持续交付(CI/CD)管道，都由该服务处理。您不需要担心服务器或 Kubernetes 集群。

AWS 承诺您只需提供他们的源代码、容器映像或部署管道，AWS App Runner 会完成所有其他工作。这包括构建和部署、负载平衡网络流量、按需扩展容量、监控应用健康状况、流量加密等。

简而言之，正如 AWS 的容器和无服务器产品营销负责人 Scott Sanchez 所说，“App Runner 提供了开发人员构建和部署应用程序所需的整个 DevOps 后端。”

这听起来好像我们以前听过这个承诺。嗯，是的，我们有。叫[弹力豆茎](https://aws.amazon.com/elasticbeanstalk/)。但是，当你仔细比较它们时，你会发现 App Runner 做得更多。例如，App Runner 会为您设置安全的 HTTPS 连接。

不过最让我想起的是[谷歌云平台(GCP)](https://cloud.google.com/) 的[云运行](https://cloud.google.com/run)。一些了解该项目的人透露，AWS 开发人员确实考虑过 Cloud Run。当然，易用系统的想法并没有什么新奇之处。

Cloud Run 和 App Runner 有一个值得注意的区别。如果对应用程序的服务没有需求，Cloud Runner 使您能够缩减到零个实例；App Runner 不支持该用例。当然，您可以手动暂停它，但是这违背了完全自动化服务的目的。GitHub 上的 [App Runner's roadmap 中有一个请求，要求增加扩展到零的能力](https://github.com/aws/apprunner-roadmap/issues/9)。

当然，如果你想更好地控制云的底层基础设施服务，你来错地方了。这是为那些想要全面管理容器服务的客户准备的。如果您想将现有的代码或容器库转移到 AWS，这是为您准备的。例如，如果您的 IT 团队和开发人员了解他们的应用程序，但没有在云上部署和管理容器的经验，您可能会希望查看 App Runner。

除了最终迁移到云的最终用户，另一个应用程序跑步者受众是 AWS 独立软件供应商(ISV)。例如， [ZS Associates](https://www.zs.com/) ，一家生物技术和制药领域的全球专业服务公司，认为他们将能够通过 App Rubber 更快地交付他们的应用。【takes 云工程架构师 Bharath Sundararaj 表示，“我们对 AWS App Runner 感到兴奋，因为它可以帮助我们缩短向客户交付解决方案的时间。AWS App Runner 抽象出了管理和配置基础设施的需求，这意味着我们可以快速从想法转向生产。”

[Burzin Patel](https://www.linkedin.com/in/burzinpatel/) ， [HashiCorp](https://www.hashicorp.com/) 的全球合作伙伴联盟副总裁从稍微不同的角度表示同意。HashiCorp 因其作为代码软件工具 [Terraform](https://www.terraform.io/) 的开源基础设施而闻名，它将 App Runner 与 Terraform 结合在一起。Patel 说，这“意味着”，开发人员可以更快、更容易地部署生产云应用，只需配置和管理更少的基础设施。”

在底层，您的计算由 AWS 的无服务器计算引擎 [AWS Fargate](https://aws.amazon.com/fargate/) 自动部署、扩展和管理。AWS 承诺“App Runner 采用 AWS 运营和配置最佳实践构建，包括自动化安全部署(在实时流量被路由到新应用环境之前对其进行监控和测试，以最大限度地减少因应用版本变化而造成的中断)和健康检查。此外，AWS App Runner 根据传入的请求对流量进行负载平衡，并根据流量模式自动调整资源。不需要使用 AWS App Runner 构建和配置 CI/CD 管道，因为它会自动检测代码或容器映像的更改，并部署新版本的应用程序。此外，通过配置内存来保持空闲应用程序的热度，AWS App Runner 消除了冷启动，并提供了一致的应用程序响应时间。”

AWS App Runner 已经在几个主要的 AWS 地区发布。有美东(N. Virginia)，美西(Oregon)，美东(Ohio)，亚太(东京)，欧洲(爱尔兰)。它将很快在其他地区推出。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>