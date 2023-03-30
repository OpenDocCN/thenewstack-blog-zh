# 带有 Neo4j 和. NET 客户端的图形数据库

> 原文：<https://thenewstack.io/graph-database-neo4j-net-client/>

[](https://www.tournr.com)

 [Chris Skardon，Tournr 的所有者

Chris Skardon 是 Tournr 的所有者，是负责维护主服务器的. NET 开发人员。Neo4j 的. NET 客户端(也称为 Neo4j 客户端)。](https://www.tournr.com) [](https://www.tournr.com)

克里斯·斯卡登，Neo4j。Net 专家和 Neo4j 的开发者倡导者 Michael Hunger 详述了图形数据库方法的一些有趣的开发属性。

我们都经历过试图将复杂的领域对象网络映射到关系数据库的挑战。尽管你可以从实体框架或者像 LINQ 这样的 API 中得到帮助，但是做起来从来都不简单——尤其是当查询变得复杂，实体变得更加紧密的时候。

也许是时候尝试一种不同的方法了:图形数据库。在本文中，我们描述了一些使用 Neo4j 的工作。NET 作为客户端，以显示使用 RDBMS 很难实现的结果。

## Neo4j 101

所有的图形数据库都是存储相关数据的理想选择。Neo4j 是理想的选择，因为它被设计为一个本地图形数据库，从一开始就强调节点和关系的快速管理、存储和遍历。

底层存储模型将关系视为“一等公民”,代表实体之间预先具体化的连接，允许从一个节点到另一个节点的持续时间导航(连接)。

通过采用不同的方法来存储和查询实体之间的连接，优化的 Neo4j 图形引擎提供了每秒每核高达 400 万跳的遍历性能。注意:由于大多数图搜索都局限于节点的较大邻域，所以存储在数据库中的数据总量不会影响操作的运行时间，这是原生图技术的另一个明显优势。

## 缩放比例

对于关键业务和高性能操作，Neo4j 可以部署为可扩展的容错机器集群。由于高度的可扩展性，即使在单台机器上，Neo4j 集群也只需要个位数的机器，而不是数百或数千，从而节省了大量成本和运营复杂性。Neo4j 使用复制的主从集群设置，并支持热备份和广泛的监控。Neo4j 还可以存储非常大量的实体，同时对紧凑存储很敏感。

## 属性图模型

Neo4j 的底层属性图模型是由定向命名关系连接的标记节点之一，两者都可以保存任意属性。这允许表达任何领域或用例。

节点不受严格模式的约束，它们的效率取决于被搜索路径的长度，而不是图的整体大小。它们的结构非常简单，一个通过关系对象相互连接的节点网络，如下所示:

这被称为标记属性图模型，允许您在构思、设计、实现、存储和可视化过程中一致地使用同一模型。这不仅允许开发人员，而且允许所有业务利益相关者积极有效地参与整个应用程序的开发，因为该模型比关系数据库模式和表更直观，非技术人员更容易掌握。您可以随着需求的变化快速地发展您的领域模型，因为不需要昂贵的模式变更和迁移。

## 查询图表

 [Neo Technology 公司 Neo4j 开发人员关系主管 Michael Hunger

Michael Hunger 对软件开发充满热情已经有很长一段时间了。在过去的几年里，他一直在与 Neo Technology 合作开发开源 Neo4j 图形数据库，担任了许多角色。作为 Neo4j 社区和生态系统的管理员，他特别喜欢与图形相关的项目、用户和贡献者一起工作。作为一名开发人员，Michael 喜欢编程语言的许多方面，每天都在学习新的东西，参与令人兴奋和雄心勃勃的开源项目，撰写与软件相关的书籍和文章。](https://neo4j.com) 

然而，虽然在白板上绘制图形模型并展示有用的应用程序流模拟很简单，但用 SQL 表达它们却不那么容易。几年来，我们已经发展了 Cypher——我们的图形查询语言——能够在图形中查询、修改、创建和描述数据。去年，Cypher 变成了一个开源项目(openCypher.org ),任何人都可以使用和实现。

Cypher 使用 ASCII-art 来表示节点和关系的图形模式，将图形模型深度集成到查询语言中。以表达来自某个领域的概念或问题的模式为中心的是附加的子句和函数，它们形成了一种功能强大、富有表现力和可读性的查询语言。该语言还提供了为特定目的定制扩展的方法。

此图中所示的关系可以用密码表示为:

```
(:Actor  {name:'Tom Hanks'})-[:ACTED_IN]-&gt;(:Movie  {title:'Cast Away'})

```

标签为“演员”的节点通过关系“ACTED_IN”连接到标签为“电影”的节点。箭头的方向决定了关系的方向，在这种情况下，它是汤姆·汉克斯在《荒岛余生》中扮演的角色。

节点可以有属性和标签。在此示例中，演员节点有一个值为“Tom Hanks”的属性“name ”,电影节点的属性“title”设置为值“Cast Away”关系还可以具有限定实体之间关系的属性，如成本、重量、等级、距离、时间间隔。

通过使用基于标签和属性的查找，然后沿着节点和关系路径进行搜索。返回由汤姆·汉克斯出演的所有电影将涉及在演员索引中查找名字“汤姆·汉克斯”，以定位他的节点，然后跟踪所有传出的 ACTED_IN 关系以找到所有电影节点。

关系可以在两个方向上遍历，因此，查找 Cast Away 的转换将涉及与前面类似的过程:首先，定位“Cast Away”节点，然后跟踪所有传入的 ACTED_IN 关系。

## 使用 Neo4j 和。网

让我们在上下文中考虑一些编码示例。我们选择了。NET 作为环境，根据定义。NET 是一个主要基于 Windows 的开发生态系统，下面将介绍在 Windows 上的安装，但是示例应该可以在您选择的交付客户端上工作。

## Windows 安装

要使用 Neo4j，需要安装它。可以在这里下载[。注意，您可以选择下载可执行安装程序，或者下载需要更多手动安装的压缩包。](http://neo4j.com/download/)

## 第一眼

使用 RDBMS，您通常有一个管理工作室或一些其他重量级环境，但使用 Neo4j，您有“Neo4j 浏览器”,一个轻量级的基于 web 的工具。

Neo4j 浏览器可以在您安装 Neo4j 的端口上访问，默认情况下，该端口是 7474，因此如果您在您选择的 web 浏览器中打开 http://localhost:7474/

使用默认凭据登录，并选择新密码。目前没什么可看的；我们有一个空数据库，空数据库对任何人来说都不好玩。Neo4j 浏览器带有许多内置指南，使您熟悉前面提到的属性图概念，并带您了解 Cypher 的基础知识。

这些指南涵盖了电影图形(:播放电影图形)和如何导入众所周知的 Northwind 数据库(:播放 northwind 图形)。在您签出它们之后，您可以使用一个快捷命令来清理您的数据库:“MATCH (n) DETACH DELETE n”。

但是作为开发人员，我们希望以编程方式访问 Neo4j。所以让我们看看我们如何连接。

## 连通性

Neo4j 2.3.x 有一种方式我们(as。NET 开发人员)可以连接到它，这是通过服务器公开的 HTTP API。随着 Neo4j 3.0 的发布，我们可以通过定制的 Bolt 二进制协议访问更新的 API。

如果您需要针对 2.x 数据库实例运行，您将需要使用一个基于 HTTP 的客户端到 Neo4j(比如 Neo4jClient)。如果运行的是 3.x 数据库，可以选择基于 HTTP 的客户机或基于 Bolt 的客户机，比如 Neo4j-Dotnet-Driver。

最佳实践是首先在 Neo4j 浏览器中尝试您的密码，然后转换到您选择的驱动程序。

## neo4j 客户端

Neo4jClient 是在上访问 Neo4j 最常用的客户端。NET 平台，最初由 Tatham Oddie 等人在 Readify Australia 编写。它现在由克里斯·斯卡登维护，许多其他人也提供了帮助。目前它基于 HTTP API，但计划很快让它与 Bolt 一起工作。

Neo4jClient 使用流畅的界面，代码的编写与您在 Neo4j 浏览器中直接访问图形信息所编写的 Cypher 语句非常相似。

## Neo4j。驾驶员

Neo4j。Driver 是 Neo4j 和 Chris Skardon 的工程师开发的新产品，旨在成为针对数据库执行 Cypher 的低级别、高性能驱动程序。它使用与 Java、JavaScript 和 Python 的其他官方驱动程序相同的简单概念来降低整体学习曲线。所有这些驱动程序都符合他们的语言习惯，但建立在相似的原则上。

## neo4j 客户端示例

对于下面的示例，我们将使用您之前在指南中看到的示例电影数据库。您可以通过键入:
从 Neo4j 浏览器安装它

然后，按照说明插入数据。

由于我们的数据库中现在有一些数据，第一步应该是取回一些数据！假设数据库运行在 localhost:7474，并且您选择的驱动程序已经连接到数据库:

```
var client  =  new GraphClient(new Uri("http://localhost:7474/db/data",
"neo4j",  "password"));
client.Connect();

```

### 示例 1 —阅读

我们想找到某部电影中的演员。一个人有两种属性——出生时间和姓名，但在这种情况下，我们只对他们的姓名感兴趣。

```
IEnumerable&lt;string&gt;  results  =  client.Cypher
.Match("(p:Person)-[:ACTED_IN]-&gt;(m:Movie {title: 'Top Gun'})")
.Return&lt;string&gt;("p.name")
.Results;

```

然后我们可以用我们选择的任何方式解析结果。

### 示例 2 —阅读更多信息

我们可能想要更多的信息，而不仅仅是名字，这就是我们需要为我们的结果定义一些普通的 CLR 对象(POCO)的地方，在本例中，是一个 Person 类和一个 Movie 类:

```
class  Movie  {
public  string  title  {  get;  set;  }
}
class  Person  {
public  string  name  {  get;  set;  }
public  int  born  {  get;  set;  }
}

```

属性的大小写是小写的，以匹配示例数据库中的属性名，从而获得更多信息。NET-y——您可以使用[JsonProperty("title")]随意命名您的属性。在这种情况下，我选择匹配数据库的大小写以使代码更小。

```
var results  =  client.Cypher
.Match(
"(actor:Person)-[:ACTED_IN]-&gt;(movie:Movie {title: {nameParam}})",
"(movie)&lt;-[:DIRECTED]-(director:Person)"
)
.WithParam("nameParam",  movieName)
.Return((actor,  director,  movie)  =&gt;  new
{
Movie  =  movie.As&lt;Movie&gt;(),
Actors  =  actor.CollectAs&lt;Person&gt;(),
Director  =  director.As&lt;Person&gt;()
})
.Results.Single();

```

在这个查询中，我们返回一部电影，包括导演和所有演员。我们还将电影的名称作为参数传入—从性能角度(允许数据库编译和缓存查询)和安全性角度(限制 Cypher 注入攻击)来看，这都很重要。响应以匿名类型返回，具有所有正常的好处和限制。我们可以用类似于
的语句来解析它

```
Console.WriteLine($"{results.Movie.Title} directed by {results.Director.name}");
foreach  (var actor in results.Actors)
{
Console.WriteLine($"\t{actor.name}");
}

```

如您所见，我们正在直接访问属性，Neo4jClient 已经自动解析了结果(通过 Json。网)。

### 示例 3 —交易中的更新

Neo4j 是一个数据库，真实的数据库是有事务的——所以我们来更新一部电影，添加一个演员。首先，我们需要启动一个事务—使用 Neo4jClient —解决方案是将您的 IGraphClient 实例转换为 ITransactionalGraphClient 实例。

```
ITransactionalGraphClient txClient  =  client;

```

然后我们需要在交易中执行我们的查询:

```
using  (var tx  =  txClient.BeginTransaction())  {
txClient.Cypher
.Match("(m:Movie)")
.Where((Movie  m)  =&gt;  m.title  ==  originalMovieName)
.Set("m.title = {newMovieNameParam}")
.WithParam("newMovieNameParam",  newMovieName)
.ExecuteWithoutResults();

txClient.Cypher
.Match("(m:Movie)")
.Where((Movie  m)  =&gt;  m.title  ==  newMovieName)
.Create("(p:Person {name: {actorNameParam}})-[:ACTED_IN]-&gt;(m)")
.WithParam("actorNameParam",  newActorName)
.ExecuteWithoutResults();

tx.Commit();
}

```

我们用这个查询做了两件事:首先，我们将给定的电影(由 originalMovieName 参数给定)重命名为一个新名称(newMovieName 参数)。之后，我们向重命名的电影添加一个新演员(newActorName)。

该事务仅由 tx 提交。Commit()调用。如果出现异常或 tx。Rollback()被调用，事务被中止，更改被回滚。

## 的真实用途。NET Neo4j

将 Neo4j 用于测试或演示项目很简单，但是从. NET 的角度来看，Neo4j 有什么实际用途吗？从 ACL /文件系统管理系统( [Aikux](http://aikux.com) )到竞赛网站( [Tournr](https://tournr.com) )到私人故事匹配系统([Onty](https://onty.com))——甚至是历史地图集(Codex)都有很好的例子。)

图表模型已经被证明足够吸引像 Tournr 这样的人从文档数据库转向 Neo4j。这是因为那里的团队发现了运行时问题，这些问题围绕着大量的数据库点击来查找信息，或者(为了防止这种情况)使用包含大量复制信息的较大文档，这些信息保存在数据库的其他地方。

从视觉角度来看，查看锦标赛和注册者要简单得多，也更直观，重要的是，你可以在白板/纸垫/餐巾纸上勾画出模型，数据库中也是如此。不像 RDBMS，不需要概念上的飞跃。

## 文档数据库表示

这是因为，为了提高页面的性能，关于用户的信息在许多地方被复制，所以只有一个对数据库的调用。从精神上来说，这里需要一点努力才能得到它。

诸如谁注册了某个类之类的简单查询非常简单——只需查看正在讨论的类。但是稍微复杂一点的查询，比如 find who registered for the competition，会更复杂，因为您需要浏览每个类，然后加入结果。

## 图形数据库表示

这样做的图形方式更容易理解，因为关系建模使询问基本问题变得简单，因为它是根锦标赛的简单遍历。

总之，使用 Neo4j 中实例化的原生图方法处理数据更好，因为它允许开发人员:

●维护丰富的数据模型。
●高效处理关系。
●轻松编写查询。
●快速开发应用。

因为。NET 开发人员，列表会增加，因为您还可以使用:

● Neo4j 安装程序。
●来自. NET 的 Neo4j 的驱动
●Azure 上的一个主机数据库。
●将应用部署到 Azure 的能力。

如果您对 RDBMS 的缓慢、僵化的模式结构和类型安全的实体感到沮丧，那么图形可能是理想的下一步。

当然，Neo4j 的 API 最初是不熟悉的，但是坚持使用它，你将能够看到 graph 技术如何帮助你与你的用户一起快速而轻松地构建伟大的应用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>