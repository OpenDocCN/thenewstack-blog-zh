# 本周数字:微服务和流数据，完美结合

> 原文：<https://thenewstack.io/week-numbers-microservices-data-perfect-together/>

“微服务”以及“无服务器”和“开发运维”是很难定义的术语，因为它们描述了模式和架构以及特定的技术。然而，调查数据表明，许多这些主题之间有很强的相关性。上个月，[我们报告了](https://thenewstack.io/week-numbers-devops-favor-microservices/)在生产中使用[微服务](/category/microservices/)的 81%的人坚持 [DevOps](/category/devops/) 或连续交付实践。

由 [Lightbend](https://www.lightbend.com/) 在 2017 年年中进行的一项关注“快速数据”的[调查](https://info.lightbend.com/rs/558-NCX-702/images/report-lightbend-fast-data-development-trends-2017.pdf)显示了微服务采用和流媒体技术使用之间的另一个强有力的联系。请注意，快速数据是一个术语，旨在表明速度，而不是大小(即大数据)是参照系。虽然只有 34%的受访者在生产中使用微服务，但在生产中使用高级 fast 数据用例的受访者中，这一数字上升至 50%。高级用例包括实时个性化、机器学习和物联网管道，不包括提取、转换和加载(ETL)以及传统统计分析等活动。

Confluent 对 Kafka 用户进行的[调查](https://www.confluent.io/blog/2017-apache-kafka-survey-streaming-data-on-the-rise/)支持了上述发现，因为 50%的人表示微服务是他们的 Kafka 用例之一。

在过去的几年里， [Kafka Streams](https://kafka.apache.org/documentation/streams/) 、[Apache Spark Streams](https://spark.apache.org/docs/latest/streaming-programming-guide.html)和 [Akka Streams](https://doc.akka.io/docs/akka/2.5/stream/index.html) (由 Lightbend 支持)获得了关注，因为它们允许开发人员处理动态数据。在许多方面，它们已经成为连接数据管道的粘合剂。虽然许多数据是以模块化方式处理的，但并非所有数据都是实时处理的。56%的受访者表示，他们的工作负载中至少有一半包含实时组件。

当被问及他们实际上需要多快时，开发人员说大多数用例不需要在一秒或一分钟内被访问。31%的人需要集成数据流的能力，32%的人需要人工智能和/或机器学习的速度。对于许多其他用例，每小时甚至每天发生的批处理符合他们的需求。

特征图像由[派恩瓦特](https://unsplash.com/@pinewatt)通过 [Unsplash](https://unsplash.com/photos/2Hzmz15wGik) 拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>