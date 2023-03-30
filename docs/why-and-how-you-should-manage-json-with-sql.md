# 为什么(以及如何)应该用 SQL 管理 JSON

> 原文：<https://thenewstack.io/why-and-how-you-should-manage-json-with-sql/>

我们都知道，许多现代应用程序依赖 REST APIs 与其他服务对话，尤其是在云中。我们都知道这些 API 通常使用最近的创新来发送和接收数据:[JavaScript Object Notation(JSON)文档](https://www.oracle.com/database/what-is-json/?source=:ex:pw:::::TNS_A&SC=:ex:pw:::::TNS_A&pcode=)。我们知道，在您的应用程序中，有很多方法可以存储、管理和共享这些文档。

 [克里斯·萨克森

Chris 是 Oracle 数据库的开发人员，他的工作是帮助您充分利用 Oracle 数据库，享受 SQL 带来的乐趣。你可以在 Twitter 上找到他，@ChrisRSaxon，在他的博客上，都是 SQL 的东西。](https://uk.linkedin.com/in/saxonchris) 

许多人不知道的是，管理 JSON 的最佳方式是使用一种看似古老的工具:SQL 语言。让我们看看这是为什么，以及如何做到这一点的五个例子。

关系数据库以及在其中操作数据的 SQL 语言是 40 多年前开发的，目的是用当时的存储技术解决数据质量问题。MySQL、Oracle Database、IBM DB2、Microsoft SQL Server 等数据库取得了巨大的成功，部分原因是与处理重复、部分或缺失记录的手动方法相比，它们为开发人员和数据库管理员节省了大量时间。这些数据库还带来了强大的事务保证，使开发人员更容易在多用户环境中确保正确的结果。

在过去的四十年中，关系模型和 SQL 语言被一次又一次地证明是处理大量数据的理想工具。大量的数据。巨大的。巨大的。这就是 JSON 的用武之地。

JSON 文档可能很大，并且包含分布在关系数据库的各个表中的值。这使得创建和使用这些 API 变得非常困难，因为您可能需要将几个表中的数据组合起来形成一个响应。

然而，在使用服务 API 时，您会遇到相反的问题，即，将一个大的(也就是海量的)JSON 文档分割成适当的表。使用定制的代码来映射应用层中的这些元素是很繁琐的。这样的定制代码，除非由了解数据库工作原理的人非常仔细地构建，否则还会导致数据库服务的多次往返，使应用程序变慢，并可能消耗额外的带宽。这对于一个手机应用来说太可怕了。

处理来自服务 API 的 JSON 的一个更快更简单的方法是通过使用 SQL 的[。](https://oracle.com/sql/?source=:ex:pw:::::TNS_B&SC=:ex:pw:::::TNS_B&pcode=)

您可以只使用几行 SQL 来更好地管理应用程序中的 JSON 文档。这里有五个简单的例子:

*   用 SQL 生成 JSON。
*   将 JSON 转换为关系行和关系列。
*   更新 JSON 文档。
*   高效搜索 JSON。
*   参见 JSON 文档的结构。

## 用 SQL 生成 JSON

你的任务是制作一个 API。它必须返回部门详细信息和在该部门工作的一系列员工。例如:

```
{

"department":  "Accounting",
"employees":  [
 {
      "name":  "Higgins, Shelley",
      "hireDate":  "2002-06-07T00:00:00"
 },
 {
      "name":  "Gietz, William",
      "hireDate":  "2002-06-07T00:00:00"
 }
  ]
}

```

部门数据和员工数据可能在不同的表中。要在应用程序中创建一个 JSON 文档，可以首先查询 departments 表，然后获取它的雇员，遍历这些雇员来创建 JSON 数组。

这可能会导致对数据库的大量调用，而网络通常是堆栈中最慢的部分。因此，每一个额外的调用都浪费了更多的时间来处理数据，或者为最终用户提供更好的体验。

使用 SQL，您可以通过一个查询创建整个文档:

```
select json_object  (
      'department'  value  d.department_name,
      'employees'  value json_arrayagg  (
        json_object  (
          'name'  value last_name  ||  ', '  ||  first_name,
          'hireDate'  value hire_date
 )
 )
 )
from hr.departments  d
join hr.employees  e
on  d.department_id  =  e.department_id
group by  d.department_name;

```

这段 SQL 代码在一次数据库访问中构建了整个 JSON 文档。即使数据分布在 10 个表中，只要将它们添加到连接中，就可以在一次读取中获得所有数据。

将数据作为 JSON 返回，这样就不必在应用程序中将列映射到 JSON 字段。这减少了您需要编写的代码量。它还将应用程序代码从数据库模式中分离出来，使您将来更容易更改表结构。您需要做的就是更新 SQL 代码。

最后一个好处是，JSON 函数的结构与 JSON 文档的模式非常匹配，这使得查看查询是否返回所需的格式更加容易。

生成 JSON 只是挑战的一半。在使用 API 时，您还需要获取 JSON 响应并将它们存储在关系表中。

## 将 JSON 转换成关系行和关系列

如果你是编程，这很难。但是 SQL 使这项任务变得简单。使用 [JSON_table，您可以取消嵌套 JSON 数组](https://blogs.oracle.com/sql/post/how-to-store-query-and-create-json-documents-in-oracle-database?source=:ex:pw:::::TNS_C&SC=:ex:pw:::::TNS_C&pcode=#json-table)，为数组中的每个元素返回一行。

例如，通过将上面的文档作为一个[绑定变量](https://blogs.oracle.com/sql/post/improve-sql-query-performance-by-using-bind-variables?source=:ex:pw:::::TNS_D&SC=:ex:pw:::::TNS_D&pcode=)传递给这个查询，SQL 可以为每个雇员生成一行:

```
select  j.*
from json_table  (
 :json_document,
 '$'  columns  (
      department path  '$.department',
      nested path  '$.employees[*]'
      columns  (
 name path  '$.name',
 hire_date path  '$.hireDate'
 )
  )
)  j;
DEPARTMENT  NAME            HIRE_DATE
Accounting  Gietz,  William  2002-06-07T00:00:00
Accounting  Higgins,  Shelley  2002-06-07  T00:00:00

```

您可以将查询的输出直接插入到您的表中，避免了对数据库映射代码的需求并限制了往返。

此时，您可能会想:将文档原样插入到数据库的单个表中不是更容易吗？这肯定会使添加新文档和通过主键获取它们变得更加容易。

但它带来了不同的挑战。您可能仍然需要更改现有的文档。搜索存储的 JSON 文档可能会很慢。你怎么确切地知道这些文件的结构是什么？

幸运的是，Oracle 数据库有许多选项可以帮助您处理存储在数据库中的 JSON 文档。

## 更新 JSON 文档

在将 JSON 文档加载到数据库中之后，您可能需要对其进行修改，比如当客户更新移动应用程序中的信息时，或者如果您向 API 添加了新的功能时。

编辑 JSON 文档可能很难，尤其是当您需要对一个文档进行许多修改时。因此，虽然更改 JSON 文档中的单个值很简单，比如客户的地址，但是更改数组中的对象却很棘手。

使用`JSON_transform`，您可以使用一条 SQL 语句添加、删除或更新许多属性。下面的 SQL 删除了 employees 数组中的第一个条目，在该数组的末尾添加了一个新对象，并更新了部门名称:

```
json_transform  (
  :json_document,  
  remove  '$.employees[0]',
  append  '$.employees'  =  (
    json_object  (  
      'name' value  'Saxon, Chris',
      'hireDate'  value  '2020-01-01T00:00:00'
    )
  ),
  replace  '$.department'  =  'Finance and Accounting'
)

```

JSON 文档的自由格式特性意味着属性可能会意外出现、缺失或为空。为了帮助您避免不必要的更改或副作用，`JSON_transform`包含了涵盖这些情况的条款。每个子句都让您可以选择忽略异常或引发异常。这些选项为您提供了对变更的细粒度控制。

使用 SQL 和 JSON，将两个部门的雇员数组合并成一个数组是很容易的。您可能想知道:如何找到这些 JSON 文档？

## 高效搜索 JSON

SQL 简单的点符号访问让您可以毫不费力地搜索 JSON。您所需要做的就是将路径传递给属性和您正在寻找的值。

例如，这将查找部门属性的值为`Finance` :
的所有文档

```
select *  from companies  c
where  c.department_data.department  =  'Finance';

```

当然，表中可能有数百万行，而现实世界中的 JSON 文档可能很大(或巨大或海量)。扫描所有这些行可能需要很长时间。这就带来了一个重要的问题:如何快速完成这些查询？

关键是[创建索引](https://blogs.oracle.com/sql/post/how-to-create-and-use-indexes-in-oracle-database?source=:ex:pw:::::TNS_E&SC=:ex:pw:::::TNS_E&pcode=#unique)来支持查询。Oracle 数据库有一系列创建索引的方法。这里有三个:

*   JSON 搜索索引。这将对整个文档进行索引。
*   基于函数的索引。这些目标是文档中的一个属性。
*   多值索引。这些方法以数组中的许多元素为目标。

当您需要报表工具或其他特定查询来访问数据时，搜索索引是最适合的。它们还启用了 [JSON 数据指南](https://blogs.oracle.com/sql/post/how-to-store-query-and-create-json-documents-in-oracle-database?source=:ex:pw:::::TNS_F&SC=:ex:pw:::::TNS_F&pcode=#json-data-guide)。使用它，您可以获得存储在数据库表中的 JSON 模式。

多值索引和基于函数的索引针对特定的属性，这使得它们比搜索索引更小、更有效。当您在应用程序中编写 JSON 搜索查询时，最好构建一个与查询的 where 子句相匹配的索引。

## 参见 JSON 文档的结构

JSON 的自由形式既是它最大的优点，也是它最大的缺点。一旦开始在数据库中存储 JSON 文档，就很容易忘记它们的结构。了解文档结构的唯一方法是查询其属性。

JSON 数据指南是一个为您解决这个问题的函数。通过将 JSON 文档传递给`JSON_dataguide`函数，可以获得它们的模式。如果创建一个搜索索引，这些信息将在数据库的数据字典中可用，其中包括存储在索引 JSON 文档中的每个属性的路径和数据类型。

例如，这个查询返回存储在`departments.department_json` :
中的 JSON 文档的结构

```
select json_dataguide  (  
 d.department_json,  
 dbms_json.format_hierarchical  
 )  
from departments  d;  

{
  "type"  :  "object",
  "o:length"  :  256,
  "properties"  :  {
    "employees"  :  {
      "type"  :  "array",
      "o:length"  :  128,
      "o:preferred_column_name"  :  "employees",
      "items"  :  {
        "properties"  :  {
          "name"  :  {
            "type"  :  "string",
            "o:length"  :  16,
            "o:preferred_column_name"  :  "name"
          },
          "hireDate"  :  {
            "type"  :  "string",
            "o:length"  :  32,
            "o:preferred_column_name"  :  "hireDate"
          }
        }
      }
    },
 "department"  :  {
      "type"  :  "string",
      "o:length"  :  16,
      "o:preferred_column_name"  :  "department"
    }
  }
}

```

## 结论

对于每个应用程序来说，处理大型 JSON 文档都具有挑战性。无论数据是如何存储的，都可能需要将 JSON 映射到关系数据库，反之亦然。Oracle SQL 提供了许多选项来简化这一过程。

这个[实时 SQL 脚本](https://livesql.oracle.com/apex/livesql/file/content_HZ0745GCRAOQYKGBJBP3LUH47.html?source=:ex:pw:::::TNS_G&SC=:ex:pw:::::TNS_G&pcode=)是一个在线课程，提供了展示这些特性如何工作的例子。看看吧！关于在 Oracle 数据库中使用 SQL 管理 JSON 文档的完整概要，请阅读 [JSON 开发人员指南](https://docs.oracle.com/en/database/oracle/oracle-database/21/adjsn/index.htmlhttps:/docs.oracle.com/en/database/oracle/oracle-database/19/adjsn/index.html?source=:ex:pw:::::TNS_H&SC=:ex:pw:::::TNS_H&pcode=)。如果您想在自己的数据库上尝试这些，请注册 [Oracle 云免费层](https://www.oracle.com/cloud/free/?source=:ex:pw:::::TNS_I&SC=:ex:pw:::::TNS_I&pcode=)。您还可以查看我在 Oracle Dev Gym 上的免费 SQL 课程和我在 YouTube 频道上的结合 SQL 和 magic 的视频。

我希望这篇文章能够帮助您了解为什么开发人员在 40 年前爱上了 SQL，以及它如何让您在今天更好地管理 JSON 文档。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>