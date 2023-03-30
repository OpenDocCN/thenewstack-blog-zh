# 数据库操作的经济学

> 原文：<https://thenewstack.io/the-economics-of-database-operations/>

不断上升的成本和不确定的经济形势正促使许多组织寻找少花钱多办事的方法。数据库也不例外。幸运的是，通过转移到文档数据库并实践适当的数据建模技术，有机会提高效率并节省资金。

文档数据库以两种方式为公司省钱:

1.  以对象为中心的跨语言 SDK 和模式灵活性意味着开发人员可以更快地创建和迭代生产代码，从而降低开发成本。
2.  对于给定的事务吞吐量，需要的硬件更少，从而大大降低了运营成本。

## 开发者效率

所有现代开发都使用对象的概念。对象定义了一组相关的值和方法，用于读取、修改和导出这些值的结果。顾客、发票和火车时刻表都是对象的例子。像所有程序变量一样，对象是短暂的，因此必须通过将它们保存到磁盘存储器中来使其持久。

我们不再像 20 世纪 90 年代 Windows 桌面开发人员那样手动将对象序列化到本地文件中。如今，数据不是存储在运行我们的应用程序的计算机上，而是存储在一个由多个应用程序或一个应用程序的实例访问的中央位置。这种共享访问意味着，我们不仅需要通过网络高效地读写数据，还需要实现允许对数据进行并发更改的机制，而不会有一个进程覆盖另一个进程的更改。

关系数据库早于面向对象编程的广泛使用和实现。在关系数据库中，数据结构是数值的数学表。与数据的交互通过一种专门的语言 SQL 进行，SQL 在过去 40 年中不断发展，以提供与存储数据的各种交互:过滤和重塑数据，将其从平面的、消除重复的相关模型转换为表格形式的、重新复制的、连接的结果呈现给应用程序。然后，数据被痛苦地从这些冗余值行转换回程序需要的对象。

