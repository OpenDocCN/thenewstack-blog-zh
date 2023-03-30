# 数据库即服务的开发人员注意事项

> 原文：<https://thenewstack.io/developer-caveats-for-database-as-a-service/>

当谈到开发人员需要做什么来利用数据库即服务工具(DBaaS)时，数据管理专家 Tony Baer 毫不讳言。

虽然开发人员可能可以注册 DBaaS 并单干，但 [dbInsight](https://www.dbinsight.io/) 的创始人兼首席执行官不建议这样做。“如果你是一名开发人员，与拥有数据的人合作，”当新的 Stack 问他推荐什么最佳实践时，Baer 说。“不要把商业分析师视为你的敌人。不要把 [SQL](https://thenewstack.io/how-to-make-sql-easier-to-understand-test-and-maintain/) 开发者当成你的敌人。”

他补充说，这并不是说开发人员必须使用关系数据库，但是决定使用哪个数据库的最好方法是与了解数据的人一起工作。

## 数据/开发人员鸿沟

数据类型和开发人员类型之间的区别由来已久，但并不总是如此。在计算机的早期，计算能力和数据运行在同一个主机上。贝尔说，从那时起，将数据从计算能力转移到自己的层，然后再转移回来，这是一个来回。数据已经从内部转移到云，最初的趋势是“提升和转移”数据库，而不改变谁来管理它们。

他说，在过去一年左右的时间里，又发生了一次转变，从大型科技公司开始——亚马逊(T8)、谷歌(T10)、谷歌(T11)、微软(T12)、微软(T13)——提供数据库托管服务。

“这些基本上是他们在内部使用的数据库平台，他们认为，‘既然亚马逊已经证明了出租计算基础设施是一项业务，我们知道如何管理我们拥有的这些数据库。我们有深厚的技术专业知识和资源，我们可以将此作为一项服务来运行。

## 进入 Kubernetes

现在，你很难找到不提供 DBaaS 的数据库供应商，他补充道。贝尔说，在某种程度上，我们应该感谢 Kubernetes。

“我们基本上是将我们所有的逻辑和所有的流程重构为[微服务](https://thenewstack.io/monoliths-to-microservices-8-technical-debt-metrics-to-know/)，反过来，我们在容器中运行它们，我们用 [Kubernetes](https://thenewstack.io/5-ways-data-protection-for-kubernetes-is-different/) 协调它们，”他说。“这是数据库的一场巨大革命，让我们真正重新思考数据库。”

Kubernetes 适合构建一个[弹性基础设施](https://thenewstack.io/a-deep-dive-into-architecting-a-kubernetes-infrastructure/)，而无需重新发明它的编排部分。Kubernetes 还提供了一种使云应用程序或数据库可移植的方法，因为不必为每个云提供商重新发明编排。

编排也是弹性的关键，弹性是指云增加服务器容量以满足需求的能力；以及数据弹性，即数据模型灵活的能力。他说，弹性对分析很重要，因为工作负载往往是峰值，而交易的流量则更平稳。

他补充道,[API](https://thenewstack.io/how-radical-api-design-changed-the-way-we-access-databases/)也在改变数据格局。

“有了 API，你可以对如何看待数据有不同的预测，”他说。“它可能是一个关系，可能是一个文档，也可能是一个图表。现在，它的性能不会像一个纯引擎那么好。但是你会看到很多多模态数据库都是这样。”

## 警告

Baer 推测，云和数据库即服务真正解放了开发人员，让他们工作得更快。

开发者也有更多对开发者友好的选择，比如文档数据库——比如由 [MongoDB Atlas](https://thenewstack.io/how-mongodbs-atlas-helped-amadeus-reengineer-a-crucial-app/) 提供的。

“MongoDB 所做的非常出色，那就是 JSON 本身就来自于 JavaScript，”他说。“MongoDB 采用了一种非常著名的结构，JSON 和 JavaScript 语言，制作了一些非常直观、非常开发人员友好的工具，使他们很容易开始使用数据库。”

他说，这让开发者可以快速“磨出”应用，而不用担心输入数据。但他警告说，有一个警告:在某个时候，如果应用程序发生变化或需要变化，开发者就会积累技术债务。他说，这可能看起来过时了，但关系数据库仍然有其作用，因为它们仍然是分析数据的最佳方式。

这也是在编码前咨询数据所有者的另一个原因。

将信用卡交给 DBaaS 提供商之前的另一个考虑因素是:了解各种云提供商提供什么服务。

“你可能想看看云中提供什么类型的服务——除了数据库——因为你可能想利用他们的一些数据流服务，你可能想利用他们的一些机器学习服务，甚至可能是他们的 Kubernetes 服务，”Baer 说。“越来越多的情况下，选择云就像选择 ERP 系统一样:你在寻找你想利用的其他服务。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>