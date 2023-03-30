# Redis 和 Mirantis 如何使用 Cloud Foundry 实现高可用性

> 原文：<https://thenewstack.io/redis-mirantis-use-cloud-foundry-hands-off-ha/>

如今开发应用程序不仅需要灵活的方法，还需要乐于接受新技术、基础设施和工作流。随着诸如 [Cloud Foundry](https://www.cloudfoundry.org/) 之类的平台变得更加广泛使用，OpenStack 之类的其他项目也利用了这一不断增长的用户基础。

在这一集的 [The New Stack Makers](/tag/the-new-stack-makers/) 播客中，我们将了解更多关于 [Redis](http://redis.io/) 和 [Mirantis](https://www.mirantis.com/) 如何利用 Cloud Foundry 为他们的客户带来好处，Cloud Foundry 如何缓解在多云环境中开发软件的挑战，以及 Mirantis 如何将自己的堆栈容器化以提高部署灵活性。《新堆栈制造商》主持人[凯尔·麦克唐纳](https://twitter.com/kylemacdonald)和联合主持人[李·卡尔科特](https://twitter.com/lcalcote)采访了 OpenStack 分销商 Mirantis 的副总裁兼首席架构师[杰森·文纳](https://www.linkedin.com/in/jasonvenner)和 Redis 实验室产品营销副总裁琳娜·乔希[，以获得他们对这些问题和更多问题的见解。](https://www.linkedin.com/in/ljoshi)

[Redis 和 Mirantis 如何利用云代工做到不插手和 HA](https://thenewstack.simplecast.com/episodes/how-redis-and-mirantis-use-cloud-foundry-to-be-hands-off-and-ha)

Joshi 在讨论开始时指出，Redis 在展会上宣布的与 Cloud Foundry 的新[集成主要是由客户需求驱动的。“它为我们打开了许多大门，因为对于许多大型组织来说，与 Cloud Foundry 集成正在成为一种要求，”他说。](https://docs.pivotal.io/redis/)

Venner 接着指出，Cloud Foundry 与 Redis 等数据服务的集成为该领域的长期发展打开了大门。“很高兴看到更多的数据服务出现。没有持久的数据层，很难实现应用程序的敏捷性。没有这一点，Cloud Foundry 就无法实现其真正的潜力。”

Venner 指出，当在一个多云甚至是标准基础设施中工作时，许多开发人员希望尽可能不插手。“我们看到大部分开发人员不想对基础设施有任何顾虑。他们只需要随时准备好开发和测试组件，这样他们就可以生活在 [Eclipse](https://eclipse.org/downloads/) 中，编写代码，按下按钮，并通过测试架构，这样就可以用相关的方式进行测试，而不必成为所有这些技术的专家。”

Redis 还利用 Cloud Foundry 为其客户提供项目经常需要的高可用性。特别是当使用 Redis 作为数据库时，Joshi 解释说，虽然容器已经以各种方式发展，但它们与存储服务的连接在某些领域仍然缺乏。“我认为容器仍处于萌芽阶段，容器与存储的连接还没有完全解决。由于 Redis 在内存中运行，它成为一个完美的场景，你可以将 Redis 部署为第一响应者，而数据库作为容器是短暂的，”他说。

Redis 还开发了一套客户可以使用的[新模块](http://redismodules.com/)，这些模块都可以通过开源获得。也鼓励开发者向 Redis Hub 提交他们自己的模块。

Venner 和 Joshi 继续讨论这一事件，Joshi 指出，Cloud Foundry 社区已经团结在该平台周围，不仅更好地开源，而且将软件开发和云平台作为一个整体。

“看到围绕这个项目建立起来的社区势头很有意思，”Joshi 说。

[https://www.youtube.com/embed/3oUcd17pyJE?feature=oembed](https://www.youtube.com/embed/3oUcd17pyJE?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>