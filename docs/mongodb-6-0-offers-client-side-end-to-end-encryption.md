# MongoDB 6.0 提供客户端端到端加密

> 原文：<https://thenewstack.io/mongodb-6-0-offers-client-side-end-to-end-encryption/>

“开发人员不是密码专家。我们只能做这么多的安全培训，坦率地说，他们不应该在这个加密模式或那个加密模式上做出艰难的选择。MongoDB 的安全负责人肯尼斯·怀特(Kenneth White)解释了 MongoDB 新的[可查询加密](https://www.mongodb.com/products/queryable-encryption)功能的必要性。

在最新一期的 [The New Stack Makers](/podcasts) 播客中，我们讨论了 [MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) 新的端到端客户端加密，该公司称，这允许应用程序查询加密的数据库，并保持查询在传输中加密，这是行业首创。

[MongoDB 6.0 提供客户端端到端加密](https://thenewstack.simplecast.com/episodes/mongodb-60-offers-client-side-end-to-end-encryption)

上周在纽约举行的 MongoDB World 大会上，怀特与 TNS 出版商亚历克斯·威廉姆斯(Alex Williams)深入讨论了这项技术。

从 MongoDB 4.2 开始，MongoDB 就提供了加密和解密文档的能力，尽管这个版本是第一个允许应用程序查询加密数据的版本。该公司声称，没有加密专业知识的开发人员可以编写在客户端使用该功能的应用程序，并且[功能本身](https://www.mongodb.com/products/queryable-encryption)(在 MongoDB 6.0 的预览模式中可用)不会给应用程序性能带来明显的开销。

[https://www.youtube.com/embed/PVlVZ9CasPE](https://www.youtube.com/embed/PVlVZ9CasPE)

视频

数据始终保持加密状态，即使在内存和 CPU 中也是如此；密钥永远不会离开应用程序，也不能被服务器访问。数据库或云服务管理员也无法查看原始数据。

对于组织来说，可查询加密极大地扩展了使用 MongoDB 处理各种敏感和机密数据的效用。例如，客户服务代表可以使用这些数据来帮助客户解决敏感数据方面的问题，如社会保险号或信用卡号。

在这个播客中，White 还谈到了为使这项技术成为可能而付出的巨大工程努力——并使其易于开发人员使用。

“就我们如何走到这一步而言，最大的突破不是密码学，而是工程方面的东西，这些东西使你可以扩展到进行密钥管理，以实际的方式做真正具有这些能力的索引，”怀特说。

有必要为需要最大技术可扩展性的用户群提供服务。他指出，许多人有“巨大的工作量”。

“我们的一些客户有 800 多个碎片，这意味着一个系统有 800 台不同的物理服务器。我的意思是，这是巨大的，”他说。“因此，在过去一年半的时间里，我们进行了大量的工程工作，将这些数学和算法技术转化为数据库中的实用技术。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>