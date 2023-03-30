# Crunchy Data 的 PostgreSQL 容器套件及其如何使用 Docker、Kubernetes 和 OpenShift

> 原文：<https://thenewstack.io/bringing-scalability-and-flexibility-to-postgresql-with-crunchy-data-solutions/>

[Crunchy Data Solutions](http://crunchydata.com/) 提供了一套开源容器套件，用于运行 PostgreSQL 数据库实例作为数据库即服务(DBaaS)，允许数据库插入不同的架构，包括基于 Docker、 [Kubernetes](/category/kubernetes/) 和 OpenShift 的架构。

在多伦多的 Cloud Native Day 上，Crunchy Data 的 [Jeff McCormick](https://www.linkedin.com/in/jeff-mccormick-361877) 讨论了他的公司如何创建他们所谓的“crunchy containers”，以及如何利用 Docker 和 Kubernetes 来自动构建他们的服务 [PostgreSQL](https://www.postgresql.org) 。

[通过易碎数据解决方案为 PostgreSQL 带来可扩展性和灵活性](https://thenewstack.simplecast.com/episodes/bringing-scalability-and-flexibility-to-postgresql-with-crunchy-data-solutions)

通过为 PostgreSQL 数据库创建容器的工作，McCormick 后来开始开发基本上是全方位监控套件的东西。软件包中包含的 Prometheus 开源监控软件用于收集数据数据库性能的指标。该套件最初打算在 OpenShift 上运行，但现在设计为在多种平台上运行。除了支持 Kubernetes 和 Docker，Crunchy 容器也将很快能够在 Mesos 上运行。

每个套件由八个或九个单独的服务容器组成。“每个容器内通常都有一些编排代码和附加功能，但本质上定制代码都是用 [Golang](https://golang.org/) 编写的，”他说。“很多都是用 [BASH 脚本](https://www.gnu.org/software/bash/)编写的。人们很容易获得 Docker 文件，并根据自己的需要定制或调整它们。”

PostgreSQL 本身也具备运行横向扩展工作负载的能力。最新版本[9.62](https://www.postgresql.org/about/news/1703/)包括新的同步复制功能，如组配置和同步副本的改进数据视图。通过 [postgres_fdw](https://www.postgresql.org/docs/9.6/static/postgres-fdw.html) 数据联合驱动程序，它还具有跨多个远程 PostgreSQL 服务器执行任务的能力。

“对于投资大规模云的人来说，这成为一种在其基础架构中标准化数据库部署的方式。有些人需要按需配置数据库，或者想要一个数据库即服务模型。这既是目的驱动的，也是任务驱动的，”麦考密克指出。

这些正在进行的 PostgreSQL 改进表明，可伸缩性和快速构思能力不仅被引入到应用程序开发中，还被引入到数据库工作中。

[![barcelona](img/19403431e61caee7d8e0ebecb3ae0718.png)](https://www.eventbrite.com/e/openstack-summit-pancake-breakfast-tickets-27692501016)

码头工人和[红帽](https://www.openshift.com/)是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>