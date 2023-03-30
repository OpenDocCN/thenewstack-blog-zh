# Maria DB 对 Java 的非阻塞连接器产生了反应

> 原文：<https://thenewstack.io/maria-db-gets-reactive-with-a-non-blocking-connector-for-java/>

开源关系数据库 [MariaDB](https://mariadb.com/) 已经于本周发布了其[反应式关系数据库连接(R2DBC)连接器](https://github.com/mariadb-corporation/mariadb-connector-r2dbc)并正式发布，这使得 Java 开发人员能够将与 MariaDB 的反应式交互集成到他们新的和现有的反应式应用程序中。

直到现在，使用 MariaDB 的 Java 开发人员不得不依赖于 20 多年前首次发布的 [Java 数据库连接(JBDC) API](https://docs.oracle.com/javase/8/docs/technotes/guides/jdbc/) 。JDBC 的问题在于它没有跟上开发方法的步伐，比如使用异步数据流的反应式编程。JDBC 是一个阻塞 API，这意味着当发出请求时，它会保持忙碌状态，直到提供响应。相比之下，R2DBC 是非阻塞的，这意味着当其他请求挂起时，可以发出请求并对其进行响应。随着 R2DBC 的加入，MariaDB 的开发人员关系主管 Rob Hedgpeth 表示，其用户现在可以更容易地享受其他类型数据库的某些好处。

“这对关系数据库非常重要，因为这是对一些更 NoSQL 方法的一种追赶。像 MongoDB 或 Couchbase 这样的东西都有事件驱动的，或者我们通常所说的反应式的交互。“这是 NoSQL 运动的优势之一，着眼于事物的现状，在一个关系环境中可能发生的事情，并能够将其添加到更多的 NoSQL 方法中。这是从 Java 生态系统中的关系数据库方面给出的答案。”

MariaDB 的 R2DBC 连接器是 [R2DBC 规范](https://r2dbc.io/spec/0.8.0.M8/spec/html/)的一个实现，该规范致力于为 Java 开发人员提供一个“事件驱动的、非阻塞的、功能性的编程模型，该模型不会对并发性或异步性做出假设”。

Hedgpeth 解释说，对于 JDBC，开发人员必须处理旋转多个线程和管理上下文，他说这是他们不愿意做的事情。

“R2DBC 的重点基本上是试图限制这种情况，尽可能地将线程数量限制在一个，基本上是说，‘嘿，我真的只是想尽可能地利用资源，’”Hedgpeth 说。" MariaDB 驱动程序有助于实现这一点."

他进一步解释说，R2DBC 通过使用流行的 API 和库，使得反应式编程变得非常容易访问。

Hedgpeth 解释说:“这种简单性源于 R2DBC 规范对 Reactive Streams API 的使用，这是一种非常流行的反应式编程库规范，旨在使用事件驱动的交互来处理异步数据流，支持一种称为非阻塞背压的思想。“基本上，这意味着开发人员可以使用任何反应流库实现，如 Project Reactor 或 RxJava，他们希望与 R2DBC 结合使用。因此，无论开发人员是计划创建一个新的反应式解决方案，还是打算更换他们的 MariaDB Connector/J (JDBC)驱动器，他们都可以使用 MariaDB Connector/R2DBC 非常轻松地做到这一点。”

除了发布 R2DBC 连接器，MariaDB 还推出了一个[开发人员中心](https://mariadb.com/developer)，其中包括 how-to 和代码示例，以及如何开始使用 R2DBC 的分步说明。MariaDB Connector/R2DBC 在[可供下载](https://mariadb.com/downloads/#connectors)，MariaDB 将于 1 月 13 日上午 10 点(太平洋时间)和下午 4 点(欧洲中部时间)通过 Maven repository 和 MariaDB 提供一个关于使用 R2DBC 创建完全反应式应用的[网络研讨会](https://go.mariadb.com/21Q2-WBN-GLBL-OSSG-R2DBC-Connector-2021-01-13_Registration-LP.html)。

特征图像由[上的](https://unsplash.com/s/photos/back-and-forth?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)[粘土堤](https://unsplash.com/@claybanks?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)剥离。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>