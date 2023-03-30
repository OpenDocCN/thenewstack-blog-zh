# TigerGraph 支持图形查询语言 openCypher

> 原文：<https://thenewstack.io/tigergraph-supports-graph-query-langauge-opencypher/>

相同名称的[图形数据库](https://www.tigergraph.com/getstarted/)的制作者 TigerGraph 已经宣布对 [openCypher](https://opencypher.org/) 的阶段性支持，openCypher 是由 tiger graph 的竞争对手 [Neo4j](https://neo4j.com/?utm_content=inline-mention) 建立的 [Cypher 图形数据库查询语言](https://neo4j.com/developer/cypher/)的开源实现。这种发展可以帮助整合市场上的图形数据库平台及其查询语言，并促进向一种新的统一语言的过渡，这种语言称为 [GQL](https://www.gqlstandards.org/) ，目前正在设计中。

[tiger graph](https://www.linkedin.com/in/yuxusandiego/)的首席执行官兼创始人徐雨这样说:“在 openCypher 的支持下，我们正在推动图形创新的界限，并为开发者提供另一种方式来采用和扩展他们对图形的使用，以在他们的数据中找到有竞争力的见解。”

《新堆栈》采访了 TigerGraph 首席运营官公司、 [Todd Blaschka](https://www.linkedin.com/in/toddblaschka/) 及其产品创新副总裁、[Jay Yu 博士](https://www.linkedin.com/in/jay-jiebing-yu-ph-d-7b97a8/)，讨论这一新闻的意义。Blaschka 和 Yu 也很友好地提供了一个教程，帮助我们理解图形查询语言的前景以及几种语言之间的一些语法差异。我们将尽最大努力在这里重复那个解释者。

## 多种语言还是多种语言？

图形数据库的世界是一个由供应商、平台和标准组成的庞大网络。就像图表本身一样，这个网络包含了许多双边关系，有助于相似性，但不是一致性。其中一个方面是各种图形数据库查询语言本身，其中一些语言受到多种平台的支持，但没有一种语言得到普遍支持。虽然一些跨平台支持的存在有所帮助，但整体的分散阻碍了生态系统的发展。

图形数据库社区想要解决这个问题。这就是为什么由该领域几家供应商的代表组成的图形数据库标准委员会正在努力捕捉几种竞争查询语言的精华，并将它们统一为 GQL，一种单一的[国际标准化组织(ISO)](https://www.iso.org/home.html) 标准图形查询语言，它是 SQL 的扩展，有望在 2024 年作为最终标准发布。

你应该听说过 GQL 吧？也许你遇到过，但是很有可能你遇到过另一种有相似名字的语言。所以要小心。不要把 GQL 和 Gremlin 查询语言混淆，后者是 [Apache Tinkerpop](https://tinkerpop.apache.org/) 项目的一部分。也不要把它和 TigerGraph 自己的查询语言 [GSQL](https://www.tigergraph.com/gsql/) 混淆。而且绝对不要把它和 [GraphQL](https://graphql.org/) 混淆，后者实际上是用于查询 API，而不是图形数据库。

## 解密 TigerGraph 的开放支持

同样，GQL 的目标是在 2024 年成为一个完全受祝福的标准。但在此之前，许多图形数据库公司已经将 openCypher 作为临时标准，现在 TigerGraph 也加入了这一行列。

TigerGraph 对 OpenCypher 的最初支持将以语言翻译器的形式出现，它在输入端接受 OpenCypher 查询，在输出端生成等价的 GSQL 查询。(开发者现在可以访问工具的[有限预览，以了解 openCypher 如何映射到 GSQL)。TigerGraph 认为，这将使更多的开发人员采用它的平台，并将为图形社区的查询语言整合工作提供重要支持。](https://opencypher.tigergraph.com/playground)

## 请举例

不应该低估开发人员的吸引力，因为各种图形查询语言的语法可能会有很大差异。例如，下面显示了一个简单的 GSQL 查询。注意它类似 SQL 的语法，许多开发人员都很熟悉:

```
CREATE QUERY findCustomers()  FOR  GRAPH  G  {
SELECT DISTINCT  c.companyName
    FROM Customer:c  -  (BUYS)  -  Order:o  -  (HAS_PRODUCT)  -  Product:p
    WHERE  p.productName  =  'Chocolade';
    PRINT Result;
}

```

看起来还好吧？与上述查询等价的 openCypher 如下所示(注意嵌入的标签和属性引用):

```
MATCH  (p:Product  {productName:"Chocolade"})  <-[:HAS_PRODUCT]-(:Order)<-  [:BUYS]  -  (c:Customer)
RETURN distinct  c.companyName

```

如果这两个不够不同，Gremlin 中一个不相关的查询可能如下所示。注意流畅的 API 风格的语法，大量使用了“方法链接”(用点分隔的连接的一系列表达式):

```
g.V().has("name","gremlin").
  out("knows").out("knows").values("name")

```

## 标准 FTW

上面的三个例子展示了在图形查询语言中可以找到的各种语法，而且这只是针对我们在这里研究的三种语言(还有更多)。无论您是否喜欢 openCypher 的语法，事实上它已经得到了许多平台的支持，现在包括 TigerGraph，这有助于图形数据库空间的内聚性。

TigerGraph 表示，它将通过将 openCypher 支持直接引入其图形数据库平台来跟进其翻译器，从而使独立的翻译器变得不必要。而且，随着行业向 GQL 1.0 版本发展，TigerGraph 也将支持这一版本。

## 自私，参与，还是两者兼而有之？

有几种方式来看待 TigerGraph 的声明。首先，这可能是一个慈善团体的努力。但是，由于 TigerGraph 使用翻译器来展示它认为自己的 GSQL 语言的高级语法，该声明也可能是游说努力的一部分，以边缘化 openCypher 的影响，支持 TigerGraph 自己的技术。

但是，由于图形数据库供应商正在向 GQL 发展，许多人认为 openCypher 支持是实现这一目标的最佳跳板，更有可能的是，TigerGraph 希望加快这一努力的势头，使图形空间不那么分散，更容易访问，更具生产力，并最终为自己和竞争对手带来更大的利润。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>