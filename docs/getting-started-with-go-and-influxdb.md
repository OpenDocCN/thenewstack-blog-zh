# Go 和 InfluxDB 入门

> 原文：<https://thenewstack.io/getting-started-with-go-and-influxdb/>

[](https://www.linkedin.com/in/alexandre-couedelo/)

 [亚历山大·库德罗

亚历山大是一位复杂系统工程和管理专家。自从他开始职业生涯，为加拿大一家领先金融机构的数字化转型做出贡献以来，他一直信奉 DevOps 文化。他的热情是 DevOps 革命和工业工程。他喜欢自己有足够的后知之明来两全其美。](https://www.linkedin.com/in/alexandre-couedelo/) [](https://www.linkedin.com/in/alexandre-couedelo/)

PostgreSQL 或 MongoDB 等传统数据库在以表格或文档格式保护系统状态方面非常出色，但与时间相关的数据呢:系统指标、物联网设备测量或应用程序状态变化？

对于这些事情，你需要一个更合适的数据库类型，一个被设计来更好地管理具有时间特性的半结构化数据的数据库。

InfluxDB 是一个高性能的数据存储，专门为时序数据编写。InfluxData 不仅提供数据库，还提供接收、转换和可视化数据的工具。例如， [Telegraf](https://www.influxdata.com/time-series-platform/telegraf/) 提供了 200 多个插件来摄取数据。然而，如果您想将 InfluxDB 直接集成到您的后端应用程序中，您需要使用专用的[客户端库](https://docs.influxdata.com/influxdb/v2.0/tools/client-libraries/)。

本教程将带您了解如何使用 [InfluxDB Go 客户端库](https://docs.influxdata.com/influxdb/v2.0/api-guide/client-libraries/go/)，创建到数据库的连接，并从中存储和查询数据。

## InfluxDB 入门

您即将向您的应用程序堆栈添加 InfluxDB。在本教程结束时，您将拥有一个代码库，演示如何将 Go 应用程序与 InfluxDB 进行接口。但是首先，让我们为这个演示创建一些背景。

您正在设计一款新的智能恒温器物联网产品。您经常从物联网传感器接收温度测量值。让我们假设您将温度测量值存储在 InfluxDB 数据库中。此外，你的用户可以使用你的应用程序调节智能恒温器的温度。每次用户改变恒温器时，您都要更新经典数据库中恒温器的状态。

此外，您希望保存所有恒温器温度设置的历史记录，以及温度测量值。温度设置和测量一起使您能够分析用户行为。有了这些数据，你可以在用户行动之前预测变化，让你的智能恒温器变得更加智能。

## 本教程的要求

本教程与操作系统无关，假设你已经安装了 [GO 1.16+](https://golang.org/doc/install) 和[Docker](https://docs.docker.com/get-docker/)。

我选择 Docker 安装，因为它最适合持续集成。不过 InfluxDB 支持[很多平台(Linux，macOS，Windows，Docker，Kubernetes)](https://docs.influxdata.com/influxdb/v2.0/install/) 。

## 启动本地数据库

要开始设置，您需要在 Docker 中定义一个定义 InfluxDB 配置的`docker-compose.yml`文件。

运行`docker-compose up`来启动数据库。出于测试目的，在一个名为`test_influxdb.env`的文件中定义您的环境变量。下面是我`test_influxdb.env`的内容:

您需要在 docker-compose 命令中添加标志`--env-file`,以强制 docker 考虑该文件。

```
```
docker-compose  --env-file test_influxdb.env up
```

```

InfluxDB 自带易用的 UI。去`http://localhost:8086`看看吧。

![InfluxDB UI](img/2cee36839c7b9038e24c6bc2572a76e6.png)

## 熟悉 InfluxDB

InfluxDB 不仅仅是一个时序数据库。这是`influxdata`生态系统背后的核心元素。这个生态系统包括:

*   一个 UI。web 界面提供了管理界面、查询构建器和数据可视化等开发工具。
*   一个命令行界面[涌入](https://docs.influxdata.com/influxdb/v2.0/write-data/developer-tools/influx-cli/)。CLI 可以管理数据库、从 CSV 加载数据、插入数据和查询数据。它是开发和调试应用程序的好伙伴。

## Go 客户端库入门

你的数据库已经准备好了，所以让我们写一些 Go。初始化您的 Go 模块。

```
```
go mod init github.com/xNok/Getting-Started-with-Go-and-InfluxDB
```

```

将`influxdb-client-go`作为依赖项添加到您的项目中。

```
```
go get github.com/influxdata/influxdb-client-go/v2
```

```

## 建立联系

让我们创建一个函数来帮助您连接到数据库。您已经在您的`test_influxdb.env`中用变量`INFLUXDB_TOKEN`定义了一个令牌。您将使用此令牌进行测试。您还可以通过 UI 创建新的令牌。您的 InfluxDB 实例应该仍在运行。

1.  返回 UI 并生成新的身份验证令牌。
2.  点击**数据**。
3.  在**客户端库**中，选择 **Go** 。

本节让您创建一个 auth 令牌，并提供一些代码片段来开始使用 Go 库。

![Create an Auth token](img/f8d4c538b3acfef15785eb243abe5c8f.png)

这是您要创建的函数:

接下来，创建测试函数。当您调用`connectToInfluxDB`时，您可以成功连接到数据库，并且您可以通过从`influxdb2.Client`调用`Health`方法来验证这一点。如您所见，我使用了`godotenv.Load("../test_influxdb.env")`来获取您在 Docker 中为 InfluxDB 定义的凭证。(您需要将`godotenv`作为依赖项添加到您的项目中)。

在创建连接时，调用 influxdb2 客户端初始化构造函数。包括从环境变量中读取凭证和验证`connectToInfluxDB`的代码，如下所示:

如果通过了测试，就可以使用 InfluxDB 实现一些特性了。但是，您还没有准备好投入生产。

强烈建议在生产环境中启用 [SSL/TLS 加密](https://docs.influxdata.com/influxdb/v2.0/security/enable-tls/)。在本教程中您不需要它，因为您使用的是本地 Docker 环境。

在您的应用程序中，您需要将证书传递给 InfluxDB 客户端。

## 插入数据

第一步:建立数据模型。您的要求是将“恒温器设置”中的更改发送到 InfluxDB。该设置包含用户的标识符以及室内所需的平均和最高温度。

第二步:写一个测试函数。您可以使用几种可能的方法来插入数据，以找到最适合您的方法。

InfluxDB Go 客户端库提供了三种插入数据的方法:

*   [线路协议](https://docs.influxdata.com/influxdb/v2.0/reference/syntax/line-protocol/)使用基于文本的数据库查询。
*   带有构造函数的数据点使用映射来填充数据。
*   流畅风格的数据点使用构建器模式。

这里是一个通用的测试函数:

您将需要一个小的助手函数`init_testDB`，在每次测试之前初始化连接并清理数据库。

最后，您已经准备好尝试每种类型的数据插入。

line 协议使用起来很简单，有点像 SQL 查询。InfluxDB 中的记录由三个元素组成:measurementName、fields 和 tags。InfluxDB 的[关键概念包括:](https://docs.influxdata.com/influxdb/v2.0/reference/key-concepts/data-elements/)

*   `measurementName`，数据集
*   `fields`，是键/值对
*   `tags`，也是键/值对，但是作为记录的索引。

点数据方法写起来很冗长，但也提供了更多的结构。当数据参数已经是期望的格式时，这很方便。

或者，您可以使用构建器`NewPointWithMeasurement`一步一步地构建查询，这很容易阅读。

哪种插入方式最适合你？不要忘记更新测试来验证您的实现。

## 定量

请注意，InfluxDB 客户端使用批处理向数据库发送数据。默认情况下，在达到批量大小(默认情况下为 5，000 点)之前，不会向数据库发送任何数据，这是数据库负载和数据可用性之间的一种平衡。较小的批处理大小意味着较高的档位，因此可能会影响数据库的性能。另一方面，等待达到批处理大小意味着数据仍然在应用程序的内存中，而不是在数据库中。

调用`influxdb2`的初始化构造函数时，可以调整`Batch Size`:

此外，您可以使用`Flush()`强制客户端发送数据。您在前面的示例中已经看到了这一点。

然而，根据我对时间序列数据库的经验，不要到处使用`Flush`方法。即使将数据立即写入数据库似乎是合理的，它也会显著影响性能。相反，使用`Batch Size`选项。

## 阻塞与非阻塞

虽然 InfluxDB 的默认行为是使用异步调用和批处理(即非阻塞 I/O)，但是您可以选择同步写入点。对于需要立即提交到数据库的非频繁写入，建议使用此选项。

## 查询数据

InfluxDB 使用一种叫做 [Flux](https://docs.influxdata.com/influxdb/v2.0/query-data/get-started/) 的查询语言。Flux 使用功能方法来选择、过滤和汇总数据。一旦掌握了基本知识，阅读和理解起来就毫不费力了。此外，InfluxDB 提供了一个强大的查询构建器，可以根据获取的数据设计查询。

![InfluxDB Query Builder](img/acb99d5dc0892e3302a06b2292df1451.png)

要完成本教程，请运行集成测试，将数据点添加到数据库中。接下来，使用查询构建器创建一个查询来隔离您需要的数据。这是使用 QueryBuilder 构建的查询:

现在剩下要做的就是实现一个使用 Go 客户端查询数据的函数。有两种方法可以查询数据。

首先是使用 [QueryTableResult](https://pkg.go.dev/github.com/influxdata/influxdb-client-go/v2/api#QueryTableResult) 。您会注意到，将数据放回`ThermostatSetting`结构需要一些工作。即使您将`ThermostatSetting`的内容作为一个数据点发送，字段`avg`和`max`作为两个独立的记录输出。

第二个选项是返回未解析结果字符串的`QueryRaw()`。

最后，您需要更新您的测试函数，看看它是否像预期的那样工作。

## 结论

如果您完成了本教程，您就拥有了一个使用 InfluxDB 的经过全面测试的应用程序。您使用了四种不同的方法来查询数据(三种非阻塞插入加上一种阻塞插入)，并且您知道在投入生产之前需要启用 SSL/TLS 证书。

您有机会在 InfluxDB UI 中插入数据并将其可视化，这样您可以快速构建查询，然后在应用程序中使用这些数据。总之，您可以在应用程序中使用的同一数据结构中插入和检索数据。你未来的智能恒温器公司肯定是在正确的轨道上。

如果您有兴趣进一步了解 InfluxDB，请阅读[官方文档](https://docs.influxdata.com/influxdb/v2.0/get-started/)以更加熟悉 [Go 客户端库](https://github.com/influxdata/influxdb-client-go)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>