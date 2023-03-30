# 时间刻度超函数降低了 PostgreSQL 查询的复杂性

> 原文：<https://thenewstack.io/timescale-hyperfunctions-ease-postgresql-query-complexities/>

PostgreSQL 数据库启动[时标](https://www.timescale.com/)引入了一些新的 SQL 函数，让 [PostgreSQL](https://www.postgresql.org/) 开发者更有效率。

时标推出了[时标 DB](https://github.com/timescale/timescaledb) 超函数，这是为开发人员今天编写的最常见的——通常也是最困难的——查询而预先构建的函数，时标的软件工程师 Joshua Lockerman 说，他参与了新超函数的开发。

Lockerman 在一篇博客文章中说:“Hyperfunctions 特别有助于帮助开发人员测量他们的时间序列数据中的重要内容，这些数据是无情的，并产生大量不断增长的信息流。”。Hyperfunctions 可用于 TimescaleDB 和 PostgreSQL

该公司声称，TimescaleDB 是一个时间序列 SQL 数据库，提供快速分析和可扩展性，并在一个成熟的存储引擎上进行自动化数据管理。

“超功能使开发人员能够更轻松地在他们的 TimescaleDB 和 PostgreSQL 数据库中操作和分析时序数据。正如我们决定在 PostgreSQL 之上构建 TimescaleDB 一样，我们使用现有的 SQL 语法和新函数构建了超函数，以便开发人员可以继续使用他们已经知道的所有工具和框架，并立即提高工作效率。“Hyperfunctions 降低了构建时序数据的门槛，因此更多开发人员可以加入现有的开发人员社区，运行近 300 万个活动 TimescaleDB 数据库，为全球各行业的关键任务应用提供支持。”

与此同时，Lockerman 指出，SQL 是一种强大的语言，Timescale 的策略是，为时间序列分析添加一组专门的函数可以使它变得更好，因为开发人员可以使用他们熟悉的相同的 [SQL 语法](https://www.w3schools.com/sql/sql_syntax.asp)调用 hyperfunction。

Lockerman 还表示，SQL 的流行是该公司在 PostgreSQL 基础上构建 TimescaleDB 的关键原因之一。根据一项堆栈溢出调查，SQL 是世界上第三大最常用的编程语言。

为了了解用户是如何分析和处理时间序列数据的，时标对其客户群进行了跟踪，注意到一些常见的查询开始成形。但是这些查询很难用标准 SQL 编写，时标营销副总裁 Prashant Sridharan 说。

因此，在处理更常见但困难的查询时，“我们决定自己走一条艰难的道路，这样我们就可以给开发者一条更容易的道路，”他说。

[Andrew Brust](https://www.linkedin.com/in/andrewbrust/) ，总部位于纽约的 IT 咨询公司 Blue Badge Insights 的首席执行官和创始人，也是微软的区域总监和最有价值的专业人士，他说他认为 TimescaleDB hyperfunctions 是“有用的”,但不是太具有开创性。

“这一宣布似乎是围绕新的库函数，可从 SQL 调用，这使得在 SQL 查询和脚本中进行时间序列计算更容易，”他说。“本质上，他们已经创建了一些高级函数，这些函数具有扩展 Postgres 的 SQL 方言以处理时间序列计算的效果，因此所述计算不必使用低级 SQL 聚合函数来完成。有助于减少代码和重新发明轮子……此外，还使那些不知道如何从头开始实现这些计算的人能够进行这些计算。"

此外，Lockerman 说，在不破坏 SQL 兼容性的情况下，Timescale 使其 API 吸引了开发人员。

“这意味着我们可以创建定制的函数、集合和过程，但没有新的语法——所有的驱动程序和接口仍然可以工作，”他在帖子中说。“您可以放心，您的查询将在所有可视化工具、数据库管理工具或使用 SQL 的数据分析工具中运行。”

这就是为什么时标选择为时间序列分析和操作创建新的 SQL 函数，而不是通过引入新的 SQL 语法来改善开发人员的体验。

Lockerman 说:“虽然从实现的角度来看，引入带有新关键字和新结构的新语法可能更容易，但我们故意决定不这样做，因为我们认为这实际上会给最终用户带来更糟糕的体验。”。“新的 SQL 语法意味着现有的驱动程序、库和工具可能不再工作。这可能会给开发人员带来更多问题，而不是解决方案，因为他们最喜欢的工具、库或驱动程序可能不支持新的语法，或者可能需要耗时的修改才能做到这一点。”

时标使用 Rust 编程语言开发了新的 hyperfunctions，因为“其卓越的生产力、社区和 T2 pgx 软件开发工具包”。我们觉得 Rust 对于我们这样的项目来说是一种更友好的语言，会鼓励更多的社区贡献，”Lockerman 写道。“ [Rust](https://thenewstack.io/rust-by-the-numbers-the-rust-programming-language-in-2021/) 的内在安全性意味着我们可以将更多的时间集中在功能开发上，而不是担心代码是如何编写的。广泛的 Rust 社区(crates.io)以及优秀的包管理工具意味着我们可以使用现成的解决方案来解决常见问题，从而让我们有更多的时间来关注不常见的问题。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>