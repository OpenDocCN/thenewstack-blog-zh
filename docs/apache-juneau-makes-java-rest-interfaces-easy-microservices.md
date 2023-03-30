# Apache 朱诺号让 Java REST 接口对微服务变得简单

> 原文：<https://thenewstack.io/apache-juneau-makes-java-rest-interfaces-easy-microservices/>

Apache 朱诺号是一个开源框架，它允许开发人员编组 POJOs(普通的旧 Java 对象)并使用 Java 开发 REST 微服务和 API，已经成为 Apache 软件基金会的顶级项目。

“我们试图让开发者尽可能简单地使用很少的代码创建 REST 界面——真正复杂和复杂的界面，”该项目的副总裁兼 Salesforce 高级软件工程师[詹姆斯·博格纳](https://www.linkedin.com/in/jamesbognar/)说，他说这是他自 2007 年以来最喜欢的项目。

阿帕奇朱诺号包括:

1.  一个通用的工具包，使用一个通用的内聚框架将 POJOs 整理成各种各样的内容类型；
2.  一个通用的 REST 服务器 API，用于使用 POJOs 创建自文档化的 REST 接口，简单地部署为任何 Servlet 3.1.0+容器中的一个或多个顶级 Servlet；
3.  使用 POJOs 和代理接口与朱诺号或第三方 REST 接口交互的通用 REST 客户端 API 和
4.  一个 REST 微服务 API，它将上述所有特性与一个简单的可配置 Jetty 服务器结合在一起，用于创建轻量级独立 REST 接口，启动只需几毫秒。

封送处理用于将对象的内存表示转换为适合在的不同部分之间(或跨程序)移动的数据格式，并简化与远程对象和对象的通信。

朱诺号很小——大约 1MB——不需要自动连接，不需要代码生成，不需要依赖注入。

> "你不需要进行 HTTP 调用，只需要进行 Java 方法调用."—詹姆斯·博格纳尔

根据 Bognar 的说法，它最初是一个 JSON 序列化库，当时 JSON 刚刚成为一个“东西”。当时没有 JSON 序列化库。这是 IBM 的一个内部项目，它发展成了一堆不同的语言，比如 XML 和 HTML。

“这是一个单一的 API，允许你将 POJOs 序列化为所有这些不同的语言，而不是必须为每种语言预先录制不同的库，”他说。

后来增加了对 REST APIs 的支持。

“我们在它的基础上开发了一个 REST API，这样只需使用 servlets 和注释，你就可以只用序列化的 POJOs 快速创建 REST API。作为一名开发人员，你不需要知道任何事情是如何被序列化的，你只需要创建 Java 方法来接收 POJO 并返回 POJO，所有的序列化工作都会为你完成。…这确实简化了在微服务中创建 REST 的过程。”

他说，IBM 开始在 Docker 容器中使用这些 REST APIs 作为其协作生命周期管理即服务产品的基础，这就是微服务组件的发明方式。

它只是一个带有 REST servlets 的嵌入式 Jetty 服务器，可以提供最大的灵活性。

“我们试图使用所有核心 Java 技术，而不引入任何先决条件，”他说。

它现在正被 IBM、开放集团和 Salesforce 等公司使用。Apache Streams 项目在 2016 年末开始整合 Apache 朱诺号库。

Apache 孵化器的副总裁兼该项目的导师 John D. Ament 将其描述为 JSON 处理的继承者。

“阿帕奇朱诺号被认为是一个清洁的解决方案。它提供了一个易于使用的 API、出色的性能和大量的功能，这使它成为其他人利用的一个强有力的推荐。”

最近添加的一个有趣的特性是 REST 客户端 API，它允许您针对第三方 REST 接口定义 Java 代理接口。

“您可以将这些调用封装在接口代理之后，而不必通过通用 HTTP 客户端进行低级 REST 调用。不是进行 HTTP 调用，而是进行 Java 方法调用。这是一个与 SOAP 非常相似的概念，但它是 RPC over REST，我们称之为 rRPC，”Bognar 解释道。

展望未来，该项目希望添加更多的语言，包括 YAML、 [Protobuf、](https://github.com/google/protobuf)这是一个谷歌 API，以及对 [gRPC](https://grpc.io/) 的支持，类似于该项目针对 REST APIs 定义接口代理的方式。

特写图片:[朱诺号(30)](https://www.flickr.com/photos/volvob12b/8108121709/in/photolist-dmuf6T-jYaqKt-7gHprn-dmubpi-fEuUeM-dmuaG9-dmugqt-dmuaZA-dmuc33-eieJ97-fEMt8o-9q9Z8W-drQ2nU-8As9k5-EU7pvU-jH6Lbj-68GhUP-8VNvD7-AFCQi-AFCQj-ArqaV-8Rhvng-hkkZY8-bqHtap-kBJ4m-jH6LHb-fDNuf)[**伯纳德·斯布拉格。NZ**](https://www.flickr.com/photos/volvob12b/) 。[公共领域](https://creativecommons.org/publicdomain/zero/1.0/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>