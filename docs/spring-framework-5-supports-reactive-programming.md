# Spring Framework 5 通过新的反应式编程模型适应微服务

> 原文：<https://thenewstack.io/spring-framework-5-supports-reactive-programming/>

Spring Framework 5 中对反应式编程的支持为达到构建在同步阻塞堆栈上的系统的极限的用户引入了另一种编程范式。

Spring [项目](https://spring.io/)的版本 5 于上周发布，支持最新的 Java 版本，包括 JDK 9 和 Java EE 8 API 级别(例如 Servlet 4.0)。它还与一系列 Java 支持工具很好地集成，包括 Reactor 3.1、JUnit 5 和 [Kotlin](https://thenewstack.io/google-adds-kotlin-support-android-developer-studio/) 语言。

Spring Framework 5 还引入了一个名为 Spring WebFlux 的专用反应式 web 框架，Pivotal 的[于尔根·希勒](https://twitter.com/springjuergen?lang=en)在[博客文章](https://spring.io/blog/2017/09/28/spring-framework-5-0-goes-ga)中写道，他是 Spring Framework 开源项目的联合创始人，也是核心框架的项目负责人和发布经理。

它被提供作为传统阻塞风格的替代，尽管该项目将继续支持这两种风格。微服务——高度分布式、事件驱动的架构——越来越受欢迎，这通常会给展现复杂功能/服务相互依赖和排序的应用带来问题，而本版本解决了这一趋势。

正如 Pieter Humphrey 的首席产品营销经理解释的那样，有了微服务，你会发现系统处理请求的速度不够快。

“如果网飞的前门是你的手机，但在后端，有一个复杂的服务动物园试图为你和 500 万人提供服务，让他们在你的手机上看电视，如果这个互联的微服务马戏团不能足够快地处理如此大量的请求，以至于你的手机或浏览器超时，这项服务还不如离线，”他说。

## 更容易接近，更熟悉

[反应式编程](https://spring.io/blog/2016/06/07/notes-on-reactive-programming-part-i-the-reactive-landscape)生态系统中的各种角色，包括[卡辛](https://kaazing.com/)、[网飞](https://www.netflix.com/)、[中枢](https://pivotal.io/)、[红帽](https://www.redhat.com/)、[推特](https://twitter.com/)和 [Lightbend](https://www.lightbend.com/) (以前是 Typesafe，Scala 编程语言的父)已经在被称为反应流的标准低级反应概念上进行了合作，现在正在 JDK 9 中使用。

总的努力是让反应式编程更容易被程序员理解和熟悉。其与 [Spring MVC](https://docs.spring.io/spring/docs/current/spring-framework-reference/web.html#mvc) 的相似性应该会缩短学习曲线。

根据汉弗莱的说法，这不是为每个人准备的。

“编程很难。很难进行调试。很难操作。对大多数开发人员来说，这是很难学习的，因为他们在过去的 10 年或 20 年里一直在开发一种势在必行的阻塞风格…

“我们花了两年时间让它变得更容易接近，对普通开发人员来说更容易接近。这仍然很棘手。但是对于达到同步分布式系统极限的人来说，这是非常重要的。……就像微服务一样，这也有好处，但您面临的复杂性很高。”

在一篇博客文章中，除了转向微服务之外，他还列出了驱动程序:

*   对于流或实时数据，需要消耗事件，这些事件很好地映射到消息，具有高并发性。
*   对高端资源可用性的需求，通过将网络延迟与请求处理分离来实现。
*   功能即服务。

Spring 5 还包含了函数式编程，并提供了几个允许您编写应用程序的构建块。如果您决定以这种方式定义您的路由器，而不是使用注释，它将检测到这一点并相应地配置服务器，Pivotal 的软件工程师[stphane Nicoll](https://spring.io/team/snicoll)[向 JAXenter 解释了](https://jaxenter.com/spring-5-interview-nicoll-pivotal-133805.html)。

这是一个通过 Spring [WebFlux](https://dzone.com/articles/spring-webflux-first-steps) 以注释或功能性风格构建的反应性网络框架。WebFlux 建立在项目反应堆 3.1 之上。它支持 RxJava 1.3 和 2.1，并在 Tomcat、Jetty、Netty 或 Undertow 上运行。您可以在首选的反应式运行时上使用它，而无需更改代码。

并且已经与流行的 Java EE 8 APIs 集成。该框架支持 Servlet 4.0 和 Bean Validation 2.0，以及 JPA 2.2。作为 Spring MVC 中 Jackson/Gson 的替代，它还可以与、和 JSON 绑定 API 一起使用。Spring Framework 5 适用于 Tomcat、Jetty 和 Wildfly 的当前版本。

您可以在此了解更多新内容[，报名参加 10 月 4 日的网络研讨会，或亲自参加 12 月 4 日至 7 日在加利福尼亚州旧金山举行的 SpringOne Platform 2017 了解更多信息。](https://github.com/spring-projects/spring-framework/wiki/What's-New-in-the-Spring-Framework#whats-new-in-spring-framework-5x)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>