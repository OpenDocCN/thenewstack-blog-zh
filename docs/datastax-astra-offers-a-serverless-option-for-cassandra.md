# Datastax Astra 为 Cassandra 提供了一个无服务器选项

> 原文：<https://thenewstack.io/datastax-astra-offers-a-serverless-option-for-cassandra/>

继续努力使开源的 Apache Cassandra 数据库更容易被用户访问，DataStax 已经完成了其 [Astra](https://astra.datastax.com/register) 无服务器软件的初步开发，该公司称该软件已经准备好作为“业内第一个也是唯一一个开放的多云无服务器数据库”投入生产

Astra serverless 背后的基本思想是，开发人员将不再需要根据他们预期的峰值使用来提供数据库。相反，他们像通常一样使用 Cassandra 数据库实例进行编码，并且在后端处理规模，既可以缩小到零，也可以扩大到所需的任何规模和数据传输速率。

“Cassandra 使用的圣杯是能够弹性地向上扩展，但也可以向下扩展。基本上，你需要做的是将数据库的计算部分、处理来自应用程序的请求和处理查询的部分与保存数据的存储部分分开，并且你需要以一种可以动态扩展的方式做到这一点， [DataStax](https://www.datastax.com/?utm_content=inline-mention) 的首席产品官[埃德·安诺夫](https://www.linkedin.com/in/edanuff)在接受采访时解释道。“它将动态地扩大或缩小规模，这为您的开发人员和您的业务提供了大量的灵活性。”

DataStax [在 2020 年 5 月推出了](https://www.datastax.com/blog/welcome-datastax-astra) Astra，让你不再为安装和管理自己的数据库实例而烦恼。然后在 12 月，该公司[推出了 Astra 无服务器](https://thenewstack.io/stargate-data-gateway-brings-rest-json-graphql-apis-to-cassandra/)的测试版，Anuff 称其立即获得了成功。

“总的来说，在测试期间，每个人都选择了无服务器选项，”他说。

虽然 Cassandra 以能够横向扩展而闻名，但他表示，这种计算与存储的分离确实是能够让纵向扩展像纵向扩展一样简单的关键因素。对于标准的 Cassandra 数据库，数据需要随着规模的变化而重新平衡，无论是增加还是减少，这可能需要一些时间。然而，Astra serverless 使用“基于微服务的架构”将计算和存储分开，使数据库能够根据需要快速扩展。

“使用 Cassandra 的人在扩大规模时往往会更加小心，缩小规模时也会非常小心。一旦你在 Cassandra 中将计算和存储分开，你就可以在一天中随时扩展和缩小，基本上是实时的，”Anuff 说。

> “Cassandra 使用的圣杯是能够弹性地向上扩展，但也可以向下扩展。”

-埃德·阿努夫，数据税

Anuff 说，除了减少开发开销，Astra serverless 还可以节省 3 到 5 倍的成本。首先根据请求确定成本，然后根据分层定价系统确定存储成本，前 25 美元的使用费目前是免费的。正如使用量可以减少到零，成本也可以减少到零。

Anuff 解释说，这部分是通过在后端使用亚马逊 S3 存储实现的，这使得在没有太多相关成本的情况下拥有大量数据成为可能。在计算方面，正如任何无服务器产品一样，冷启动时间可能是一个问题，Astra 无服务器也不例外，但 Anuff 表示，如果这是一个问题，有一些配置选项可用于预热实例。

展望未来，Anuff 表示，他们希望在初夏增加多区域功能，总体上希望给 Cassandra 带来无服务器功能。

“我们的目标是让无服务器成为各种风格的 Cassandra 的标准部分，”Anuff 说。“我们真的希望这是 Cassandra 本身的用途，当人们去问，‘我们应该使用什么数据库？’他们将使用 Cassandra，因为它是无服务器的。"

哈维尔罗德里格斯德皮沙贝。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>