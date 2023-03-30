# AWS EC2 容器服务，Docker 的调度层，现在有 5000 万次下载

> 原文：<https://thenewstack.io/aws-ec2-container-service-a-scheduling-layer-for-docker-now-with-50-million-downloads/>

在 AWS re:Invent today 上，亚马逊网络服务(AWS)宣布通过 EC2 容器服务(ECS)对 Docker 容器提供几乎原生的支持，EC2 容器服务是一种高度可扩展的高性能容器管理服务。

到目前为止，集装箱可以部署到 ASW。但这仅仅意味着容器可以被启动，而不能联网或协调。有了这个消息，AWS 就有可能使用 API 和其他工具，在一个由[亚马逊弹性计算云](https://aws.amazon.com/ec2/) (EC2)实例组成的托管集群上运行任意数量的 [Docker](https://www.docker.com/) 容器。

Docker 首席执行官 Ben Golub 在大会舞台上表示，AWS 推出 ECS 之前，Docker 的下载量急剧上升，现已达到 5000 万次。

据 [AWS 博客](https://aws.amazon.com/blogs/aws/cloud-container-management/)报道，这一消息意味着 Docker 上管理集装箱的人工任务正在实现自动化。这意味着用户不必安装集群管理软件、购买和维护集群硬件，或者将硬件清单与用户的软件需求相匹配。相反，现在由 ECS 处理。

用户启动一个集群，定义任务，并启动它们。ECS 围绕一个可扩展、容错的多租户基础构建，代表用户处理集群管理的所有细节。

Docker 生态系统中的网络和工具提供商 Tutum 的联合创始人 Borja Burgos 说:“很高兴看到云计算领域的知名人士对容器技术感兴趣并下注。“随着 AWS 的发布，用户现在能够在亚马逊的云上本地使用容器。基本构建块不再是 VM (EC2 实例)，而是容器。”

Burgos 说，ECS 不是“真正的”容器本地服务，因为它依赖于底层的 EC2 服务。这仍然意味着用户必须“管理”并支付基于底层虚拟机(实例)的基础架构。
最终，它是 EC2 基础设施之上的容器调度层。

> “我们正处于一个新时代的开端，其他云服务将紧随其后，实现自己的容器管理。”

AWS 博客列出了 ECS 附带的特性及其使用方法。

根据该博客，启用 ECS 的 AMI 和实例将被登记到默认集群中。如果启动到不同的集群，用户可以通过修改映像中的配置文件或在启动时传递用户数据来指定它。要启用 ECS 的 Linux AMI，只需安装 ECS 代理和 [Docker 守护进程](https://docs.docker.com/articles/basics/)。

ECS 会将新启动的实例添加到其容量池中，并按照调度程序的指示在其上运行容器。这意味着用户可以通过在集群中启动额外的 EC2 实例来增加集群的容量。

ECS 代理将在 Apache 许可下以开源形式提供。您可以将它安装在任何现有的 Linux AMIs 上，并调用将它们添加到集群中。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>