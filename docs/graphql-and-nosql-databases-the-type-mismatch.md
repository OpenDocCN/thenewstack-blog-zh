# GraphQL 和 NoSQL 数据库:类型不匹配

> 原文：<https://thenewstack.io/graphql-and-nosql-databases-the-type-mismatch/>

[](https://www.linkedin.com/in/bobbiecochrane/)

[Bobbie Cochrane](https://www.linkedin.com/in/bobbiecochrane/)

[Bobbie 是一位经验丰富的高级研究科学家，曾在信息技术和服务行业工作过。她是一名优秀的研究专家，精通区块链、可伸缩性、IBM DB2、云、计算机科学和企业软件。](https://www.linkedin.com/in/bobbiecochrane/)

[](https://www.linkedin.com/in/bobbiecochrane/)[](https://www.linkedin.com/in/bobbiecochrane/)

无类型系统，如 NoSQL 数据库、JSON、JavaScript 和 Python，已经流行起来，并且在实践中非常有用，因为世界上的数据并没有很好地符合一致的、严格的结构。

即使有，也几乎不可能捕获数据的所有方面并预测这些数据的未来用途。

然而，数据也不是完全无模式的，任何使用数据的应用程序都将实施定义良好的模式。

NoSQL 的反对者抱怨说，NoSQL 的流行使应用程序开发回到了 60 年代的层次数据库时代，忽略了这样一个事实，即这些无类型系统中的数据实际上具有一致的结构，并且它们的模式是精心设计的，并且随着应用程序开发过程有序地发展。

随着 GraphQL 的出现，我们可以在这些系统上引入一个类型系统，而不影响它们所引入的灵活性，将有序带回到看似无序的地方。

让我们使用我们最喜欢的后端数据库之一 MongoDB 来完成这个过程。

假设我们有一个代表客户的 GraphQL 模式:

```
 type  Customer  {
      id:  ID!
      name:  String!
      email:  String
      age:  Int
      joined:  Date!
 }

```

上面说客户有五个属性，每个属性都必须是如下所示的类型。“！”的存在在 GraphQL 中表示字段不可为空，类似于 SQL 中的`NOT NULL`。

现在假设您的 MongoDB 集合包含以下三个 JSON 风格的文档:

```
 [
      {
 “id”:  “12345”,
 “name”:  “John Doe”,
 “email”:  “john.doe@example.com”,
 “age”:  20,
 “joined”:  “2021-01-10”,
 “children”:  [“John”,  “Mary”]
      },
      {
 “id”:  “23456”,
 “name”:  “Jane Doe”,
 “email”:  “jane.doe@example.com”,
 “age”:  30,
 “joined”:  “2020-01-10”,
 “hobbies”:  [“surfing”,  “reading”]
      },
      {
 “id”:  “34567”,
 “name”:  “John Smith”,
 “email”:  “john.smith@example.com”,
 “age”:  40.1
 “offices”:  [“StepZen”]
      }
      ]

```

如您所见，除了少数例外，数据的结构相当一致。显而易见的是，每个文档都有不同的特征。无名氏有孩子，无名氏有爱好，约翰·史密斯有办公室。“joined”属性似乎很常见，但是仔细观察，我们发现其中一个文档缺少这个字段。最后，我们注意到，如果我们只考虑无名氏夫妇，我们可能会认为年龄可以用整数来表示，但史密斯先生的年龄显然不是整数。

 [赫尔曼·卡马雷纳

Herman 是 StepZen 的首席软件工程师，拥有超过 25 年的技术经验。赫尔曼是谷歌的数据科学家和高级软件工程师。在此之前，他曾在 Spribo 和 QoS Labs 担任 CTO，并在 Apple、WebMethods 和 BEA Systems 担任高级职位，开始了他的科技之旅。](https://www.linkedin.com/in/herman-camarena-b112a4/) 

这些数据如何符合我们的 GraphQL 模型？存在明显的问题:

1.  连接的字段不能设置为！因为在最后一份文件中，它不见了。很容易解决，对吧？将它转换成连接的“日期”，而不是连接的“日期！”但是，如果在数百万个文档中，这是唯一一个看起来没有任何连接价值的记录，该怎么办呢？随着这种视角的增加，删除！现在似乎是一个坏主意，因为这种异常可能代表坏数据。
2.  文档似乎有不同的额外字段。这是一种非常常见的模式，即使数据是在关系数据库管理系统等严格类型的系统中，这也是引入 BLOBS(二进制大对象)、XML 和 JSON 的原因。使用 GraphQL，我们可以做一些事情，比如:

    ```
          type  Customer  {       ...  children:  [String!]  hobbies:  [String!]  office:  [String!]       } 
    ```

    确保所有三个记录都可以被映射。注意，字段孩子，爱好和办公室没有！表示它们是可选的。(字符串！列表中的描述符意味着列表中的项目不能为空)。然而，这似乎也不是最理想的；毕竟，我们可能会在数百万条记录中得到数百个这样的字段，这导致了过度膨胀和应用程序逻辑。下面我们会给你看一个更好的方法。
3.  我们的 GraphQL 模式假设年龄的类型为 INT，这适用于 Doe 先生和夫人，但与 Smith 先生的年龄不兼容，这种情况最好用 FLOAT 类型处理，除非将其类型转换为 INT。

这些只是几个简单的例子，说明了强类型(GraphQL)和弱类型(在本例中是 JSON)之间的结合问题。

然而，我们在 StepZen 的团队已经发现了一些使用 GraphQL 解决这些和其他问题的优秀解决方案。

1.  GraphQL 类型可以是 JSON。这意味着尽管 JSON 中的数据对于 GraphQL 是不透明的，但是任何类似 JSON 的数据都可以被赋给该字段，从而保持了底层无类型系统的类型灵活性。例如，如果有一个字段:

    ```
          type  Customer  {       ...  extras:  JSON       } 
    ```

    ，那么所有记录都可以通过 GraphQL 层传递。
2.  GraphQL 类型可以是联合类型。因此，我们可以声明:

    ```
          union Extra  =Hobbies  |  Children  |  Offices       type  Customer  {       ...  extras:  [Extra!]       } 
    ```

    ，这保持了表示的紧凑性。此外，记录仍然是强类型的，除了字段 extras，它可以是三种类型中的一种或多种。此外，我们可以使用带有类型条件的片段来捕获特定于额外类型的设计:

    ```
     {       customers  (id:  “12345”)  {  name  extras:  {             __typeName             …  on  hobbies  {  level             }             …  on  children  {  name             }             …  on  offices  {  location             }  }       }  } 
    ```

在上面的例子中，GraphQL 查询明确地说，“如果 extras 的一个元素是业余爱好类型，那么返回级别，等等。”这允许 GraphQL API 做正确的事情，以正确的形式返回数据，从而减轻应用程序的负担。

在上面的所有内容中，GraphQL API 的开发人员做出了一些明确的选择，即她想要的类型与后端的类型大致匹配。如果我们有相反的问题呢？如果我们检查后端并从底层数据中自动导出 GraphQL 类型会怎么样？对于这样的系统:

1.  对足够多的记录进行采样，以了解多样性。MongoDB 有一个 find，您可以在其中检索多个记录。REST APIs 可能有分页模型。SQL 系统有限制和偏移。不管怎样，一打左右的记录是一个很好的样本。
2.  做出一些明智的选择。如上所述，这些系统中的数据并不是完全无模式的；它们包含一些简单的模式。找到最大的公共子结构，并将不常见的子结构声明为 UNION 或 JSON。
3.  选择正确的类型，当有疑问时，放弃！

如果你查看一下 [JSON2SDL](https://json2sdl.com) ，你会发现我们工作的公司 [StepZen](https://stepzen.com) 构建了一个这样的实现。事实上，我们已经构建了一套自省器来做出这些明智的选择，包括反对各种各样的 REST、SQL 和 NoSQL 后端。我们目前正在向公众发布我们的 [REST2GraphQL 内省程序。](https://rest2graphql.io)

类型不匹配的问题是 GraphQL 最终实现其潜力需要解决的一个重要问题。然而，作为一种语言，它有许多特性使得不匹配问题不那么严重。StepZen 的 JSON2SDL 等工具使这项工作越来越自动化。像 MongoDB 和 GraphQL 这样的 NoSQL 数据库之间的范式不匹配可以很容易地弥合。对于 REST 和 SQL 等其他后端也是如此。所有迹象都表明 GraphQL 将成为访问各种后端的默认强类型 API 层。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>