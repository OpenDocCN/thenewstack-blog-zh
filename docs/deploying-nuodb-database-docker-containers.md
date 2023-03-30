# 在 Docker 容器中部署 NuoDB 数据库

> 原文：<https://thenewstack.io/deploying-nuodb-database-docker-containers/>

[](https://www.nuodb.com/)

 [本·希金斯

作为产品洞察的 DevOps 工程师，本·希金斯负责开发在基于云和基于容器的环境中部署 NuoDB 的工具、自动化和最佳实践，特别关注微服务架构。Ben 从事云技术工作超过 17 年，包括在 Rackspace、Attenda 和 Pega 担任云专家。](https://www.nuodb.com/) [](https://www.nuodb.com/)

在 NuoDB，我们不仅努力改进我们的弹性 SQL 数据库引擎，还努力让开发者更容易使用它。NuoDB 是一个用于基于云和基于容器的环境的 SQL 数据库，具有可伸缩性和容错性，能够在分布式架构中进行负载平衡。

我们提供了一个运行在 CentOS 7 上的 NuoDB Docker 容器。该容器可通过 [Docker Hub](https://hub.docker.com/) 获得，我们将不断进行更新，以提高部署到每个云环境中的便利性。

要获得 NuoDB 的副本，请从以下 repo 中执行 docker pull。

```
docker pull nuodb/nuodb-ce:3.0.0

```

## 启动命令

如果你不熟悉 NuoDB 的架构，请阅读我们的架构白皮书(gated)。您还可以查看我们的电子书，了解 NuoDB 和 Docker 如何适应(非门控)高级架构讨论。

TL；该架构的灾难恢复版本是将 NuoDB 分为三个组件。这使您可以利用 AWS 的自动扩展组或 Kubernetes 的自动扩展 pod 等服务来提高 NuoDB 的事务引擎(tes)和存储管理器(SMs)的吞吐量和高可用性。因此，我们将 NuoDB 配置为将每个组件进程作为自己的容器来启动。

它们不必位于同一个主机上，但需要位于同一个覆盖网络上才能相互通信。或者，您可以将主机端口映射到容器，以便通过更大的网络进行连接。我们还建议您将 TE 容器放在与应用程序相同的主机上。这将允许您的应用程序与您的缓存数据库进行本地通信，中间没有网络中继。

以下是 NuoDB 的三个组件:

*   代理——用于管理 NuoDB 的域状态和负载平衡。
*   存储管理器(SMs) —用于数据归档。SMs 负责确保数据持久性和磁盘复制。
*   事务引擎(TEs) —作为数据表的端点和缓存。TEs 基于内存并管理事务处理。

让我们通过首先启动代理来启动 NuoDB。代理是 NuoDB 及其域状态同步的单一固定点。SM 和 TE 需要随时知道在哪里可以找到代理，所以一旦代理容器启动，我们将获取代理的 Docker 网络地址。

从命令行运行以下命令。参数定义在 docker 运行命令之后。

```
docker run  -d  \
-e  "DOMAIN_PASSWORD=bird"  \
-e  "NODE_TYPE=BROKER"  \
-e  "BROKER_PORT=48004"  \
-e  "NODE_REGION=local"  \
-e  "AGENT_PORT=48004"  \
-p  48004:48004  \
-p  8888:8888  \
--name broker  \
nuodb/nuodb-ce:3.0.0

```

通过检查集装箱获取集装箱的 IP 地址:

现在启动 SM 和 TE。将< broker_ip >替换为您的经纪人的 docker 网络 ip。

```
docker run  -d  \
-e  "DOMAIN_PASSWORD=bird"  \
-e  "BROKER_PORT=48004"  \
-e  "NODE_REGION=local"  \
-e  "PEER_ADDRESS=&lt;broker_ip&gt;"  \
-e  "AGENT_PORT=48004"  \
-e  "NODE_TYPE=SM"  \
-e  "NODE_PORT=48005"  \
--name sm  \
nuodb/nuodb-ce:3.0.0
docker run  -d  \
-e  "DOMAIN_PASSWORD=bird"  \
-e  "BROKER_PORT=48004"  \
-e  "NODE_REGION=local"  \
-e  "PEER_ADDRESS=&lt;broker_ip&gt;"  \
-e  "NODE_TYPE=TE"  \
-e  "NODE_PORT=48005"  \
-e  "AGENT_PORT=48004"  \
-p  48005:48005
--name TE  \
nuodb/nuodb-ce:3.0.0

```

论据:

## 正在连接到 NuoDB

如果您没有在本地下载并安装 NuoDB 二进制文件，您将需要在 docker 容器中访问 nuodbmgr。首先，使用下面的命令登录 docker 容器:

```
docker exec  -it broker  /bin/bash

```

下面的命令将把您连接到您的 NuoDB 实例。

```
/opt/nuodb/bin/nuodbmgr  --broker localhost  --password bird

```

为了开发和测试您的应用程序，您可以在同一个容器中启动所有三个 NuoDB 组件。下面是运行命令:

```
docker run  -d  \
-e  "DOMAIN_PASSWORD=bird"  \
-e  "AGENT_PORT=48004"  \
-e  "NODE_TYPE=ALL"  \
-e  "BROKER_PORT=48004"  \
-e  "NODE_REGION=aws"  \
-p  48004:48004  \
-p  8888:8888  \
nuodb/nuodb-ce:3.0.0

```

## 接下来呢？

现在您已经有了一个正在 Docker 中运行的 NuoDB 实例。从这里开始，你可以做更多的事情。有一点需要注意——我上面概述的一切都是基于带有瞬态文件系统的瞬态容器。要讨论容器中的持久性，您可以看看这个博客，并向下滚动到标题为“Docker 中的‘D’不代表持久性”的部分。

如果你想扩展你的处理能力，我们的社区版(我们放在 Docker Hub 上的)可以支持三个事务引擎。单击此处了解有关开始使用 NuoDB 的更多分步信息。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>