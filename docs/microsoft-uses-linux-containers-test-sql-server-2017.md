# 微软如何部署 Kubernetes 来加速在 Linux 上测试 SQL Server 2017

> 原文：<https://thenewstack.io/microsoft-uses-linux-containers-test-sql-server-2017/>

当微软 SQL Server 团队开始为 [SQL Server 2017](https://www.microsoft.com/en-us/sql-server/sql-server-2017) 开发支持 Linux 的[时，他们的整个测试基础设施自然都在 Windows Server 上(使用部署在 Azure 上的虚拟机)。他们不是简单地为 Linux 复制那个环境，而是使用](https://thenewstack.io/sql-server-2017-brings-microsofts-database-linux-container-worlds/) [Azure 容器服务](https://azure.microsoft.com/en-us/services/container-service/)来生产一个全自动测试系统，该系统将七倍多的实例打包到相同数量的虚拟机中，运行速度至少是两倍。

“我们对 SQL Server 进行了成千上万次测试，我们决定在 Linux 上测试 SQL Server 的方式是采用我们自己的故事，”SQL 项目经理 [Tony Petrossian](https://twitter.com/tonypetrossian) 告诉新堆栈。“我们自动化了整个构建过程，并发布了具有不同版本和风格的各种容器。我们的整个测试基础设施已经集装箱化，部署在 ACS 中。SQL Server 的测试和构建(我们正在测试)已经容器化，我们在 Kubernetes 托管集群中部署了数十万个容器。这为我们带来了更快的测试、更多的并行化、更高的效率、更多的自动化和更简单的流程。”

Kubernetes 是一个开源的容器编排引擎，最初由 Google 开发，现在由[云原生计算基金会](https://www.cncf.io/)管理。

对于每日构建，测试使用 700-800 个容器。这曾经是每夜的构建测试，因为它需要很长时间来运行，但现在它更快了。Petrossian 解释说:“每个容器都经历了一系列任务的排列，然后就消失了。”“我们现在可以在几个小时内修改代码、构建、发布容器、部署它们并运行我们的日常测试。过去通常需要一天以上的时间才能通过。现在，我们正在进行更多的测试，因为管理 Kubernetes 集群的自动化比部署虚拟机的自动化更容易一些，而且我们运行的速度更快，因此我们有更多的时间。如果我们真的需要，我们可以每天进行两到三次构建，而不仅仅是一次。”

对于每周测试套件，使用 1500 到 1600 个容器，通过使用容器提高的密度更加有用。“我们正在以更快的速度进行更多的测试，并且成本更低，因为我们正在部署每个虚拟机具有更高容器密度的 ACS。在 Windows 端，我们过去常常部署一个带有 SQL Server 实例的虚拟机，它可以通过测试，”Petrossian 说。

“我们在 Linux 方面有 7 比 1 的改进，因为我们在一台虚拟机上部署了 7 个容器，而不是 7 台虚拟机各自运行一个版本的 SQL Server 及其相关测试。ACS 中运行的每个容器都是独立的，我们可以在单个虚拟机上运行多个容器。”

因为 SQL Server 本身的许多代码在两个平台上都是相同的，所以测试不一定是针对 Linux 上的 SQL Server 的。很大一部分 SQL 测试是完全与操作系统无关的；他们不在乎运行的是 Windows 还是 Linux。这些测试测试 SQL Server 的一些内部组件，与操作系统无关，操作系统是 SQL Server 的大部分。

“SQL Server 在边缘与操作系统进行交互，例如身份验证、I/O 和联网。Petrossian 说:“我们有数以万计的优化器测试，它们只是纯 SQL 代码，没有进行系统调用，可以在任何地方运行。

[云本地计算基金会](https://www.cncf.io/)是新堆栈的赞助商。

简·埃里克·韦德在 [Unsplash](https://unsplash.com) 上的照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>