# 在生产 Kubernetes 上自动化分布式日志记录的技巧

> 原文：<https://thenewstack.io/tips-automating-distributed-logging-kubernetes-production/>

[](http://kenzan.com/)

 [克雷格·马丁，肯赞

克雷格·马丁是肯赞的工程界 SVP，他领导工程运营，自称的使命是找到复杂挑战的优雅解决方案。在他的职位上，Craig 帮助领导公司的技术方向，确保探索新的和新兴的技术并将其纳入战略愿景。最近，克雷格一直专注于通过构建大规模微服务应用来帮助公司进行数字化转型。他长期从事专业服务领域的定制软件开发，在加入 Kenzan 之前，Craig 是 Flatiron Solutions 的工程总监。他在乔治梅森大学获得了理学学士学位。](http://kenzan.com/) [](http://kenzan.com/)

任何 Kubernetes 生产环境都将严重依赖日志。使用内置的 [Kubernetes](/category/kubernetes/) 功能以及一些额外的数据收集工具，您可以轻松地自动化日志收集和聚合，以便对您的 Kubernetes 集群进行持续分析。

在 [Kenzan](https://kenzan.com/) ，我们通常会尝试将平台日志记录与应用日志记录分开。这可以通过非常不同的工具和应用程序来完成，甚至可以通过日志本身的过滤和标记来完成。

与任何分布式系统一样，日志记录为准确跟踪特定调用提供了重要证据，即使它们在不同的微服务上，以便可以确定问题的根本原因。

以下是我们对分布式 Kubernetes 环境中日志记录的建议:

*   使用一个高度可用的日志聚合器，从一个位置捕获整个环境中的数据。
*   在整个端到端呼叫过程中，为每个客户端创建一个通用的事务 ID。这将使追踪线一路到地面变得容易得多。
*   确保记录服务名称和应用程序。
*   标准化整个堆栈中的日志记录级别。
*   确保没有旨在保护安全的数据被明文记录。

## 在 Kubernetes 伐木

除了这种高级的日志记录方法，您还应该了解 Kubernetes 如何处理自己的日志记录和事件。

Kubernetes 节点运行在虚拟的 Linux 计算平台上。像 [kubelet](https://kubernetes.io/docs/reference/generated/kubelet/) 和 Docker runtime 这样的组件在 Linux 上本地运行，登录到它的本地系统。Linux 日志记录配置在不同的文件夹位置，包括无处不在的/var/log 文件。

[cyclone slider id = " kubernetes-series-book-1-赞助商"]

管理员应该做的第一件事是验证这些日志文件的日志轮转，以及所有其他杂项 Linux 日志。Kubernetes 的文档为文件轮换提供了很好的建议。即使您打算用替代机制替换本地日志记录机制，也应该检查日志记录配置。

我们不建议您在短暂的云计算环境中保存虚拟计算实例的日志。这种情况可能会突然消失。现代日志和分析工具提供了足够的上下文和可视化帮助，帮助运营商确定大型 Kubernetes 集群部署内部实际发生了什么。您应该使用日志聚合服务将您的日志从 Kubernetes 环境中运出，以供以后查看和分析。

## 捕获 Kubernetes 日志

有一些可靠的方法可以捕获 Kubernetes 本地 Linux 日志、基于 Kubernetes 容器的组件日志和所有应用程序容器日志数据:

*   只需扩展 Kubernetes 现有的日志功能。随着日志在节点上累积和旋转，您可以将它们运送到其他地方。一种流行的方法是使用日志容器，其全部目的是将日志发送到另一个系统。
*   或者，您可以使用 [Fluentd](https://www.fluentd.org/) 数据收集器将日志传输到 ELK 堆栈(Elasticsearch、Logstash 和 Kibana)，或者其他日志聚合和分析系统。这种日志传送方法利用了命令 [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) logs。您可以在每个节点上都有一个带有 Fluentd 容器的日志记录 pod(Kubernetes 通过 DaemonSets 的概念简化了这一过程)。Fluentd 将被配置为(通过 configmap)读取每个节点的所有日志位置，并将它们聚集到一个公共的搜索位置。
*   这种方法有多种变体，其中您的应用程序容器在同一个 pod 中有一个日志记录容器(也称为容器边车方法)，将应用程序与系统日志记录分开。

无论您选择哪种方法，日志最终都会驻留在某个节点上，并且它们必须移动到其他地方。上面提到的所有方法都可能非常成功，但我们发现它们之间有一个非常重要的共同点。它们都将日志聚合从应用程序代码中分离出来。这对于分离责任的关注点非常重要，对于性能原因也是如此。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>