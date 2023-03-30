# Docker CLI 现在可以直接进入 Amazon Web Services

> 原文：<https://thenewstack.io/docker-cli-now-has-a-direct-path-into-amazon-web-services/>

由于亚马逊弹性容器服务(ECS)和 Docker 命令行界面(CLI)之间的新集成，Docker 开发人员应该可以更容易地将他们的多容器应用程序运送到亚马逊 Web 服务。

“这消除了开发人员将他们的应用程序放到亚马逊网络服务上的一系列复杂性”，[Justin Graham](https://www.linkedin.com/in/justingraham/),[Docker](https://www.docker.com/)产品副总裁在接受新堆栈采访时说。“我们希望这两件事尽可能无缝地配合。”

[Docker Compose](https://docs.docker.com/compose/) 和 [Docker Desktop](https://www.docker.com/products/docker-desktop) [的用户将能够](https://www.docker.com/blog/from-docker-straight-to-aws/)使用 [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/) 内置的 ECS 命令在[亚马逊弹性容器服务](https://aws.amazon.com/ecs/)(亚马逊 ECS)和 [AWS Fargate](https://aws.amazon.com/fargate/) 上直接部署他们的应用。

通常，开发人员会使用 Docker Compose 来描述一个应用程序如何通过一个 YAML 文件跨多个容器映像工作。然而，在以前，将一个容器化的应用从本地开发环境移动到 ECS 需要许多不同的手动步骤。他们可能不得不离开 Docker 桌面，跳转到 AWS 界面来配置[亚马逊 VPC](https://aws.amazon.com/vpc/) 、[亚马逊 ECS 集群](https://aws.amazon.com/ecs/)、[亚马逊 ECS 任务](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definitions.html)定义，或者其他服务的设置。现在，开发人员将能够直接在 Docker CLI 中完成这些任务。

AWS 首席解决方案架构师[卡门·普西奥](https://github.com/CarmenAPuccio)在一篇详细介绍新功能的[博客文章中写道:“通过在 Docker 中创建并切换到一个新的](https://aws.amazon.com/blogs/containers/aws-and-docker-collaborate-to-simplify-the-developer-experience/)[上下文](https://docs.docker.com/engine/context/working-with-contexts/)，开发者可以通过 Docker Compose 简单地发出一个 **up** 命令，这将在 AWS 中自动创建那些资源。在本文的演示中，开发人员使用 Docker CLI 中提供的额外 ECS 语法向 AWS 上传了一个 web 应用程序。用户定义 AWS 配置文件、ECS 集群名称和 AWS 区域。

Docker Desktop Edge[的最新版本](https://hub.docker.com/signup/awsedge?utm_source=awsedge)包含了该功能的测试版，[最初作为插件](https://github.com/docker/ecs-plugin)。这一功能将被嵌入到 Docker 产品中，并于今年年底正式上市。

Docker 与 AWS 合作构建这一新功能，作为该公司与第三方服务提供商更紧密合作的战略的一部分。

“我们希望确保开发人员，无论他们在哪里运行应用程序，都有一个尽可能简单、高效和低复杂性的方法来运行这些应用程序，”Graham 说，他指的是最近与微软和 Snyk 的其他集成。

[https://www.youtube.com/embed/UE162PzO2s0?feature=oembed](https://www.youtube.com/embed/UE162PzO2s0?feature=oembed)

视频

*要了解更多信息，请查看太平洋时间今天下午 3:50 在 AWS 云容器大会上的 Docker 会议。*

亚马逊网络服务和 Snyk 是新堆栈的赞助商。

图片由 Pixabay 的 MikesPhotos 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>