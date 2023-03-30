# 新年前又一个 Log4j 安全漏洞

> 原文：<https://thenewstack.io/one-more-log4j-security-hole-before-the-new-year/>

当我们得知又一个安全漏洞被发现时，有多少人会感到惊讶？在我的办公室，这将是一个巨大的零。我们不喜欢它介意你，但惊讶吗？见鬼，没有。最新的 [CVE-2021-44832](https://logging.apache.org/log4j/2.x/security.html#:~:text=CVE-2021-44832) ，通用漏洞评分系统(CVSS)评级为 6.6，中等，还不算糟糕。但是这个漏洞仍然可以被用来进行[任意代码执行(ACE)](https://www.okta.com/identity-101/arbitrary-code-execution/) 攻击。这已经够糟了。

Apache Software Foundation(ASF)已经在 12 月 29 日发布了修复程序 [Log4j 2.17.1](https://logging.apache.org/log4j/2.x/changes-report.html#a2.17.1) 。现在，您需要找到[易受攻击的 log4j2 库](https://thenewstack.io/how-to-find-dangerous-log4j-libraries/)并修补它们。

如果不打补丁，攻击者可以利用该漏洞通过 [Java 数据库连接(JDBC)](https://docs.oracle.com/javase/tutorial/jdbc/overview/index.html) Appender 进行 RCE。顾名思义，这是 Java 访问数据库管理系统的默认应用编程接口(API)。

除了使用易受攻击的 log4j 版本之外，这种攻击还要求攻击者拥有修改日志配置文件的权限。这样，他们就可以使用 JDBC 附加器构建恶意配置，该附加器的数据源引用可执行远程代码的 [Java 命名和目录接口(JNDI)](https://docs.oracle.com/javase/tutorial/jndi/overview/index.html) URI。您可以通过在 Log4j2 版本 2.17.1、2.12.4 和 2.3.2 中将 JNDI 数据源名称限制为 java 协议来解决这个问题。

安全研究员[亚尼夫·尼兹里](https://checkmarx.com/author/yaniv/)声称发现了这个漏洞。在他描述 log4j2 安全漏洞的[博客文章中，Nizry 补充说，这一漏洞比“原始的 CVE-2021-44228”更难利用，因为它需要攻击者控制配置(就像‘登录回退’漏洞](https://checkmarx.com/blog/cve-2021-44832-apache-log4j-2-17-0-arbitrary-code-execution-via-jdbcappender-datasource-element/) [CVE-2021-42550](https://nvd.nist.gov/vuln/detail/CVE-2021-42550) )。与 logback 不同，log4j 具有加载远程配置文件或通过代码配置日志记录器的功能，因此利用[中间人(MITM)](https://www.imperva.com/learn/application-security/man-in-the-middle-attack-mitm/) 攻击，“使用以易受攻击的配置变量结尾的输入或通过修改配置文件”，可以执行任意代码。

因此，尽管难度更大，但勤奋的黑客仍然可以用它来破坏您的系统。在查看代码时， [JDBC 附加器](https://logging.apache.org/log4j/2.x/manual/appenders.html#JDBCAppender)引起了 Nizry 的注意，因为有一些公共的方法可以通过 JDBC [Java 反序列化](https://snyk.io/blog/serialization-and-deserialization-in-java/)导致[远程代码执行(RCE)](https://www.bugcrowd.com/glossary/remote-code-execution-rce/) 。但是他注意到您可以配置 log4j，这样它就可以使用 DataSource 元素通过 JNDI 动态地远程获取数据库源。更糟糕的是，您可以向它提供任意的[轻量级目录访问协议(LDAP)](https://ldap.com/) 远程 URL。你可以从这里看到它的发展方向。一旦完成，他们就可以插入恶意的有效载荷。在他们的测试中，他们只是使用 calc.exe 作为他们的交货。不过，如果您想开始使用远程 shell，也可以这样做。

当我写这篇文章时，还没有已知的漏洞。让我重复一遍，没有“已知的”利用。是时候动手做更多的修补工作了。

祝你玩得开心，并希望你的传呼机在新年前夕不会响。

哦，我们在骗谁呢？按照现在的方式，到 2022 年，你还会继续追踪和修补 log4j2 库。坚持住，伙计们！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>