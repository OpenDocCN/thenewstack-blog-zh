# Mesosphere 的新 SDK:在笔记本电脑上构建应用程序，扩展到整个数据中心

> 原文：<https://thenewstack.io/mesospheres-new-sdk-build-apps-on-a-laptop-scale-to-the-entire-data-center/>

用于 [Mesosphere 的数据中心操作系统(DCOS)](https://mesosphere.com/product/) 的[新软件开发工具包(SDK)](https://mesosphere.com/blog/2015/07/15/mesosphere-sdk/) 为开发人员提供了一种在笔记本电脑上构建应用程序的试验场，这些应用程序无需更改代码就可以扩展到整个数据中心。这证明了关于数据中心开发人员的新想法，他们可以使用命令行界面和基本用户界面创建分布式应用程序。通过 SDK，开发人员可以使用各种编程语言，如 Java、Python 或 Go，来利用本质上是一台巨型计算机的资源，这些资源可以抽象数据中心管理的复杂性，以构建应用程序。

对于我们如何看待数据中心及其对开发人员的作用，这是一个重大发展。这一发展超越了关于容器的讨论，并将其置于关于大规模应用程序开发和管理的背景中。

“我们希望让这种新的外形变得非常容易，”Mesosphere 的首席执行官 Florian Leibert 在接受 New Stack 采访时谈到了本周宣布的消息。

> “您甚至不会注意到您正在编写一个分布式应用程序。在您看来，您似乎只是在针对资源编写应用程序。机器之间的界限变得非常模糊。”

莱博特称 [Mesosphere 的新 SDK](https://mesosphere.com/blog/2015/07/15/mesosphere-sdk/) 在某种程度上是 [Mesos API](http://mesos.apache.org/documentation/latest/) 的继承者。它将通过 API 公开原语，使面向容器的任务调度自动化。尽管 Mesosphere 特别提到了 Docker，但高管们小心翼翼地指出，容器调度不仅仅局限于 Docker，还涵盖了自科学开始以来的所有类型的隔离和分区，包括直接 LXC。

“我们在 Mesos 一直使用一种集装箱化的形式，甚至在 Docker 出现之前，”Leibert 说。“对我们来说，集装箱化是非常非常可插拔的。…我们为您提供最大的灵活性，让您选择想要使用的集装箱化技术。

> “可以使用 appcontainer 规范，可以使用 Docker，也可以使用 native cgroups。可以想象，如果在一两年内，另一种容器技术出现，那么，它将很容易被替换。我们真的对此一无所知。”

## 每个月都有新的火花

为了让新开发人员掌握分布式计算的工作原理，SDK 将直接在开发人员的笔记本电脑中创建一个完全本地化的 DCOS 环境，将它们转换为微型数据中心试验场。我们被告知，遵循 SDK 的“入门”轨道，将引导开发人员走上一条道路，他们最终可能会提交他们的第一个 DCOS 应用程序供检查，并最终从该公司获得 Mesosphere 认证。

SDK 将捆绑许多开发者工具，其中一些来自第三方，以促进分布式应用程序的开发。Leibert 提到，一个这样的工具是命名服务，它使网络应用程序的组件更容易发现彼此。

这位首席执行官指出了 Apache Spark 集群计算系统的成功，特别是它在短短几个月的时间内就成功地让 Hadoop 的 MapReduce 组件变得过时。他认为 [Spark 与 Mesos](https://spark.apache.org/docs/latest/running-on-mesos.html) 的完美契合是关键原因，并表示他相信 Mesosphere SDK 将使开发人员能够只需几个月甚至几周的努力，就能生产出 Spark 规模的分布式系统。

“不仅仅是 Spark，现在像 Mesos 上的 [Kafka 这样的消息队列都是基于这个 SDK 构建的，”Leibert 说，“它们运行得非常好，非常健壮。实际上，以这种方式考虑编写一个分布式系统要容易得多，因为你不必考虑单独的机器。考虑单个机器并将它们连接在一起是编写分布式应用程序的错误思维模式。”](https://databricks.com/blog/2015/03/30/improvements-to-kafka-integration-of-spark-streaming.html)

## 瓶中超大规模

这听起来像是一个不可能完成的任务:第一步，你学习如何写“你好，世界！”第二步，构建一个分析驱动的容器，它可以在一个大型数据中心中扩展一千倍。与集装箱和 Mesos 的区别在于，配送的物流从来不需要编程。您构建容器，只要您使用 Mesosphere API，就可以稍后通过 orchestrator 确定后勤工作。

“如果你要为像金融服务这样的垂直行业建立一个新的复杂的分析系统，你必须有很多领域的专业知识，你可能必须有一些统计学博士学位，”Mesosphere 高级副总裁马特·特里费罗说那是一个相当复杂的系统。但是，如果您正在自己的公司内部构建一个新的 PaaS 层(顺便说一下，有 12 个或更多的 PaaS 写入我们的堆栈，其中一半是由 Apple 等公司为自己的内部使用而构建的)，这是一个相当简单的 PaaS 工作。

“所以我认为你已经有了一整类的应用程序，”特里费罗继续说，“从高度复杂和专业到相对简单，但解决特定的利基。…从业务角度来看，这可能是开发商最大的新机会，因为需要提供这些类型的服务的业务发生了重大转变。十年前，只有谷歌和推特必须是谷歌和推特——甚至五年前。现在，每个人都得分一杯羹。任何出售联网“东西”的人都需要一个物联网后端。每个拥有收银机的人都需要实时数据分析。这是每个客户公司都要解决的问题，不仅仅是硅谷的那帮家伙。”

对早期访问 SDK 感兴趣的开发者现在可以注册中间层 DCOS 开发者计划。

Docker 是新堆栈的赞助商。

特征图片:[rave fitity](https://www.flickr.com/photos/ravefinity/ "Go to RAVEfinity's photostream")的:[245-霓虹-火花-蓝色](https://www.flickr.com/photos/ravefinity/12180712013/in/photolist-jynkj6-jypZaH-jyp2yH-jynK2Z-jysbFC-dpkrbL-adX2HD-paCj6o-vLoN71-pVuzTs-hdkU1v-t4Zw9k-qWy7pW-nit7z4-rcaaZk-fBaQ8k-uRKur7-tnincm-jWkKMr-f57b3r-nK21A1-tuGnpq-utN48s-rpxivL-eaY8J5-ry8wv8-s3WdTW-oFdFuL-hD66aU-qVzgth-fsDmaM-er7icZ-voDJv9-rasAww-eyoMnj-vwMFv9-oNJ3wx-qzm1CR-9x4PsD-oALWR7-q332j-a5X8eL-HJuuU-gkru1Z-edusYT-9xyu1b-ePwZD7-6EJk7d-7vCFKg-ejbbvJ)在 [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>