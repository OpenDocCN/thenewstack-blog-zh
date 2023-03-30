# 使用 Bitnami 包在一个小时之内建立一个 MongoDB 副本集

> 原文：<https://thenewstack.io/set-mongodb-replica-set-hour-using-bitnami-package/>

当然，在你喜欢的云提供商上设置一个应用程序的单一副本是很容易的。点击几个按钮，你就可以走了。但是，如果您想在云中建立一个复杂的多层应用程序，比如分布式数据库和相关的监控工具，该怎么办呢？这时你就要开始从你的云提供商那里寻找 Bitnami 品牌的包了。他们可以节省大量部署时间。

作为一个例子，下面的嵌入式 TNS 教程展示了如何在不到一个小时的时间内在 Microsoft Azure 上设置一个 MongoDB 副本集，而这段时间大部分被虚拟机启动所占用。 [Bitnami](https://bitnami.com/) 营销副总裁 [David Dennis](https://www.linkedin.com/in/davidpdennis) 还展示了如何直接从 Azure 内部使用 Datadog 来装备您的新 MongoDB 集群:

[https://www.youtube.com/embed/GpDrXCeVUbI?feature=oembed](https://www.youtube.com/embed/GpDrXCeVUbI?feature=oembed)

视频

MongoDB 云部署的便利性在很大程度上要归功于 Bitnami 为该软件提供的多层应用程序模板。虽然大多数管理员可能不知道 Bitnami 的名字，但该公司一直在为云提供商提供打包的应用程序，如亚马逊网络服务和微软 Azure，通过他们自己的特定环境向他们的客户提供——分别是 AWS [云形成模板](https://aws.amazon.com/cloudformation/aws-cloudformation-templates/)和 [Azure 资源管理器](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-authoring-templates)模板。

[Bitnami](https://thenewstack.io/qa-erica-brescia-bitnami/) 与[云提供商](https://docs.bitnami.com/)及其部署机制[非常熟悉](https://thenewstack.io/throw-code-wall-see-sticks-not-bitnami/)，也非常熟悉应用本身的部署复杂性。这使得该公司不仅可以在单个虚拟机中打包应用程序，还可以为更复杂的应用程序提供包。

“因此，您将获得一个复杂的多层集群应用程序，并且易于在单个虚拟机上部署，”Dennis 说。

丹尼斯说，这个演示展示了 Bitnami 如何“利用最流行的应用程序使用的所有复杂拓扑，为流行的云提供商制作一键模板”。“我们希望达到部署复杂拓扑像部署简单拓扑一样简单的地步。”

Bitnami 为各种不同的软件应用程序提供了超过 20 种多层模板，包括 Jenkins、LAMP Stack、RabbitMQ、WordPress、MongoDB 和 MEAN Stack。

为了后续的演示，Dennis 承诺展示如何用 [Redash](https://redash.io/) 增强这个设置，它可以可视化 SQL 和 NoSQL 数据。所以赶快来看看这个空间吧。

[Bitnami](https://bitnami.com/) 赞助了这篇文章。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>