# Apache 水仙花解决通用数据交换的问题

> 原文：<https://thenewstack.io/apache-daffodil-tackles-problems-of-universal-data-interchange/>

Daffodil 是获得 Apache Software Foundation[顶级地位的最新项目之一，](https://www.globenewswire.com/en/news-release/2021/03/04/2187212/17401/en/The-Apache-Software-Foundation-Announces-Apache-Daffodil-as-a-Top-Level-Project.html)不是什么华丽的新编程语言，而是[数据格式描述语言](https://daffodil.apache.org/docs/dfdl/)的实现，用于在固定格式数据和 XML/JSON 之间进行转换。

在分布式计算中，为了让软件和硬件协同工作，它们必须能够读写各种格式的数据。[水仙花](https://daffodil.apache.org/)是由[开放网格论坛](https://www.ogf.org/ogf/doku.php)开发的开放标准框架。它本身不是一种数据格式，而是一种描述任何数据格式的属性并实现通用数据交换的方式。

“尽管世界上有很多数据格式，但人们仍在不断发明新的数据格式，”Apache Daffodil 副总裁 Mike Beckerle 说。

他说，人们谈论遗留数据格式“好像它们有什么不好的地方”。“从某种意义上说，保留下来并仍在大量使用的传统数据格式是非常成功的。因此，以更经济的方式和标准化的方式满足他们的需求非常重要。”

该项目历史悠久。贝克尔说，早在 21 世纪初，他就开始研究 DFDL，这是一种以标准方式描述一般文本和二进制数据的方法，尽管这不是他的日常工作。他和其他人合作了伊利诺伊大学国家超级计算应用中心 2009 年创建的一个项目，水仙花项目于 2017 年加入了阿帕奇孵化器。

DFDL 用于描述文本和二进制数据格式—科学和数字、传统和现代、面向商业记录以及许多工业和军事标准。贝克尔说，国防部和 IBM 是该项目早期的两个主要支持者。

DFDL 是 W3C XML 模式的子集，用于描述数据的逻辑格式，并在模式中添加注释来描述物理表示。

DFDL 可用于描述遗留数据文件，简化跨域的数据传输而无需全球标准格式，或者允许第三方工具轻松访问多种格式。根据[文档](https://daffodil.apache.org/docs/dfdl/)，随着格式的发展，DFDL 也可以成为支持向后兼容的强大工具。

贝克尔说，它使开发人员能够使用 XML 或 JSON 来消费、检查和操作固定格式的数据，而不必了解数据结构的所有细节。水仙花也可以用来逆转这个过程，将数据返回到原始格式。

水仙花在许多大型组织中使用，如 DARPA、GE Research、海军研究生院、Owl 网络防御、Perspecta Labs 和雷神 BBN Technologies 等。

贝克尔解释说，被甲骨文、IBM 和 SAP 等公司收购的初创公司通常会以特别的方式引入数据，然后收购公司会有各种数据格式的产品组合。

“在大多数情况下，它们不是库，你必须购买这个产品并以某种方式部署它，”他说。“DFDL 和 Apache 水仙花实现的贡献是提供了一个标准…一个开源实现，从而使这些东西的不断扩散停止。”

Apache 水仙花可以嵌入到数据接收工具中来理解数据格式，而不需要这些工具开发自己的方法来理解数据格式。它也可以用于数据导向的路由，通过理解数据，它被路由到适当的地方。

它有 Java 和 Scala APIs，并提供了 [Apache NiFi](https://nifi.apache.org/docs/nifi-docs/html/nifi-in-depth.html) 处理器来解析和解解析 NiFi 流文件。

作为其前进道路的一部分，该项目承担了贝克尔所描述的“雄心勃勃的项目”,以使水仙花更快——能够生成用 C 编写的程序,“像你手写的一样紧凑和快速”

它还在努力使水仙花更容易使用，包括改进其数据调试器。

贝克尔白天是 T2 猫头鹰网络防御公司的首席工程师，他解释了他的公司如何使用水仙花:

*“在像互联网这样的不可信网络和安全网络之间有一个防火墙，你的服务器和数据库就在这个安全网络中，你有数据通过这个防火墙。所以大多数人都熟悉防火墙中白名单的概念，只有特定类型的数据被允许通过。所以问题是:防火墙如何知道一个给定的数据有幻数和正确的文件扩展名等等？*

*因此，你这样做的方式是通过构造来证明的——数据传入，你使用水仙花和描述该数据的 DFDL 模式将其分割，将其分解成这种数据结构……检查所有这些，然后使用水仙花的解解析功能将它们放回一起，这是解析的逆过程。现在你肯定知道，通过构造，它就是它所说的那样。如果它不能通过这个过程，那么它就不是有效数据。”*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>