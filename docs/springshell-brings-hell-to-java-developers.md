# SpringShell 给 Java 开发者带来了地狱

> 原文：<https://thenewstack.io/springshell-brings-hell-to-java-developers/>

[Logj4Shell 带来了很多苦难](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/)，新发现的 SpringShell 漏洞，不要和完全不同的 [Spring Shell 项目](https://spring.io/projects/spring-shell)混淆，可能会带来同样多甚至更多的苦难。原因如下。

SpringShell 是一个新的，“令人兴奋的”Java 开发工具包的(JDK) Spring Framework 远程代码执行(RCE)，又名 [CVE-2022-22965](https://tanzu.vmware.com/security/cve-2022-22965) ，安全漏洞。一些人给它一个[恐怖的常见漏洞评分系统(CVSS)9.8 分](https://www.first.org/cvss/calculator/3.0#CVSS:3.0/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H)。这意味着你应该在读完这篇文章之前修补它。

## 影响了许多版本的 Spring

基本上所有版本的 [Spring Framework](https://spring.io/) ，包括 5.3.0 到 5.3.17，5.2.0 到 5.2.19，以及更老的不支持的版本都容易受到攻击。如果你有任何感觉，你会从 5.3.x 升级到 5.3.18+，从 5.2.x 升级到 5.2.20+。如果您还在使用任何过时的 Spring Framework 版本，请停止使用！尽快迁移到 5.3.18 或 5.2.20。

更糟糕的是，Spring 框架是世界上最流行的 Java 框架。到处都在用。雪上加霜的是，RCE 漏洞在 CVE 发布和补丁发布之前就被泄露了。完整的细节，以及如何利用它，已经松散，并为黑客准备好了。

能说零日噩梦吗？我可以。

安全公司[rapid 7](https://www.rapid7.com/)检查了暴露的漏洞，发现它起作用了。有了它，[攻击者可以在 Tomcat 根目录](https://www.rapid7.com/blog/post/2022/03/30/spring4shell-zero-day-vulnerability-in-spring-framework/)中删除一个名为 tomcatwar.jsp 的受密码保护的 webshell。然而，Rapid7 评论说，同样的方法可以传递其他恶意有效载荷。简而言之，“我们确信恶意的类加载负载会很快出现。”他们可能已经在外面了。根据来自[bleeding computer](https://www.bleepingcomputer.com/news/security/new-spring-java-framework-zero-day-allows-remote-code-execution/)和 [GreyNoise](https://twitter.com/GreyNoiseIO/status/1509569701248217088?s=20&t=NGRakPJf-zEs6Jib9LAUoA) 的报告，它已经被开发了。

## 你脆弱吗？

要实现这一点，除了使用未受保护的 Spring 框架版本之外，您还必须使用:

*   JDK 9 或更高版本
*   Apache Tomca 作为 Servlet 容器。
*   打包成一个传统的 WAR(与 Spring Boot 的可执行 jar 相反)。
*   spring-webmvc 或 spring-webflux 依赖关系。

但是请注意，即使你没有做到以上任何一点，你仍然可能是脆弱的。Spring 社区承认，“该漏洞的性质更加普遍，可能有其他方式来利用它。”

你还可以采取其他措施来保护自己。您可以升级到 Apache Tomcat 10.0.20、9.0.62 或 8.5.78。这应该会阻止 Tomcat 的攻击途径，如果情况变得更糟，并且您无法升级 Spring 框架或 Tomcat，您总是可以降级到 Java 8。不会很好看，但应该有用。

## 大于 Log4j？

让事情变得更加混乱的是，这与 commit to deprecate serialization utils 或最近发布的 [Spring Cloud Function CVE](https://spring.io/blog/2022/03/29/cve-report-published-for-spring-cloud-function) 有关。也与这次重大安全事故无关。

那么，问题从何而来？据安全开发软件公司 [Veracode](https://www.veracode.com/) 称，实际原因是由于[意外访问了 Tomcat 的新 Java 9 模块特性](https://www.veracode.com/blog/security-news/spring-framework-remote-code-execution-cve-2022-22965)的类加载器。新的模块对象有一个 classLoader 属性，因此当一个 Java 对象被绑定到一个请求参数时，可以通过 Spring 的属性绑定来访问它。将对 classLoader 属性的访问与一个众所周知的方法[结合起来，使用 Tomcat AccessLogValve 类执行任意文件写操作。攻击者可以编写可通过应用服务器访问的恶意 Java 服务器页面(JSP)文件。](https://securityintelligence.com/struts-vulnerabilities-analysis-parameters-cookie-interceptors-impact-exploitation/)

未来可能会有更多的麻烦。当前的利用依赖于通过 Tomcat 的类加载器可访问的类的特定链，但是有可能存在通过其他应用服务器的类加载器可访问的其他可利用的类。这不太可能，毕竟 12 年来没有出版过替代链，但还是有可能的。

可以说，其他人也对此感到担忧。应用安全公司[的大卫·林德纳](https://www.linkedin.com/in/dlindner/)、CISO[对比安全](https://www.contrastsecurity.com/)指出，Spring 框架被用于“74%的 Java 应用”林德认为“它可能会比 Log4j 产生更大的影响。”

我不知道情况会不会那么糟，但让我们现实一点，这已经够糟了。打补丁的人。祝你好运。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>