这样做需要大量的开发人员的努力、技能和领域知识。开发人员必须理解表之间的关系。他们需要知道如何检索不同的信息集，然后从这些数据行中重建他们的数据对象。有一个假设是，开发人员在进入工作世界之前学会了这一点，并且能够做到这一点。但这完全是不真实的。即使一个开发人员在 [SQL](https://thenewstack.io/everything-you-need-to-know-about-distributed-sql/) 方面受过一些正规教育，他也不太可能知道如何高效地编写重要的例子。

文档数据库从持久化对象的想法开始。它们允许您用很少的代码或转换将强类型对象持久化到数据库，并使用 exemplar 对象过滤、整形和聚合结果，而不是试图用蹩脚的英语(即 SQL)来表达描述。

假设我们想要存储一个客户对象，其中客户有一些重复属性的数组，在本例中是地址。这里的地址是不在客户之间共享的弱实体。下面是用 c#/类 Java 伪代码编写的代码:

```
class Address  :  Object  {

 Integer number;
 String street,  town,  type;

 Address(number,  street,  town,  type)  {
 this.number  =  number
 this.street  =  street
 this.town  =  town,
 this.type  =  type
 }

 //Getters and setters or properties as required
}
class Customer  :  Object  {
 GUID customerId;
 String name,  email
 Array  <  Address  >  addresses;

 Customer(id,  name,  email)  {
 this.name  =  name;
 this.email  =  email;
 this.customerId  =  id
 this.addresses  =  new Array  <  Address  >  ()
 }
 //Getters and setters or properties as required
}

Customer newCustomer  =  new Customer(new GUID(),
 "Sally Smith",  "sallyport@piratesrule.com")

Address home  =  new Address(62,  'Swallows Lane',  'Freeport',  'home')
newCustomer.addresses.push(home)

```

要将这个客户对象存储在关系数据库管理系统(RDBMS)中，然后检索给定位置的所有客户，我们需要以下代码或类似代码:

```
//Connect
RDBMSClient rdbms  =  new RDBMSClient(CONNECTION_STRING)
rdbms.setAutoCommit(false);

// Add a customer

insertAddressSQL  =  "INSERT INTO Address (number,street,town,type,customerId) values(?,?,?,?,?)"
preparedSQL  =  rdbms.prepareStatement(insertAddressSQL)
for  (Address address of newCustomer.addresses)  {
 preparedSQL.setInt(1,  address.number)
 preparedSQL.setString(2,  address.street)
 preparedSQL.setString(3,  address.town)
 preparedSQL.setString(4,  address.type)
 preparedSQL.setObject(5,  customer.customerId)
 preparedStatement.executeUpdate()
}

insertCustomerSQL  =  "INSERT INTO Customer (name,email,customerId) values(?,?,?)"
preparedSQL  =  rdbms.prepareStatement(insertCustomerSQL)
preparedSQL.setString(1,  customer.name)
preparedSQL.setString(2,  customer.email)
preparedSQL.setObject(3,  customer.customerId)
preparedStatement.executeUpdate()
rdbms.commit()

//Find all the customers with an address in freeport

freeportQuery  =  "SELECT ct.*, ads.* FROM address ad
INNER JOIN address ads ON ad.customerId=ads.customerId AND ad.town=?
INNER JOIN customer ct ON ct.customerId = ad.customerId"

preparedSQL  =  rdbms.prepareStatement(freeportQuery)
preparedSQL.setString(1,  'Freeport')
ResultSet rs  =  preparedSQL.executeQuery()
String CustomerId  =  ""
Customer customer;  

//Convert rows back to objects

while  (rs.next())  {
 //New CustomerID value
 if rs.getObject('CustomerId').toString  !=  Customerid)  {
 if  (customerId  !=  "")  {  print(customer.email)  }
 customer  =  new Customer(rs.getString("ct.name"), 
 rs.getString('ct.email'),  
 rd.getObject('CustomerId')

  }
 customer.addresses.push(new Address(rs.getInteger('ads.number'),  
 rs.getString("ads.street"),
 rs.getString('ads.town'), 
 rs.getString("ads.type")))
}
if  (customerId  !=  "")  {  print(customer.email)  }

```

随着对象中字段深度或数量的增加，这段代码不仅冗长且越来越复杂，而且添加一个新字段将需要大量相关的更改。

相比之下，使用[文档数据库](https://thenewstack.io/debunking-the-myth-of-going-schemaless/)，您的代码将如下所示，并且如果您向对象添加新的字段或深度，不需要更改数据库交互:

```
//Connect
mongodb  =  new MongoClient(CONNECTION_STRING)
customers  =  mongodb.getDatabase("shop").getCollection("customers",Customer.class)

//Add Sally with her addresses
customers.insertOne(newCustomer)

//Find all the customers with an address in freeport
FreeportCustomer  =  new Customer()
FreeportCustomer.set("addresses.town")  =  "Freeport"

FindIterable  <  Customer  >  freeportCustomers  =  customers.find(freeportCustomer)
for  (Customer customer  :  freeportCustomers)  {
 print(customer.email)  //These have the addresses populated too
}

```

当开发人员遇到编程模型(对象)和存储模型(行)之间的脱节时，他们会很快创建一个抽象层，对他们的同事和未来的自己隐藏起来。自动将对象转换为表以及将表转换为对象的代码称为对象关系映射器或 ORM。不幸的是，ORM 往往是特定于语言的，这将开发团队局限于该语言，使得使用额外的工具和技术处理数据变得更加困难。

当您想要执行更复杂的操作时，使用 ORM 也不能让您摆脱 SQL 的负担。此外，由于底层数据库不知道对象，ORM 通常不能在其数据库存储和处理中提供很高的效率。

像 MongoDB 这样的文档数据库保存了开发人员已经熟悉的对象，所以不需要像 ORM 这样的抽象层。一旦你知道如何在一种语言中使用 MongoDB，你就知道如何在所有语言中使用它，你永远不必从对象回到伪英语 SQL 查询。

PostgreSQL 和 Oracle 有 JSON 数据类型也是事实，但是你不能用 JSON 来摆脱 SQL。RDBMS 中的 JSON 是针对非托管、非结构化数据的，一种美化了的字符串类型，带有可怕的附加查询语法。JSON 不是针对数据库结构的。为此，您需要一个实际的文档数据库。

## 给定工作负载所需的硬件更少

现代文档数据库在内部非常类似于 RDBMS，但与模式规定所有请求都被平等对待的规范化关系模型不同，文档数据库以牺牲其他工作负载为代价为给定工作负载优化该模式。文档模型将按索引组织的表和聚集索引的思想提升到了一个新的层次，不仅像在关系模型中那样共同定位相关的行，而且共同定位您可能希望用于给定任务的所有数据。它的思想是，如果您有一个一阶数组类型，关系的重复子属性不需要在一个单独的表中(因此也不需要在存储中)。或者换句话说，您可以拥有一个“嵌入式表格”列类型

这种协同定位，或者像有些人所说的那样，弱实体表的隐式连接，降低了从存储中检索数据的成本，因为通常只需要读取一个缓存或磁盘位置，就可以将对象返回给客户端或对其应用过滤器。

相比之下，需要识别、定位和读取许多行来返回相同的数据，并且需要客户端硬件来从这些行中重建对象，这一成本如此之高，以至于许多开发人员会在其主数据库前放置一个更简单的辅助键值存储来充当缓存。

这些开发人员知道主数据库无法单独满足工作负载需求。文档数据库不需要外部缓存来满足性能目标，但仍然可以执行 RDBMS 的所有任务，只是效率更高。

效率有多高？我已经完成了创建测试工具的步骤，以确定与标准关系数据库相比，使用文档数据库可以实现多少效率和成本节约。在这些测试中，我试图量化同类最佳的云托管 RDBMS 与云托管文档数据库(特别是 MongoDB Atlas)的每美元事务吞吐量。

我选择的用例代表了一个常见的真实世界的应用程序，其中一组数据被频繁更新，甚至被更频繁地读取:一个英国车辆检查(MOT)系统及其公共和私有接口的实现，使用它自己发布的数据。

测试表明，在 MongoDB Atlas 中，创建、更新和读取操作要快得多。总的来说，在具有类似实例成本的类似指定服务器实例上，MongoDB Atlas 每秒多管理大约 50%的事务。随着关系结构变得越来越复杂，这种情况也会增加，从而使连接更加昂贵。

除了基本实例成本之外，由于磁盘使用的额外费用，关系数据库的每小时运行成本在这些测试的 Atlas 成本的 200%到 500%之间。在 Atlas 系统上，托管该系统的费用总体上要便宜三至五倍，因为该系统高度可用，可满足既定的性能目标。最简单地说，Atlas 每秒每美元可以推动更多的交易。

独立测试证实了文档模型的效率。Temenos 是一家总部位于瑞士的软件公司，被世界上最大的银行和金融机构所使用，已经进行了超过 15 年的基准测试。在最近的测试中，该公司通过 MongoDB Atlas 每秒运行了 74，000 次交易。

测试结果显示，与三年前的类似测试相比，每内核吞吐量提高了四倍，而基础设施使用量却减少了 20%。该测试使用生产级基准架构进行，其配置反映了生产系统，包括高可用性、安全性和专用链接等非功能性需求。

在测试过程中，MongoDB 读取了 74，000 个 TPS，响应时间为 1 毫秒，同时还接收了另外 24，000 个 TPS。另外，因为 Temenos 使用的是文档数据库，所以中间没有缓存。所有的查询都直接针对数据库运行。

## 摘要

除非您希望在您的组织中有一个供所有应用程序使用的数据库，否则将您的工作负载从关系模型转移到文档模型将允许您用同样数量的开发人员在更短的时间内构建更多的数据库，并且在生产环境中运行数据库的时间会大大减少。你的企业还没有开始使用面向对象编程是不太可能的。那么为什么还没有开始使用面向对象的文档数据库呢？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>