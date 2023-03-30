# Redis 企业来到云铸造平台

> 原文：<https://thenewstack.io/redis-cloudfoundry-group-microservices/>

[Redis](https://redis.io/) 和 [Pivotal](https://pivotal.io/labs) 联手将广受欢迎的 Redis NoSQL 数据存储的企业版带到 Pivotal 的[云铸造](https://www.cloudfoundry.org/)平台。当使用 Cloud Foundry 作为平台即服务层时，这一举措使快速部署和管理 Redis 集群作为容器映像变得更加容易。

Redis 实验室的首席营销官 Manish Gupta 表示，这一举措是为了响应大量 Pivotal 客户希望在其应用程序中使用 Redis Enterprise 的需求。Redis 已经在 Docker Hub 中变得相当受欢迎，Gupta 说 Redis 是最常被下载的数据库容器。

随着迁移到 Cloud Foundry， [Redis Enterprise](https://redis.com/why-redis/redis-enterprise/) 用户将能够更好地管理集群以及他们现有的容器和应用程序。他说，Cloud Foundry 现在被捆绑到 Redis API 中进行管理，形成了一个无缝的环境。

“我们的平台中有一个非常强大的管理 GUI。Pivotal 在 Cloud Foundry 上提供了这一功能。平台中支持的所有层对运营经理都是可见的；从平台的规模到数据的分布。该 API 从 Pivotal 一直延伸到 Redis 企业平台，后者有自己的管理层。这些对 Cloud Foundry 管理层是可见的。你可以看到数据是如何分片的，数据的健康状况如何，数据看起来是什么样的，比如有多少节点在处理这些数据，以及一个节点中有多少分片，”Gupta 说。

到目前为止，Cloud Foundry 版本是作为概念验证提供的，Gupta 说，客户已经使用该系统管理单个数据库集群中的几十个服务器。他补充说，现在该系统已经普遍可用，这些数字可以上升到具有 100 个 Redis 集群节点的系统。

Gupta 说这是 Redis 的优势之一:它适合与容器一起使用。“我认为总的来说，数据存储在这种环境下更难运作。Redis 则完全不同。我们非常适合集装箱环境。它是在一个容器环境中构造的，其中每个节点都有基本的 Redis 数据结构，在这个结构之上是企业层，它执行代理和工具、自动恢复、自动分片，作为一个容器化的节点，”Gupta 说。

[Cloud Foundry](https://www.cloudfoundry.org/) 是新堆栈的赞助商。

由[奥斯汀·尼尔](https://unsplash.com/@arstyy)通过 [Unsplash](https://unsplash.com/?photo=kQzFr1JqSKM) 拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>